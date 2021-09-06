---
title: Membuat dan mengelola segmen
description: Buat segmen pelanggan untuk mengelompokkan mereka berdasarkan berbagai atribut.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e759872643cc7387cf732d73c7a320ae8901e5a9
ms.sourcegitcommit: 42692a815695b9fdc93b9358eae09f2c3e97293c
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/13/2021
ms.locfileid: "7377792"
---
# <a name="create-and-manage-segments"></a>Membuat dan mengelola segmen

> [!IMPORTANT]
> Ada beberapa perubahan yang diluncurkan untuk pengalaman pembuatan segmen pada bulan September 2021: 
> - Pembangun segmen akan terlihat sedikit berbeda dengan elemen gaya ulang dan alur pengguna yang ditingkatkan.
> - Operator datetime baru dan pemilih tanggal yang disempurnakan diaktifkan di pembangun segmen.
> - Anda dapat menambahkan atau menghapus kondisi dan aturan dari segmen. 
> - Aturan berkurung yang dimulai dengan kondisi OR akan tersedia. Anda tidak lagi memerlukan kondisi AND di lapisan terluar.
> - Panel samping untuk memilih atribut akan terus tersedia.
> - Opsi untuk memilih jalur relasi entitas.
> Untuk mencoba pembangun segmen baru, kirim email dengan subjek "Permintaan untuk mengaktifkan pembangun segmen baru" ke cihelp [at] microsoft.com. Sertakan nama orgnisasi Anda dan ID lingkungan sandbox Anda.
> :::image type="content" source="media/segment-builder-overview.png" alt-text="Elemen pembuat segmen." lightbox="media/segment-builder-overview.png":::
>
> 1 - Menyusun segmen dengan aturan dan sub-aturan. Setiap aturan atau sub-aturan terdiri dari kondisi. Menggabungkan kondisi dengan operator logika
>
> 2 - Pilih [jalur relasi](relationships.md) antara entitas yang berlaku untuk aturan. Jalur relasi menentukan atribut yang dapat digunakan dalam kondisi.
>
> 3 - Mengelola aturan dan sub-aturan. Mengubah posisi aturan atau menghapusnya.
>
> 4 - Tambah kondisi dan buat tingkat yang tepat untuk mengurung dengan menggunakan sub-aturan.
>
> 5 - Terapkan rangkaian operasi ke aturan yang tersambung.
>
> 6 - Gunakan panel atribut untuk menambahkan atribut entitas yang tersedia atau membuat kondisi berdasarkan atribut. Panel menampilkan daftar entitas dan atribut, berdasarkan jalur relasi yang dipilih, yang tersedia untuk aturan yang dipilih.
>
> 7 - Tambahkan kondisi berdasarkan atribut ke aturan dan sub-aturan yang ada atau tambahkan ke aturan baru.
>
> 8 - Batalkan dan kembalikan perubahan saat membangun segmen.

Tentukan filter kompleks di sekitar entitas pelanggan terpadu dan entitas terkaitnya. Setiap segmen, setelah pemrosesan, membuat kumpulan rekaman pelanggan yang dapat Anda ekspor dan lakukan tindakan padanya. Segmen dikelola pada halaman **segmen**. 

Contoh berikut menjelaskan kemampuan segmentasi. Kami telah mendefinisikan segmen untuk pelanggan yang memesan setidaknya $500 barang di 90 hari terakhir *dan* yang terlibat dalam panggilan layanan pelanggan yang dieskalasi.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Cuplikan layar antarmuka pembuat segmen dengan dua grup yang menentukan segmen pelanggan.":::

## <a name="create-a-new-segment"></a>Buat segmen baru

Tersedia beberapa cara untuk membuat segmen baru. Bagian ini menjelaskan cara membuat *segmen kosong* dari awal. Anda juga dapat membuat *segmen cepat* berdasarkan entitas yang ada atau menggunakan model Pembelajaran Mesin untuk mendapatkan *segmen yang disarankan*. Informasi selengkapnya: [Ikhtisar segmen](segments.md).

Saat membuat segmen, Anda dapat menyimpan draf. Fitur tersebut akan disimpan sebagai segmen dan tidak dapat diaktifkan jika diselesaikan dengan konfigurasi yang valid.

1. Buka halaman **Segmen**.

1. Pilih **Baru** > **segmen kosong**.

1. Di panel **Segmen baru**, pilih jenis segmen:

   - **Segmen dinamis** [di-refresh](segments.md#refresh-segments) pada jadwal berulang.
   - **Segmen statis** berjalan sekali saat Anda membuatnya.

1. Berikan **nama entitas Output** untuk segmen. Atau, berikan nama tampilan, dan deskripsi yang membantu mengidentifikasi segmen.

1. Pilih **berikutnya** untuk mengakses halaman **pembuat segmen** dengan menentukan grup. Grup adalah satu set pelanggan.

1. Pilih entitas yang mencakup atribut yang ingin Anda segmentasikan.

1. Pilih atribut untuk segmentasi. Atribut ini dapat memiliki salah satu dari empat jenis nilai: numerik, string, tanggal, atau Boolean.

1. Pilih operator dan nilai untuk atribut dipilih.

   > [!div class="mx-imgBorder"]
   > ![Filter grup kustom.](media/customer-group-numbers.png "Filter grup pelanggan")

   |Angka |Definisi  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribut          |
   |3    |Operator         |
   |4    |Nilai         |

   1. Untuk menambahkan kondisi ke grup, Anda dapat menggunakan dua operator logika:

      - Operator **AND**: kedua kondisi harus dipenuhi sebagai bagian dari proses segmentasi. Pilihan ini paling berguna saat Anda menentukan kondisi di seluruh entitas yang berbeda.

      - Operator **OR**: Salah satu dari kondisi harus dipenuhi sebagai bagian dari proses segmentasi. Pilihan ini paling berguna saat Anda menentukan beberapa kondisi untuk entitas yang sama.

      > [!div class="mx-imgBorder"]
      > ![Operator OR bila kedua kondisi harus dipenuhi.](media/segmentation-either-condition.png "Operator OR bila kedua kondisi harus dipenuhi")

      Saat ini mungkin untuk mengurung operator **OR** di bawah operator **AND**, namun tidak sebaliknya.

   1. Setiap grup cocok dengan rangkaian pelanggan. Anda dapat menggabungkan grup untuk menyertakan pelanggan yang diperlukan untuk kasus bisnis Anda.    
   Pilih **Tambah Grup**.

      > [!div class="mx-imgBorder"]
      > ![Grup pelanggan Tambah grup.](media/customer-group-add-group.png "Grup pelanggan Tambah grup")

   1. Pilih salah satu operator rangkaian: **Gabungan**, **Irisan**, atau **Lepas**.

   > [!div class="mx-imgBorder"]
   > ![Grup pelanggan Tambah penyatuan.](media/customer-group-union.png "Grup pelanggan Tambah penyatuan")

   - **Semesta** menyatukan dua kelompok.

   - **Berpotongan** tumpang-tindih kedua grup. Hanya data yang *umum* untuk kedua grup yang dipertahankan dalam Grup Terpadu.

   - **Kecuali** menggabungkan dua grup. Hanya data dalam grup A yang *tidak umum* untuk data di Grup B yang dipertahankan.

1. Jika entitas terhubung ke entitas pelanggan terpadu melalui [Relasi](relationships.md), Anda harus menentukan jalur relasi untuk membuat segmen valid. Tambahkan entitas dari jalur relasi hingga Anda dapat memilih entitas **pelanggan: CustomerInsights** dari dropdown. Selanjutnya, pilih **Semua rekaman** untuk setiap langkah.

   > [!div class="mx-imgBorder"]
   > ![Jalur relasi selama pembuatan segmen.](media/segments-multiple-relationships.png "Jalur relasi selama pembuatan segmen")

1. Secara default, segmen akan menghasilkan entitas output yang berisi semua atribut profil pelanggan yang cocok dengan filter yang ditentukan. Jika segmen didasarkan pada entitas lain dari entitas *Pelanggan*, Anda dapat menambahkan lebih banyak atribut dari entitas ini ke entitas output. Pilih **atribut Proyek** untuk memilih atribut yang akan ditambahkan ke entitas output.  
  
   Contoh: Segmen didasarkan pada entitas yang berisi data aktivitas pelanggan yang terkait dengan entitas *Pelanggan*. Segmen tersebut mencari semua pelanggan yang menelepon pusat bantuan dalam 60 hari terakhir. Anda dapat memilih untuk menambahkan durasi panggilan dan jumlah panggilan ke semua rekaman pelanggan yang cocok di entitas output. Informasi ini mungkin berguna untuk mengirim email dengan tautan bermanfaat ke artikel bantuan online dan Tanya Jawab kepada pelanggan yang sering menelepon.

   > [!NOTE]
   > - Atribut yang diproyeksikan hanya berfungsi untuk entitas yang memiliki relasi satu ke banyak dengan entitas pelanggan. Misalnya, satu pelanggan dapat memiliki beberapa langganan.
   > - Anda hanya dapat memproyeksikan atribut dari entitas yang digunakan di setiap grup kueri segmen yang Anda bentuk.
   > - Atribut yang diproyeksikan digunakan saat menggunakan operator yang ditentukan.

1. Pilih **Simpan** untuk menyimpan segmen Anda. Segmen Anda akan disimpan dan diproses jika semua persyaratan divalidasi. Jika tidak, maka akan disimpan sebagai draf.

1. Untuk kembali ke halaman **Segmen**, pilih **kembali ke segmen**.



## <a name="quick-segments"></a>Segmen ringkas

Segmen singkat memungkinkan Anda membuat segmen sederhana dengan satu operator secara cepat untuk wawasan yang lebih cepat.

1. Pada halaman **Segmen**, pilih **Baru** > **Buat dari**.

   - Pilih pilihan **profil** untuk membuat segmen yang didasarkan pada entitas *pelanggan terpadu*.
   - Pilih pilihan **Ukuran** untuk membuat segmen di sekitar ukuran yang telah Anda buat sebelumnya.
   - Pilih **pilihan intelijen** untuk membuat segmen di sekitar salah satu entitas output yang dihasilkan menggunakan **prediksi** maupun kemampuan **model kustom**.

2. Di kotak dialog **segmen ringkas baru**, pilih atribut dari dropdown **bidang**.

3. Sistem akan memberikan beberapa wawasan tambahan yang membantu Anda membuat segmen pelanggan yang lebih baik.
   - Untuk bidang kategoris, kami akan menampilkan 10 hitungan pelanggan teratas. Pilih **nilai** dan pilih **tinjau**.

   - Untuk atribut numerik, sistem akan menampilkan nilai atribut yang berada di dalam persentil masing-masing pelanggan. Pilih **operator** dan **nilai**, lalu pilih **tinjau**.

4. Sistem akan memberi Anda **perkiraan ukuran segmen**. Anda dapat memilih apakah akan menghasilkan segmen yang telah Anda tetapkan, atau pertama-tama, mengunjungi kembali untuk mendapatkan ukuran segmen yang berbeda.

    > [!div class="mx-imgBorder"]
    > ![Nama dan estimasi untuk segmen cepat.](media/quick-segment-name.png "Nama dan estimasi untuk segmen cepat")

5. Beri **nama** segmen Anda. Atau, berikan **nama tampilan**.

6. Klik **Simpan** untuk membuat segmen Anda.

7. Setelah segmen selesai diproses, Anda dapat melihatnya seperti segmen lain yang Anda buat.

## <a name="next-steps"></a>Langkah berikutnya

[Ekspor segmen](export-destinations.md) dan jelajahi [integrasi Kartu Pelanggan](customer-card-add-in.md) untuk menggunakan segmen di aplikasi lain.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
