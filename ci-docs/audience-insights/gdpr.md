---
title: Permintaan hak subjek data (DSR) di bawah GDPR | Microsoft Docs
description: Merespons permintaan subjek Data untuk kemampuan wawasan audiens Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e832fbbdfb59cb06d98715223edca438d2c3a7f2
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554326"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Permintaan hak subjek data (DSR) di bawah GDPR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Merespons permintaan penghapusan subjek GDPR untuk kemampuan wawasan audiens Dynamics 365 Customer Insights

"Hak untuk menghapus" data pribadi dari data pelanggan organisasi adalah perlindungan kunci dalam peraturan perlindungan data umum (GDPR). Menghapus data pribadi mencakup penghapusan semua data pribadi dan log yang dihasilkan sistem, kecuali informasi log audit.

### <a name="manage-data-subject-delete-requests"></a>Mengelola permintaan penghapusan subjek data

Wawasan audiens menawarkan pengalaman dalam produk berikut untuk menghapus data pribadi untuk pelanggan tertentu atau pengguna:

- **Mengelola permintaan untuk data pelanggan**: data pelanggan dalam Customer Insights terserap dari sumber data asli eksternal untuk Customer Insights. Semua permintaan penghapusan GDPR harus dilakukan di sumber data asli.
- **Mengelola permintaan penghapusan untuk data pengguna Customer Insights**: data untuk pengguna dibuat oleh Customer Insights. Semua permintaan penghapusan GDPR harus dilakukan di Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Mengelola permintaan untuk data pelanggan

Admin Customer Insights dapat mengikuti langkah berikut untuk menghapus data pelanggan yang telah dihapus di sumber data:

1. Masuk ke Dynamics 365 Customer Insights.
2. Di wawasan audiens, buka **Data** > **Sumber data**
3. Untuk setiap sumber data dalam daftar berisi data pelanggan yang telah dihapus:
   1. Pilih (...) dan kemudian pilih **Segarkan**.
   2. Periksa status sumber data dalam **status**. Tanda centang berarti penyegaran berhasil. Segitiga peringatan berarti terjadi kesalahan. Jika segitiga peringatan ditampilkan, hubungi D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Menangani permintaan penghapusan GDPR untuk data pelanggan.](media/gdpr-data-sources.png "Menangani permintaan penghapusan GDPR untuk data pelanggan")

#### <a name="manage-delete-requests-for-user-data"></a>Mengelola permintaan penghapusan untuk data pengguna

Admin Customer Insights dapat mengikuti langkah berikut untuk menghapus data pengguna Customer Insights:

1. Masuk ke Dynamics 365 Customer Insights.
2. Di wawasan audiens, buka **Admin** > **Izin**.
3. Centang kotak untuk pengguna yang akan dihapus.
4. Pilih **Hapus**.

> [!div class="mx-imgBorder"]
> ![Menangani permintaan penghapusan untuk data pengguna.](media/gdpr-permissions.png "Menangani permintaan penghapusan untuk data pengguna")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Merespons permintaan ekspor subjek data GDPR

Sebagai bagian dari komitmen kami untuk bermitra dengan Anda dalam perjalanan Anda ke peraturan perlindungan data umum (GDPR), kami telah mengembangkan dokumentasi untuk membantu Anda bersiap. Dokumentasi ini menjelaskan langkah yang dapat anda lakukan hari ini untuk mendukung kepatuhan GDPR saat menggunakan wawasan audiens.

### <a name="manage-export-and-view-requests"></a>Mengelola ekspor dan lihat permintaan

Hak portabilitas data memungkinkan subjek data untuk meminta salinan data pribadi mereka dalam format elektronik (yaitu format "terstruktur, umum digunakan, dapat dibaca mesin, dan dapat dioperasikan") yang dapat ditransmisikan ke pengontrol data lainnya.

#### <a name="export-customer-data-tenant-admin"></a>Ekspor data pelanggan (admin penyewa)

Administrator penyewa dapat mengikuti langkah berikut untuk mengekspor data:

1. Kirim email ke D365CI@microsoft.com yang menentukan alamat email pelanggan yang diminta. Tim Customer Insights akan mengirim email ke alamat email admin penyewa yang terdaftar, meminta konfirmasi untuk mengekspor data.
2. Berikan konfirmasi untuk mengekspor data untuk pelanggan yang diminta.
3. Terima data yang diekspor melalui alamat email admin penyewa.

#### <a name="export-user-data-tenant-admin"></a>Ekspor data pengguna (admin penyewa)

1. Kirim email ke D365CI@microsoft.com yang menentukan alamat email pengguna yang diminta. Tim Customer Insights akan mengirim email ke alamat email admin penyewa yang terdaftar, meminta konfirmasi untuk mengekspor data.
2. Berikan konfirmasi untuk mengekspor data untuk pengguna yang diminta.
3. Terima data yang diekspor melalui alamat email admin penyewa.


[!INCLUDE[footer-include](../includes/footer-banner.md)]