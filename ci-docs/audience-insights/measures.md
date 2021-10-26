---
title: Membuat dan mengelola ukuran
description: Menentukan ukuran untuk menganalisis dan mencerminkan kinerja bisnis Anda.
ms.date: 09/30/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 39acca78c022bc15ebc15dc80f21fe175da04d4d
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622974"
---
# <a name="define-and-manage-measures"></a>Menentukan dan mengelola ukuran

Ukuran membantu Anda untuk lebih memahami perilaku pelanggan dan kinerja bisnis. Mereka melihat nilai-nilai yang relevan dari [profil terpadu](data-unification.md). Misalnya, bisnis ingin melihat *total pengeluaran per pelanggan* untuk memahami riwayat pembelian pelanggan individual atau mengukur *total penjualan perusahaan* untuk memahami pendapatan tingkat agregat dalam seluruh bisnis.  

Ukuran dibuat menggunakan pembuat ukuran, platform kueri data dengan berbagai operator, dan pilihan pemetaan sederhana. Alat ini memungkinkan Anda memfilter data, mengelompokkan hasil, mendeteksi [jalur relasi entitas](relationships.md), dan mempratinjau output.

Gunakan pembuat ukuran untuk merencanakan aktivitas bisnis dengan mengkueri data pelanggan dan mengekstrak wawasan. Contohnya, membuat ukuran *total pengeluaran per pelanggan* dan *penghasilan total per pelanggan* membantu mengidentifikasi grup pelanggan dengan pengeluaran tinggi namun penghasilan yang tinggi. Anda dapat [membuat segmen](segments.md) untuk mendorong tindakan terbaik berikutnya. 

## <a name="build-your-own-measure-from-scratch"></a>Buat ukuran sendiri dari awal

Bagian ini akan memandu Anda membuat pengukuran baru dari awal. Anda dapat membuat pengukuran dengan atribut data dari entitas data yang telah diatur relasinya untuk terhubung dengan entitas profil pelanggan terpadu.

# <a name="individual-customers-b2c"></a>[Pelanggan perorangan (B2C)](#tab/b2c)

1. Di wawasan audiens, buka **Ukuran**.

1. Pilih **Baru** dan pilih **Bangun milik Anda sendiri**.

1. Pilih **Edit nama** dan berikan **Nama** untuk ukurannya. 

1. Di area konfigurasi, pilih fungsi agregasi dari menu dropdown **Pilih Fungsi**. Fungsi agresi mencakup: 
   - **Sum**
   - **Rata-rata**
   - **Count**
   - **Jumlah Unik**
   - **Max**
   - **Min**
   - **Pertama**: mengambil nilai pertama rekaman data
   - **Terakhir**: mengambil nilai terakhir yang ditambahkan ke rekaman data

   :::image type="content" source="media/measure-operators.png" alt-text="Operator untuk menghitung pengukuran.":::

1. Pilih **Tambah atribut** untuk memilih data yang diperlukan untuk membuat pengukuran ini.
   
   1. Pilih tab **atribut**. 
   1. Entitas data: Pilih entitas yang mencakup atribut yang ingin Anda ukur. 
   1. Atribut data: Pilih atribut yang ingin Anda gunakan di fungsi agresi untuk menghitung ukuran. Anda hanya dapat memilih satu atribut setiap kali.
   1. Anda juga dapat memilih atribut data dari ukuran yang ada dengan memilih tab **Ukuran**. Atau, Anda dapat mencari entitas atau nama ukuran. 
   1. Pilih **Tambah** untuk menambahkan atribut yang dipilih ke ukuran.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Pilih atribut untuk digunakan dalam penghitungan.":::

1. Untuk membuat ukuran yang lebih kompleks, Anda dapat menambahkan lebih banyak atribut atau menggunakan operator hitung pada fungsi pengukuran Anda.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Buat pengukuran yang kompleks dengan operator hitung.":::

1. Untuk menambahkan filter, pilih **Filter** pada area konfigurasi. 
  
   1. Di bagian **Tambah atribut** pada panel **Filter**, pilih atribut yang akan digunakan untuk membuat filter.
   1. Atur operator filter untuk menentukan filter untuk setiap atribut yang dipilih.
   1. Pilih **Terapkan** untuk menambahkan filter ke ukuran.

1. Untuk menambahkan dimensi, pilih **Dimensi** pada area konfigurasi. Dimensi akan ditampilkan sebagai kolom dalam entitas output pengukuran.
 
   1. Pilih **Edit dimensi** untuk menambahkan atribut data untuk mengelompokkan nilai ukuran. Misalnya, kota atau jenis kelamin. Secara default, dimensi *CustomerID* dipilih untuk membuat *ukuran tingkat pelanggan*. Anda dapat menghilangkan dimensi default jika ingin membuat *ukuran tingkat bisnis*.
   1. Pilih **Selesai** untuk menambahkan dimensi ke ukuran.

1. Jika ada nilai pada data yang harus ganti dengan bilangan bulat, pilih **Aturan**. Konfigurasikan aturan dan pastikan Anda hanya memilih bilangan cacah sebagai pengganti. Contohnya, ganti *nihil* dengan *0*.

1. Jika ada beberapa jalur antara entitas data yang Anda petakan dan entitas *Pelanggan*, Anda harus memilih salah satu jalur relasi [entitas yang diidentifikasi](relationships.md). Hasil ukuran dapat bervariasi, tergantung pada jalur yang dipilih. 
   
   1. Pilih **Jalur relasi** dan pilih jalur entitas yang harus digunakan untuk mengidentifikasi ukuran Anda. Jika hanya ada satu jalur ke entitas *Pelanggan*, kontrol ini tidak akan ditampilkan.
   1. Pilih **Selesai** untuk menerapkan pilihan Anda. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Pilih jalur entitas untuk ukuran.":::

1. Untuk menambahkan perhitungan lainnya untuk pengukuran, pilih **Penghitungan baru**. Anda hanya dapat menggunakan entitas pada jalur entitas yang sama untuk perhitungan baru. Perhitungan lainnya akan ditampilkan sebagai kolom baru dalam entitas output pengukuran.

1. Pilih **...** pada penghitungan untuk **membuat duplikat**, **Mengganti Nama**, atau **Menghapus perhitungan** dari pengukuran.

1. Di area **Pratinjau**, Anda akan melihat skema data dari entitas output pengukuran, termasuk filter dan dimensi. Pratinjau merespons secara dinamis terhadap perubahan dalam konfigurasi.

1. Pilih **Jalankan** untuk menghitung hasil pengukuran yang dikonfigurasi. Pilih **Simpan dan tutup** jika Anda ingin menyimpan konfigurasi saat ini dan menjalankan pengukuran nanti.

1. Buka **Ukuran** untuk melihat ukuran yang baru dibuat dalam daftar.

# <a name="business-accounts-b2b"></a>[Akun bisnis (B2B)](#tab/b2b)

1. Di wawasan audiens, buka **Ukuran**.

1. Pilih **Baru** dan pilih **Bangun milik Anda sendiri**.

1. Pilih **Edit nama** dan berikan **Nama** untuk ukurannya. 

1. Di area konfigurasi, pilih fungsi agregasi dari menu dropdown **Pilih Fungsi**. Fungsi agresi mencakup: 
   - **Sum**
   - **Rata-rata**
   - **Count**
   - **Jumlah Unik**
   - **Max**
   - **Min**
   - **Pertama**: mengambil nilai pertama rekaman data
   - **Terakhir**: mengambil nilai terakhir yang ditambahkan ke rekaman data

   :::image type="content" source="media/measure-operators.png" alt-text="Operator untuk menghitung pengukuran.":::

1. Pilih **Tambah atribut** untuk memilih data yang diperlukan untuk membuat pengukuran ini.
   
   1. Pilih tab **atribut**. 
   1. Entitas data: Pilih entitas yang mencakup atribut yang ingin Anda ukur. 
   1. Atribut data: Pilih atribut yang ingin Anda gunakan di fungsi agresi untuk menghitung ukuran. Anda hanya dapat memilih satu atribut setiap kali.
   1. Anda juga dapat memilih atribut data dari ukuran yang ada dengan memilih tab **Ukuran**. Atau, Anda dapat mencari entitas atau nama ukuran. 
   1. Pilih **Tambah** untuk menambahkan atribut yang dipilih ke ukuran.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Pilih atribut untuk digunakan dalam penghitungan.":::

1. Untuk membuat ukuran yang lebih kompleks, Anda dapat menambahkan lebih banyak atribut atau menggunakan operator hitung pada fungsi pengukuran Anda.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Buat pengukuran yang kompleks dengan operator hitung.":::

1. Untuk menambahkan filter, pilih **Filter** pada area konfigurasi. 
  
   1. Di bagian **Tambah atribut** pada panel **Filter**, pilih atribut yang akan digunakan untuk membuat filter.
   1. Atur operator filter untuk menentukan filter untuk setiap atribut yang dipilih.
   1. Pilih **Terapkan** untuk menambahkan filter ke ukuran.

1. Untuk menambahkan dimensi, pilih **Dimensi** pada area konfigurasi. Dimensi akan ditampilkan sebagai kolom dalam entitas output pengukuran.
 
   1. Pilih **Edit dimensi** untuk menambahkan atribut data untuk mengelompokkan nilai ukuran. Misalnya, kota atau jenis kelamin. Secara default, dimensi *CustomerID* dipilih untuk membuat *ukuran tingkat pelanggan*. Anda dapat menghilangkan dimensi default jika ingin membuat *ukuran tingkat bisnis*.
   1. Pilih **Selesai** untuk menambahkan dimensi ke ukuran.

1. Jika ada nilai pada data yang harus ganti dengan bilangan bulat, pilih **Aturan**. Konfigurasikan aturan dan pastikan Anda hanya memilih bilangan cacah sebagai pengganti. Contohnya, ganti *nihil* dengan *0*.

1. Anda dapat menggunakan tombol **Roll up sub-akun** jika Anda [menggunakan akun dengan hierarki](relationships.md#set-up-account-hierarchies).
   - Jika diatur ke **Tidak Aktif**, maka ukuran dihitung untuk setiap akun. Setiap akun memiliki hasil.
   - Jika diatur ke **Aktif**, pilih **Edit** untuk memilih hierarki akun sesuai hierarki yang diserap. Pengukuran hanya akan menghasilkan satu hasil karena digabung dengan sub-akun.

1. Jika ada beberapa jalur antara entitas data yang Anda petakan dan entitas *Pelanggan*, Anda harus memilih salah satu jalur relasi [entitas yang diidentifikasi](relationships.md). Hasil ukuran dapat bervariasi, tergantung pada jalur yang dipilih. 
   
   1. Pilih **Jalur relasi** dan pilih jalur entitas yang harus digunakan untuk mengidentifikasi ukuran Anda. Jika hanya ada satu jalur ke entitas *Pelanggan*, kontrol ini tidak akan ditampilkan.
   1. Pilih **Selesai** untuk menerapkan pilihan Anda. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Pilih jalur entitas untuk ukuran.":::

1. Pilih **...** pada penghitungan untuk **membuat duplikat**, **Mengganti Nama**, atau **Menghapus perhitungan** dari pengukuran.

1. Di area **Pratinjau**, Anda akan melihat skema data dari entitas output pengukuran, termasuk filter dan dimensi. Pratinjau merespons secara dinamis terhadap perubahan dalam konfigurasi.

1. Pilih **Jalankan** untuk menghitung hasil pengukuran yang dikonfigurasi. Pilih **Simpan dan tutup** jika Anda ingin menyimpan konfigurasi saat ini dan menjalankan pengukuran nanti.

1. Buka **Ukuran** untuk melihat ukuran yang baru dibuat dalam daftar.

---

## <a name="use-a-template-to-build-a-measure"></a>Gunakan templat untuk menyusun pengukuran

Anda dapat menggunakan templat yang sudah ditentukan sebelumnya dari langkah-langkah yang umum digunakan untuk membuatnya. Deskripsi terperinci tentang templat dan pengalaman terpandu membantu Anda mengukur pembuatan yang efisien. Templat dibuat berdasarkan data yang dipetakan dari entitas *Aktivitas Terpadu*. Jadi pastikan Anda telah mengonfigurasi [aktivitas pelanggan](activities.md) sebelum membuat ukuran dari templat.

# <a name="individual-customers-b2c"></a>[Pelanggan perorangan (B2C)](#tab/b2c)

Anda dapat menggunakan templat yang sudah ditentukan sebelumnya dari langkah-langkah yang umum digunakan untuk membuatnya. Deskripsi terperinci tentang templat dan pengalaman terpandu membantu Anda mengukur pembuatan yang efisien. Templat dibuat berdasarkan data yang dipetakan dari entitas *Aktivitas Terpadu*. Jadi pastikan Anda telah mengonfigurasi [aktivitas pelanggan](activities.md) sebelum membuat ukuran dari templat.

Template ukuran yang tersedia: 
- Nilai transaksi rata-rata (ATV)
- Nilai transaksi total
- Pendapatan rata-rata harian
- Pendapatan rata-rata tahunan
- Jumlah transaksi
- Poin loyalitas yang diperoleh
- Poin loyalitas yang ditukarkan
- Saldo poin loyalitas
- Rentang periode aktif pelanggan aktif
- Durasi keanggotaan loyalitas
- Waktu sejak pembelian terakhir

Prosedur berikut ini menguraikan langkah-langkah untuk menyusun ukuran baru menggunakan templat.

1. Di wawasan audiens, buka **Ukuran**.

1. Pilih **Baru** dan pilih **pilih template**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Cuplikan layar menu dropdown saat membuat pengukuran baru dengan sorotan di template.":::

1. Temukan templat yang sesuai dengan kebutuhan Anda dan pilih **Pilih templat**.

1. Tinjau data yang diperlukan dan pilih **Mulai** jika Anda memiliki semua data yang ada.

1. Di panel **Edit nama**, atur nama untuk ukuran Anda dan entitas output. 

1. Pilih **Selesai**.

1. Di bagian **Atur periode waktu**, tentukan jangka waktu data yang akan digunakan. Pilih jika Anda menginginkan ukuran baru mencakup seluruh rangkaian data dengan memilih **Sepanjang waktu**, atau jika Anda ingin agar pengukuran fokus pada **periode waktu Tertentu**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Cuplikan layar memperlihatkan bagian periode waktu saat mengonfigurasi ukuran dari templat.":::

1. Di bagian berikutnya, pilih **Tambahkan data** untuk memilih aktivitas dan memetakan data terkait dari entitas *Aktivitas Terpadu* Anda.

    1. Langkah 1 dari 2: Di bawah **Tipe aktivitas**, pilih tipe entitas yang ingin Anda gunakan. Untuk **Aktivitas**, pilih entitas yang ingin Anda petakan.
    1. Langkah 2 dari 2: Pilih atribut dari entitas *Aktivitas Terpadu* untuk komponen yang diperlukan oleh rumus. Misalnya, untuk nilai transaksi rata-rata, itu adalah atribut yang mewakili nilai Transaksi. Untuk **Cap waktu Aktivitas**, pilih atribut dari entitas Aktivitas Terpadu yang menunjukkan tanggal dan waktu aktivitas.
   
1. Setelah pemetaan data berhasil, Anda dapat melihat status sebagai **Selesai** dan nama aktivitas dan atribut yang dipetakan.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Cuplikan layar konfigurasi templat ukuran yang selesai.":::

1. Sekarang Anda dapat memilih **Jalankan** untuk menghitung hasil pengukuran. Untuk memperbaikinya nanti, pilih **Simpan draf**.

# <a name="business-accounts-b2b"></a>[Akun bisnis (B2B)](#tab/b2b)

Fitur ini hanya tersedia untuk langkah-langkah yang dibuat di lingkungan dengan pelanggan individual sebagai target audiens.

---

## <a name="manage-your-measures"></a>Kelola ukuran Anda

Anda dapat menemukan daftar ukuran di halaman **Ukuran**.

Anda akan menemukan informasi tentang jenis pengukuran, pembuat, tanggal pembuatan, status, dan status. Bila Anda memilih ukuran dari daftar, Anda dapat mempratinjau output dan mengunduh file CSV.

Untuk me-refresh semua ukuran Anda pada waktu yang sama, pilih **Segarkan semua** tanpa memilih ukuran tertentu.

> [!div class="mx-imgBorder"]
> ![Tindakan untuk mengelola ukuran tunggal.](media/measure-actions.png "Tindakan untuk mengelola ukuran tunggal.")

Pilih ukuran dari daftar untuk pilihan berikut:

- Pilih nama ukuran untuk melihat rinciannya.
- **Edit** konfigurasi ukuran.
- **segarkan** pengukuran berdasarkan data terbaru.
- **Ubah nama** ukuran.
- **Hapus** ukuran.
- **Aktifkan** atau **Nonaktifkan**. Ukuran yang tidak aktif tidak akan di-refresh selama [refresh terjadwal](system.md#schedule-tab).

> [!TIP]
> Ada [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies). Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan. Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda akan menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, serta semua kesalahan dan peringatan yang terkait dengan tugas.

## <a name="next-step"></a>Langkah selanjutnya

Anda dapat menggunakan langkah-langkah yang ada untuk membuat [segmen pelanggan](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
