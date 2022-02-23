---
title: Data Wawasan Pelanggan dalam Microsoft Dataverse
description: Gunakan entitas Wawasan Pelanggan sebagai tabel dalam Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866938"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Bekerja dengan data Customer Insights di Microsoft Dataverse

Customer Insights menyediakan opsi untuk membuat entitas output tersedia di [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Integrasi ini memungkinkan pembagian data yang mudah dan pengembangan kustom melalui kode rendah/tanpa pendekatan kode. Entitas output akan tersedia sebagai tabel dalam Dataverse. Tabel ini memungkinkan skenario seperti [alur kerja otomatis melalui](/power-automate/getting-started) Power Automate, aplikasi berbasis [model](/powerapps/maker/model-driven-apps/), dan aplikasi [kanvas melalui](/powerapps/maker/canvas-apps/) Power Apps. Anda dapat menggunakan data untuk aplikasi lain yang didasarkan pada tabel Dataverse. Penerapan saat ini terutama mendukung pencarian dengan data dari entitas wawasan audiens yang tersedia dapat diambil untuk ID pelanggan tertentu.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Melampirkan lingkungan Dataverse ke Wawasan Pelanggan

**Organisasi dengan lingkungan Dataverse yang ada**

Organisasi yang sudah menggunakan Dataverse dapat [menggunakan salah satu lingkungan Dataverse yang ada ketika administrator menyiapkan wawasan](create-environment.md) audiens. Dengan menyediakan URL ke lingkungan Dataverse, itu melekat pada lingkungan wawasan audiens baru mereka. Untuk memastikan kinerja terbaik, Wawasan Pelanggan dan lingkungan Dataverse harus dihosting di wilayah yang sama.

**Organisasi baru**

Jika Anda membuat organisasi baru saat menyiapkan Wawasan Pelanggan, Anda akan secara otomatis mendapatkan lingkungan Dataverse baru.

> [!NOTE]
> Jika organisasi Anda sudah menggunakan Dataverse di penyewa mereka, penting untuk diingat bahwa [pembuatan lingkungan Dataverse dikendalikan oleh](/power-platform/admin/control-environment-creation.md) admin. Misalnya, jika Anda menyiapkan lingkungan wawasan audiens baru dengan akun organisasi Anda dan admin telah menonaktifkan pembuatan lingkungan uji coba Dataverse untuk semua orang kecuali admin, Anda tidak dapat membuat lingkungan uji coba baru.
> 
> Lingkungan uji coba Dataverse yang dibuat dalam Customer Insights memiliki penyimpanan 3 GB yang tidak akan dihitung terhadap kapasitas keseluruhan yang berhak atas penyewa. Langganan berbayar mendapatkan hak Dataverse sebesar 15 GB untuk database dan 20 GB untuk penyimpanan file.

## <a name="output-entities"></a>Entitas output

Beberapa entitas output dari audiens wawasan tersedia sebagai tabel dalam Dataverse. Bagian di bawah ini menjelaskan skema yang diharapkan dari tabel ini.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Pengayaan](#enrichment)
- [Prediksi](#prediction)
- [Keanggotaan segmen](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Tabel ini berisi profil pelanggan terpadu dari Customer Insights. Skema untuk profil pelanggan terpadu tergantung pada entitas dan atribut yang digunakan dalam proses penggabungan. Skema profil pelanggan biasanya berisi subset atribut dari definisi [Common Data Model dari CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabel AlternateKey berisi kunci entitas, yang berpartisipasi dalam proses penyatuan.

|Column  |Jenis  |KETERANGAN  |
|---------|---------|---------|
|DataSourceName    |String         | Nama sumber data. Contoh: `datasource5`        |
|EntityName        | String        | Nama entitas di wawasan audiens. Contoh: `contact1`        |
|AlternateValue    |String         |ID alternatif yang dipetakan ke ID pelanggan. Contoh: `cntid_1078`         |
|KeyRing           | Teks multibaris        | Nilai JSON  </br> Sampel: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|ID Pelanggan         | String        | ID profil pelanggan terpadu.         |
|AlternateKeyId     | GUID         |  GUID deterministik AlternateKey berdasarkan msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Sampel: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Tabel ini berisi aktivitas oleh pengguna yang tersedia dalam Customer Insights.

| Column            | Jenis        | KETERANGAN                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| ID Pelanggan        | String      | ID Profil pelanggan                                                                      |
| ActivityId        | String      | ID internal aktivitas pelanggan (kunci utama)                                       |
| SourceEntityName  | String      | Nama entitas sumber                                                                |
| SourceActivityId  | String      | Kunci utama dari entitas sumber                                                       |
| ActivityType      | String      | Jenis aktivitas semantik atau nama aktivitas kustom                                        |
| ActivityTimeStamp | DATETIME    | Cap waktu aktivitas                                                                      |
| Judul             | String      | Judul atau nama aktivitas                                                               |
| KETERANGAN       | String      | Deskripsi Aktivitas                                                                     |
| URL               | String      | Tautan ke URL eksternal yang spesifik untuk aktivitas                                         |
| SemanticData      | String JSON | Mencakup daftar pasangan nilai utama untuk bidang pemetaan semantis yang spesifik untuk jenis aktivitas |
| RangeIndex        | String      | Cap waktu unik yang digunakan untuk mengurutkan timeline aktivitas dan kueri rentang yang efektif |
| mydynci_unifiedactivityid   | GUID | ID internal aktivitas pelanggan (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Tabel ini berisi data output tindakan berbasis atribut pelanggan.

| Column             | Jenis             | KETERANGAN                 |
|--------------------|------------------|-----------------------------|
| ID Pelanggan         | String           | ID Profil pelanggan        |
| Pengukuran           | String JSON      | Mencakup daftar pasangan nilai utama untuk mengukur nama dan nilai untuk pelanggan tertentu | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID Profil pelanggan |


### <a name="enrichment"></a>Pengayaan

Tabel ini berisi output proses pengayaan.

| Column               | Jenis             |  KETERANGAN                                          |
|----------------------|------------------|------------------------------------------------------|
| ID Pelanggan           | String           | ID Profil pelanggan                                 |
| EnrichmentProvider   | String           | Nama penyedia pengayaan                                  |
| EnrichmentType       | String           | Jenis pengayaan                                      |
| Nilai               | String JSON      | Daftar atribut yang dihasilkan oleh proses pengayaan |
| msdynci_enrichmentid | GUID             | GUID deterministis yang dihasilkan dari msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prediksi

Tabel ini berisi output prediksi model.

| Column               | Jenis        | KETERANGAN                                          |
|----------------------|-------------|------------------------------------------------------|
| ID Pelanggan           | String      | ID Profil pelanggan                                  |
| ModelProvider        | String      | Nama penyedia model                                      |
| Model                | String      | Nama model                                                |
| Nilai               | String JSON | Daftar atribut yang dihasilkan oleh model |
| msdynci_predictionid | GUID        | GUID deterministis yang dihasilkan dari msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Keanggotaan segmen

Tabel ini berisi informasi keanggotaan segmen profil pelanggan.

| Column        | Tipe | Deskripsi                        |
|--------------------|--------------|-----------------------------|
| ID Pelanggan        | String       | ID Profil pelanggan        |
| SegmentProvider      | String       | Aplikasi yang menerbitkan segmen. Default: audiens wawasan         |
| SegmentMembershipType | String       | Jenis pelanggan catatan keanggotaan segmen ini. Mendukung beberapa jenis seperti Pelanggan, Kontak, atau Akun. Default: Pelanggan  |
| Segmen       | String JSON  | Daftar segmen unik yang profil pelanggan adalah anggota      |
| msdynci_identifier  | String   | Pengenal unik dari catatan keanggotaan segmen. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID deterministik yang dihasilkan dari`msdynci_identifier`          |
