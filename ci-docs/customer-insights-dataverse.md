---
title: Bekerja dengan Customer Insights di Microsoft Dataverse
description: Pelajari cara menghubungkan Customer Insights dan Microsoft Dataverse serta memahami entitas output yang diekspor ke Dataverse.
ms.date: 07/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 89ff629033230de3c6252b6a3a16816d9b3c1287
ms.sourcegitcommit: 85b198de71ff2916fee5500ed7c37c823c889bbb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/15/2022
ms.locfileid: "9153408"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Bekerja dengan Customer Insights di Microsoft Dataverse

Customer Insights menyediakan opsi untuk membuat entitas output tersedia sebagai file [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Integrasi ini memungkinkan berbagi data yang mudah dan pengembangan kustom melalui pendekatan kode rendah/tanpa kode. Entitas [output](#output-entities) tersedia sebagai tabel di Dataverse lingkungan. Anda dapat menggunakan data untuk aplikasi lain berdasarkan Dataverse tabel. Tabel ini memungkinkan skenario seperti alur kerja otomatis melalui Power Automate atau membangun aplikasi dengan Power Apps.

Menyambungkan ke lingkungan Anda Dataverse juga memungkinkan Anda menyerap [data dari sumber data lokal menggunakan Power Platform aliran data dan gateway](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Prasyarat

- Customer Insights dan Dataverse lingkungan harus dihosting di wilayah yang sama.
- Anda harus memiliki peran administrator global di Dataverse lingkungan. Verifikasi apakah lingkungan ini [Dataverse terkait dengan](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) grup keamanan tertentu dan pastikan Anda ditambahkan ke grup keamanan tersebut.
- Tidak ada lingkungan Customer Insights lain yang sudah dikaitkan dengan lingkungan yang Dataverse ingin Anda sambungkan. Pelajari cara [menghapus koneksi yang ada ke Dataverse lingkungan](#remove-an-existing-connection-to-a-dataverse-environment).
- Lingkungan Microsoft Dataverse hanya dapat terhubung ke satu akun penyimpanan. Ini hanya berlaku jika Anda mengonfigurasi lingkungan untuk [menggunakan Azure Data Lake Storage](own-data-lake-storage.md) file.

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse hak kapasitas penyimpanan

Langganan Customer Insights memberi Anda hak atas kapasitas ekstra untuk kapasitas [Dataverse penyimpanan organisasi Anda yang ada](/power-platform/admin/capacity-storage). Kapasitas yang ditambahkan bergantung pada jumlah profil yang digunakan langganan Anda.

**Contoh:**

Dengan asumsi Anda mendapatkan penyimpanan database 15 GB dan penyimpanan file 20 GB per 100.000 profil pelanggan. Jika langganan Anda mencakup 300.000 profil pelanggan, total kapasitas penyimpanan Anda adalah penyimpanan database 45 GB (3 x 15 GB) dan penyimpanan file 60 GB (3 x 20 GB). Demikian pula, jika Anda memiliki langganan B2B dengan 30 ribu akun, total kapasitas penyimpanan Anda adalah penyimpanan database 45 GB (3 x 15 GB), dan penyimpanan file 60 GB (3 x 20 GB).

Kapasitas log tidak bertambah bertahap dan tetap untuk organisasi Anda.

Untuk informasi selengkapnya tentang hak kapasitas terperinci, lihat [Panduan](https://go.microsoft.com/fwlink/?LinkId=866544) Lisensi Dynamics 365.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Dataverse Menghubungkan lingkungan ke Customer Insights

Langkah ini **Microsoft Dataverse** memungkinkan Anda menghubungkan Customer Insights dengan lingkungan Anda Dataverse sambil [menciptakan lingkungan](create-environment.md) Customer Insights.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="berbagi data dengan Microsoft Dataverse diaktifkan secara otomatis untuk lingkungan baru bersih.":::

Administrator dapat mengonfigurasi Customer Insights untuk menghubungkan lingkungan yang ada Dataverse. Dengan menyediakan URL ke lingkungan, URL tersebut Dataverse terhubung ke lingkungan Customer Insights baru mereka. Setelah membuat hubungan antara Customer Insights dan Dataverse, jangan ubah nama organisasi untuk lingkungan.Dataverse Nama organisasi digunakan dalam Dataverse URL dan nama yang diubah memutuskan koneksi dengan Customer Insights.

Jika Anda tidak ingin menggunakan lingkungan yang sudah ada Dataverse, sistem akan membuat lingkungan baru untuk data Customer Insights di penyewa Anda. [Power Platform admin dapat mengontrol siapa yang dapat membuat lingkungan](/power-platform/admin/control-environment-creation). Saat Menyiapkan lingkungan Customer Insights baru dan admin telah menonaktifkan pembuatan Dataverse lingkungan untuk semua orang kecuali admin, Anda mungkin tidak dapat membuat lingkungan baru.

**Aktifkan berbagi** data dengan cara Dataverse memilih kotak centang berbagi data.

Jika Anda menggunakan akun Data Lake Storage Anda sendiri, Anda juga memerlukan **Pengidentifikasi izin**. Untuk informasi selengkapnya cara mendapatkan pengidentifikasi izin, tinjau bagian berikut ini.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Aktifkan berbagi data dengan Dataverse dari Anda sendiri Azure Data Lake Storage (Pratinjau)

Mengaktifkan berbagi data saat Microsoft Dataverse lingkungan [Anda menggunakan akun Azure Data Lake Storage Anda sendiri](own-data-lake-storage.md) memerlukan konfigurasi tambahan. Pengguna yang menyiapkan lingkungan Customer Insights harus memiliki setidaknya **izin Pembaca** Data Blob Penyimpanan pada *kontainer CustomerInsights* di Azure Data Lake Storage akun.

1. Buat dua grup keamanan pada langganan Azure Anda - satu **Pembaca** grup keamanan dan satu **grup keamanan kontributor** dan atur Microsoft Dataverse layanan sebagai pemilik untuk kedua grup keamanan.
2. Kelola Daftar Kontrol Akses (ACL) pada kontainer CustomerInsights di akun penyimpanan Anda melalui grup keamanan ini. Microsoft Dataverse Tambahkan layanan dan aplikasi bisnis berbasis apa pun Dataverse seperti Dynamics 365 Marketing ke **grup keamanan Pembaca** dengan **izin baca-saja**. Tambahkan *hanya* aplikasi Customers Insights ke **grup keamanan kontributor** untuk memberikan **izin baca dan tulis** untuk menulis profil dan wawasan.

### <a name="limitations"></a>Pembatasan

Ada dua batasan saat menggunakan Dataverse dengan akun Anda sendiri Azure Data Lake Storage:

- Ada pemetaan satu-ke-satu antara Dataverse organisasi dan Azure Data Lake Storage akun. Dataverse Setelah organisasi tersambung ke akun penyimpanan, organisasi tidak dapat tersambung ke akun penyimpanan lain. Batasan ini mencegah a Dataverse tidak mengisi beberapa akun penyimpanan.
- Berbagi data tidak akan berfungsi jika penyiapan Azure Private Link diperlukan untuk mengakses akun Anda Azure Data Lake Storage karena berada di belakang firewall. Dataverse saat ini tidak mendukung koneksi ke titik akhir privat melalui Private Link.

### <a name="set-up-powershell"></a>Menyiapkan PowerShell

Untuk menjalankan skrip PowerShell, Anda harus terlebih dahulu menyiapkan PowerShell yang sesuai.

1. Instal versi [Azure Active Directory terbaru PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. Di PC, pilih tombol Windows di keyboard dan cari **Windows PowerShell**, lalu pilih **Jalankan sebagai administrator**.
   1. Di jendela PowerShell yang terbuka, masukkan `Install-Module AzureAD`.
2. Impor tiga modul.
    1. Di jendela PowerShell, masukkan `Install-Module -Name Az.Accounts` dan ikuti langkah-langkahnya.
    1. Ulangi untuk `Install-Module -Name Az.Resources` dan `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Langkah Konfigurasi

1. Unduh dua skrip PowerShell yang perlu Anda jalankan dari repositori [GitHub teknisi](https://github.com/trin-msft/byol) kami.
    1. `CreateSecurityGroups.ps1`
       - Anda memerlukan *izin admin* penyewa untuk menjalankan skrip PowerShell ini.
       - Skrip PowerShell ini membuat dua grup keamanan pada langganan Azure Anda. Satu untuk grup Pembaca dan satu lagi untuk grup kontributor dan akan menjadikan Microsoft Dataverse layanan sebagai pemilik untuk kedua grup keamanan ini.
       - Jalankan skrip PowerShell ini di Windows PowerShell dengan menyediakan ID langganan Azure yang Azure Data Lake Storage berisi file. Buka skrip PowerShell di editor untuk meninjau informasi tambahan dan logika yang diterapkan.
       - Simpan kedua nilai ID grup keamanan yang dihasilkan oleh skrip ini karena kita akan menggunakannya dalam `ByolSetup.ps1` skrip.

        > [!NOTE]
        > Pembuatan grup keamanan dapat dinonaktifkan pada penyewa Anda. Dalam hal ini, pengaturan manual akan diperlukan dan admin Anda Azure AD harus [mengaktifkan pembuatan grup keamanan](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Anda memerlukan *izin Pemilik* Data Blob Penyimpanan di tingkat akun/kontainer penyimpanan untuk menjalankan skrip ini atau skrip ini akan membuatnya untuk Anda. Penetapan peran Anda dapat dihapus secara manual setelah berhasil menjalankan skrip.
        - Skrip PowerShell ini menambahkan kontrol akses berbasis peran yang diperlukan untuk Microsoft Dataverse layanan dan aplikasi bisnis berbasis apa pun Dataverse. Ini juga memperbarui Daftar Kontrol Akses (ACL) pada kontainer CustomerInsights untuk grup keamanan yang dibuat dengan `CreateSecurityGroups.ps1` skrip. Grup kontributor akan memiliki *izin rwx* dan grup Pembaca hanya akan memiliki *izin r-x*.
        - Jalankan skrip PowerShell ini di Windows PowerShell dengan menyediakan ID langganan Azure yang berisi nama akun penyimpanan, nama grup sumber daya, dan nilai ID grup keamanan Pembaca dan kontributor Anda Azure Data Lake Storage. Buka skrip PowerShell di editor untuk meninjau informasi tambahan dan logika yang diterapkan.
        - Salin string output setelah berhasil menjalankan skrip. String output terlihat seperti ini: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Masukkan string output yang disalin dari atas ke bidang **pengidentifikasi** Izin dari langkah konfigurasi lingkungan untuk Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opsi konfigurasi untuk mengaktifkan berbagi data dari Anda sendiri Azure Data Lake Storage dengan Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Menghapus koneksi yang sudah ada ke Dataverse lingkungan

Saat menyambungkan ke Dataverse lingkungan, pesan **kesalahan Organisasi CDS ini sudah dilampirkan ke instans** Customer Insights lain berarti bahwa lingkungan tersebut Dataverse sudah digunakan di lingkungan Customer Insights. Anda dapat menghapus koneksi yang ada sebagai administrator global di Dataverse lingkungan. Diperlukan waktu beberapa jam untuk mengisi perubahan.

1. Tuju [Power Apps](https://make.powerapps.com).
1. Pilih lingkungan dari pemilih lingkungan.
1. Pergi ke **Solusi**
1. Copot pemasangan atau hapus solusi bernama **Dynamics 365 Customer Insights Customer Card Add-in (Pratinjau)**.

ATAU

1. Buka lingkungan Anda Dataverse.
1. Buka **Solusi** > **Pengaturan** Lanjutan.
1. **Hapus instalan solusi CustomerInsightsCustomerCard**.

Jika penghapusan koneksi gagal karena dependensi, Anda juga harus menghapus dependensi. Untuk informasi selengkapnya, lihat [Menghapus dependensi](/power-platform/alm/removing-dependencies).

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

Tabel ini berisi profil pelanggan terpadu dari Customer Insights. Skema untuk profil pelanggan terpadu bergantung pada entitas dan atribut yang digunakan dalam proses penyatuan data. Skema profil pelanggan biasanya berisi subset atribut dari definisi [Common Data Model dari CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

Tabel AlternateKey berisi kunci entitas, yang berpartisipasi dalam proses penyatuan.

|Column  |Jenis  |KETERANGAN  |
|---------|---------|---------|
|DataSourceName    |String         | Nama sumber data. Contoh: `datasource5`        |
|EntityName        | String        | Nama entitas di Customer Insights. Contoh: `contact1`        |
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
| SegmenProvider      | String       | Aplikasi yang memublikasikan segmen.      |
| SegmentMembershipType | String       | Jenis pelanggan catatan keanggotaan segmen ini. Mendukung beberapa jenis seperti Pelanggan, Kontak, atau Akun. Default: Pelanggan  |
| Segmen       | String JSON  | Daftar segmen unik yang menjadi anggota profil pelanggan      |
| msdynci_identifier  | String   | Pengidentifikasi unik dari catatan keanggotaan segmen. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID deterministik yang dihasilkan dari`msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
