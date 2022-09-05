---
title: Permintaan hak subjek data (DSR) di bawah GDPR | Microsoft Docs
description: Merespons permintaan subjek data untuk Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387115"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Permintaan hak subjek data (DSR) di bawah GDPR

Peraturan Perlindungan Data Umum Uni Eropa (GDPR) telah berlaku sejak 25 Mei 2018. Peraturan ini memberikan hak yang signifikan kepada individu terkait data mereka. GDPR adalah tentang melindungi dan mengaktifkan hak privasi individu. Baca selengkapnya tentang komitmen Microsoft terhadap keamanan dan kepatuhan di [Pusat Kepercayaan Microsoft](https://www.microsoft.com/trust-center).

Kami berkomitmen untuk membantu pelanggan memenuhi persyaratan GDPR. Ini termasuk hak untuk menghapus atau mengekspor data yang mencakup informasi pribadi seperti ID pengguna, nomor telepon, dan alamat email. Administrator dapat menerapkan permintaan pengguna untuk menghapus atau mengekspor data pribadi.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Menanggapi permintaan penghapusan subjek data GDPR untuk Customer Insights

"Hak untuk menghapus" data pribadi dari data pelanggan organisasi adalah perlindungan kunci dalam peraturan perlindungan data umum (GDPR). Menghapus data pribadi mencakup penghapusan semua data pribadi dan log yang dihasilkan sistem, kecuali informasi log audit.

### <a name="manage-data-subject-delete-requests"></a>Mengelola permintaan penghapusan subjek data

Customer Insights menawarkan pengalaman dalam produk berikut untuk menghapus data pribadi bagi pelanggan atau pengguna tertentu:

- **Mengelola permintaan untuk data pelanggan**: data pelanggan dalam Customer Insights terserap dari sumber data asli eksternal untuk Customer Insights. Lakukan permintaan penghapusan GDPR di sumber data asli terlebih dahulu.
- **Mengelola permintaan penghapusan untuk data pengguna Customer Insights**: data untuk pengguna dibuat oleh Customer Insights. Lakukan semua permintaan penghapusan GDPR di Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Mengelola permintaan untuk menghapus data pelanggan

Sebagai admin Customer Insights, hapus data pelanggan Customer Insights yang telah dihapus di sumber data. Verifikasi bahwa permintaan penghapusan GDPR dilakukan di sumber data asli.

1. Masuk ke Dynamics 365 Customer Insights.

1. Buka **Data** > **Sumber data**.

1. Untuk setiap sumber data dalam daftar berisi data pelanggan yang telah dihapus:
   1. Pilih sumber data lalu pilih **Refresh**.
   1. Periksa status sumber data dalam **status**. Tanda centang berarti penyegaran berhasil. Segitiga peringatan berarti terjadi kesalahan. Jika segitiga peringatan ditampilkan, hubungi D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Menangani permintaan penghapusan GDPR untuk data pelanggan.":::

1. Setelah refresh sumber data berhasil, jalankan refresh hilir juga. Terutama, jika Anda tidak memiliki penyegaran penuh berulang dari Customer Insights yang dijadwalkan.

   > [!IMPORTANT]
   > Segmen statis tidak disertakan dalam refresh penuh atau menjalankan refresh hilir setelah permintaan penghapusan. Untuk memastikan bahwa data pelanggan juga dihapus dari segmen statis, buat ulang segmen statis dengan data sumber yang disegarkan.

#### <a name="manage-delete-requests-for-user-data"></a>Mengelola permintaan penghapusan untuk data pengguna

Sebagai admin Customer Insights, hapus data pengguna Customer Insights.

1. Masuk ke Dynamics 365 Customer Insights.

1. Buka **> Keamanan** > **Admin** dan pilih tab **Pengguna**.

1. Pilih kotak centang untuk pengguna yang ingin Anda hapus.

1. Pilih **Hapus**.

1. Konfirmasikan Penghapusan.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Merespons permintaan ekspor subjek data GDPR

Hak portabilitas data memungkinkan subjek data untuk meminta salinan data pribadi mereka dalam format elektronik (yaitu format "terstruktur, umum digunakan, dapat dibaca mesin, dan dapat dioperasikan") yang dapat ditransmisikan ke pengontrol data lainnya.

### <a name="manage-export-and-view-requests"></a>Mengelola ekspor dan lihat permintaan

Mengelola permintaan untuk mengekspor data pelanggan atau pengguna.

#### <a name="export-customer-data-tenant-admin"></a>Ekspor data pelanggan (admin penyewa)

Sebagai administrator penyewa, ekspor data pelanggan.

1. Kirim email ke D365CI@microsoft.com yang menentukan alamat email pelanggan yang diminta. Tim Customer Insights akan mengirim email ke alamat email admin penyewa yang terdaftar, meminta konfirmasi untuk mengekspor data.
2. Berikan konfirmasi untuk mengekspor data untuk pelanggan yang diminta.
3. Terima data yang diekspor melalui alamat email admin penyewa.

#### <a name="export-user-data-tenant-admin"></a>Ekspor data pengguna (admin penyewa)

Sebagai administrator penyewa, ekspor data pengguna.

1. Kirim email ke D365CI@microsoft.com yang menentukan alamat email pengguna yang diminta. Tim Customer Insights mengirimkan email ke alamat email admin penyewa terdaftar, meminta konfirmasi untuk mengekspor data.
1. Berikan konfirmasi untuk mengekspor data untuk pengguna yang diminta.
1. Terima data yang diekspor melalui alamat email admin penyewa.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Penanganan penghapusan data di Dynamics 365 Customer Insights

Data dihapus (partisi data dan snapshot data) jika partisi data dan snapshot data tidak aktif selama lebih dari 30 hari, yang berarti mereka telah digantikan oleh partisi data baru dan snapshot melalui penyegaran sumber data.

Tidak semua data dan snapshot dihapus. Partisi data dan rekam jepret data terbaru aktif karena digunakan di Customer Insights. Untuk data terbaru, tidak masalah jika sumber data tidak disegarkan dalam 30 hari terakhir.

[!INCLUDE [footer-include](includes/footer-banner.md)]
