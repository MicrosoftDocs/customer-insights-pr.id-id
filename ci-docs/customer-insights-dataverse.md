---
title: Data Customer Insights di Microsoft Dataverse
description: Gunakan entitas Customer Insights sebagai tabel di Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 1e629cd218b104b115f74f59a53a14e9d60fcc8a
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741369"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Bekerja dengan Customer Insights di Microsoft Dataverse

Customer Insights memberikan pilihan untuk menyediakan entitas output dalam [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Integrasi ini memungkinkan berbagi data yang mudah dan pengembangan kustom melalui pendekatan kode rendah / tanpa kode. Entitas [output](#output-entities) tersedia sebagai tabel dalam Dataverse lingkungan. Anda dapat menggunakan data untuk aplikasi lain berdasarkan Dataverse tabel. Tabel ini memungkinkan skenario seperti alur kerja otomatis melalui Power Automate atau membangun aplikasi dengan Power Apps. Implementasi saat ini terutama mendukung pencarian di mana data dari entitas Customer Insights yang tersedia dapat diambil untuk ID pelanggan tertentu.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Melampirkan lingkungan Dataverse ke Customer Insights

**Organisasi yang sudah ada**

Administrator dapat mengonfigurasi Wawasan Pelanggan untuk [menggunakan lingkungan Dataverse yang](create-environment.md) ada saat mereka membuat lingkungan Wawasan Pelanggan. Dengan memberikan URL ke Dataverse lingkungan, URL tersebut melekat pada lingkungan Customer Insights baru mereka. Wawasan pelanggan dan Dataverse lingkungan harus dihosting di wilayah yang sama. 

Jika Anda tidak ingin menggunakan lingkungan yang sudah ada Dataverse, sistem akan membuat lingkungan baru untuk data Wawasan Pelanggan di penyewa Anda. 

> [!NOTE]
> Jika organisasi Anda sudah menggunakan Dataverse penyewanya, penting untuk diingat bahwa [Dataverse pembuatan lingkungan dikendalikan oleh admin](/power-platform/admin/control-environment-creation). Misalnya, jika Anda menyiapkan lingkungan Customer Insights baru dengan akun organisasi Anda dan admin telah menonaktifkan pembuatan Dataverse lingkungan uji coba untuk semua orang kecuali admin, Anda tidak dapat membuat lingkungan uji coba baru.
> 
> Lingkungan uji coba Dataverse yang dibuat dalam Customer Insights memiliki penyimpanan sebesar 3 GB yang tidak akan dihitung terhadap kapasitas keseluruhan yang diberikan kepada penyewa. Langganan berbayar mendapatkan penetapan Dataverse 15 GB untuk database dan 20 GB untuk penyimpanan file.

**Organisasi baru**

Jika Anda membuat organisasi baru saat menyiapkan Customer Insights, sistem secara otomatis membuat lingkungan baru Dataverse di organisasi Anda untuk Anda.

## <a name="output-entities"></a>Entitas output

Beberapa entitas output dari Customer Insights tersedia sebagai tabel di Dataverse. Bagian di bawah ini menjelaskan skema yang diharapkan dari tabel ini.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Pengayaan](#enrichment)
- [Prediksi](#prediction)
- [Keanggotaan segmen](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

Tabel ini berisi profil pelanggan terpadu dari Customer Insights. Skema untuk profil pelanggan terpadu tergantung pada entitas dan atribut yang digunakan dalam proses penyatuan data. Skema profil pelanggan biasanya berisi subset atribut dari definisi [Common Data Model dari CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabel AlternateKey berisi kunci entitas, yang berpartisipasi dalam proses penyatuan.

|Column  |Jenis  |KETERANGAN  |
|---------|---------|---------|
|DataSourceName    |String         | Nama sumber data. Contoh: `datasource5`        |
|EntityName        | String        | Nama entitas dalam Wawasan Pelanggan. Contoh: `contact1`        |
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
| SegmentProvider      | String       | Aplikasi yang menerbitkan segmen.      |
| SegmentMembershipType | String       | Jenis pelanggan catatan keanggotaan segmen ini. Mendukung beberapa jenis seperti Pelanggan, Kontak, atau Akun. Default: Pelanggan  |
| Segmen       | String JSON  | Daftar segmen unik profil pelanggan adalah anggota      |
| msdynci_identifier  | String   | Pengidentifikasi unik dari catatan keanggotaan segmen. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID deterministik yang dihasilkan dari`msdynci_identifier`          |
