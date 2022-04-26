---
title: Buat segmen dengan pembuat segmen
description: Buat segmen pelanggan untuk mengelompokkan mereka berdasarkan berbagai atribut.
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
ms.openlocfilehash: 1a28289ecb740ab6cdfa603b2cd66376e7e8b576
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529589"
---
# <a name="create-segments"></a>Buat segmen

Tentukan filter kompleks di sekitar entitas pelanggan terpadu dan entitas terkaitnya. Setiap segmen, setelah pemrosesan, membuat kumpulan rekaman pelanggan yang dapat Anda ekspor dan lakukan tindakan padanya. Segmen dikelola pada halaman **segmen**. Anda dapat [membuat segmen baru](#create-a-new-segment) menggunakan pembuat segmen atau [membuat segmen cepat](#quick-segments) dari area lain dalam aplikasi.

> [!TIP]
> - Segmen singkat hanya didukung di lingkungan untuk **pelanggan individual**.
> - Segmen berdasarkan **pelanggan individual** secara otomatis mencakup informasi kontak yang tersedia untuk anggota segmen. Di lingkungan untuk **akun bisnis**, segmen didasarkan pada akun (perusahaan atau anak perusahaan). Untuk menyertakan informasi kontak dalam segmen, gunakan fungsi **atribut Proyek** dalam pembuat segmen. Pastikan sumber data kontak [dipetakan secara semantis ke entitas ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Pembuat segmen

Gambar berikut menjelaskan berbagai aspek dari pembuat segmen. Ini menunjukkan segmen yang menghasilkan grup pelanggan. Pelanggan memesan barang dalam waktu jangka waktu dan mengumpulkan poin hadiah atau menggunakan sejumlah uang tertentu.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elemen pembuat segmen." lightbox="media/segment-builder-overview.png":::

1. Menyusun segmen dengan aturan dan sub-aturan. Setiap aturan atau sub-aturan terdiri dari kondisi. Menggabungkan kondisi dengan operator logika

1. Pilih [jalur relasi](relationships.md) antara entitas yang berlaku untuk aturan. Jalur relasi menentukan atribut yang dapat digunakan dalam kondisi.

1. Mengelola aturan dan sub-aturan. Mengubah posisi aturan atau menghapusnya.

1. Tambah kondisi dan buat tingkat yang tepat untuk mengurung dengan menggunakan sub-aturan.

1. Terapkan rangkaian operasi ke aturan yang tersambung.

1. Gunakan panel atribut untuk menambahkan atribut entitas yang tersedia atau membuat kondisi berdasarkan atribut. Panel menampilkan daftar entitas dan atribut, berdasarkan jalur relasi yang dipilih, yang tersedia untuk aturan yang dipilih.

1. Tambahkan kondisi berdasarkan atribut ke aturan dan sub-aturan yang ada atau tambahkan ke aturan baru.

1. Batalkan dan kembalikan perubahan saat membangun segmen.

Contoh di atas menjelaskan kemampuan segmentasi. Kami telah mendefinisikan segmen untuk pelanggan yang membeli sekurangnya $500 barang secara online *dan* memiliki minat pada pengembangan perangkat lunak.

## <a name="create-a-new-segment"></a>Buat segmen baru

Tersedia beberapa cara untuk membuat segmen baru. Bagian ini menjelaskan cara membangun segmen Anda sendiri dari awal. Anda juga dapat membuat *segmen cepat* berdasarkan entitas yang ada atau menggunakan model Pembelajaran Mesin untuk mendapatkan *segmen yang disarankan*. Untuk informasi lebih lanjut, buka [Ikhtisar segmen](segments.md).

Saat membuat segmen, Anda dapat menyimpan draf. Pada tahapan draf, segmen disimpan sebagai segmen tidak aktif. Setelah menyelesaikan konfigurasi segmen, jalankan untuk mengaktifkan segmen. Anda juga dapat **Aktifkan** segmen dari halaman **Semua segmen**.

1. Buka halaman **Segmen**.

1. Pilih **Baru** > **buat milik Anda sendiri**.

1. Pada halaman pembuat segmen, Anda menentukan atau menyusun aturan. Aturan terdiri dari satu atau beberapa kondisi yang menentukan rangkaian pelanggan.

1. **Di bagian Aturan1**, pilih atribut entitas yang ingin Anda filter oleh pelanggan. Ada dua cara untuk memilih atribut:
   - Tinjau daftar entitas dan atribut yang tersedia di panel **Tambah ke Aturan**, lalu pilih ikon **+** di sebelah atribut untuk menambahkan. Pilih jika Anda ingin menambahkan atribut ke aturan yang ada atau menggunakannya untuk membuat aturan baru.
   - Masukkan nama atribut di bagian aturan untuk melihat saran yang cocok.

1. Pilih operator untuk menentukan nilai yang cocok dari kondisi. Atribut dapat memiliki salah satu dari empat jenis data sebagai nilai: numerik, string, tanggal, atau Boolean. Tergantung pada jenis data atribut, operator lain tersedia untuk menentukan kondisi. Untuk segmen dengan akun bisnis, dua operator khusus tersedia untuk mencakup kemungkinan hierarki antara akun yang diserap. Gunakan operator *anak dari* dan *induk dari* untuk menyertakan akun terkait.

1. Pilih **Tambah kondisi** untuk menambahkan kondisi lainnya ke aturan. Untuk membuat aturan di dalam aturan saat ini, pilih **Tambah sub-aturan**.

1. Jika aturan menggunakan entitas lain selain entitas *Pelanggan*, Anda harus menetapkan jalur relasi. Jalur relasi akan diperlukan untuk menginformasikan sistem Relasi mana yang Anda inginkan untuk mengakses entitas pelanggan. Pilih **Atur jalur relasi** untuk memetakan entitas yang dipilih ke entitas pelanggan terpadu. Jika hanya ada satu jalur relasi yang mungkin, sistem akan memilihnya secara otomatis. Jalur relasi yang berbeda dapat menghasilkan hasil yang berbeda. Setiap aturan dapat memiliki jalur relasi sendiri.

   :::image type="content" source="media/relationship-path.png" alt-text="Jalur relasi potensial saat membuat aturan berdasarkan entitas yang dipetakan ke entitas pelanggan terpadu.":::

   Contohnya, entitas *eCommerce_eCommercePurchases* di cuplikan layar memiliki empat opsi untuk memetakan ke entitas *Pelanggan*:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Pelanggan
   - eCommerce_eCommercePurchases > Pelanggan
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Pelanggan
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Pelanggan Saat memilih pilihan terakhir, kita dapat menyertakan atribut dari semua entitas terdaftar dalam kondisi aturan. Kemungkinan kita akan mendapatkan hasil yang lebih sedikit karena rekaman pelanggan yang cocok harus menjadi bagian dari semua entitas. Dalam contoh ini, mereka telah membeli barang melalui e-commerce (*eCommerce_eCommercePurchases*), pada titik penjualan (*POS_posPurchases*), dan berpartisipasi dalam program loyalitas kita (*loyaltyScheme_loyCustomers*). Saat memilih pilihan kedua, kita hanya dapat memilih atribut dari *eCommerce_eCommercePurchases* dan entitas *Pelanggan*. Hal ini mungkin akan mengakibatkan profil pelanggan lebih banyak hasil.

1. Jika Anda memiliki beberapa kondisi dalam aturan, Anda dapat memilih operator logika yang menghubungkannya.  
   - Operator **AND**: Semua kondisi harus dipenuhi untuk mencakup rekaman dalam segmen. Pilihan ini paling berguna saat Anda menentukan kondisi di seluruh entitas yang berbeda.
   - Operator **OR**: Salah satu kondisi harus dipenuhi untuk mencakup rekaman dalam segmen. Pilihan ini paling berguna saat Anda menentukan beberapa kondisi untuk entitas yang sama.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Aturan dengan kondisi AND.":::

   Saat menggunakan operator OR, semua kondisi harus didasarkan pada entitas yang tercakup dalam jalur relasi.

   - Anda dapat membuat beberapa aturan untuk membuat kumpulan rekaman pelanggan yang berbeda. Anda dapat menggabungkan grup untuk menyertakan pelanggan yang diperlukan untuk kasus bisnis Anda. Pilih **Tambah aturan** untuk membuat aturan baru. Secara khusus, jika Anda tidak dapat menyertakan entitas dalam aturan karena jalur relasi yang ditentukan, Anda harus membuat aturan baru untuk memilih atribut darinya.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Tambahkan aturan baru ke segmen, lalu pilih operator yang ditentukan.":::

   - Pilih salah satu operator rangkaian: **Gabungan**, **Irisan**, atau **Lepas**.

      - **Semesta** menyatukan dua kelompok.
      - **Berpotongan** tumpang-tindih kedua grup. Hanya data yang *umum* untuk kedua grup yang tetap dalam Grup Terpadu.
      - **Kecuali** menggabungkan dua grup. Hanya data dalam grup A yang *tidak umum* pada data di grup B yang dipertahankan.

1. Secara default, segmen akan menghasilkan entitas output yang berisi semua atribut profil pelanggan yang cocok dengan filter yang ditentukan. Jika segmen didasarkan pada entitas lain dari entitas *Pelanggan*, Anda dapat menambahkan lebih banyak atribut dari entitas ini ke entitas output. Pilih **atribut Proyek** untuk memilih atribut yang akan ditambahkan ke entitas output.

   > [!IMPORTANT]
   > Untuk segmen berdasarkan akun bisnis, rincian satu atau beberapa kontak dari setiap akun dari entitas *ContactProfile* harus disertakan dalam segmen agar segmen tersebut dapat diaktifkan atau diekspor ke tujuan yang memerlukan informasi kontak. Untuk informasi lebih lanjut tentang entitas *ContactProfile*, lihat [pemetaan Semantis](semantic-mappings.md).
   > Output sampel untuk segmen berdasarkan akun bisnis dengan atribut kontak yang diproyeksikan dapat terlihat seperti ini:
   >
   > |ID  |Nama akun  |Pendapatan  |Nama kontak  | Peran Kontak|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100 K | [Abbie Moss, Ruth Soto]  | [CEO, manajer Pengadaan]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Contoh atribut yang diproyeksikan dipilih di panel sisi untuk ditambahkan ke entitas output.":::
  
   Contoh: Segmen didasarkan pada entitas yang berisi data pembelian, yang terkait dengan entitas *Pelanggan*. Segmen tersebut mencari semua pelanggan dari Spanyol yang membeli barang pada tahun berjalan. Anda dapat memilih untuk menambahkan atribut seperti harga barang, atau tanggal pembelian untuk semua rekaman pelanggan yang cocok di entitas output. Informasi ini mungkin berguna untuk menganalisis korelasi musiman terhadap total pengeluaran.

   > [!NOTE]
   > - **Atribut proyek** hanya berfungsi untuk entitas yang memiliki relasi satu ke banyak dengan entitas pelanggan. Misalnya, satu pelanggan dapat memiliki beberapa langganan.
   > - Jika atribut yang ingin Anda proyeksikan lebih dari satu lompatan dari entitas *Pelanggan*, sebagaimana ditentukan oleh relasi, atribut tersebut harus digunakan di setiap aturan kueri segmen yang Anda bentuk.
   > - Jika atribut yang ingin Anda proyeksikan hanya satu lompatan dari entitas *Pelanggan*, atribut tersebut tidak harus ada di setiap aturan kueri segmen yang Anda bentuk.
   > - **Atribut yang diproyeksikan** digunakan saat menggunakan operator yang ditentukan.

1. Pilih **Edit detail di** samping segmen Tanpa Judul. Berikan nama untuk segmen Anda dan perbarui **nama entitas Output** yang disarankan untuk segmen. Secara opsional, tambahkan deskripsi dan [tag](work-with-tags-columns.md#manage-tags) ke segmen.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Kotak dialog Edit detail.":::

1. Pilih **Jalankan** untuk menyimpan segmen, aktifkan dan mulai memproses segmen Anda berdasarkan semua aturan dan kondisi. Jika tidak, maka akan disimpan sebagai segmen tidak aktif.

1. Untuk kembali ke halaman **Segmen**, pilih **kembali ke segmen**.

1. Secara default, segmen dibuat sebagai segmen dinamis. Berarti segmen di-refresh selama pembaruan sistem. Untuk [menghentikan pembaruan otomatis](segments.md#manage-existing-segments), pilih segmen, pilih pilihan **Buat statis**. Segmen statis dapat [di-refresh secara manual](segments.md#refresh-segments) kapan saja.

> [!TIP]
> - Pembuat segmen tidak akan menyarankan nilai yang valid dari entitas saat mengatur operator untuk kondisi tersebut. Anda dapat membuka **Data** > **Entitas** dan mengunduh data entitas untuk melihat nilai yang tersedia.
> - Kondisi berdasarkan tanggal memungkinkan Anda beralih antara tanggal tetap dan rentang tanggal mengambang.
> - Jika Anda memiliki beberapa aturan untuk segmen, aturan yang sedang Anda edit memiliki garis biru vertikal di sebelahnya.
> - Anda dapat memindahkan aturan dan kondisi ke tempat lain dalam definisi segmen. Pilih [...] di sebelah aturan atau kondisi, lalu pilih cara dan lokasi memindahkannya.
> - Kontrol **Batalkan** dan **Kembalikan** di bilah perintah memungkinkan Anda membatalkan perubahan.

## <a name="quick-segments"></a>Segmen ringkas

Segmen singkat memungkinkan Anda membuat segmen sederhana dengan satu operator secara cepat untuk wawasan yang lebih cepat.

1. Pada halaman **Segmen**, pilih **Baru** > **Buat dari**.
   - Pilih pilihan **profil** untuk membuat segmen yang didasarkan pada entitas *pelanggan terpadu*.
   - Pilih pilihan **Ukuran** untuk membuat segmen di sekitar ukuran yang telah Anda buat sebelumnya.
   - Pilih **pilihan intelijen** untuk membuat segmen di sekitar salah satu entitas output yang dihasilkan menggunakan **prediksi** maupun kemampuan **model kustom**.

2. Di kotak dialog **segmen ringkas baru**, pilih atribut dari dropdown **bidang**.

3. Sistem akan memberikan lebih banyak wawasan yang membantu Anda membuat segmen pelanggan yang lebih baik.
   - Untuk bidang kategoris, kami akan menampilkan 10 hitungan pelanggan teratas. Pilih **nilai** dan pilih **tinjau**.
   - Untuk atribut numerik, sistem akan menampilkan nilai atribut yang berada di dalam persentil masing-masing pelanggan. Pilih **operator** dan **nilai**, lalu pilih **tinjau**.

4. Sistem akan memberi Anda **perkiraan ukuran segmen**. Anda dapat memilih apakah akan menghasilkan segmen yang telah Anda tetapkan, atau pertama-tama, mengunjungi kembali untuk mendapatkan ukuran segmen yang berbeda.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nama dan estimasi untuk segmen cepat.":::

5. **Berikan nama** entitas Nama **dan** Output untuk segmen Anda. Secara opsional, tambahkan [tag](work-with-tags-columns.md#manage-tags).

6. Klik **Simpan** untuk membuat segmen Anda.

7. Setelah segmen selesai diproses, Anda dapat melihatnya seperti segmen lain yang Anda buat.

## <a name="next-steps"></a>Langkah berikutnya

[Ekspor segmen](export-destinations.md) dan jelajahi [integrasi Kartu Pelanggan](customer-card-add-in.md) untuk menggunakan segmen di aplikasi lain.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
