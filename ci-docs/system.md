---
title: Lihat konfigurasi sistem
description: Pelajari tentang pengaturan sistem di Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2498814a3d2e6330124fb97c036b9b310bcf1f7a
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246251"
---
# <a name="view-system-configuration"></a>Lihat konfigurasi sistem

Lihat informasi sistem, status sistem, dan penggunaan API.

## <a name="view-api-usage"></a>Melihat penggunaan API

Lihat detail tentang penggunaan API real-time dan lihat peristiwa mana yang terjadi dalam jangka waktu tertentu.

1. Buka **Sistem** > **Admin** dan pilih tab **penggunaan** API.

1. **Pilih jangka waktu** untuk dilihat.

   Halaman **penggunaan** API berisi tiga bagian:

   - **Panggilan API** - diagram yang memvisualisasikan jumlah panggilan agregat ke API dalam jangka waktu yang dipilih.
   - **Transfer data** - diagram yang menunjukkan jumlah data yang ditransfer melalui API dalam jangka waktu yang dipilih.
   - **Operasi** - tabel dengan baris untuk setiap operasi API yang tersedia dan rincian tentang penggunaan operasi. Pilih nama operasi untuk masuk ke [referensi](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) API.

   Operasi yang menggunakan [penyerapan](real-time-data-ingestion.md) data real-time berisi simbol teropong untuk melihat penggunaan API real-time.

   1. Pilih teropong untuk membuka **panel penggunaan** API Real-time yang berisi detail penggunaan untuk operasi.
   1. **Pilih jangka waktu** untuk dilihat.
   1. Gunakan kotak Kelompokkan **menurut** untuk memilih cara terbaik menyajikan interaksi real-time Anda. Kelompokkan data berdasarkan Metode API, Nama yang memenuhi syarat entitas (entitas yang diserap), **Dibuat oleh** (sumber peristiwa), **Hasil** (keberhasilan atau kegagalan) atau **kode Kesalahan**.**·** **·** Data tersedia dalam bentuk grafik riwayat dan sebagai tabel.

## <a name="view-system-information"></a>Lihat informasi sistem

Lihat lingkungan nama tampilan, ID, wilayah, jenis, dan ID sesi.

1. Buka **Sistem** > **Admin** dan pilih tab **Tentang**.

1. Untuk melihat bahasa dan negara/kawasan, pilih tab **Umum**.

### <a name="update-preferred-language-or-countryregion"></a>Memperbarui bahasa atau negara/kawasan pilihan

Customer Insights [mendukung banyak bahasa](/dynamics365/get-started/availability). Aplikasi menggunakan preferensi bahasa Anda untuk menampilkan elemen seperti menu, teks label, dan pesan sistem dalam bahasa pilihan Anda.

Data dan informasi impor yang Anda masukkan secara manual tidak diterjemahkan.

1. Buka **Sistem** > **Admin** dan pilih tab **Umum**.

1. Untuk mengubah bahasa yang diinginkan, pilih **bahasa** dari menu pilihan.

1. Untuk mengubah pemformatan yang diinginkan untuk tanggal, waktu, dan angka, gunakan menu pilihan **format negara/kawasan**. Pratinjau pemformatan ditampilkan. Sistem secara otomatis menyarankan pilihan saat Anda memilih bahasa baru.

1. Pilih **Simpan**.

## <a name="view-system-status"></a>Lihat status sistem

Lacak kemajuan tugas, penyerapan data, ekspor data, dan beberapa proses produk penting lainnya. Tinjau informasi untuk memastikan kelengkapan tugas dan proses aktif Anda.

1. Buka **Sistem** > **Admin** dan pilih tab **Status**.

   Status dan informasi pemrosesan untuk berbagai proses ditampilkan. **Lihat Nama** tugas, **Status** eksekusi terbarunya, dan kapan **terakhir kali diperbarui**.

1. Untuk melihat detail dari beberapa eksekusi terakhir, pilih nama tugas atau proses.

1. Untuk melihat detail kemajuan tugas, pilih status. Panel **Detail** kemajuan ditampilkan.

   :::image type="content" source="media/system-progress-details.png" alt-text="Panel detail kemajuan sistem":::

1. Untuk menampilkan detail kemajuan untuk semua tugas, pilih **Seluruh alur kerja**.

### <a name="status-definitions"></a>Definisi status

Sistem menggunakan status berikut untuk tugas dan proses:

|Status  |Devinisi  |
|---------|---------|
|Dibatalkan |Tugas atau proses dibatalkan oleh pengguna sebelum selesai.   |
|Gagal   |Tugas atau proses mengalami kesalahan.         |
|Kegagalan  |Tugas atau proses telah gagal.  |
|Belum dimulai   |Sumber data belum ada data yang diserap atau tugas masih dalam mode draf.         |
|Sedang memproses  |Tugas atau proses sedang berlangsung.  |
|Me-refresh    |Tugas atau proses sedang berlangsung. Untuk membatalkan operasi ini, pilih **Menyegarkan** dan **Batalkan pekerjaan**. Menghentikan refresh tugas atau proses akan mengembalikannya ke status refresh terakhirnya.       |
|Dilewati  |Tugas atau proses dilewati. Satu atau beberapa proses hilir yang tugas ini tergantung padanya gagal atau dilewati.|
|Berhasil  |Tugas atau proses berhasil diselesaikan. Untuk sumber data, menunjukkan bahwa data telah berhasil diserap jika waktu disebutkan di **kolom Refresh**.|
|Dalam Antrean | Pemrosesan diantrekan dan akan dimulai setelah semua tugas dan proses hulu selesai. Untuk informasi selengkapnya, lihat [Merefresh proses](#refresh-processes).|

### <a name="refresh-processes"></a>Proses penyegaran

Refresh untuk tugas dan proses dijalankan sesuai dengan jadwal [yang](schedule-refresh.md) dikonfigurasi.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
