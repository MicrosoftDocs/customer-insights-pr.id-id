---
title: Laporan corong
description: Cara menggunakan laporan corong untuk memahami cara audiens membuat keputusan.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7c6b7b7285556f8a531ce9e29f0d1de162562be6fb43dd826a65fd9e00d87b30
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032259"
---
# <a name="create-and-manage-funnel-reports"></a>Membuat dan mengelola laporan corong

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Laporan corong mengumpulkan informasi tentang langkah-langkah yang terjadi selama beberapa perjalanan pelanggan melalui situs web atau aplikasi seluler Anda. Ini membantu Anda memahami proses kemajuan audiens dan mengidentifikasi titik mampir. Contohnya, Anda dapat menggunakan laporan corong untuk mengidentifikasi jalur yang diambil pelanggan Anda sebelum mereka melakukan pembelian. Laporan corong memberikan data untuk menginformasikan keputusan dan mengidentifikasi area untuk pengoptimalan dan peningkatan proses.

## <a name="create-a-funnel-report"></a>Membuat laporan corong

Untuk membuat laporan corong, tentukan langkah yang akan disertakan dan aktivitas untuk setiap langkah. Aktivitas adalah [aktivitas](glossary.md) yang menunjukkan perilaku pengguna. Laporan corong menampilkan jumlah pengguna yang menyelesaikan setiap langkah yang ditentukan. 

1. Buka **Corong**, lalu pilih **+Corong Baru** untuk memulai laporan corong.

1. Di **Editor Corong**, dalam **Langkah-Langkah**, pilih **+Tambah langkah**. 

1. Masukkan nama dalam  **judul Langkah**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Laporan corong baru.":::

1. Pilih **aktivitas**. Aktivitas merekam ketika pengguna melihat halaman (aktivitas **melihat**) atau berinteraksi dengan konten (aktivitas **tindakan)**.

1. Gunakan **kriteria langkah** untuk menentukan dimensi aktivitas. [Dimensi](dimensions.md) adalah atribut yang dapat mendeskripsikan, memfilter, atau mengelompokkan data.

1. Atau, Anda dapat mengkonfigurasi langkah corong multi-kondisi. Pilih **Tambah kondisi** untuk menentukan dimensi lainnya pada langkah. Kriteria tambahan harus menggunakan jenis aktivitas yang sama. Anda dapat memilih apakah beberapa kondisi terhubung dengan operator AND atau OR.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Editor corong yang menampilkan konfigurasi langkah dengan langkah multi-kondisi.":::

1. Pilih **Tambah langkah** hingga Anda menyelesaikan semua langkah yang diinginkan dalam laporan.

1. Pilih **Simpan**, namai laporan, lalu **Simpan** lagi. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Contoh: Laporan corong perusahaan Kopi Keempat

Skenario berikut memperagakan satu cara menggunakan laporan corong. Seorang analis di perusahaan Kopi Keempat ingin memahami pengaruh promosi terakhir pada tingkat langganan. Analis membuat laporan corong untuk mengidentifikasi aktivitas pelanggan. Proses dimulai ketika pelanggan tiba di halaman beranda perusahaan hingga mereka menggunakan kode promosi langganan. Para analisis membuat laporan corong dengan langkah-langkah berikut:

Langkah 1: Pelanggan yang tiba di laman beranda   
Langkah 2: Pelanggan yang melakukan pembelian   
Langkah 3: Pelanggan yang menggunakan kode promosi untuk mendapatkan diskon langganan   
Langkah 4: Pendaftaran langganan   

:::image type="content" source="media/funnel-report-example.png" alt-text="contoh laporan corong.":::
  
Corong ini memungkinkan Anda melihat jumlah pengguna yang menggunakan kode promosi setelah pembelian satu kali untuk mendaftar program langganan.

### <a name="configure-advanced-settings"></a>Mengonfigurasi pengaturan lanjutan 

Laporan corong memungkinkan Anda menentukan batas pada waktu yang diperlukan untuk menyelesaikan corong. Contohnya, Anda dapat mengatur waktu untuk menyelesaikan corong menjadi empat hari. Pengaturan ini hanya akan menghitung pendaftaran langganan yang berhasil dalam empat hari sejak pengguna mengunjungi beranda.

1. Buka **Corong** untuk membuka **pustaka Corong**.

1. Pilih nama untuk membuka laporan. 

1. Di panel **Editor Corong**, pilih **Pengaturan tingkat lanjut**. 

1. Atur Batasi waktu penyelesaian corong ke **Aktif**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Editor corong yang menampilkan pengaturan dan pilihan lanjutan untuk membatasi waktu untuk menyelesaikan corong.":::

1. Pilih waktu ketika corong harus telah selesai dalam daftar dropdown **Atur batas ke**.

1. Pilih **Simpan** untuk menerapkan perubahan.


## <a name="cross-channel-funnel-reports"></a>Laporan corong lintas saluran 

Wawasan keterlibatan juga dapat mengumpulkan data pelanggan perilaku pada aplikasi seluler Anda. Setelah aplikasi seluler anda diinstrumentasi dengan SDK wawasan keterlibatan atau [SDK Android](get-started-android.md) atau [SDK iOS](get-started-ios.md), Anda dapat membuat laporan corong antar-saluran. 

### <a name="create-a-cross-channel-funnel-report"></a>Buat laporan corong lintas saluran 

1. Ikuti langkah-langkah untuk [membuat laporan corong](#create-a-funnel-report).    

1. Untuk melacak interaksi pelanggan dengan merek Anda di situs web dan aplikasi seluler, atau beberapa situs web, gunakan switcher ruang kerja untuk membuat langkah-langkah corong dengan data dari ruang kerja lain. Di **Editor Corong**, dalam **Langkah-Langkah**, pilih ruang kerja yang akan diambil data untuk langkah corong Anda.

## <a name="manage-funnel-reports"></a>Kelola laporan corong

Anda dapat memeriksa laporan corong untuk menganalisis data, melacak kinerja, dan mengumpulkan wawasan.

> [!NOTE]
> - Laporan corong wawasan keterlibatan saat ini mendukung skenario dengan semua pengguna di corong anonim atau semua pengguna terotentikasi. 
> - Data historis dalam laporan corong tersedia untuk 30 hari terakhir.

### <a name="view-funnel-reports"></a>Lihat Laporan corong

1. Buka **Corong** untuk membuka **pustaka Corong**.
1. Pilih nama untuk membuka laporan.    

### <a name="see-the-data-collected-for-a-report"></a>Lihat data yang dikumpulkan untuk laporan   

Untuk melihat informasi tentang fase

- Arahkan ke langkah dalam laporan.

:::image type="content" source="media/funnel-step-data.png" alt-text="data corong.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Mengubah rentang tanggal untuk laporan corong

1. Buka **Corong** untuk membuka **pustaka Corong**.

1. Pilih nama untuk membuka laporan.

1. Buka **rentang waktu** dan pilih periode waktu baru dari daftar atau **Rentang tanggal tetap** untuk menentukan rentang tanggal.

## <a name="edit-or-delete-funnel-reports"></a>Mengedit atau menghapus laporan corong

Anda dapat mengubah nama laporan corong, menghapusnya, atau memodifikasi langkah-langkah dalam laporan.

### <a name="rename-or-delete-a-funnel-report"></a>Mengganti nama atau menghapus laporan corong

1. Buka **Corong** untuk membuka **pustaka Corong**. 

1. Pilih **Lainnya** di sebelah laporan yang akan diubah, lalu pilih **Edit nama** atau **Hapus**.

### <a name="edit-a-funnel-step"></a>Mengedit langkah corong  

1. Buka **Corong** untuk membuka **pustaka Corong**. 

1. Pilih nama untuk membuka laporan.

1. Pilih langkah yang ingin Anda edit.

1. Pilih **Edit**.

1. Di **Editor Corong**, perbarui informasi yang ingin Anda ubah.  

1. Pilih **Simpan**.

### <a name="reorder-a-funnel-step"></a>Urutkan ulang langkah corong

1. Buka **Corong** untuk membuka **pustaka Corong**. 

1. Pilih nama untuk membuka laporan.

1. Pilih langkah yang ingin Anda urutkan ulang.

1. Pilih **Pindahkan**, lalu Ke **Atas**, **Bawah**, Ke **puncak**, atau Ke **dasar**, untuk memindahkan langkah.

### <a name="delete-a-funnel-step"></a>Hapus langkah corong

1. Buka **Corong** untuk membuka **pustaka Corong**. 

1. Pilih nama untuk membuka laporan.

1. Pilih langkah yang ingin Anda hapus, kemudian pilih **Hapus**.

