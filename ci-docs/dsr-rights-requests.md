---
title: Permintaan hak subjek data (DSR) di bawah GDPR | Microsoft Docs
description: Merespons permintaan subjek data untuk Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6c6ce49c18de3a09d28138316d893e6842919042
ms.sourcegitcommit: ff0f4b5664d995870c91adb87c7d3780a582efca
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/13/2022
ms.locfileid: "9146699"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Permintaan hak subjek data (DSR) di bawah GDPR

Peraturan Perlindungan Data Umum Uni Eropa (GDPR) telah berlaku sejak 25 Mei 2018. Peraturan ini memberikan hak yang signifikan kepada individu terkait data mereka. GDPR adalah tentang melindungi dan mengaktifkan hak privasi individu. Anda dapat membaca lebih lanjut tentang komitmen Microsoft untuk keamanan dan kesesuaian di [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Kami berkomitmen untuk membantu pelanggan memenuhi persyaratan GDPR. Ini mencakup hak untuk menghapus dan mengekspor data yang mencakup informasi pribadi seperti ID pengguna, nomor telepon, dan alamat email. Administrator dapat menerapkan permintaan pengguna untuk menghapus atau mengekspor data pribadi.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Merespons permintaan penghapusan subjek data GDPR untuk Dynamics 365 Customer Insights

"Hak untuk menghapus" data pribadi dari data pelanggan organisasi adalah perlindungan kunci dalam peraturan perlindungan data umum (GDPR). Menghapus data pribadi mencakup penghapusan semua data pribadi dan log yang dihasilkan sistem, kecuali informasi log audit.

#### <a name="manage-data-subject-delete-requests"></a>Mengelola permintaan penghapusan subjek data

Customer Insights menawarkan pengalaman dalam produk berikut untuk menghapus data pribadi bagi pelanggan atau pengguna tertentu:

- **Mengelola permintaan untuk data pelanggan**: data pelanggan dalam Customer Insights terserap dari sumber data asli eksternal untuk Customer Insights. Lakukan permintaan penghapusan GDPR di sumber data asli terlebih dahulu.
- **Mengelola permintaan penghapusan untuk data pengguna Customer Insights**: data untuk pengguna dibuat oleh Customer Insights. Semua permintaan penghapusan GDPR harus dilakukan di Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Mengelola permintaan untuk menghapus data pelanggan

Admin Customer Insights dapat mengikuti langkah-langkah ini untuk menghapus data pelanggan yang telah dihapus di sumber data. Pastikan bahwa permintaan penghapusan dilakukan di sumber data Anda sebelum melanjutkan dengan langkah-langkah yang tercantum di bawah ini. 

1. Masuk ke Dynamics 365 Customer Insights.
1. **Buka Sumber Data Data** > **·**
1. Untuk setiap sumber data dalam daftar berisi data pelanggan yang telah dihapus:
   1. Pilih elipsis vertikal (&vellip;) lalu pilih **Refresh**.
   1. Periksa status sumber data dalam **status**. Tanda centang berarti penyegaran berhasil. Segitiga peringatan berarti terjadi kesalahan. Jika segitiga peringatan ditampilkan, hubungi D365CI@microsoft.com.
1. Setelah refresh sumber data berhasil, jalankan refresh hilir juga. Terutama, jika Anda tidak memiliki penyegaran penuh berulang dari Customer Insights yang dijadwalkan. 

> [!IMPORTANT]
> Segmen statis tidak disertakan dalam refresh penuh atau menjalankan refresh hilir setelah permintaan penghapusan. Untuk memastikan bahwa data pelanggan juga dihapus dari segmen statis, buat ulang segmen statis dengan data sumber yang disegarkan.

> [!div class="mx-imgBorder"]
> ![Menangani permintaan penghapusan GDPR untuk data pelanggan.](media/gdpr-data-sources.png "Menangani permintaan penghapusan GDPR untuk data pelanggan")

##### <a name="manage-delete-requests-for-user-data"></a>Mengelola permintaan penghapusan untuk data pengguna

Admin Customer Insights dapat mengikuti langkah berikut untuk menghapus data pengguna Customer Insights:

1. Masuk ke Dynamics 365 Customer Insights.
2. Buka **Izin** > **Keamanan** > **Admin**.
3. Centang kotak untuk pengguna yang akan dihapus.
4. Pilih **Hapus**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Merespons permintaan ekspor subjek data GDPR

Sebagai bagian dari komitmen kami untuk bermitra dengan Anda dalam perjalanan Anda menuju Peraturan Perlindungan Data Umum (GDPR), kami telah mengembangkan dokumentasi untuk membantu Anda menanggapi permintaan dari subjek data.

#### <a name="manage-export-and-view-requests"></a>Mengelola ekspor dan lihat permintaan

Hak portabilitas data memungkinkan subjek data untuk meminta salinan data pribadi mereka dalam format elektronik (yaitu format "terstruktur, umum digunakan, dapat dibaca mesin, dan dapat dioperasikan") yang dapat ditransmisikan ke pengontrol data lainnya.

##### <a name="export-customer-data-tenant-admin"></a>Ekspor data pelanggan (admin penyewa)

Administrator penyewa dapat mengikuti langkah berikut untuk mengekspor data:

1. Kirim email ke D365CI@microsoft.com yang menentukan alamat email pelanggan yang diminta. Tim Customer Insights akan mengirim email ke alamat email admin penyewa yang terdaftar, meminta konfirmasi untuk mengekspor data.
2. Berikan konfirmasi untuk mengekspor data untuk pelanggan yang diminta.
3. Terima data yang diekspor melalui alamat email admin penyewa.

##### <a name="export-user-data-tenant-admin"></a>Ekspor data pengguna (admin penyewa)

1. Kirim email ke D365CI@microsoft.com yang menentukan alamat email pengguna yang diminta. Tim Customer Insights akan mengirim email ke alamat email admin penyewa yang terdaftar, meminta konfirmasi untuk mengekspor data.
2. Berikan konfirmasi untuk mengekspor data untuk pengguna yang diminta.
3. Terima data yang diekspor melalui alamat email admin penyewa.

### <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Penanganan penghapusan data di Dynamics 365 Customer Insights

1. Data akan dihapus (partisi data dan snapshot data) jika partisi data dan snapshot data tidak aktif selama lebih dari 30 hari, yang berarti mereka telah digantikan oleh partisi data baru dan snapshot melalui penyegaran sumber data.
2. Tidak semua data dan snapshot dihapus. Partisi data terbaru dan rekam jepret data menurut definisi aktif karena digunakan di Customer Insights. Untuk data terbaru, tidak masalah jika sumber data tidak disegarkan dalam 30 hari terakhir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
