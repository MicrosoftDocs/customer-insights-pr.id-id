---
title: Data Customer Insights di Microsoft Dataverse
description: Gunakan entitas Customer Insights sebagai tabel di Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 45535a7368b89e19a91f08fcd825bda9d57a8709653104bf4043c29ffa14d0b8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032900"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Bekerja dengan Customer Insights di Microsoft Dataverse

Customer Insights memberikan pilihan untuk menyediakan entitas output dalam [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Integrasi ini memungkinkan pembagian data yang mudah dan pengembangan kustom melalui kode rendah/tanpa pendekatan kode. Entitas output akan tersedia sebagai tabel dalam Dataverse. Tabel ini mengaktifkan skenario seperti [alur kerja otomatis melalui Power Automate](/power-automate/getting-started), [aplikasi berdasarkan model](/powerapps/maker/model-driven-apps/), dan [aplikasi kanvas](/powerapps/maker/canvas-apps/) melalui Power Apps. Anda dapat menggunakan data untuk aplikasi lain yang didasarkan pada tabel Dataverse. Penerapan saat ini terutama mendukung pencarian dengan data dari entitas wawasan audiens yang tersedia dapat diambil untuk ID pelanggan tertentu.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Melampirkan lingkungan Dataverse ke Customer Insights

**Organisasi dengan lingkungan Dataverse yang ada**

Organisasi yang telah menggunakan Dataverse dapat [menggunakan salah satu lingkungan Dataverse yang ada](get-started-paid.md) saat administrator menyiapkan audiens wawasan. Dengan menyediakan URL ke lingkungan Dataverse, maka URL tersebut akan dilampirkan ke lingkungan wawasan audiens baru. Untuk memastikan kinerja terbaik, lingkungan Customer Insights dan Dataverse harus di-host di kawasan yang sama.

Untuk melampirkan lingkungan Dataverse, perluas **pengaturan Tingkat Lanjut** saat membuat lingkungan wawasan audiens. Berikan **URL lingkungan Microsoft Dataverse** dan pilih kotak centang untuk **Aktifkan berbagi data**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="alt.":::

**Organisasi baru**

Jika Anda membuat organisasi baru saat menyiapkan Customer Insights, Anda akan secara otomatis mendapatkan lingkungan baru Dataverse.

> [!NOTE]
> Jika organisasi Anda telah menggunakan penyewa Dataverse, maka penting untuk diingat bahwa pembuatan [lingkungan Dataverse dikontrol oleh admin](/power-platform/admin/control-environment-creation.md). Contohnya, jika Anda menyiapkan lingkungan wawasan audiens baru dengan akun organisasional Anda dan admin telah menonaktifkan pembuatan lingkungan uji coba Dataverse untuk semua orang, kecuali admin, Anda tidak dapat membuat lingkungan uji coba baru.
> 
> Lingkungan uji coba Dataverse yang dibuat dalam Customer Insights memiliki penyimpanan sebesar 3 GB yang tidak akan dihitung terhadap kapasitas keseluruhan yang diberikan kepada penyewa. Langganan berbayar mendapatkan penetapan Dataverse 15 GB untuk database dan 20 GB untuk penyimpanan file.

## <a name="output-entities"></a>Entitas output

Beberapa entitas output dari audiens wawasan tersedia sebagai tabel dalam Dataverse. Bagian di bawah ini menjelaskan skema yang diharapkan dari tabel ini.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Pengayaan](#enrichment)
- [Prediksi](#prediction)


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
