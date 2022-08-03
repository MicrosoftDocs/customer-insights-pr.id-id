---
title: Buat langkah-langkah dengan pembuat ukuran
description: Buat langkah-langkah dari awal untuk menganalisis metrik utama tentang bisnis Anda.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170853"
---
# <a name="create-measures-with-measure-builder"></a>Buat langkah-langkah dengan pembuat ukuran

Pembuat pengukuran memungkinkan Anda menentukan perhitungan menggunakan operator matematika, fungsi agregasi, dan filter. Tentukan pengukuran menggunakan atribut dari entitas yang terkait dengan entitas Klien *terpadu*.

Membuat langkah-langkah di lingkungan B-to-C dan B-to-B bekerja dengan cara yang sama. Namun, jika lingkungan [B-ke-B Anda menggunakan akun dengan hierarki](relationships.md#set-up-account-hierarchies), pilih apakah akan menggabungkan pengukuran di seluruh sub-akun terkait.

# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

Buat ukuran pada tingkat pelanggan individu (atribut pelanggan, ukuran pelanggan) atau pada tingkat bisnis / organisasi (ukuran bisnis). Atribut pelanggan dan ukuran pelanggan memungkinkan Anda melacak kinerja per pelanggan. Misalnya, total pembelanjaan oleh setiap pelanggan. Ukuran bisnis melacak kinerja per bisnis. Misalnya, total pendapatan oleh perusahaan.

- Atribut pelanggan: Menghasilkan output sebagai atribut baru, yang disimpan sebagai kolom baru di entitas yang dihasilkan sistem bernama *Customer_Measure*. Saat me-refresh atribut pelanggan, semua atribut pelanggan lainnya di entitas Customer_Measure *di-refresh* secara bersamaan. Selain itu, atribut pelanggan ditampilkan di kartu profil pelanggan. Setelah dijalankan atau disimpan, Anda tidak dapat mengubah atribut pelanggan ke ukuran pelanggan.

- Ukuran pelanggan: Menghasilkan output sebagai entitasnya sendiri dan Anda tidak dapat mengubahnya ke atribut pelanggan setelah dijalankan atau disimpan. Tindakan pelanggan tidak ditampilkan di kartu profil pelanggan.

- Ukuran bisnis: Menghasilkan output sebagai entitasnya sendiri dan ditampilkan di halaman beranda lingkungan Customer Insights Anda.

1. Pergi ke **Tindakan**.

1. Pilih **Baru** > **buat milik Anda sendiri**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Layar konfigurasi kosong untuk pengukuran B-to-C." lightbox="media/measure-b2c.png":::

1. Pilih **Edit detail** di samping Pengukuran tanpa judul. Berikan nama untuk ukuran tersebut. Secara opsional, tambahkan [tag](work-with-tags-columns.md#manage-tags) ke pengukuran.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Kotak dialog Edit detail.":::

1. Pilih **Selesai**.

1. Untuk melacak performa tingkat bisnis, alihkan **Jenis pengukuran** ke **tingkat** Bisnis. **Tingkat** pelanggan dipilih secara default. **Tingkat** pelanggan secara otomatis menambahkan *atribut CustomerId* ke Dimensi sementara **tingkat** Bisnis secara otomatis menghapusnya.

1. Di area konfigurasi, pilih fungsi agregasi dari **menu tarik-turun Pilih fungsi**. Fungsi agresi mencakup:
   - **Sum**
   - **Rata-rata**
   - **Count**
   - **Jumlah Unik**
   - **Max**
   - **Min**
   - **Pertama**: mengambil nilai pertama rekaman data
   - **Terakhir**: mengambil nilai terakhir yang ditambahkan ke rekaman data
   - **ArgMax**: menemukan catatan data yang memberikan nilai maksimum dari fungsi target
   - **ArgMin**: menemukan catatan data yang memberikan nilai minimum dari fungsi target

1. Pilih **Tambahkan atribut** untuk memilih data untuk membuat pengukuran ini.

   1. Pilih tab **atribut**.
   1. Entitas data: Pilih entitas yang mencakup atribut yang ingin Anda ukur.
   1. Atribut data: Pilih atribut yang ingin Anda gunakan di fungsi agresi untuk menghitung ukuran. Anda hanya dapat memilih satu atribut setiap kali.
   1. Secara opsional, pilih atribut data dari pengukuran yang ada dengan memilih tab **Tindakan**, atau cari entitas atau nama pengukuran.
   1. Pilih **Tambahkan**.

1. Untuk membangun ukuran yang lebih kompleks, tambahkan lebih banyak atribut atau gunakan operator matematika pada fungsi pengukuran Anda.

1. Untuk menambahkan filter, pilih **Filter** pada area konfigurasi. Menerapkan filter hanya akan menggunakan rekaman yang cocok dengan filter untuk menghitung pengukuran.
  
   1. Di bagian **Tambah atribut** pada panel **Filter**, pilih atribut yang akan digunakan untuk membuat filter.
   1. Atur operator filter untuk menentukan filter untuk setiap atribut yang dipilih.
   1. Pilih **Terapkan**.

1. Pilih **Dimensi** untuk memilih bidang lainnya untuk ditambahkan sebagai kolom ke entitas output pengukuran.

   1. Pilih **Edit dimensi** untuk menambahkan atribut data untuk mengelompokkan nilai ukuran. Misalnya, kota atau jenis kelamin.
      > [!TIP]
      > Jika Anda memilih **Tingkat pelanggan** sebagai **jenis** Pengukuran, *atribut CustomerId* sudah ditambahkan. Jika Anda menghapus atribut, **Jenis** pengukuran akan beralih ke **Tingkat bisnis**.
   1. Pilih **Selesai**.

1. Jika ada nilai dalam data Anda yang harus diganti dengan bilangan bulat, pilih **Aturan**. Konfigurasikan aturan dan pastikan Anda hanya memilih bilangan cacah sebagai pengganti. Contohnya, ganti *nihil* dengan *0*.

1. Jika ada beberapa jalur antara entitas data yang Anda petakan dan *entitas Pelanggan*, pilih salah satu jalur hubungan entitas yang [diidentifikasi](relationships.md). Hasil ukuran dapat bervariasi, tergantung pada jalur yang dipilih.

   1. Pilih **Jalur relasi** dan pilih jalur entitas yang harus digunakan untuk mengidentifikasi ukuran Anda. Jika hanya ada satu jalur ke entitas *Pelanggan*, kontrol ini tidak akan ditampilkan.
   1. Pilih **Selesai**.

1. Untuk menambahkan perhitungan lainnya untuk pengukuran, pilih **Penghitungan baru**. Hanya gunakan entitas pada jalur entitas yang sama untuk perhitungan baru. Perhitungan lainnya akan ditampilkan sebagai kolom baru dalam entitas output pengukuran. Secara opsional, pilih **Edit nama** untuk membuat nama untuk perhitungan.

1. Pilih elipsis vertikal (&vellip;) pada perhitungan untuk **Menduplikasi** atau **Menghapus** perhitungan dari ukuran.

1. Di area **Pratinjau**, Anda akan melihat skema data dari entitas output pengukuran, termasuk filter dan dimensi. Pratinjau merespons secara dinamis terhadap perubahan dalam konfigurasi.

1. Pilih **Jalankan** untuk menghitung hasil pengukuran yang dikonfigurasi. Pilih **Simpan dan tutup** jika Anda ingin menyimpan konfigurasi saat ini dan menjalankan pengukuran nanti. Halaman **Pengukuran** ditampilkan.

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

Buat ukuran pada tingkat akun individu (ukuran pelanggan) atau pada tingkat semua akun (ukuran bisnis).

- Ukuran pelanggan: Menghasilkan output sebagai entitasnya sendiri. Tindakan pelanggan tidak ditampilkan di kartu profil pelanggan.

- Ukuran bisnis: Menghasilkan output sebagai entitasnya sendiri dan ditampilkan di halaman beranda lingkungan Customer Insights Anda.

1. Pergi ke **Tindakan**.

1. Pilih **baru**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Layar konfigurasi kosong untuk pengukuran B-ke-B.":::

1. Pilih **Edit detail** di samping Pengukuran tanpa judul. Berikan nama untuk ukuran tersebut. Secara opsional, tambahkan [tag](work-with-tags-columns.md#manage-tags) ke pengukuran. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Kotak dialog Edit detail.":::

1. Pilih **Selesai**.

1. Di area konfigurasi, pilih fungsi agregasi dari **menu tarik-turun Pilih fungsi**. Fungsi agresi mencakup:
   - **Sum**
   - **Rata-rata**
   - **Count**
   - **Jumlah Unik**
   - **Max**
   - **Min**
   - **Pertama**: mengambil nilai pertama rekaman data
   - **Terakhir**: mengambil nilai terakhir yang ditambahkan ke rekaman data

1. Pilih **Tambahkan atribut** untuk memilih data untuk membuat pengukuran ini.

   1. Pilih tab **atribut**.
   1. Entitas data: Pilih entitas yang mencakup atribut yang ingin Anda ukur.
   1. Atribut data: Pilih atribut yang ingin Anda gunakan di fungsi agresi untuk menghitung ukuran. Anda hanya dapat memilih satu atribut setiap kali.
   1. Secara opsional, pilih atribut data dari pengukuran yang ada dengan memilih tab **Tindakan**, atau cari entitas atau nama pengukuran.
   1. Pilih **Tambah** untuk menambahkan atribut yang dipilih ke ukuran.

1. Untuk membangun ukuran yang lebih kompleks, tambahkan lebih banyak atribut atau gunakan operator matematika pada fungsi pengukuran Anda.

1. Untuk menambahkan filter, pilih **Filter** pada area konfigurasi. Menerapkan filter hanya akan menggunakan rekaman yang cocok dengan filter untuk menghitung pengukuran.
  
   1. Di bagian **Tambah atribut** pada panel **Filter**, pilih atribut yang akan digunakan untuk membuat filter.
   1. Atur operator filter untuk menentukan filter untuk setiap atribut yang dipilih.
   1. Pilih **Terapkan** untuk menambahkan filter ke ukuran.

1. Pilih **Dimensi** untuk memilih bidang lainnya untuk ditambahkan sebagai kolom ke entitas output pengukuran.

   1. Pilih **Edit dimensi** untuk menambahkan atribut data untuk mengelompokkan nilai ukuran. Misalnya, kota atau jenis kelamin.
      > [!TIP]
      > Atribut *CustomerId* sudah ditambahkan yang menunjukkan bahwa ini adalah jenis pengukuran tingkat pelanggan. Jika Anda menghapus atribut, jenis pengukuran akan berubah ke tingkat bisnis.
   1. Pilih **Selesai** untuk menambahkan dimensi ke ukuran.

1. Jika ada nilai dalam data Anda yang harus diganti dengan bilangan bulat, pilih **Aturan**. Konfigurasikan aturan dan pastikan Anda hanya memilih bilangan cacah sebagai pengganti. Contohnya, ganti *nihil* dengan *0*.

1. Jika Anda [menggunakan akun dengan hierarki](relationships.md#set-up-account-hierarchies), tinjau **Menggulung sub-akun**.
   - Jika diatur ke **Tidak Aktif**, maka ukuran dihitung untuk setiap akun. Setiap akun mendapatkan hasilnya sendiri.
   - Jika diatur ke **Aktif**, pilih **Edit** untuk memilih hierarki akun sesuai hierarki yang diserap. Ukuran hanya akan menghasilkan satu hasil karena diagregasi dengan sub-akun.

1. Jika ada beberapa jalur antara entitas data yang Anda petakan dan *entitas Pelanggan*, pilih salah satu jalur hubungan entitas yang [diidentifikasi](relationships.md). Hasil ukuran dapat bervariasi, tergantung pada jalur yang dipilih.

   1. Pilih **Jalur relasi** dan pilih jalur entitas yang harus digunakan untuk mengidentifikasi ukuran Anda. Jika hanya ada satu jalur ke entitas *Pelanggan*, kontrol ini tidak akan ditampilkan.
   1. Pilih **Selesai** untuk menerapkan pilihan Anda.

1. Pilih elipsis vertikal (&vellip;) pada perhitungan untuk **Menduplikasi** atau **Menghapus** perhitungan dari ukuran.

1. Di area **Pratinjau**, Anda akan melihat skema data dari entitas output pengukuran, termasuk filter dan dimensi. Pratinjau merespons secara dinamis terhadap perubahan dalam konfigurasi.

1. Pilih **Jalankan** untuk menghitung hasil pengukuran yang dikonfigurasi. Pilih **Simpan dan tutup** jika Anda ingin menyimpan konfigurasi saat ini dan menjalankan pengukuran nanti. Halaman **Pengukuran** ditampilkan.

---

## <a name="next-step"></a>Langkah selanjutnya

Gunakan langkah-langkah yang ada untuk membuat [segmen](segments.md) pelanggan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
