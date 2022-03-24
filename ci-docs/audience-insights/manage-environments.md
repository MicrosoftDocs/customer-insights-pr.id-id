---
title: Membuat dan mengelola lingkungan
description: Pelajari cara mendaftar ke layanan dan cara mengelola lingkungan.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376880"
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

Untuk [menggunakan model prediksi siap pakai](predictions-overview.md#out-of-box-models), konfigurasikan berbagi data dengan Dataverse. Atau Anda dapat mengaktifkan penyerapan data dari sumber data lokal, yang memberikan URL lingkungan Microsoft Dataverse yang dikelola organisasi Anda.

> [!IMPORTANT]
> Wawasan Pelanggan dan Dataverse harus berada di wilayah yang sama untuk mengaktifkan berbagi data.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Pilihan konfigurasi untuk mengaktifkan berbagi data dengan Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights tidak mendukung skenario berbagi data berikut ini:
> - Jika Anda menyimpan semua data ke Azure Data Lake Storage Anda sendiri, Anda tidak akan dapat mengaktifkan berbagi data dengan Data Lake Terkelola Dataverse.
> - Jika Anda mengaktifkan berbagi data dengan Dataverse, Anda tidak akan dapat [membuat nilai yang terduga atau tidak ada dalam entitas](predictions.md).

## <a name="copy-the-environment-configuration"></a>Salin konfigurasi lingkungan

Bila membuat lingkungan baru, Anda dapat memilih untuk menyalin konfigurasi dari lingkungan yang ada. 

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

Data berikut ini *tidak* disalin:

- Profil pelanggan.
- Kredensial sumber data. Anda harus memberikan kredensial untuk setiap sumber data dan menyegarkan sumber data secara manual.

- Sumber data dari folder Common Data Model dan data lake terkelola Dataverse. Anda harus membuat sumber data secara manual dengan nama yang sama seperti di lingkungan sumber.

Bila Anda menyalin lingkungan, Anda akan melihat pesan konfirmasi bahwa lingkungan baru telah dibuat. Pilih **buka sumber data** untuk melihat daftar sumber data.

Semua sumber data akan menampilkan status **kredensial yang diperlukan**. Edit sumber data dan masukkan kredensial untuk me-refresh mereka.

:::image type="content" source="media/data-sources-copied.png" alt-text="Daftar sumber data yang disalin dan memerlukan otentikasi.":::

Setelah menyegarkan sumber data, buka **data** > **Satukan**. Di sini Anda akan menemukan pengaturan dari lingkungan sumber. Edit sesuai kebutuhan atau pilih **Jalankan** untuk memulai proses penyatuan data dan buat entitas pelanggan terpadu.

Bila penyatuan data selesai, buka **langkah** dan **segmen** untuk me-refresh juga.

## <a name="change-the-owner-of-an-environment"></a>Mengubah pemilik lingkungan

Sementara beberapa pengguna dapat memiliki izin admin di Customer Insights, hanya satu pengguna yang merupakan pemilik lingkungan. Secara default, adminlah yang membuat lingkungan pada awalnya. Sebagai admin lingkungan, Anda dapat menetapkan kepemilikan ke pengguna lain dengan izin admin.

1. Pilih pemilih **Lingkungan** di header aplikasi.

1. Pilih ikon **Edit**.

1. **Dalam kotak Edit lingkungan**, buka **langkah Informasi** dasar.

1. **Di bidang Ubah pemilik lingkungan**, pilih pemilik baru lingkungan.  

1. Pilih **Tinjau dan selesaikan**, lalu **Perbarui** untuk menerapkan perubahan. 

## <a name="claim-ownership-of-an-environment"></a>Klaim kepemilikan lingkungan

Jika pemilik lingkungan meninggalkan organisasi atau akun pengguna mereka dihapus, lingkungan tidak akan memiliki pemilik. Pengguna dengan izin admin dapat mengklaim kepemilikan dan menjadi pemilik baru. Mereka dapat terus memiliki lingkungan atau [mengubah kepemilikan ke admin](#change-the-owner-of-an-environment) lain. 

Untuk mengklaim kepemilikan, pilih **tombol Ambil kepemilikan** yang ditampilkan di bagian atas setiap halaman di Wawasan Pelanggan saat pemilik asli meninggalkan organisasi.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
