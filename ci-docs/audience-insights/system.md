---
title: Konfigurasi sistem dalam wawasan audiens
description: Pelajari tentang pengaturan sistem dalam kemampuan wawasan Dynamics 365 Customer Insights audiens.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1b790106f8b9617d0c1f244e1d15a74c7ef9a82b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732374"
---
# <a name="system-configuration"></a>Konfigurasi sistem

Untuk mengakses konfigurasi sistem dalam audiens wawasan, dari bilah navigasi kiri pilih **Sistem Admin untuk melihat daftar tugas dan proses** > **·** sistem.

Halaman **Sistem** mencakup tab berikut:
- [Status](#status-tab)
- [Jadwal](#schedule-tab)
- [Penggunaan API](#api-usage-tab)
- [Tentang](#about-tab)
- [Umum](#general-tab)
- [Keamanan](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Tab Pengaturan di halaman sistem.":::

## <a name="status-tab"></a>Tab status

Tab **Status memungkinkan Anda melacak kemajuan** tugas, konsumsi data, ekspor data, dan beberapa proses produk penting lainnya. Tinjau informasi pada tab ini untuk memastikan kelengkapan tugas dan proses aktif Anda.

Tab ini mencakup tabel dengan status dan informasi pemrosesan untuk berbagai proses. Setiap tabel akan melacak **nama** tugas dan entitas yang sesuai, **status** dijalankan terbaru, dan Kapan **terakhir diperbarui**. Anda dapat melihat detail beberapa run terakhir dengan memilih tugas atau nama proses. 

Pilih status di samping tugas atau proses di **kolom Status untuk membuka panel Detail** **·** Kemajuan.

   :::image type="content" source="media/system-progress-details.png" alt-text="Panel detail kemajuan sistem":::

### <a name="status-definitions"></a>Definisi status

Sistem menggunakan status berikut untuk tugas dan proses:

|Status  |Devinisi  |
|---------|---------|
|Dibatalkan |Pemrosesan dibatalkan oleh pengguna sebelum selesai.   |
|Gagal   |Penyerapan data mengalami kesalahan.         |
|Kegagalan  |Pengolahannya gagal.  |
|Belum dimulai   |Sumber data belum diserap datanya atau masih dalam mode draf.         |
|Sedang memproses  |Tugas atau proses sedang berlangsung.  |
|Me-refresh    |Penyerapan data sedang berlangsung. Anda dapat membatalkan operasi ini dengan memilih **berhenti menyegarkan** di kolom **tindakan**. Menghentikan refresh sumber data akan mengembalikannya ke status refresh terakhir.       |
|Dilewati  |Tugas atau proses dilewati. Satu atau beberapa proses hilir yang tugas ini tergantung padanya gagal atau dilewati.|
|Berhasil  |Tugas atau proses berhasil diselesaikan. Untuk sumber data, menunjukkan data telah berhasil dicerna jika suatu waktu disebutkan dalam **kolom** Refreshed.|
|Diantrekan | Pemrosesan diantri dan akan dimulai setelah semua tugas dan proses hulu selesai. Untuk informasi selengkapnya, lihat [Refresh proses](#refresh-processes).|

### <a name="refresh-processes"></a>Proses refresh

Refresh untuk tugas dan proses dijalankan sesuai dengan [jadwal yang](#schedule-tab) dikonfigurasi. 

|Proses  |KETERANGAN  |
|---------|---------|
|Aktivitas  |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada proses penggabungan. Wawasan tergantung pada prosesnya.|
|Penautan analisis |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada segmen.  |
|Persiapan analisis |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada segmen.  |
|Persiapan data   |Tergantung pada penggabungan.   |
|Sumber Data   |Tidak tergantung pada proses lainnya. Kecocokan tergantung pada keberhasilan penyelesaian proses ini.  |
|Pengayaan   |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada proses penggabungan. |
|Tujuan ekspor |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada segmen.  |
|Wawasan |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada segmen.  |
|Kecerdasan   |Tergantung pada penggabungan.   |
|Cocokkan |Tergantung pada pemrosesan sumber data yang digunakan dalam definisi pencocokan.      |
|Pengukuran  |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada proses penggabungan.  |
|Penggabungan   |Tergantung pada penyelesaian proses kecocokan. Segmen, tindakan, pengayaan, pencarian, aktivitas, Prediksi, dan persiapan data tergantung pada keberhasilan penyelesaian proses ini.   |
|Profil   |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada proses penggabungan. |
|Pencarian   |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada proses penggabungan. |
|Segmen  |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada proses penggabungan. Wawasan tergantung pada prosesnya.|
|Sistem   |Tergantung pada penyelesaian proses kecocokan. Segmen, tindakan, pengayaan, pencarian, aktivitas, Prediksi, dan persiapan data tergantung pada keberhasilan penyelesaian proses ini.   |
|Pengguna  |Berjalan secara manual (penyegaran waktu tunggal). Tergantung pada entitas.  |

Pilih status proses untuk melihat detail kemajuan dari seluruh pekerjaan yang ada di dalamnya. Proses penyegaran di atas dapat membantu memahami apa yang dapat Anda lakukan untuk mengatasi tugas atau proses yang **Dilewati** atau Di **·** antrian.

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

Anda dapat mengubah bahasa dan format negara/kawasan pada tab **Umum**.

Customer Insights [mendukung banyak](/dynamics365/get-started/availability) bahasa. Aplikasi menggunakan preferensi bahasa Anda untuk menampilkan elemen seperti menu, teks label, dan pesan sistem dalam bahasa pilihan Anda.

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

   Operasi yang menggunakan [konsumsi data real-time](real-time-data-ingestion.md) berisi tombol dengan simbol teropong untuk melihat penggunaan API real-time. Pilih tombol untuk membuka panel samping berisi rincian penggunaan untuk penggunaan API real-time di lingkungan saat ini.   
   Gunakan kotak **Grup berdasarkan** di panel **penggunaan API Real-time** untuk memilih cara terbaik menyajikan interaksi real-time Anda. Anda dapat mengelompokkan data berdasarkan metode API, nama berkualifikasi entitas (entitas yang diserap), dibuat oleh (sumber aktivitas), hasil (keberhasilan atau kegagalan), atau kode kesalahan. Data tersedia dalam bentuk grafik riwayat dan sebagai tabel.

## <a name="security-tab"></a>tab Keamanan

Tab **Keamanan** memungkinkan Anda menautkan dan mengelola [Azure key vault](/azure/key-vault/general/basic-concepts) Anda sendiri ke lingkungan.
Key Vault khusus dapat digunakan untuk melakukan tahapan dan menggunakan rahasia di batas kepatuhan organisasi. Audiens dapat menggunakan rahasia di Azure Key Vault untuk [mengkonfigurasi sambungan](connections.md) ke sistem pihak ketiga.

Untuk informasi lebih lanjut, lihat [bawa Azure key vault Anda sendiri](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
