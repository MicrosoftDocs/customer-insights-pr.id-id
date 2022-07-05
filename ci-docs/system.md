---
title: Konfigurasi sistem
description: Pelajari tentang pengaturan sistem di Dynamics 365 Customer Insights.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 0ef84d8e286d8135eb8938e72f1319925e948bed
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050675"
---
# <a name="system-configuration"></a>Konfigurasi sistem

Untuk mengakses konfigurasi sistem, buka **Sistem** > **Admin** untuk melihat daftar tugas dan proses sistem.

Halaman **Sistem** mencakup tab berikut:
- [Status](#status-tab)
- [Jadwal](#schedule-tab)
- [Penggunaan API](#api-usage-tab)
- [Tentang](#about-tab)
- [Umum](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Tab Pengaturan di halaman sistem.":::

## <a name="status-tab"></a>Tab status

Tab **Status** memungkinkan Anda melacak kemajuan tugas, penyerapan data, ekspor data, dan beberapa proses produk penting lainnya. Tinjau informasi pada tab ini untuk memastikan kelengkapan tugas dan proses aktif Anda.

Tab ini mencakup tabel dengan status dan informasi pemrosesan untuk berbagai proses. Setiap tabel akan melacak **nama** tugas dan entitas yang sesuai, **status** dijalankan terbaru, dan Kapan **terakhir diperbarui**. Anda dapat melihat detail dari beberapa eksekusi terakhir dengan memilih tugas atau nama proses. 

Pilih status di samping tugas atau proses di **kolom Status** untuk membuka **panel Detail** kemajuan.

   :::image type="content" source="media/system-progress-details.png" alt-text="Panel detail kemajuan sistem":::

### <a name="status-definitions"></a>Definisi status

Sistem menggunakan status berikut untuk tugas dan proses:

|Status  |Devinisi  |
|---------|---------|
|Dibatalkan |Pemrosesan dibatalkan oleh pengguna sebelum selesai.   |
|Gagal   |Penyerapan data mengalami kesalahan.         |
|Kegagalan  |Pemrosesan telah gagal.  |
|Belum dimulai   |Sumber data belum diserap datanya atau masih dalam mode draf.         |
|Sedang memproses  |Tugas atau proses sedang berlangsung.  |
|Me-refresh    |Penyerapan data sedang berlangsung. Anda dapat membatalkan operasi ini dengan memilih **berhenti menyegarkan** di kolom **tindakan**. Menghentikan refresh sumber data akan mengembalikannya ke status refresh terakhir.       |
|Dilewati  |Tugas atau proses dilewati. Satu atau beberapa proses hilir yang tugas ini tergantung padanya gagal atau dilewati.|
|Berhasil  |Tugas atau proses berhasil diselesaikan. Untuk sumber data, menunjukkan bahwa data telah berhasil diserap jika waktu disebutkan di **kolom Refresh**.|
|Dalam Antrean | Pemrosesan diantrekan dan akan dimulai setelah semua tugas dan proses hulu selesai. Untuk informasi selengkapnya, lihat [Merefresh proses](#refresh-processes).|

### <a name="refresh-processes"></a>Proses penyegaran

Refresh untuk tugas dan proses dijalankan sesuai dengan jadwal [yang](#schedule-tab) dikonfigurasi. 

|Proses  |Deskripsi  |
|---------|---------|
|Aktivitas  |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada proses penggabungan. Wawasan tergantung pada prosesnya.|
|Penautan analisis |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada segmen.  |
|Persiapan analisis |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada segmen.  |
|Persiapan data   |Membutuhkan entitas untuk dijalankan. Entitas sumber data bergantung pada penyerapan. Entitas yang diperkaya tergantung pada pengayaan. Entitas Pelanggan bergantung pada penggabungan.  |
|Sumber Data   |Tidak tergantung pada proses lainnya. Kecocokan tergantung pada keberhasilan penyelesaian proses ini.  |
|Pengayaan   |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada proses penggabungan. |
|Ekspor tujuan |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada segmen.  |
|Wawasan |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada segmen.  |
|Intelijen   |Tergantung pada penggabungan.   |
|Cocokkan |Tergantung pada pemrosesan sumber data yang digunakan dalam definisi pencocokan.      |
|Tindakan  |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada proses penggabungan.  |
|Penggabungan   |Tergantung pada penyelesaian proses kecocokan. Segmen, tindakan, pengayaan, pencarian, aktivitas, Prediksi, dan persiapan data tergantung pada keberhasilan penyelesaian proses ini.   |
|Profil   |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada proses penggabungan. |
|Pencarian   |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada proses penggabungan. |
|Segmen  |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada proses penggabungan. Wawasan tergantung pada prosesnya.|
|Sistem   |Tergantung pada penyelesaian proses kecocokan. Segmen, tindakan, pengayaan, pencarian, aktivitas, Prediksi, dan persiapan data tergantung pada keberhasilan penyelesaian proses ini.   |
|User  |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada entitas.  |

Pilih status proses untuk melihat detail kemajuan dari seluruh pekerjaan yang dijalaninya. Proses refresh di atas dapat membantu memahami apa yang dapat Anda lakukan untuk mengatasi tugas atau proses yang **Dilewati** atau **Diantrekan**.

## <a name="schedule-tab"></a>tab Jadwal

Gunakan tab **jadwal** untuk menjadwalkan penyegaran otomatis dari semua [sumber data yang diserap](data-sources.md). Penyegaran otomatis membantu memastikan bahwa pembaruan dari sumber data Anda tercermin dalam profil pelanggan terpadu Anda.

> [!NOTE]
> Sumber data yang dikelola oleh Anda refresh pada jadwal mereka sendiri. Untuk menjadwalkan refresh sumber data yang dikelola oleh Anda, konfigurasikan pengaturan refresh pada sumber data tertentu dari **halaman Sumber** data.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Pengaturan refresh aliran data.":::

1. Buka **Sistem** > **Admin** dan pilih tab **Jadwal**.

2. Status default untuk refresh terjadwal adalah **tidak aktif**. Untuk mengaktifkan penyegaran terjadwal, Ubah pengalih di bagian atas layar ke **aktif**.

3. Pilih antara penyegaran **mingguan** (default) dan **harian**. Jika Anda ingin menjadwalkan penyegaran mingguan, pilih satu atau beberapa hari untuk menjalankan refresh.

4. Atur **zona waktu**, lalu gunakan dropdown **waktu** untuk mengatur waktu penyegaran. Setelah selesai, pilih **Atur**. Jika Anda ingin menjadwalkan beberapa penyegaran dalam satu hari, pilih **Tambah waktu lain**.

5. Pilih **Simpan** untuk menerapkan perubahan.

## <a name="about-tab"></a>tab Tentang

tab **tentang** berisi **nama tampilan** organisasi anda, **id lingkungan** aktif, **kawasan**, dan **id sesi** anda. Jika anda memiliki lebih dari satu lingkungan kerja, anda harus memberikan nama tampilan yang mudah diidentifikasi.

## <a name="general-tab"></a>Tab Umum

Anda dapat mengubah bahasa dan format negara/kawasan pada tab **Umum**.

Customer Insights [mendukung banyak bahasa](/dynamics365/get-started/availability). Aplikasi menggunakan preferensi bahasa Anda untuk menampilkan elemen seperti menu, teks label, dan pesan sistem dalam bahasa pilihan Anda.

Data dan informasi impor yang Anda masukkan secara manual tidak diterjemahkan.

### <a name="update-the-settings"></a>Perbarui pengaturan

Untuk mengubah bahasa yang diinginkan, pilih **bahasa** dari menu pilihan.

Untuk mengubah pemformatan yang diinginkan untuk tanggal, waktu, dan angka, gunakan menu pilihan **format negara/kawasan**. Pratinjau pemformatan ditampilkan di bidang ini. Sistem akan secara otomatis menyarankan pilihan saat Anda memilih bahasa baru.

Pilih **Simpan** untuk mengonfirmasikan pilihan.

## <a name="api-usage-tab"></a>Tab penggunaan API

Cari rincian tentang penggunaan API real-time dan lihat kejadian yang terjadi pada waktu jangka waktu tertentu. Anda memilih jangka waktu di menu dropdown **Pilih Jangka waktu**. 

**Penggunaan API** berisi tiga bagian: 
- **Panggilan API** - diagram yang memvisualisasikan jumlah panggilan agregat ke API dalam jangka waktu yang dipilih.

- **Transfer data** - diagram yang menunjukkan jumlah data yang ditransfer melalui API dalam jangka waktu yang dipilih.

-  **Operasi** - tabel dengan baris untuk setiap operasi API yang tersedia dan rincian tentang penggunaan operasi. Anda dapat memilih nama operasi untuk membuka [referensi API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operasi yang menggunakan [penyerapan](real-time-data-ingestion.md) data real-time berisi tombol dengan simbol teropong untuk melihat penggunaan API real-time. Pilih tombol untuk membuka panel samping berisi rincian penggunaan untuk penggunaan API real-time di lingkungan saat ini.   
   Gunakan kotak **Grup berdasarkan** di panel **penggunaan API Real-time** untuk memilih cara terbaik menyajikan interaksi real-time Anda. Anda dapat mengelompokkan data berdasarkan metode API, nama berkualifikasi entitas (entitas yang diserap), dibuat oleh (sumber aktivitas), hasil (keberhasilan atau kegagalan), atau kode kesalahan. Data tersedia dalam bentuk grafik riwayat dan sebagai tabel.


[!INCLUDE [footer-include](includes/footer-banner.md)]
