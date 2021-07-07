---
title: Konfigurasi sistem dalam wawasan audiens
description: Pelajari tentang pengaturan sistem di kemampuan wawasan audiens Dynamics 365 Customer Insights.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 09d449e51a3a47ec916ab3d017419c9d9be1ffcf
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305714"
---
# <a name="system-configuration"></a>Konfigurasi sistem

Halaman **Sistem** mencakup tab berikut:
- [Status](#status-tab)
- [Jadwal](#schedule-tab)
- [Penggunaan API](#api-usage-tab)
- [Tentang](#about-tab)
- [Umum](#general-tab)

> [!div class="mx-imgBorder"]
> ![Halaman sistem](media/system-tabs.png "Halaman sistem")

## <a name="status-tab"></a>Tab status

**Tab status** memungkinkan Anda melacak kemajuan konsumsi data, ekspor data, serta beberapa proses produk penting lainnya. Tinjau informasi pada tab ini untuk memastikan kelengkapan proses aktif.

Tab ini mencakup tabel dengan status dan informasi pemrosesan untuk berbagai proses. Setiap tabel akan melacak **nama** tugas dan entitas yang sesuai, **status** dijalankan terbaru, dan Kapan **terakhir diperbarui**.

Lihat rincian beberapa aktivitas terakhir dari tugas dengan memilih nama.

### <a name="status-types"></a>Jenis status

Ada enam jenis status untuk tugas. Jenis status berikut juga menampilkan tentang *kecocokan*, *penggabungan*, *sumber data*, *segmen*, *Ukuran*, *pengayaan*, *aktivitas*, dan halaman *prediksi*:

- **Pemrosesan:** tugas sedang berlangsung. Status dapat berubah menjadi sukses atau kegagalan.
- **Berhasil:** tugas berhasil diselesaikan.
- **Dilewati:** tugas dilewati. Satu atau beberapa proses hilir yang tugas ini tergantung padanya gagal atau dilewati.
- **Kegagalan:** pemrosesan tugas gagal.
- **Dibatalkan:** pemrosesan dibatalkan oleh pengguna sebelum selesai.
- **Antrean:** Pemrosesan diantrekan dan akan dimulai setelah semua tugas hulu selesai. Untuk informasi selengkapnya, lihat [Segarkan kebijaksanaan](#refresh-policies).

### <a name="refresh-policies"></a>Segarkan kebijakan

Daftar ini menampilkan kebijakan penyegaran untuk setiap proses utama:

- **Sumber data:** berjalan berdasarkan [jadwal yang dikonfigurasi](#schedule-tab). Tidak tergantung pada proses lainnya. Kecocokan tergantung pada keberhasilan penyelesaian proses ini.
- **Kecocokan:** berjalan berdasarkan [jadwal yang dikonfigurasi](#schedule-tab). Tergantung pada pemrosesan sumber data yang digunakan dalam definisi pencocokan. Penggabungan tergantung pada keberhasilan penyelesaian proses ini.
- **Gabungkan**: berjalan berdasarkan [jadwal yang dikonfigurasi](#schedule-tab). Tergantung pada penyelesaian proses kecocokan. Segmen, tindakan, pengayaan, pencarian, aktivitas, Prediksi, dan persiapan data tergantung pada keberhasilan penyelesaian proses ini.
- **Segmen**: berjalan secara manual (refresh waktu tunggal) dan berdasarkan [jadwal yang dikonfigurasi](#schedule-tab). Tergantung pada penggabungan. Wawasan tergantung pada prosesnya.
- **Ukuran**: berjalan secara manual (refresh waktu tunggal) dan berdasarkan [jadwal yang dikonfigurasi](#schedule-tab). Tergantung pada penggabungan.
- **Aktivitas**: berjalan secara manual (refresh waktu tunggal) dan berdasarkan [jadwal yang dikonfigurasi](#schedule-tab). Tergantung pada penggabungan.
- **Pengayaan**: berjalan secara manual (refresh waktu tunggal) dan berdasarkan [jadwal yang dikonfigurasi](#schedule-tab). Tergantung pada penggabungan.
- **Pencarian**: berjalan secara manual (refresh waktu tunggal) dan berdasarkan [jadwal yang dikonfigurasi](#schedule-tab). Tergantung pada penggabungan.
- **Persiapan data**: berjalan berdasarkan [jadwal yang dikonfigurasi](#schedule-tab). Tergantung pada penggabungan.
- **Wawasan**: berjalan secara manual (refresh waktu tunggal) dan berdasarkan [jadwal yang dikonfigurasi](#schedule-tab). Tergantung pada segmen.

Pilih status tugas untuk melihat rincian kemajuan seluruh pekerjaan tempatnya berada. Kebijakan penyegaran di atas dapat membantu memahami tindakan yang dapat Anda lakukan untuk menangani tugas yang **dilewati** atau **Mengantre**.

## <a name="schedule-tab"></a>tab Jadwal

Gunakan tab **jadwal** untuk menjadwalkan penyegaran otomatis dari semua [sumber data yang diserap](data-sources.md). Penyegaran otomatis membantu memastikan bahwa pembaruan dari sumber data Anda tercermin dalam profil pelanggan terpadu Anda.

1. Di wawasan audiens, buka **Admin** > **sistem** dan pilih tab **Jadwal**.

2. Status default untuk refresh terjadwal adalah **tidak aktif**. Untuk mengaktifkan penyegaran terjadwal, Ubah pengalih di bagian atas layar ke **aktif**.

3. Pilih antara penyegaran **mingguan** (default) dan **harian**. Jika Anda ingin menjadwalkan penyegaran mingguan, pilih satu atau beberapa hari untuk menjalankan refresh.

4. Atur **zona waktu**, lalu gunakan dropdown **waktu** untuk mengatur waktu penyegaran. Setelah selesai, pilih **Atur**. Jika Anda ingin menjadwalkan beberapa penyegaran dalam satu hari, pilih **Tambah waktu lain**.

5. Pilih **Simpan** untuk menerapkan perubahan.

## <a name="about-tab"></a>tab Tentang

tab **tentang** berisi **nama tampilan** organisasi anda, **id lingkungan** aktif, **kawasan**, dan **id sesi** anda. Jika anda memiliki lebih dari satu lingkungan kerja, anda harus memberikan nama tampilan yang mudah diidentifikasi.

## <a name="general-tab"></a>Tab Umum

Terdapat dua pilihan pada format tab **Umum**, **bahasa**, dan **negara/kawasan**.

Aplikasi ini [mendukung sejumlah bahasa](supported-languages.md). Untuk mengubah bahasa yang diinginkan, pilih **bahasa** dari menu pilihan.

Untuk mengubah pemformatan yang diinginkan untuk tanggal, waktu, dan angka, gunakan menu pilihan **format negara/kawasan**. Pratinjau pemformatan ditampilkan di bidang ini. Sistem akan secara otomatis menyarankan pilihan saat Anda memilih bahasa baru.

Pilih **Simpan** untuk mengonfirmasikan pilihan.

## <a name="api-usage-tab"></a>Tab penggunaan API

Cari rincian tentang penggunaan API real-time dan lihat kejadian yang terjadi pada waktu jangka waktu tertentu. Anda memilih jangka waktu di menu dropdown **Pilih Jangka waktu**. 

**Penggunaan API** berisi tiga bagian: 
- **Panggilan API** - diagram yang memvisualisasikan jumlah panggilan agregat ke API dalam jangka waktu yang dipilih.

- **Transfer data** - diagram yang menunjukkan jumlah data yang ditransfer melalui API dalam jangka waktu yang dipilih.

-  **Operasi** - tabel dengan baris untuk setiap operasi API yang tersedia dan rincian tentang penggunaan operasi. Anda dapat memilih nama operasi untuk membuka [referensi API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operasi yang menggunakan [penyerapan data real-time](real-time-data-ingestion.md) berisi tombol dengan simbol teropong untuk melihat penggunaan API real-time. Pilih tombol untuk membuka panel samping berisi rincian penggunaan untuk penggunaan API real-time di lingkungan saat ini.   
   Gunakan kotak **Grup berdasarkan** di panel **penggunaan API Real-time** untuk memilih cara terbaik menyajikan interaksi real-time Anda. Anda dapat mengelompokkan data berdasarkan metode API, nama berkualifikasi entitas (entitas yang diserap), dibuat oleh (sumber aktivitas), hasil (keberhasilan atau kegagalan), atau kode kesalahan. Data tersedia dalam bentuk grafik riwayat dan sebagai tabel.


[!INCLUDE[footer-include](../includes/footer-banner.md)]