---
title: Membuat dan mengelola lingkungan
description: Pelajari cara mendaftar ke layanan dan cara mengelola lingkungan.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fcdb7f073ff73322ff69d0a8684391819a809d00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643619"
---
# <a name="manage-environments"></a>Kelola lingkungan

## <a name="switch-environments"></a>Alihkan Lingkungan

Pilih kontrol **lingkungan** di sudut kanan atas halaman untuk mengubah lingkungan.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Cuplikan layar kontrol untuk beralih lingkungan.":::

Administrator dapat [membuat](create-environment.md) dan mengelola lingkungan.

## <a name="edit-an-existing-environment"></a>Edit lingkungan yang ada

Anda dapat mengedit beberapa rincian lingkungan yang ada.

1.  Pilih pemilih **Lingkungan** di header aplikasi.

2.  Pilih ikon **Edit**.

3. Di kotak **Edit lingkungan**, Anda dapat memperbarui pengaturan lingkungan.

Untuk informasi lebih lanjut tentang pengaturan lingkungan, lihat [Membuat lingkungan baru](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Sambungkan ke Microsoft Dataverse
   
Langkah **Microsoft Dataverse** memungkinkan Anda menghubungkan Customer Insights dengan lingkungan Dataverse Anda. 

Menyediakan lingkungan Anda sendiri Microsoft Dataverse untuk berbagi data (profil dan wawasan) dengan aplikasi bisnis berdasarkan Dataverse, seperti Dynamics 365 Marketing atau aplikasi berbasis model di Power Apps.

Untuk [menggunakan model prediksi siap pakai](predictions-overview.md#out-of-box-models), konfigurasikan berbagi data dengan Dataverse. Atau Anda dapat mengaktifkan penyerapan data dari sumber data lokal, yang memberikan URL lingkungan Microsoft Dataverse yang dikelola organisasi Anda.

Mengaktifkan berbagi data dengan dengan Microsoft Dataverse memilih kotak centang berbagi data akan memicu penyegaran penuh satu kali dari sumber data Anda dan semua proses lainnya.

> [!IMPORTANT]
> 1. Wawasan Pelanggan dan Dataverse harus berada di wilayah yang sama untuk memungkinkan berbagi data.
> 1. Anda harus memiliki peran administrator global di Dataverse lingkungan. Verifikasi apakah lingkungan ini [Dataverse terkait dengan](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) grup keamanan tertentu dan pastikan Anda ditambahkan ke grup keamanan tersebut.
> 1. Tidak ada lingkungan Customer Insights yang ada yang sudah dikaitkan dengan lingkungan tersebut Dataverse. Pelajari cara [menghapus koneksi yang ada ke Dataverse lingkungan](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Pilihan konfigurasi untuk mengaktifkan berbagi data dengan Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Aktifkan berbagi data dengan Dataverse dari Anda sendiri Azure Data Lake Storage (Pratinjau)

Jika lingkungan Anda dikonfigurasi untuk menggunakan milik Anda sendiri Azure Data Lake Storage untuk menyimpan data Customer Insights, memungkinkan berbagi data dengan Microsoft Dataverse memerlukan beberapa konfigurasi tambahan.

1. Buat dua grup keamanan di langganan Azure Anda - satu **Pembaca** grup keamanan dan satu **grup keamanan kontributor** dan atur Microsoft Dataverse layanan sebagai pemilik untuk kedua grup keamanan.
2. Kelola Daftar Kontrol Akses (ACL) pada kontainer CustomerInsights di akun penyimpanan Anda melalui grup keamanan ini. Microsoft Dataverse Tambahkan layanan dan aplikasi bisnis berbasis apa pun Dataverse seperti Dynamics 365 Marketing ke **grup keamanan Pembaca** dengan **izin baca-saja**. Tambahkan *hanya* aplikasi Wawasan Pelanggan ke **grup keamanan kontributor** untuk memberikan **izin baca dan tulis** untuk menulis profil dan wawasan.
   
#### <a name="prerequisites"></a>Prasyarat

Untuk menjalankan skrip PowerShell, Anda harus mengimpor tiga modul berikut. 

1. Instal versi [Azure Active Directory terbaru PowerShell untuk Graph](/powershell/azure/active-directory/install-adv2).
   1. Di PC, pilih tombol Windows di keyboard dan cari **Windows PowerShell**, lalu pilih **Jalankan sebagai administrator**.
   1. Di jendela PowerShell yang terbuka, masukkan `Install-Module AzureAD`.
2. Impor tiga modul.
    1. Di jendela PowerShell, masukkan `Install-Module -Name Az.Accounts` dan ikuti langkah-langkahnya. 
    1. Ulangi untuk `Install-Module -Name Az.Resources` dan `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Langkah Konfigurasi

1. Unduh dua skrip PowerShell yang perlu Anda jalankan dari repo [GitHub insinyur](https://github.com/trin-msft/byol) kami.
    1. `CreateSecurityGroups.ps1`
       - Anda memerlukan *izin admin* penyewa untuk menjalankan skrip PowerShell ini. 
       - Skrip PowerShell ini membuat dua grup keamanan di langganan Azure Anda. Satu untuk grup Pembaca dan satu lagi untuk grup kontributor dan akan membuat Microsoft Dataverse layanan sebagai pemilik untuk kedua kelompok keamanan ini.
       - Jalankan skrip PowerShell ini di Windows PowerShell dengan menyediakan ID langganan Azure yang berisi Azure Data Lake Storage. Buka skrip PowerShell di editor untuk meninjau informasi tambahan dan logika yang diterapkan.
       - Simpan kedua nilai ID grup keamanan yang dihasilkan oleh skrip ini karena kita akan menggunakannya dalam `ByolSetup.ps1` skrip.
       
        > [!NOTE]
        > Pembuatan grup keamanan dapat dinonaktifkan pada penyewa Anda. Dalam hal ini, pengaturan manual akan diperlukan dan admin Anda Azure AD harus [mengaktifkan pembuatan](/azure/active-directory/enterprise-users/groups-self-service-management) grup keamanan.

    2. `ByolSetup.ps1`
        - Anda memerlukan *izin Pemilik* Data Blob Penyimpanan di tingkat akun penyimpanan/kontainer untuk menjalankan skrip ini atau skrip ini akan membuatnya untuk Anda. Penetapan peran Anda dapat dihapus secara manual setelah berhasil menjalankan skrip.
        - Skrip PowerShell ini menambahkan kontrol akses berbasis tole yang diperlukan (RBAC) untuk Microsoft Dataverse layanan dan aplikasi bisnis berbasis apa pun Dataverse. Ini juga memperbarui Daftar Kontrol Akses (ACL) pada kontainer CustomerInsights untuk grup keamanan yang dibuat dengan `CreateSecurityGroups.ps1` skrip. Grup kontributor akan memiliki *izin RWX* dan grup Pembaca hanya akan memiliki *izin r-x*.
        - Jalankan skrip PowerShell ini di Windows PowerShell dengan menyediakan ID langganan Azure yang berisi, nama akun penyimpanan, nama grup sumber daya, dan nilai id grup keamanan Pembaca dan kontributor Anda Azure Data Lake Storage. Buka skrip PowerShell di editor untuk meninjau informasi tambahan dan logika yang diterapkan.
        - Salin string output setelah berhasil menjalankan skrip. String output terlihat seperti ini: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Masukkan string output yang disalin dari atas ke **bidang Pengenal** izin dari langkah konfigurasi lingkungan untuk Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opsi konfigurasi untuk mengaktifkan berbagi data dari Anda sendiri Azure Data Lake Storage dengan Microsoft Dataverse.":::

Customer Insights tidak mendukung skenario berbagi data berikut ini:
- Jika Anda mengaktifkan berbagi data dengan Dataverse, Anda tidak akan dapat [membuat nilai yang terduga atau tidak ada dalam entitas](predictions.md).
- Jika mengaktifkan berbagi data dengan Dataverse, Anda tidak akan dapat melihat laporan Tertanam PowerBI opsional di lingkungan Customer Insights Anda.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Menghapus koneksi yang ada ke Dataverse lingkungan

Saat menyambungkan ke Dataverse lingkungan, pesan **kesalahan Organisasi CDS ini sudah dilampirkan ke instans** Customer Insights lain berarti lingkungan sudah Dataverse digunakan dalam lingkungan Customer Insights. Anda dapat menghapus koneksi yang ada sebagai administrator global di Dataverse lingkungan. Ini bisa memakan waktu beberapa jam untuk mengisi perubahan.

1. Tuju [Power Apps](https://make.powerapps.com).
1. Pilih lingkungan dari pemilih lingkungan.
1. Pergi ke **Solusi**
1. Hapus instalan atau hapus solusi bernama **Dynamics 365 Customer Insights Add-in Kartu Pelanggan (Pratinjau)**.

ATAU 

1. Buka lingkungan Anda Dataverse.
1. **Buka Pengaturan** > **LanjutanSolutions**.
1. **Hapus instalan solusi CustomerInsightsCustomerCard**.

## <a name="copy-the-environment-configuration"></a>Salin konfigurasi lingkungan

Sebagai admin, Anda dapat memilih untuk menyalin konfigurasi dari lingkungan yang sudah ada saat membuat yang baru. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Cuplikan layar pilihan pengaturan di pengaturan lingkungan.":::

Anda akan melihat daftar semua lingkungan yang tersedia di organisasi tempat Anda dapat menyalin data.

Pengaturan konfigurasi berikut disalin:

- Sumber data yang diserap/diimpor
- Konfigurasi penyatuan data (petakan, cocokkan, gabungkan)
- Segmen
- Tindakan
- Relasi
- Aktivitas
- Indeks Pencarian & filter
- Tujuan ekspor
- Refresh terjadwal
- Pengayaan
- Manajemen model
- Penetapan peran

## <a name="set-up-a-copied-environment"></a>Menyiapkan lingkungan yang disalin

Saat Anda menyalin konfigurasi lingkungan, data *berikut tidak* disalin:

- Profil pelanggan.
- Kredensial sumber data. Anda harus memberikan kredensial untuk setiap sumber data dan menyegarkan sumber data secara manual.
- Sumber data dari folder Common Data Model dan data lake terkelola Dataverse. Anda harus membuat sumber data secara manual dengan nama yang sama seperti di lingkungan sumber.
- Rahasia koneksi yang digunakan untuk ekspor dan pengayaan. Anda harus mengautentikasi ulang koneksi dan kemudian mengaktifkan kembali pengayaan dan ekspor. 

Bila Anda menyalin lingkungan, Anda akan melihat pesan konfirmasi bahwa lingkungan baru telah dibuat. Pilih **buka sumber data** untuk melihat daftar sumber data.

Semua sumber data akan menampilkan status **kredensial yang diperlukan**. Edit sumber data dan masukkan kredensial untuk me-refresh mereka.

:::image type="content" source="media/data-sources-copied.png" alt-text="Daftar sumber data yang disalin dan memerlukan otentikasi.":::

Setelah menyegarkan sumber data, buka **data** > **Satukan**. Di sini Anda akan menemukan pengaturan dari lingkungan sumber. Edit sesuai kebutuhan atau pilih **Jalankan** untuk memulai proses penyatuan data dan buat entitas pelanggan terpadu.

Bila penyatuan data selesai, buka **langkah** dan **segmen** untuk me-refresh juga.

Sebelum Mengaktifkan kembali ekspor dan pengayaan, buka **AdminConnections** > **untuk** mengautentikasi ulang koneksi di lingkungan baru Anda.

## <a name="change-the-owner-of-an-environment"></a>Mengubah pemilik lingkungan

Meskipun beberapa pengguna dapat memiliki izin admin di Customer Insights, hanya satu pengguna yang menjadi pemilik lingkungan. Secara default, adminlah yang membuat lingkungan pada awalnya. Sebagai admin lingkungan, Anda dapat menetapkan kepemilikan ke pengguna lain dengan izin admin.

1. Pilih pemilih **Lingkungan** di header aplikasi.

1. Pilih ikon **Edit**.

1. **Dalam kotak Edit lingkungan**, buka **langkah Informasi** dasar.

1. Di **bidang Ubah pemilik lingkungan**, pilih pemilik lingkungan baru.  

1. Pilih **Tinjau dan selesaikan**, lalu **Perbarui** untuk menerapkan perubahan. 

## <a name="claim-ownership-of-an-environment"></a>Mengklaim kepemilikan lingkungan

Jika pemilik lingkungan meninggalkan organisasi atau akun penggunanya dihapus, lingkungan tidak akan memiliki pemilik. Pengguna dengan izin admin dapat mengklaim kepemilikan dan menjadi pemilik baru. Mereka dapat terus memiliki lingkungan atau [mengubah kepemilikan ke admin](#change-the-owner-of-an-environment) lain. 

Untuk mengklaim kepemilikan, pilih tombol **Ambil kepemilikan** yang ditampilkan di bagian atas setiap halaman di Customer Insights saat pemilik asli meninggalkan organisasi.

## <a name="reset-an-existing-environment"></a>Mengatur ulang lingkungan yang ada

Sebagai pemilik lingkungan, Anda dapat mengatur ulang lingkungan ke status kosong jika Anda ingin menghapus semua konfigurasi dan menghapus data yang tertelan.

1.  Pilih pemilih **Lingkungan** di header aplikasi. 

2.  Pilih lingkungan yang ingin Anda atur ulang dan pilih elipsis (**...**). 

3. Pilih opsi **Atur ulang**. 

4.  Untuk mengkonfirmasi penghapusan, masukkan nama lingkungan dan pilih **Atur ulang**.

## <a name="delete-an-existing-environment"></a>Menghapus lingkungan yang ada

Sebagai pemilik lingkungan, Anda dapat menghapus lingkungan yang Anda kelola.

1.  Pilih pemilih **Lingkungan** di header aplikasi.

2.  Pilih lingkungan yang ingin Anda atur ulang dan pilih elipsis (**...**). 

3. Pilih opsi **Hapus**. 

4.  Untuk mengonfirmasikan penghapusan, masukkan nama lingkungan dan pilih **Hapus**.

> [!NOTE]
> Menghapus lingkungan tidak menghapus asosiasi ke Dataverse lingkungan. Pelajari cara [menghapus koneksi yang ada ke Dataverse lingkungan](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE [footer-include](includes/footer-banner.md)]
