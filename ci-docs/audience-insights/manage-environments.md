---
title: Membuat dan mengelola lingkungan
description: Pelajari cara mendaftar ke layanan dan cara mengelola lingkungan.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683477"
---
# <a name="manage-environments"></a>Kelola lingkungan

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Alihkan Lingkungan

Pilih kontrol **lingkungan** di sudut kanan atas halaman untuk mengubah lingkungan.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Cuplikan layar kontrol untuk beralih lingkungan.":::

Administrator dapat [membuat](get-started-paid.md) dan mengelola lingkungan.

## <a name="edit-an-existing-environment"></a>Edit lingkungan yang ada

Anda dapat mengedit beberapa rincian lingkungan yang ada.

1.  Pilih pemilih **Lingkungan** di header aplikasi.

2.  Pilih ikon **Edit**.

3. Di kotak **Edit lingkungan**, Anda dapat memperbarui **nama tampilan** lingkungan, tetapi Anda tidak dapat mengubah **Kawasan** atau **Jenis**.

4. Jika lingkungan dikonfigurasi untuk menyimpan data dalam Azure Data Lake Storage, Anda dapat memperbarui **kunci Akun**. Namun, Anda tidak dapat mengubah **nama akun** atau nama **penampung**.

5. Atau, Anda dapat memperbarui dari sambungan berbasis kunci akun ke sambungan berbasis sumber daya atau berbasis langganan. Setelah ditingkatkan, Anda tidak dapat kembali ke kunci akun setelah pembaruan. Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md). Anda tidak dapat **mengubah** informasi penampung saat memperbarui sambungan.

6. Secara opsional, Anda dapat menyediakan URL lingkungan Microsoft Dataverse di **konfigurasikan berbagi data dengan Microsoft Dataverse dan aktifkan kemampuan tambahan**. Kemampuan ini melibatkan berbagi data dengan aplikasi dan solusi berdasarkan Microsoft Dataverse, penyerapan data dari sumber data lokal, atau [prediksi](predictions.md) penggunaan. Pilih **Aktifkan berbagi data** untuk berbagi data output Customer Insights dengan Data Lake terkelola Microsoft Dataverse.

   > [!NOTE]
   > - Berbagi data dengan Data Lake terkelola Microsoft Dataverse saat ini tidak didukung bila Anda menyimpan semua data untuk Azure Data Lake Storage Anda sendiri.
   > - [Prediksi nilai yang tidak ditemukan dalam entitas](predictions.md) dan laporan PowerBI Embedded dalam wawasan audiens (jika diaktifkan pada lingkungan Anda) saat ini tidak didukung bila Anda mengaktifkan berbagi data dengan telaga data terkelola Microsoft Dataverse.

   Setelah mengaktifkan berbagi data dengan Microsoft Dataverse, refresh penuh pada sumber data Anda dan proses lainnya akan dimulai. Jika proses saat ini berjalan, Anda tidak melihat opsi untuk mengaktifkan berbagi data dengan Microsoft Dataverse. Tunggu proses tersebut selesai atau membatalkannya untuk mengaktifkan berbagi data. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Pilihan konfigurasi untuk mengaktifkan berbagi data dengan Microsoft Dataverse.":::
   
   Bila Anda menjalankan proses, seperti konsumsi data atau pembuatan segmen, folder yang sesuai akan dibuat di akun penyimpanan yang Anda tentukan di atas. File data dan file model.json akan dibuat dan ditambahkan ke subfolder masing-masing, tergantung pada proses yang Anda jalankan.

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
- Sumber data dari folder Common Data Model dan Data Lake terkelola Dataverse. Anda harus membuat sumber data secara manual dengan nama yang sama seperti di lingkungan sumber.

Bila Anda menyalin lingkungan, Anda akan melihat pesan konfirmasi bahwa lingkungan baru telah dibuat. Pilih **buka sumber data** untuk melihat daftar sumber data.

Semua sumber data akan menampilkan status **kredensial yang diperlukan**. Edit sumber data dan masukkan kredensial untuk me-refresh mereka.

:::image type="content" source="media/data-sources-copied.png" alt-text="Daftar sumber data yang disalin dan memerlukan otentikasi.":::

Setelah menyegarkan sumber data, buka **data** > **Satukan**. Di sini Anda akan menemukan pengaturan dari lingkungan sumber. Edit sesuai kebutuhan atau pilih **Jalankan** untuk memulai proses penyatuan data dan buat entitas pelanggan terpadu.

Bila penyatuan data selesai, buka **langkah** dan **segmen** untuk me-refresh juga.

## <a name="reset-an-existing-environment"></a>Mengatur ulang lingkungan yang ada

Sebagai administrator, Anda dapat mengatur ulang lingkungan ke status kosong jika Anda ingin menghapus semua konfigurasi dan menghapus data yang diserap.

1.  Pilih pemilih **Lingkungan** di header aplikasi. 

2.  Pilih lingkungan yang ingin Anda atur ulang dan pilih elipsis (**...**). 

3. Pilih opsi **Atur ulang**. 

4.  Untuk mengkonfirmasi penghapusan, masukkan nama lingkungan dan pilih **Atur ulang**.

## <a name="delete-an-existing-environment"></a>Menghapus lingkungan yang ada

Sebagai administrator, Anda dapat menghapus lingkungan yang dikelola.

1.  Pilih pemilih **Lingkungan** di header aplikasi.

2.  Pilih lingkungan yang ingin Anda atur ulang dan pilih elipsis (**...**). 

3. Pilih opsi **Hapus**. 

4.  Untuk mengonfirmasikan penghapusan, masukkan nama lingkungan dan pilih **Hapus**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
