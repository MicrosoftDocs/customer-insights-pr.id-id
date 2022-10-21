---
title: Bekerja dengan Customer Insights di Microsoft Dataverse
description: Pelajari cara menghubungkan Customer Insights dan dan Microsoft Dataverse memahami entitas output yang diekspor ke Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9433c411a2c7eb0db137c6392578993d47be82a2
ms.sourcegitcommit: 8559ca47a22d1d7cd9be13531c2eaf0c1083942b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671255"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Bekerja dengan Customer Insights di Microsoft Dataverse

Customer Insights memberikan pilihan untuk menyediakan entitas output dalam [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Integrasi ini memungkinkan berbagi data yang mudah dan pengembangan khusus melalui pendekatan kode rendah/tanpa kode. Entitas [output](#output-entities) tersedia sebagai tabel di Dataverse lingkungan. Anda dapat menggunakan data untuk aplikasi lain berdasarkan Dataverse tabel. Tabel ini memungkinkan skenario seperti alur kerja otomatis melalui Power Automate atau membangun aplikasi dengan Power Apps.

Menyambungkan ke lingkungan Anda juga memungkinkan Anda Dataverse menyerap [data dari sumber data lokal menggunakan Power Platform aliran data dan gateway](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Prasyarat

- Customer Insights dan Dataverse lingkungan harus dihosting di wilayah yang sama.
- Peran administrator global disiapkan di Dataverse lingkungan. Verifikasi apakah lingkungan ini [Dataverse terkait dengan](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) grup keamanan tertentu dan pastikan Anda ditambahkan ke grup keamanan tersebut.
- Tidak ada lingkungan Customer Insights lain yang sudah terkait dengan lingkungan yang Dataverse ingin Anda hubungkan. Pelajari cara [menghapus koneksi yang ada ke Dataverse lingkungan](#remove-an-existing-connection-to-a-dataverse-environment).
- Lingkungan yang Microsoft Dataverse terhubung ke satu akun penyimpanan jika Anda mengonfigurasi lingkungan untuk [menggunakan Azure Data Lake Storage](own-data-lake-storage.md) file.

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse Hak kapasitas penyimpanan

Langganan Customer Insights memberi Anda hak atas kapasitas ekstra untuk kapasitas [Dataverse penyimpanan organisasi Anda yang ada](/power-platform/admin/capacity-storage). Kapasitas tambahan bergantung pada jumlah profil yang digunakan langganan Anda.

**Contoh:**

Dengan asumsi Anda mendapatkan penyimpanan database 15 GB dan penyimpanan file 20 GB per 100.000 profil pelanggan. Jika langganan Anda menyertakan 300.000 profil pelanggan, total kapasitas penyimpanan Anda adalah penyimpanan database 45 GB (3 x 15 GB) dan penyimpanan file 60 GB (3 x 20 GB). Demikian pula, jika Anda memiliki langganan B-to-B dengan akun 30K, total kapasitas penyimpanan Anda adalah penyimpanan database 45 GB (3 x 15 GB), dan penyimpanan file 60 GB (3 x 20 GB).

Kapasitas log tidak bertambah dan tetap untuk organisasi Anda.

Untuk informasi selengkapnya tentang penetapan kapasitas terperinci, lihat [Panduan](https://go.microsoft.com/fwlink/?LinkId=866544) Lisensi Dynamics 365.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Dataverse Menghubungkan lingkungan ke Customer Insights

Langkah **Microsoft Dataverse** ini memungkinkan Anda menghubungkan Customer Insights dengan lingkungan Anda Dataverse saat [membuat lingkungan](create-environment.md) Customer Insights.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="berbagi data dengan Microsoft Dataverse diaktifkan secara otomatis untuk lingkungan baru.":::

1. Berikan URL ke lingkungan Anda atau biarkan kosong agar URL dibuat untuk Anda Dataverse.

   > [!NOTE]
   > Setelah membuat koneksi antara Customer Insights dan Dataverse, jangan ubah nama organisasi untuk Dataverse lingkungan. Nama organisasi digunakan dalam Dataverse URL dan nama yang diubah memutus koneksi dengan Customer Insights.

   [Power Platform Admin dapat mengontrol siapa yang dapat membuat lingkungan Dataverse baru](/power-platform/admin/control-environment-creation). Jika Anda mencoba menyiapkan lingkungan Customer Insights baru dan tidak bisa, admin mungkin telah menonaktifkan pembuatan Dataverse lingkungan untuk semua orang kecuali admin.

1. Jika Anda menggunakan akun Data Lake Storage Anda sendiri:
   1. Pilih **Aktifkan berbagi** data dengan Dataverse.
   1. **Masukkan Pengidentifikasi izin**. Untuk mendapatkan pengidentifikasi izin, [aktifkan berbagi data dengan Dataverse dari file Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Aktifkan berbagi data dengan Dataverse dari Anda sendiri Azure Data Lake Storage (pratinjau)

Di [akun Anda sendiri Azure Data Lake Storage, verifikasi bahwa pengguna yang menyiapkan lingkungan Customer Insights memiliki setidaknya](own-data-lake-storage.md) Data Blob Penyimpanan Pembaca **izin pada** kontainer di akun`customerinsights` penyimpanan.

> [!NOTE]
> Berbagi data hanya berlaku jika Anda menggunakan akun Anda sendiri Azure Data Lake Storage. Pengaturan ini tidak tersedia jika lingkungan Customer Insights menggunakan penyimpanan default Dataverse.

### <a name="limitations"></a>Pembatasan

- Hanya pemetaan satu-ke-satu antara Dataverse organisasi dan Azure Data Lake Storage akun. Setelah tersambung Dataverse ke akun penyimpanan, organisasi tidak dapat tersambung ke akun penyimpanan lain. Batasan ini mencegah Dataverse mengisi beberapa akun penyimpanan.
- Berbagi data tidak akan berfungsi jika penyiapan Azure Private Link diperlukan untuk mengakses akun Anda Azure Data Lake Storage karena berada di belakang firewall. Dataverse saat ini tidak mendukung koneksi ke titik akhir privat melalui Private Link.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Menyiapkan grup keamanan sendiri Azure Data Lake Storage

1. Buat dua grup keamanan di langganan Azure Anda - satu grup keamanan Pembaca **dan satu** **grup keamanan kontributor** dan atur Microsoft Dataverse layanan sebagai pemilik untuk kedua grup keamanan.

1. Kelola Daftar Kontrol Akses (ACL) pada `customerinsights` kontainer di akun penyimpanan Anda melalui grup keamanan ini.
   1. Microsoft Dataverse Tambahkan layanan dan aplikasi bisnis berbasis apa pun Dataverse seperti Dynamics 365 Marketing ke **grup keamanan Pembaca** dengan **izin baca-saja**.
   1. Tambahkan *hanya* aplikasi Customer Insights ke **grup keamanan kontributor** untuk memberikan **izin baca dan tulis** untuk menulis profil dan wawasan.

### <a name="set-up-powershell"></a>Menyiapkan PowerShell

Siapkan PowerShell untuk menjalankan skrip PowerShell.

1. Instal versi [Azure Active Directory terbaru PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. Di PC, pilih tombol Windows di keyboard dan cari **Windows PowerShell**, lalu pilih **Jalankan sebagai administrator**.
   1. Di jendela PowerShell yang terbuka, masukkan `Install-Module AzureAD`.

1. Impor tiga modul.
   1. Di jendela PowerShell, masukkan `Install-Module -Name Az.Accounts` dan ikuti langkah-langkahnya.
   1. Ulangi untuk `Install-Module -Name Az.Resources` dan `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Menjalankan skrip PowerShell dan mendapatkan Pengidentifikasi Izin

1. Unduh dua skrip PowerShell yang perlu Anda jalankan dari repositori [GitHub teknisi](https://github.com/trin-msft/byol) kami.
   - `CreateSecurityGroups.ps1`: Memerlukan izin admin penyewa.
   - `ByolSetup.ps1`: Memerlukan izin Pemilik Data Blob Penyimpanan di tingkat akun penyimpanan/kontainer. Skrip ini akan membuat izin untuk Anda. Penetapan peran Anda dapat dihapus secara manual setelah berhasil menjalankan skrip.

1. Jalankan `CreateSecurityGroups.ps1` di Windows PowerShell dengan menyediakan ID langganan Azure yang berisi Azure Data Lake Storage file. Buka skrip PowerShell di editor untuk meninjau informasi tambahan dan logika yang diterapkan.

   Skrip ini membuat dua grup keamanan di langganan Azure Anda: satu untuk grup Pembaca dan satu lagi untuk grup kontributor. Microsoft Dataverse Layanan adalah pemilik untuk kedua grup keamanan ini.

1. Simpan kedua nilai ID grup keamanan yang dihasilkan oleh skrip ini untuk digunakan dalam `ByolSetup.ps1` skrip.

   > [!NOTE]
   > Pembuatan grup keamanan dapat dinonaktifkan pada penyewa Anda. Dalam hal ini, pengaturan manual akan diperlukan dan admin Anda Azure AD harus [mengaktifkan pembuatan grup keamanan](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Jalankan `ByolSetup.ps1` di Windows PowerShell dengan menyediakan ID langganan Azure yang berisi Azure Data Lake Storage, nama akun penyimpanan, nama grup sumber daya, dan nilai ID grup keamanan Pembaca dan kontributor. Buka skrip PowerShell di editor untuk meninjau informasi tambahan dan logika yang diterapkan.

   Skrip ini menambahkan kontrol akses berbasis peran yang diperlukan untuk Microsoft Dataverse layanan dan aplikasi bisnis berbasis apa pun Dataverse. Ini juga memperbarui Daftar Kontrol Akses (ACL) pada `customerinsights` kontainer untuk grup keamanan yang dibuat dengan `CreateSecurityGroups.ps1` skrip. Grup kontributor diberi izin rwx dan grup Pembaca hanya diberi *izin* r-x *.*

1. Salin string output yang terlihat seperti: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Masukkan string output yang disalin ke dalam **bidang Pengidentifikasi** izin dari langkah konfigurasi lingkungan untuk Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opsi konfigurasi untuk mengaktifkan berbagi data dari Anda sendiri Azure Data Lake Storage dengan Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Menghapus koneksi yang ada ke Dataverse lingkungan

Saat menyambungkan ke lingkungan, pesan Dataverse kesalahan Organisasi CDS ini sudah dilampirkan ke **instans** Customer Insights lain berarti bahwa Dataverse lingkungan tersebut sudah digunakan di lingkungan Customer Insights. Anda dapat menghapus koneksi yang ada sebagai administrator global di Dataverse lingkungan. Diperlukan waktu beberapa jam untuk mengisi perubahan.

1. Tuju [Power Apps](https://make.powerapps.com).
1. Pilih lingkungan dari pemilih lingkungan.
1. Pergi ke **Solusi**.
1. Copot pemasangan atau hapus solusi bernama **Dynamics 365 Customer Insights Add-in Kartu Pelanggan (Pratinjau)**.

ATAU

1. Buka lingkungan Anda Dataverse.
1. **Buka Solusi** > **Pengaturan** Lanjutan.
1. Copot pemasangan **solusi CustomerInsightsCustomerCard**.

Jika penghapusan koneksi gagal karena dependensi, Anda juga perlu menghapus dependensi. Untuk informasi selengkapnya, lihat [Menghapus dependensi](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entitas output

Beberapa entitas output dari Customer Insights tersedia sebagai tabel dalam Dataverse format. Bagian di bawah ini menjelaskan skema yang diharapkan dari tabel ini.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Pengayaan](#enrichment)
- [Prediksi](#prediction)
- [Keanggotaan segmen](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

Tabel ini berisi profil pelanggan terpadu dari Customer Insights. Skema untuk profil pelanggan terpadu bergantung pada entitas dan atribut yang digunakan dalam proses penyatuan data. Skema profil pelanggan biasanya berisi subset atribut dari definisi [Common Data Model dari CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). Untuk skenario B-to-B, profil pelanggan berisi akun terpadu, dan skema biasanya berisi subset atribut dari [definisi Common Data Model akun](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

ContactProfile berisi informasi terpadu tentang kontak. Kontak adalah [individu yang dipetakan ke akun](data-unification-contacts.md) dalam skenario B-to-B.

| Column                       | Tipe                | Description     |
| ---------------------------- | ------------------- | --------------- |
|  Tanggal Lahir            | WaktuTanggal       |  Tanggal lahir kontak               |
|  Kota                 | SMS |  Kota alamat kontak               |
|  ContactId            | SMS |  ID profil kontak               |
|  ContactProfileId     | Pengidentifikasi unik   |  GUID untuk kontak               |
|  NegaraOrRegion      | SMS |  Negara/Wilayah alamat kontak               |
|  ID Pelanggan           | SMS |  ID akun tempat kontak dipetakan               |
|  EntityName           | SMS |  Entitas dari mana data berasal                |
|  FirstName            | SMS |  Nama depan kontak               |
|  Jenis kelamin               | SMS |  Jenis kelamin kontak               |
|  Id                   | SMS |  GUID deterministik berdasarkan`Identifier`               |
|  pengidentifikasi           | SMS |  ID internal profil kontak: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | SMS |  Jabatan kontak               |
|  LastName             | SMS |  Nama belakang kontak               |
|  PostalCode           | SMS |  Kode pos alamat kontak               |
|  Email Utama         | SMS |  Alamat email kontak               |
|  Telepon Utama         | SMS |  Nomor telepon kontak               |
|  StateOrProvince      | SMS |  Negara bagian atau provinsi alamat kontak               |
|  Alamat Jalan        | SMS |  Jalan alamat kontak               |

### <a name="alternatekey"></a>AlternateKey

Tabel AlternateKey berisi kunci entitas, yang berpartisipasi dalam proses penyatuan.

|Column  |Tipe  |Description  |
|---------|---------|---------|
|DataSourceName    |SMS         | Nama sumber data. Contoh: `datasource5`        |
|EntityName        | SMS        | Nama entitas di Customer Insights. Contoh: `contact1`        |
|AlternateValue    |SMS         |ID alternatif yang dipetakan ke ID pelanggan. Contoh: `cntid_1078`         |
|KeyRing           | SMS        | Nilai JSON  </br> Sampel: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|ID Pelanggan         | SMS        | ID profil pelanggan terpadu.         |
|AlternateKeyId     | Pengidentifikasi unik        |  AlternatifKey deterministik GUID berdasarkan`Identifier`      |
|pengidentifikasi |   SMS      |   `DataSourceName|EntityName|AlternateValue`  </br> Sampel: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Tabel ini berisi aktivitas oleh pengguna yang tersedia dalam Customer Insights.

| Column            | Tipe        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| ID Pelanggan        | SMS      | ID Profil pelanggan                                                                      |
| ActivityId        | SMS      | ID internal aktivitas pelanggan (kunci utama)                                       |
| SourceEntityName  | SMS      | Nama entitas sumber                                                                |
| SourceActivityId  | SMS      | Kunci utama dari entitas sumber                                                       |
| ActivityType      | SMS      | Jenis aktivitas semantik atau nama aktivitas kustom                                        |
| ActivityTimeStamp | WaktuTanggal    | Stempel waktu aktivitas                                                                      |
| Titel             | SMS      | Judul atau nama aktivitas                                                               |
| Description       | SMS      | Deskripsi Aktivitas                                                                     |
| URL               | SMS      | Tautan ke URL eksternal yang spesifik untuk aktivitas                                         |
| SemanticData      | SMS | Mencakup daftar pasangan nilai utama untuk bidang pemetaan semantis yang spesifik untuk jenis aktivitas |
| RangeIndex        | SMS      | Cap waktu unik yang digunakan untuk mengurutkan timeline aktivitas dan kueri rentang yang efektif |
| UnifiedActivityId   | Pengidentifikasi unik | ID internal aktivitas pelanggan (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Tabel ini berisi data output tindakan berbasis atribut pelanggan.

| Column             | Tipe             | Description                 |
|--------------------|------------------|-----------------------------|
| ID Pelanggan         | SMS           | ID Profil pelanggan        |
| Tindakan           | SMS      | Mencakup daftar pasangan nilai utama untuk mengukur nama dan nilai untuk pelanggan tertentu |
| pengidentifikasi | SMS           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Pengidentifikasi unik     | ID Profil pelanggan |

### <a name="enrichment"></a>Pengayaan

Tabel ini berisi output proses pengayaan.

| Column               | Tipe             |  Description                                          |
|----------------------|------------------|------------------------------------------------------|
| ID Pelanggan           | SMS           | ID Profil pelanggan                                 |
| EnrichmentProvider   | SMS           | Nama penyedia pengayaan                                  |
| EnrichmentType       | SMS           | Jenis pengayaan                                      |
| Values               | SMS      | Daftar atribut yang dihasilkan oleh proses pengayaan |
| PengayaanId | Pengidentifikasi unik            | GUID deterministik yang dihasilkan dari`Identifier` |
| pengidentifikasi   | SMS           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prediksi

Tabel ini berisi output prediksi model.

| Column               | Tipe        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| ID Pelanggan           | SMS      | ID Profil pelanggan                                  |
| ModelProvider        | SMS      | Nama penyedia model                                      |
| Model                | SMS      | Nama model                                                |
| Values               | SMS | Daftar atribut yang dihasilkan oleh model |
| PredictionId | Pengidentifikasi unik       | GUID deterministik yang dihasilkan dari`Identifier` |
| pengidentifikasi   | SMS      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Keanggotaan segmen

Tabel ini berisi informasi keanggotaan segmen profil pelanggan.

| Column        | Tipe | Description                        |
|--------------------|--------------|-----------------------------|
| ID Pelanggan        | SMS       | ID Profil pelanggan        |
| SegmentProvider      | SMS       | Aplikasi yang memublikasikan segmen.      |
| SegmentMembershipType | SMS       | Jenis pelanggan untuk catatan keanggotaan segmen ini. Mendukung beberapa jenis seperti Pelanggan, Kontak, atau Akun. Default: Pelanggan  |
| Segmen       | SMS  | Daftar segmen unik yang menjadi anggota profil pelanggan      |
| pengidentifikasi  | SMS   | Pengidentifikasi unik dari catatan keanggotaan segmen. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Pengidentifikasi unik      | GUID deterministik yang dihasilkan dari`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
