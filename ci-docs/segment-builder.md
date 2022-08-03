---
title: Buat segmen kompleks dengan pembuat segmen
description: Gunakan pembuat segmen untuk membuat segmen pelanggan yang kompleks dengan mengelompokkannya berdasarkan berbagai atribut.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: cde373cd65e296675e1b3c92f3024e1093853842
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170639"
---
# <a name="create-complex-segments-with-segment-builder"></a>Buat segmen kompleks dengan pembuat segmen

Tentukan filter kompleks di sekitar entitas pelanggan terpadu dan entitas terkaitnya. Setiap segmen, setelah pemrosesan, membuat kumpulan rekaman pelanggan yang dapat Anda ekspor dan lakukan tindakan padanya.

> [!TIP]
> Segmen berdasarkan **pelanggan individual** secara otomatis mencakup informasi kontak yang tersedia untuk anggota segmen. Di lingkungan untuk **akun bisnis**, segmen didasarkan pada akun (perusahaan atau anak perusahaan). Untuk menyertakan informasi kontak dalam segmen, gunakan fungsi **atribut Proyek** dalam pembuat segmen. Pastikan sumber data kontak [dipetakan secara semantis ke entitas ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Pembuat segmen

Gambar berikut menjelaskan berbagai aspek dari pembuat segmen. Ini menunjukkan segmen yang menghasilkan grup pelanggan. Pelanggan memesan barang dalam waktu jangka waktu dan mengumpulkan poin hadiah atau menggunakan sejumlah uang tertentu.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elemen pembuat segmen." lightbox="media/segment-builder-overview.png":::

1. Menyusun segmen dengan aturan dan sub-aturan. Setiap aturan atau sub-aturan terdiri dari kondisi. Gabungkan kondisi dengan operator logis.

1. Pilih [jalur relasi](relationships.md) antara entitas yang berlaku untuk aturan. Jalur relasi menentukan atribut yang dapat digunakan dalam kondisi.

1. Mengelola aturan dan sub-aturan. Mengubah posisi aturan atau menghapusnya.

1. Tambah kondisi dan buat tingkat yang tepat untuk mengurung dengan menggunakan sub-aturan.

1. Terapkan rangkaian operasi ke aturan yang tersambung.

1. Gunakan panel atribut untuk menambahkan atribut entitas yang tersedia atau membuat kondisi berdasarkan atribut. Panel menampilkan daftar entitas dan atribut, berdasarkan jalur relasi yang dipilih, yang tersedia untuk aturan yang dipilih.

1. Tambahkan kondisi berdasarkan atribut ke aturan dan sub-aturan yang ada atau tambahkan ke aturan baru.

1. Batalkan dan kembalikan perubahan saat membangun segmen.

Contoh di atas menjelaskan kemampuan segmentasi. Kami telah mendefinisikan segmen untuk pelanggan yang membeli sekurangnya $500 barang secara online *dan* memiliki minat pada pengembangan perangkat lunak.

## <a name="create-a-new-segment-with-segment-builder"></a>Membuat segmen baru dengan pembuat segmen

1. Buka **Segmen**.

1. Pilih **Baru** > **buat milik Anda sendiri**. Pada halaman pembuat segmen, Anda menentukan atau menyusun aturan. Aturan terdiri dari satu atau beberapa kondisi yang menentukan rangkaian pelanggan.

1. Pilih **Edit detail** di samping Segmen tanpa judul. Berikan nama untuk segmen Anda dan perbarui **nama entitas Output** yang disarankan untuk segmen. Secara opsional, tambahkan deskripsi dan [tag](work-with-tags-columns.md#manage-tags) ke segmen.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Kotak dialog Edit detail.":::

1. Di bagian **Aturan1**, pilih atribut entitas yang ingin Anda filter pelanggannya. Ada dua cara untuk memilih atribut:
   - Tinjau daftar entitas dan atribut yang tersedia di panel **Tambah ke Aturan**, lalu pilih ikon **+** di sebelah atribut untuk menambahkan. Pilih jika Anda ingin menambahkan atribut ke aturan yang ada atau menggunakannya untuk membuat aturan baru.
   - Masukkan nama atribut di bagian aturan untuk melihat saran yang cocok.

1. Pilih operator untuk menentukan nilai yang cocok dari kondisi. Atribut dapat memiliki salah satu dari empat jenis data sebagai nilai: numerik, string, tanggal, atau Boolean. Tergantung pada jenis data atribut, operator lain tersedia untuk menentukan kondisi. Untuk segmen dengan akun bisnis, dua operator khusus tersedia untuk mencakup kemungkinan hierarki antara akun yang diserap. Gunakan operator *anak dari* dan *induk dari* untuk menyertakan akun terkait.

1. Pilih **Tambah kondisi** untuk menambahkan kondisi lainnya ke aturan. Untuk membuat aturan di dalam aturan saat ini, pilih **Tambah sub-aturan**.

1. Jika aturan menggunakan entitas lain selain *entitas Pelanggan*, pilih **Atur jalur** hubungan untuk memetakan entitas yang dipilih ke entitas pelanggan terpadu. Jika hanya ada satu jalur hubungan yang mungkin, sistem akan memilihnya secara otomatis. Jalur hubungan yang berbeda [dapat menghasilkan hasil yang](relationships.md#relationship-paths) berbeda. Setiap aturan dapat memiliki jalur relasi sendiri.

   :::image type="content" source="media/relationship-path.png" alt-text="Jalur relasi potensial saat membuat aturan berdasarkan entitas yang dipetakan ke entitas pelanggan terpadu.":::

1. Jika Anda memiliki beberapa kondisi dalam aturan, pilih operator logis mana yang menghubungkannya.  
   - Operator **AND**: Semua kondisi harus dipenuhi untuk mencakup rekaman dalam segmen. Gunakan opsi ini saat Anda menentukan kondisi di berbagai entitas.
   - Operator **OR**: Salah satu kondisi harus dipenuhi untuk mencakup rekaman dalam segmen. Gunakan opsi ini saat Anda menentukan beberapa kondisi untuk entitas yang sama.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Aturan dengan kondisi AND.":::

   Saat menggunakan operator OR, semua kondisi harus didasarkan pada entitas yang tercakup dalam jalur relasi.

1. Untuk membuat kumpulan catatan pelanggan yang berbeda, buat beberapa aturan. Untuk menyertakan pelanggan yang diperlukan untuk kasus bisnis Anda, gabungkan grup. Secara khusus, jika Anda tidak dapat menyertakan entitas dalam aturan karena jalur hubungan yang ditentukan, buat aturan baru untuk memilih atribut darinya.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Tambahkan aturan baru ke segmen, lalu pilih operator yang ditentukan.":::

   1. Pilih **Tambahkan aturan**.
   1. Pilih salah satu operator rangkaian: **Gabungan**, **Irisan**, atau **Lepas**.

      - **Semesta** menyatukan dua kelompok.
      - **Berpotongan** tumpang-tindih kedua grup. Hanya data yang *umum* untuk kedua grup yang tetap dalam Grup Terpadu.
      - **Kecuali** menggabungkan dua grup. Hanya data dalam grup A yang *tidak umum* pada data di grup B yang dipertahankan.

1. Secara default, entitas output akan secara otomatis berisi semua atribut profil pelanggan yang cocok dengan filter yang ditentukan. Jika segmen didasarkan pada entitas lain selain *entitas Pelanggan*, pilih **Atribut proyek** untuk menambahkan lebih banyak atribut dari entitas ini ke entitas output.

   > [!IMPORTANT]
   > Untuk segmen berdasarkan akun bisnis, detail satu atau beberapa kontak setiap akun dari *entitas ContactProfile* harus disertakan dalam segmen untuk memungkinkan segmen tersebut diaktifkan atau diekspor ke tujuan yang memerlukan informasi kontak. Untuk informasi lebih lanjut tentang entitas *ContactProfile*, lihat [pemetaan Semantis](semantic-mappings.md).
   > Output sampel untuk segmen berdasarkan akun bisnis dengan atribut kontak yang diproyeksikan dapat terlihat seperti ini:
   >
   > |ID  |Nama akun  |Pendapatan  |Nama kontak  | Peran Kontak|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100 K | [Abbie Moss, Ruth Soto]  | [CEO, manajer Pengadaan]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Contoh atribut yang diproyeksikan dipilih di panel sisi untuk ditambahkan ke entitas output.":::
  
   Contoh: Segmen didasarkan pada entitas yang berisi data pembelian, yang terkait dengan entitas *Pelanggan*. Segmen tersebut mencari semua pelanggan dari Spanyol yang membeli barang pada tahun berjalan. Anda dapat memilih untuk menambahkan atribut seperti harga barang, atau tanggal pembelian ke semua catatan pelanggan yang cocok di entitas output. Informasi ini mungkin berguna untuk menganalisis korelasi musiman terhadap total pengeluaran.

   > [!NOTE]
   > - **Atribut proyek** hanya berfungsi untuk entitas yang memiliki relasi satu ke banyak dengan entitas pelanggan. Misalnya, satu pelanggan dapat memiliki beberapa langganan.
   > - Jika atribut yang ingin Anda proyeksikan lebih dari satu lompatan dari entitas *Pelanggan*, sebagaimana ditentukan oleh relasi, atribut tersebut harus digunakan di setiap aturan kueri segmen yang Anda bentuk.
   > - Jika atribut yang ingin Anda proyeksikan hanya satu lompatan dari entitas *Pelanggan*, atribut tersebut tidak harus ada di setiap aturan kueri segmen yang Anda bentuk.
   > - **Atribut yang diproyeksikan** digunakan saat menggunakan operator yang ditentukan.

1. Pilih **Jalankan** untuk membuat segmen. Pilih **Simpan** jika Anda ingin mempertahankan konfigurasi saat ini dan menjalankan segmen nanti. Halaman **Segmen** ditampilkan.

### <a name="segment-builder-tips"></a>Kiat pembangun segmen

Saat membuat segmen menggunakan pembuat segmen, ingatlah tips berikut:

- Pembuat segmen tidak akan menyarankan nilai yang valid dari entitas saat mengatur operator untuk kondisi tersebut. Anda dapat membuka **Data** > **Entitas** dan mengunduh data entitas untuk melihat nilai yang tersedia.
- Kondisi berdasarkan tanggal memungkinkan Anda beralih antara tanggal tetap dan rentang tanggal mengambang.
- Jika Anda memiliki beberapa aturan untuk segmen, aturan yang sedang Anda edit memiliki garis biru vertikal di sebelahnya.
- Anda dapat memindahkan aturan dan kondisi ke tempat lain dalam definisi segmen. Pilih elipsis vertikal (&vellip;) di samping aturan atau kondisi dan pilih bagaimana dan di mana harus memindahkannya.
- Kontrol **Batalkan** dan **Kembalikan** di bilah perintah memungkinkan Anda membatalkan perubahan.
- Setelah membuat segmen, beberapa segmen memungkinkan Anda [melacak penggunaan segmen](segments.md#track-usage-of-a-segment) tersebut.

## <a name="next-steps"></a>Langkah berikutnya

[Ekspor segmen](export-destinations.md) dan jelajahi [integrasi Kartu Pelanggan](customer-card-add-in.md) untuk menggunakan segmen di aplikasi lain.

[!INCLUDE [footer-include](includes/footer-banner.md)]
