---
title: Permintaan hak subjek data (DSR) di bawah GDPR | Microsoft Docs
description: Merespons permintaan subjek Data untuk kemampuan wawasan audiens Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6faaeb6a1ee34c3e5c8e7d465b37cee589bc920c
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483676"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Permintaan hak subjek data (DSR) di bawah GDPR

Peraturan Perlindungan Data Umum Uni Eropa (GDPR) telah berlaku sejak 25 Mei 2018. Peraturan ini memberikan hak yang signifikan kepada individu terkait data mereka. GDPR adalah tentang melindungi dan mengaktifkan hak privasi individu. Anda dapat membaca lebih lanjut tentang komitmen Microsoft untuk keamanan dan kesesuaian di [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Kami berkomitmen untuk membantu pelanggan memenuhi persyaratan GDPR. Ini mencakup hak untuk menghapus dan mengekspor data yang mencakup informasi pribadi seperti ID pengguna, nomor telepon, dan alamat email. Administrator dapat menerapkan permintaan pengguna untuk menghapus atau mengekspor data pribadi.

## <a name="audience-insights"></a>Wawasan audiens

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Merespons permintaan penghapusan subjek GDPR untuk kemampuan wawasan audiens Dynamics 365 Customer Insights

"Hak untuk menghapus" data pribadi dari data pelanggan organisasi adalah perlindungan kunci dalam peraturan perlindungan data umum (GDPR). Menghapus data pribadi mencakup penghapusan semua data pribadi dan log yang dihasilkan sistem, kecuali informasi log audit.

#### <a name="manage-data-subject-delete-requests"></a>Mengelola permintaan penghapusan subjek data

Wawasan audiens menawarkan pengalaman dalam produk berikut untuk menghapus data pribadi untuk pelanggan tertentu atau pengguna:

- **Mengelola permintaan untuk data pelanggan**: data pelanggan dalam Customer Insights terserap dari sumber data asli eksternal untuk Customer Insights. Semua permintaan penghapusan GDPR harus dilakukan di sumber data asli.
- **Mengelola permintaan penghapusan untuk data pengguna Customer Insights**: data untuk pengguna dibuat oleh Customer Insights. Semua permintaan penghapusan GDPR harus dilakukan di Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Mengelola permintaan untuk menghapus data pelanggan

Admin Customer Insights dapat mengikuti langkah berikut untuk menghapus data pelanggan yang telah dihapus di sumber data:

1. Masuk ke Dynamics 365 Customer Insights.
2. Di wawasan audiens, buka **Data** > **Sumber data**
3. Untuk setiap sumber data dalam daftar berisi data pelanggan yang telah dihapus:
   1. Pilih (...) dan kemudian pilih **Segarkan**.
   2. Periksa status sumber data dalam **status**. Tanda centang berarti penyegaran berhasil. Segitiga peringatan berarti terjadi kesalahan. Jika segitiga peringatan ditampilkan, hubungi D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Menangani permintaan penghapusan GDPR untuk data pelanggan.](audience-insights/media/gdpr-data-sources.png "Menangani permintaan penghapusan GDPR untuk data pelanggan")

##### <a name="manage-delete-requests-for-user-data"></a>Mengelola permintaan penghapusan untuk data pengguna

Admin Customer Insights dapat mengikuti langkah berikut untuk menghapus data pengguna Customer Insights:

1. Masuk ke Dynamics 365 Customer Insights.
2. Di wawasan audiens, buka **Admin** > **Izin**.
3. Centang kotak untuk pengguna yang akan dihapus.
4. Pilih **Hapus**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Merespons permintaan ekspor subjek data GDPR

Sebagai bagian dari komitmen kami untuk bermitra dengan Anda dalam perjalanan Anda ke peraturan perlindungan data umum (GDPR), kami telah mengembangkan dokumentasi untuk membantu Anda bersiap. Dokumentasi ini menjelaskan langkah yang dapat anda lakukan hari ini untuk mendukung kepatuhan GDPR saat menggunakan wawasan audiens.

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

## <a name="engagement-insights"></a>Wawasan keterlibatan

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Menghapus dan mengekspor data aktivitas yang berisi informasi identitas pengguna akhir

Bagian berikut menjelaskan cara menghapus dan mengekspor data aktivitas yang mungkin berisi data pribadi.

Untuk menghapus atau mengekspor data:

1. Tandai properti aktivitas yang berisi data dengan informasi pribadi.
2. Hapus atau ekspor data yang terkait dengan nilai tertentu (contoh: ID pengguna tertentu).

#### <a name="tag-and-update-event-properties"></a>Tandai dan perbarui properti aktivitas

Data pribadi ditandai pada tingkat properti aktivitas. Pertama, tandai properti yang sedang dipertimbangkan untuk penghapusan atau ekspor.

Untuk menandai properti aktivitas sebagai berisi informasi pribadi, ikuti langkah-langkah berikut:

1. Buka ruang kerja yang berisi aktivitas.

1. Buka **Data** > **Aktivitas** untuk melihat daftar aktivitas dalam ruang kerja yang dipilih.
  
1. Pilih aktivitas yang ingin Anda tandai.

1. Pilih **Edit properti** untuk membuka daftar panel semua properti dari aktivitas yang dipilih.
     
1. Pilih **...** dan kemudian pilih **Edit** untuk mencapai dialog **Perbarui properti**.

   ![Edit aktivitas.](engagement-insights/media/edit-event.png "Edit aktivitas")

1. Di jendela **Perbarui Properti**, pilih **...** di sudut kanan atas, lalu pilih kotak **Berisi EUII**. Pilih **Perbarui** untuk menyimpan perubahan.

   ![Simpan perubahan.](engagement-insights/media/update-property.png "Simpan perubahan")

   > [!NOTE]
   > Setiap kali skema aktivitas berubah atau Anda membuat aktivitas baru, Sebaiknya Anda mengevaluasi properti dan tag aktivitas terkait atau hapus tag mereka sebagai berisi data pribadi, jika perlu.

#### <a name="delete-or-export-tagged-event-data"></a>Menghapus atau mengekspor data aktivitas yang ditandai

Jika semua properti aktivitas telah ditandai dengan benar sebagaimana dijelaskan pada langkah sebelumnya, admin lingkungan dapat mengeluarkan permintaan penghapusan terhadap data aktivitas yang ditandai.

Untuk mengelola permintaan penghapusan atau ekspor EUII

1. Buka **Admin** > **Lingkungan** > **Pengaturan**.

1. Di bagian **Kelola informasi identifikasi pengguna akhir (EUII)**, pilih **Kelola EUII**.

##### <a name="deletion"></a>Penghapusan

Untuk penghapusan, Anda dapat memasukkan daftar ID pengguna di bagian **hapus informasi identifikasi pengguna akhir (EUII)**. ID ini kemudian akan dibandingkan dengan semua properti aktivitas yang ditandai dari semua proyek di lingkungan saat ini melalui pencocokan string yang sama persis. 

Jika nilai properti sesuai dengan salah satu ID yang disediakan, aktivitas terkait akan dihapus secara permanen. Karena tindakan ini tidak dapat diurungkan, Anda harus mengkonfirmasi penghapusan setelah memilih **Hapus**.

##### <a name="export"></a>Export

Proses ekspor sama dengan proses penghapusan dalam menentukan nilai properti aktivitas di bagian **Ekspor informasi identifikasi pengguna akhir (EUII)**. Selain itu, Anda harus menyediakan **URL penyimpanan blob Azure** untuk menentukan tujuan ekspor. URL Azure Blob harus mencakup [SAS (Tanda Tangan Akses Bersama)](/azure/storage/common/storage-sas-overview).

Setelah memilih **Ekspor**, semua aktivitas tim saat ini yang berisi properti yang ditandai dan cocok akan diekspor dalam format CSV ke tujuan ekspor.

### <a name="good-practices"></a>Praktik yang baik

* Coba untuk menghindari pengiriman aktivitas yang berisi data pribadi.
* Jika Anda perlu mengirim aktivitas yang berisi data EUII, batasi jumlah properti aktivitas dan aktivitas yang berisi data EUII. Idealnya, batasi diri Anda pada salah satu aktivitas tersebut.
* Pastikan hanya sedikit orang yang memiliki akses ke data pribadi yang dikirim.
* Untuk aktivitas yang berisi data pribadi, pastikan Anda mengatur satu properti untuk menghasilkan pengidentifikasi unik yang dapat dengan mudah ditautkan ke pengguna tertentu (misalnya, ID pengguna). Hal ini memudahkan untuk memisahkan data dan mengekspor atau menghapus data yang benar.
* Cukup tandai satu properti per aktivitas sebagai berisi data pribadi. Idealnya adalah yang hanya berisi pengidentifikasi unik.
* Jangan tandai properti yang berisi nilai terlalu besar (misalnya, seluruh badan permintaan). Kemampuan wawasan keterlibatan menggunakan pencocokan string sama persis saat menentukan aktivitas yang akan dihapus atau diekspor.

[!INCLUDE[footer-include](includes/footer-banner.md)]