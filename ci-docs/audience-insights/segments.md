---
title: Membuat dan mengelola segmen
description: Buat segmen pelanggan untuk mengelompokkan mereka berdasarkan berbagai atribut.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406087"
---
# <a name="create-and-manage-segments"></a>Membuat dan mengelola segmen

Segmen memungkinkan Anda mengelompokkan pelanggan berdasarkan atribut demografi, transaksional, atau perilaku. Anda dapat menggunakan segmen untuk menargetkan kampanye promosi, aktivitas penjualan, dan tindakan dukungan pelanggan untuk mencapai sasaran bisnis Anda.

Anda dapat menentukan filter kompleks di sekitar entitas profil pelanggan dan entitas terkait. Setiap segmen, setelah pemrosesan, membuat kumpulan rekaman pelanggan yang dapat Anda ekspor dan lakukan tindakan padanya. Beberapa [batas Layanan](service-limits.md) berlaku.

Kecuali jika dinyatakan lain, semua segmen adalah **segmen dinamis**, yang diperbarui pada jadwal berulang.

Contoh berikut menjelaskan kemampuan segmentasi. Kami telah mendefinisikan segmen untuk pelanggan yang memesan setidaknya $500 barang di 90 hari terakhir *dan* yang terlibat dalam panggilan layanan pelanggan yang dieskalasi.

> [!div class="mx-imgBorder"]
> ![Beberapa grup](media/segmentation-group1-2.png "Beberapa grup")

## <a name="create-a-new-segment"></a>Buat segmen baru

Segmen dikelola pada halaman **segmen**.

1. Di wawasan audiens, buka halaman **segmen**.

2. Pilih **Baru** > **segmen kosong**.

3. Di panel **segmen baru**, pilih jenis segmen dan berikan **nama**.

   Atau, berikan nama tampilan, dan deskripsi yang membantu mengidentifikasi segmen.

4. Pilih **berikutnya** untuk mengakses halaman **pembuat segmen** dengan menentukan grup. Grup adalah satu set pelanggan.

5. Pilih entitas yang mencakup atribut yang ingin Anda segmentasikan.

6. Pilih atribut untuk segmentasi. Atribut ini dapat memiliki salah satu dari empat jenis nilai: numerik, string, tanggal, atau Boolean.

7. Pilih operator dan nilai untuk atribut dipilih.

   > [!div class="mx-imgBorder"]
   > ![Filter grup kustom](media/customer-group-numbers.png "Filter grup pelanggan")

   |Nomor |Definisi  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operator         |
   |4    |Nilai         |

8. Jika entitas terhubung ke entitas pelanggan terpadu melalui [Relasi](relationships.md), Anda harus menentukan jalur relasi untuk membuat segmen valid. Tambahkan entitas dari jalur relasi hingga Anda dapat memilih entitas **pelanggan: CustomerInsights** dari dropdown. Selanjutnya, pilih **semua rekaman** untuk setiap kondisi.

   > [!div class="mx-imgBorder"]
   > ![Jalur relasi selama pembuatan segmen](media/segments-multiple-relationships.png "Jalur relasi selama pembuatan segmen")

9. Pilih **Simpan** untuk menyimpan segmen Anda. Segmen Anda akan disimpan dan diproses jika semua persyaratan divalidasi. Jika tidak, maka akan disimpan sebagai draf.

10. Untuk kembali ke halaman **Segmen**, pilih **kembali ke segmen**.

## <a name="manage-existing-segments"></a>Mengelola segmen yang ada

Di halaman **segmen**, Anda dapat melihat semua segmen tersimpan dan mengelolanya.

Setiap segmen diwakili oleh baris yang berisi informasi tambahan tentang segmen.

Anda dapat mengurutkan segmen di kolom dengan memilih heading kolom.

Gunakan kotak **Cari** di sudut kanan atas untuk memfilter segmen.

> [!div class="mx-imgBorder"]
> ![Pilihan untuk mengelola segmen yang ada](media/segments-selected-segment.png "Pilihan untuk mengelola segmen yang ada")

Tindakan berikut tersedia bila Anda memilih segmen:

- **Lihat** rincian segmen, termasuk tren jumlah anggota yang menampilkan pratinjau anggota segmen.
- **Edit** segmen untuk mengubah properti.
- **Refresh** segmen untuk menyertakan data terbaru.
- **Aktifkan** atau **Nonaktifkan** segmen. Segmen memiliki dua kemungkinan status - aktif atau tidak aktif. Status ini berguna saat mengedit segmen. Untuk segmen yang tidak aktif, definisi segmen ada, namun tidak berisi pelanggan. Bila Anda mengaktifkan segmen, status akan berubah dari ' tidak aktif ' menjadi ' aktif ' dan mulai mencari Pelanggan yang cocok dengan definisi segmen. Jika [penyegaran terjadwal](system.md#schedule-tab) dikonfigurasi, segmen yang tidak aktif memiliki **status** yang didaftarkan sebagai **dilewati**, yang menunjukkan bahwa penyegaran bahkan tidak dicoba. Bila segmen aktif diaktifkan, segmen akan diperbarui dan akan disertakan dalam penyegaran terjadwal.
  Atau, Anda dapat menggunakan fungsi **jadwalkan nanti** dalam menu menurun **Aktifkan/Nonaktifkan** untuk menentukan tanggal dan waktu di masa mendatang untuk pengaktifan dan penonaktifan segmen tertentu.
- **Ganti nama** segmen.
- **Unduh** Daftar anggota sebagai File .CSV.
- Pilihan **Tambahkan ke** akan mengirimkan daftar id pelanggan di segmen untuk diproses di aplikasi lain.
- **Hapus** segmen.

## <a name="refresh-segments"></a>Refresh Segmen

Anda dapat menyegarkan semua segmen sekaligus dengan memilih **Segarkan semua** pada halaman **segmen** atau Anda dapat menyegarkan satu atau beberapa segmen saat memilih dan memilih **Segarkan** dari pilihan. Atau, Anda dapat mengkonfigurasi refresh berulang pada **Admin** > **sistem** > **jadwal**.

> [!TIP]
> Ada [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies). Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan. Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.

## <a name="download-and-export-segments"></a>Unduh dan ekspor Segmen

Anda dapat mengunduh segmen ke file CSV atau mengekspornya ke Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Mengunduh segmen ke file CSV

1. Di wawasan audiens, buka halaman **segmen**.

2. Pilih elipsis (...) dalam ubin segmen tertentu.

3. Pilih **Unduh sebagai CSV** dari daftar tarik-turun tindakan.

### <a name="export-segments-to-dynamics-365-sales"></a>Ekspor segmen ke Dynamics 365 Sales

Sebelum mengekspor segmen ke Dynamics 365 Sales, admin harus [membuat tujuan ekspor](export-destinations.md) untuk Dynamics 365 Sales.

1. Di wawasan audiens, buka halaman **segmen**.

2. Pilih elipsis (...) dalam ubin segmen tertentu.

3. Pilih **Tambah ke** dari daftar drop-down tindakan, lalu pilih tujuan ekspor yang akan Anda kirimi data.

## <a name="draft-mode-for-segments"></a>Mode draf untuk segmen

Jika tidak semua persyaratan untuk memproses segmen terpenuhi, Anda dapat menyimpan segmen sebagai draf dan mengaksesnya dari halaman **segmen**.

Ini akan disimpan sebagai segmen yang tidak aktif, dan tidak dapat diaktifkan hingga berlaku.

## <a name="add-more-conditions-to-a-group"></a>Menambah kondisi lainnya ke grup

Untuk menambahkan kondisi ke grup, Anda dapat menggunakan dua operator logika:

- Operator **AND**: kedua kondisi harus dipenuhi sebagai bagian dari proses segmentasi. Pilihan ini paling berguna saat Anda menentukan kondisi di seluruh entitas yang berbeda.

- Operator **OR**: Salah satu dari kondisi harus dipenuhi sebagai bagian dari proses segmentasi. Pilihan ini paling berguna saat Anda menentukan beberapa kondisi untuk entitas yang sama.

   > [!div class="mx-imgBorder"]
   > ![Operator OR bila kedua kondisi harus dipenuhi](media/segmentation-either-condition.png "Operator OR bila kedua kondisi harus dipenuhi")

Saat ini mungkin untuk mengurung operator **OR** di bawah operator **AND**, namun tidak sebaliknya.

## <a name="combine-multiple-groups"></a>Menggabungkan beberapa grup

Setiap grup menghasilkan himpunan pelanggan tertentu. Anda dapat menggabungkan grup ini untuk menyertakan Pelanggan yang diperlukan untuk kasus bisnis Anda.

1. Di wawasan audiens, buka halaman **segmen**, lalu pilih segmen.

2. Pilih **Tambah Grup**.

   > [!div class="mx-imgBorder"]
   > ![Grup pelanggan Tambah grup](media/customer-group-add-group.png "Grup pelanggan Tambah grup")

3. Pilih salah satu operator rangkaian yang berikut: **Himpunan**, **Berpotongan**, atau **Kecuali**.

   > [!div class="mx-imgBorder"]
   > ![Grup pelanggan Tambah penyatuan](media/customer-group-union.png "Grup pelanggan Tambah penyatuan")

   Pilih himpunan operator untuk menentukan grup baru. Simpan grup berbeda untuk menentukan data apa yang akan dipertahankan:

   - **Semesta** menyatukan dua kelompok.

   - **Berpotongan** tumpang-tindih kedua grup. Hanya data yang *umum* untuk kedua grup yang dipertahankan dalam Grup Terpadu.

   - **Kecuali** menggabungkan dua grup. Hanya data dalam grup A yang *tidak umum* untuk data di Grup B yang dipertahankan.

## <a name="view-processing-history-and-segment-members"></a>Melihat riwayat pemrosesan dan anggota segmen

Anda dapat melihat data gabungan tentang segmen dengan meninjau detailnya.

Pada halaman **segmen**, pilih segmen yang ingin Anda tinjau.

Bagian atas halaman mencakup diagram tren yang memvisualkan perubahan dalam jumlah anggota. Arahkan kursor ke poin data untuk melihat jumlah anggota pada tanggal tertentu.

Anda dapat memperbarui jangka waktu visualisasi.

> [!div class="mx-imgBorder"]
> ![Rentang Waktu segmen](media/segment-time-range.png "Rentang Waktu segmen")

Bagian bawah berisi daftar anggota segmen.

> [!NOTE]
> Bidang yang muncul di daftar ini didasarkan pada atribut entitas segmen.
>
>Daftar ini adalah pratinjau anggota segmen yang cocok dan menampilkan rekaman 100 pertama segmen Anda sehingga Anda dapat dengan cepat mengevaluasinya dan meninjau definisinya jika diperlukan. Untuk melihat semua rekaman yang cocok, Anda harus [mengekspor segmen](export-destinations.md).

## <a name="quick-segments"></a>Segmen ringkas

Selain pembuat segmen, ada jalur lain untuk membuat segmen. Segmen ringkas memungkinkan Anda membuat segmen sederhana dengan satu operator dengan cepat dan dengan wawasan instan.

1. Pada halaman **segmen**, pilih **baru** > **Buat cepat dari**.

   - Pilih pilihan **profil** untuk membuat segmen yang didasarkan pada entitas pelanggan terpadu.
   - Pilih pilihan **tindakan** untuk membuat segmen di sekitar masing-masing jenis atribut Pelanggan yang sebelumnya Anda buat di halaman **Ukuran**.
   - Pilih **pilihan intelijen** untuk membuat segmen di sekitar salah satu entitas output yang dihasilkan menggunakan **prediksi** maupun kemampuan **model kustom**.

2. Di kotak dialog **segmen ringkas baru**, pilih atribut dari dropdown **bidang**.

3. Sistem akan memberikan beberapa wawasan tambahan yang membantu Anda membuat segmen pelanggan yang lebih baik.
   - Untuk bidang kategoris, kami akan menampilkan 10 hitungan pelanggan teratas. Pilih **nilai** dan pilih **tinjau**.

   - Untuk atribut numerik, sistem akan menampilkan nilai atribut yang berada di dalam persentil masing-masing pelanggan. Pilih **operator** dan **nilai**, lalu pilih **tinjau**.

4. Sistem akan memberi Anda **perkiraan ukuran segmen**. Anda dapat memilih apakah akan menghasilkan segmen yang telah Anda tetapkan, atau pertama-tama, mengunjungi kembali untuk mendapatkan ukuran segmen yang berbeda.

    > [!div class="mx-imgBorder"]
    > ![Nama dan estimasi untuk segmen cepat](media/quick-segment-name.png "Nama dan estimasi untuk segmen cepat")

5. Beri **nama** segmen Anda. Atau, berikan **nama tampilan**.

6. Klik **Simpan** untuk membuat segmen Anda.

7. Setelah segmen selesai diproses, Anda dapat melihatnya seperti segmen lain yang Anda buat.

Untuk skenario berikut, kami menyarankan menggunakan pembuat segmen daripada kemampuan segmen yang direkomendasikan:

- Membuat segmen dengan filter pada bidang kategoris di mana operator berbeda dengan operator **Is**
- Membuat segmen dengan filter pada bidang numerik di mana operator berbeda daripada operator **antara**, **lebih besar dari**, dan **kurang dari**
- Membuat segmen dengan filter pada bidang jenis tanggal

## <a name="next-steps"></a>Langkah-langkah berikutnya

[Ekspor segmen](export-destinations.md) dan jelajahi bagian [kartu pelanggan](customer-card-add-in.md) dan [konektor](export-power-bi.md) untuk mendapatkan wawasan tentang tingkat pelanggan.
