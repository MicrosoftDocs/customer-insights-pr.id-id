---
title: Sesuaikan entitas untuk penyatuan data
description: Sesuaikan entitas untuk membuat profil pelanggan terpadu.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 05afd17b7f1b34f7f24a8fa8cb2dc32c1649d40f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267482"
---
# <a name="match-entities"></a>Pencocokan Entitas

Setelah menyelesaikan fase pemetaan, Anda siap mencocokkan entitas Anda. Fase pencocokan menentukan cara menggabungkan kumpulan data menjadi himpunan data profil pelanggan terpadu. Fase pencocokan memerlukan setidaknya [dua entitas yang dipetakan](map-entities.md).

## <a name="specify-the-match-order"></a>Tentukan urutan kecocokan

Buka **Data** > **Satukan** > **Cocokkan**, lalu pilih **Atur urutan** untuk memulai fase pencocokan.

Setiap kecocokan menyatukan dua atau lebih entitas ke dalam satu entitas, sekaligus mempertahankan setiap rekaman pelanggan unik. Pada contoh berikut, kita memilih tiga entitas: **ContactCSV: TestData** sebagai entitas **Primary**, **WebAccountCSV: TestData** sebagai **Entitas 2**, dan **CallRecordSmall: TestData** sebagai **Entitas 3**. Diagram di atas pilihan ini mengilustrasikan bagaimana urutan kecocokan dijalankan.

> [!div class="mx-imgBorder"]
> ![Mengedit urutan kecocokan data](media/configure-data-match-order-edit-page.png "Mengedit urutan kecocokan data")
  
Entitas **utama** disesuaikan dengan **entitas 2**. Himpunan data hasil dari pencocokan pertama disesuaikan dengan **entitas 3**.
Dalam contoh ini, kami hanya memilih dua kecocokan, namun sistem dapat mendukung lebih banyak.

> [!IMPORTANT]
> Entitas yang Anda pilih sebagai entitas **utama** akan berfungsi sebagai dasar untuk himpunan data induk terpadu Anda. Entitas tambahan yang dipilih selama fase pencocokan akan ditambahkan ke entitas ini. Pada saat yang sama, ini tidak berarti bahwa entitas terpadu akan mencakup *semua* data yang tercakup dalam entitas ini.
>
> Ada dua pertimbangan yang dapat membantu Anda memilih hierarki entitas Anda:
>
> - Entitas apa yang Anda pertimbangkan memiliki data yang paling lengkap dan andal tentang pelanggan Anda?
> - Apakah entitas yang baru saja Anda identifikasi memiliki atribut yang juga dimiliki oleh entitas lain (misalnya, nama, nomor telepon, atau alamat email)? Jika tidak, pilih entitas Anda yang paling andal kedua.

Pilih **selesai** untuk menyimpan urutan kecocokan.

## <a name="define-rules-for-your-first-match-pair"></a>Tentukan aturan untuk pasangan pencocokan pertama

Setelah menentukan urutan kecocokan, Anda akan melihat kecocokan yang ditentukan pada halaman **Kecocokan**. Ubin di bagian atas layar akan kosong hingga Anda menjalankan urutan kecocokan.

> [!div class="mx-imgBorder"]
> ![Mendefinisikan aturan](media/configure-data-match-need-rules.png "Mendefinisikan aturan")

Peringatan **Memerlukan aturan** menunjukkan bahwa tidak ada aturan kecocokan yang ditentukan untuk pasangan pencocokan. Aturan kecocokan menentukan logika dengan mana sepasang entitas tertentu akan dicocokkan.

1. Untuk menentukan aturan pertama, Buka panel **definisi aturan** dengan memilih baris pencocokan yang sesuai di tabel kecocokan (1), lalu memilih **Buat aturan baru** (2).

   > [!div class="mx-imgBorder"]
   > ![Buat aturan baru](media/configure-data-match-new-rule2.png "Buat aturan baru")

2. Di panel **Edit aturan**, konfigurasikan kondisi untuk aturan tersebut. Setiap kondisi diwakili oleh dua baris yang mencakup pilihan wajib.

   > [!div class="mx-imgBorder"]
   > ![Panel aturan baru](media/configure-data-match-new-rule-condition.png "Panel aturan baru")

   Entitas/Bidang (pertama) - Atribut yang akan digunakan untuk pencocokan dari entitas kecocokan pasangan pertama. Contohnya dapat mencakup nomor telepon atau alamat email. Pilih atribut yang mungkin unik untuk pelanggan.

   > [!TIP]
   > Hindari pencocokan berdasarkan atribut jenis aktivitas. Dengan kata lain, jika atribut tampaknya merupakan aktivitas, maka mungkin kriteria buruk untuk dicocokkan.  

   Entitas/Bidang (Kedua) - Atribut yang akan digunakan untuk pencocokan dari entitas kecocokan pasangan kedua.

   Normalisasi- **metode normalisasi**: berbagai pilihan normalisasi tersedia untuk atribut yang dipilih. Misalnya, menghapus tanda baca atau menghapus spasi

   Untuk normalisasi nama organisasi (pratinjau), Anda juga dapat memilih **jenis (telepon, nama, organisasi)**

   > [!div class="mx-imgBorder"]
   > ![Normalisasi-B2B](media/match-normalization-b2b.png "Normalisasi-B2B")

   Tingkat presisi - yang akan digunakan untuk kondisi tersebut. Menetapkan tingkat presisi untuk kondisi kecocokan dapat memiliki dua jenis: **dasar** dan **kustom**.  
   - Dasar: menyediakan empat opsi untuk dipilih: rendah, sedang, tinggi, dan tepat. Pilih **tepat** untuk hanya mencocokkan rekaman yang cocok 100 persen. Pilih salah satu tingkat lainnya untuk mencocokkan rekaman yang bukan 100 persen identik.
   - Kustom: Gunakan penggeser untuk menentukan persentase kustom yang harus cocok dengan rekaman atau masukkan nilai di bidang **kustom**. Sistem hanya akan mencocokkan rekaman yang melewati ambang batas ini sebagai pasangan cocok digabungkan. Nilai pada slider adalah antara 0 dan 1. Jadi 0,64 mewakili 64 persen.

3. Untuk menyimpan aturan, pilih **Selesai**.

### <a name="add-multiple-conditions"></a>Menambahkan beberapa kondisi

Untuk mencocokkan entitas hanya jika beberapa kondisi terpenuhi, tambahkan kondisi lainnya yang ditautkan melalui operator AND.

1. Di panel **Edit aturan**, pilih **Tambah kondisi**. Anda juga dapat menghapus kondisi dengan memilih tombol Hapus di samping kondisi yang ada.

2. Untuk menyimpan aturan, pilih **Selesai**.

## <a name="add-multiple-rules"></a>Menambahkan beberapa aturan

Setiap kondisi berlaku untuk satu sepasang atribut, sedankan aturan mewakili rangkaian beberapa kondisi. Agar entitas Anda cocok dengan kumpulan atribut yang berbeda, Anda dapat menambahkan aturan lainnya.

1. Di wawasan audiens, buka **Data** > **Satukan** > **Sesuaikan**.

2. Pilih entitas yang ingin Anda perbarui dan pilih **Tambahkan aturan**.

3. Ikuti prosedur seperti diuraikan dalam [menentukan aturan untuk pasangan pencocokan pertama](#define-rules-for-your-first-match-pair).

> [!NOTE]
> Aturan urutan itu penting. Algoritma pencocokan mencoba untuk mencocokkan berdasarkan aturan pertama Anda dan melanjutkan ke aturan kedua hanya jika tidak ada kecocokan yang diidentifikasi dalam aturan pertama.

## <a name="define-deduplication-on-a-match-entity"></a>Menentukan deduplikasi pada entitas kecocokan

Bersama dengan menentukan aturan pencocokan entitas silang sebagaimana diuraikan dalam bagian di atas, Anda juga dapat menentukan aturan deduplikasi. *Deduplikasi* adalah proses. Ia mengidentifikasi rekaman duplikat, menggabungkannya ke dalam satu rekaman, dan menautkan semua rekaman sumber ke rekaman gabungan ini dengan ID alternatif ke rekaman gabungan.

Setelah rekaman yang dideduplikasi teridentifikasi, rekaman tersebut akan digunakan dalam proses pencocokan lintas entitas. Deduplikasi diimplementasikan pada tingkat entitas dan dapat diterapkan ke setiap entitas yang digunakan dalam proses pencocokan.

### <a name="add-deduplication-rules"></a>Menambahkan aturan deduplikasi

1. Di wawasan audiens, buka **Data** > **Satukan** > **Sesuaikan**.

1. Di Bagian **duplikat yang digabungkan**, pilih **Atur entitas**.

1. Di Bagian **preferensi penggabungan**, pilih entitas yang akan diterapkan deduplikasinya.

1. Tentukan cara menggabungkan rekaman duplikat dan memilih salah satu dari tiga pilihan penggabungan:
   - *Paling terisi*: mengidentifikasi rekaman dengan atribut yang paling banyak diisi sebagai rekaman pemenang. Ini adalah pilihan penggabungan default.
   - *Terbaru* : mengidentifikasi rekaman pemenang berdasarkan keterkinian. Memerlukan tanggal atau bidang numerik untuk menentukan keterkinian.
   - *Paling lama* : mengidentifikasi rekaman pemenang berdasarkan keterkinian terlama. Memerlukan tanggal atau bidang numerik untuk menentukan keterkinian.
 
   > [!div class="mx-imgBorder"]
   > ![Aturan deduplikasi langkah 1](media/match-selfconflation.png "Aturan deduplikasi langkah 1")
 
1. Setelah entitas dipilih dan preferensi penggabungan mereka diatur, pilih **Buat aturan baru** untuk menentukan aturan deduplikasi pada tingkat entitas.
   - **Pilih bidang** berisi daftar semua bidang tersedia dari entitas yang ingin Anda deduplikasikan data sumbernya.
   - Tentukan pengaturan normalisasi dan presisi dengan cara yang sama seperti yang ditentukan dalam pencocokan entitas silang.
   - Anda dapat menentukan kondisi tambahan dengan memilih **Tambah kondisi**.
 
   > [!div class="mx-imgBorder"]
   > ![Aturan deduplikasi langkah 2](media/match-selfconflation-rules.png "Aturan deduplikasi langkah 2")

  Anda dapat membuat beberapa aturan deduplikasi untuk suatu entitas. 

1. Menjalankan proses pencocokan sekarang mengelompokkan rekaman berdasarkan kondisi yang ditentukan dalam aturan deduplikasi. Setelah mengelompokkan rekaman, kebijakan gabungan diterapkan untuk mengidentifikasi rekaman pemenang.

1. Rekaman pemenang ini kemudian diteruskan ke pencocokan lintas entitas, bersama dengan rekaman non-pemenang (misalnya, ID alternatif) untuk meningkatkan kualitas pencocokan.

1. Aturan kecocokan kustom yang ditentukan untuk selalu cocok dan tidak pernah cocok dengan aturan deduplikasi pengesampingan. Jika aturan deduplikasi mengidentifikasi rekaman yang cocok dan aturan kecocokan kustom diatur untuk tidak pernah cocok dengan rekaman tersebut, maka kedua rekaman tersebut tidak akan dicocokkan.

1. Setelah menjalankan proses pencocokan, Anda akan melihat status deduplikasi.
   
> [!NOTE]
> Menentukan aturan deduplikasi tidak wajib. Jika tidak ada aturan yang dikonfigurasi, aturan yang ditentukan sistem akan diterapkan. Mereka menciutkan semua rekaman yang memiliki kombinasi nilai yang sama (pencocokan sama persis) dari primary key dan bidang dalam aturan yang cocok ke dalam satu rekaman sebelum meneruskan data entitas ke pencocokan entitas silang untuk kelogisan sistem dan kinerja yang ditingkatkan.

## <a name="run-your-match-order"></a>Menjalankan urutan kecocokan

Setelah menentukan aturan kecocokan, termasuk aturan pencocokan entitas silang dan deduplikasi, Anda dapat menjalankan urutan pencocokan. Pada halaman **pencocokan**, pilih **Jalankan** untuk memulai proses. Algoritma pencocokan mungkin memerlukan waktu untuk diselesaikan. Anda tidak dapat mengubah properti pada halaman **pencocokan** hingga proses pencocokan selesai. Anda akan menemukan entitas profil pelanggan terpadu yang dibuat pada halaman **entitas**. Entitas gabungan pelanggan Anda disebut **ConflationMatchPairs : CustomerInsights**.

Untuk membuat perubahan tambahan dan menjalankan ulang langkah tersebut, Anda dapat membatalkan pencocokan yang sedang berlangsung. Pilih teks **menyegarkan...** dan pilih **Batalkan pekerjaan** di bagian bawah panel sisi yang muncul.

Setelah proses kecocokan selesai, teks **menyegarkan...** akan berubah menjadi **sukses** dan Anda dapat menggunakan semua fungsi halaman lagi.

Proses pencocokan pertama menghasilkan pembuatan entitas induk terpadu. Semua penjalanan kecocokan berikutnya mengakibatkan perluasan entitas tersebut.

> [!TIP]
> Ada [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies). Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan. Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.

## <a name="deduplication-output-as-an-entity"></a>Output deduplikasi sebagai entitas
Selain entitas induk terpadu yang dibuat sebagai bagian dari pencocokan lintas entitas, proses deduplikasi juga menghasilkan entitas baru untuk setiap entitas dari perintah pencocokan untuk mengidentifikasi rekaman yang dideduplikasi. Entitas ini dapat ditemukan bersama dengan **ConflationMatchPairs:CustomerInsights** di bagian **Sistem** di halaman **Entitas**, dengan nama **Deduplication_Datasource_Entity**.

Entitas output deduplikasi berisi informasi berikut:
- ID/Kunci
  - Bidang kunci utama dan bidang ID alternatif. Bidang ID alternatif terdiri dari semua ID alternatif yang diidentifikasi untuk rekaman.
  - Bidang Deduplication_GroupId menunjukkan grup atau kluster yang diidentifikasi dalam entitas yang mengelompokkan semua rekaman serupa berdasarkan bidang deduplikasi yang ditentukan. Ini digunakan untuk tujuan pemrosesan sistem. Jika tidak ada aturan deduplikasi manual yang ditentukan dan aturan deduplikasi yang didefinisikan sistem berlaku, Anda tidak dapat menemukan bidang ini dalam entitas output deduplikasi.
  - Deduplication_WinnerId: Bidang ini berisi ID pemenang dari grup atau kluster yang teridentifikasi. Jika Deduplication_WinnerId sama dengan nilai kunci Utama untuk rekaman, berarti rekaman adalah rekaman pemenang.
- Bidang yang digunakan untuk mendefinisikan aturan deduplikasi.
- Bidang Aturan dan Skor untuk menunjukkan aturan deduplikasi mana yang diterapkan dan skor yang dihasilkan oleh algoritme yang cocok.

## <a name="review-and-validate-your-matches"></a>Tinjau dan validasi kecocokan Anda

Evaluasi kualitas pasangan pencocokan Anda dan Perbaiki:

- Pada halaman **pencocokan**, Anda akan menemukan dua ubin yang menampilkan wawasan awal tentang data Anda.

  - **Pelanggan yang unik**: menunjukkan jumlah profil unik yang diidentifikasi sistem.
  - **Rekaman yang sesuai**: akan menampilkan jumlah kecocokan di semua pasangan pencocokan.

- Di tabel **urutan kecocokan**, Anda dapat menilai hasil setiap pasangan pencocokan dengan membandingkan jumlah rekaman yang berasal dari entitas pasangan pencocokan ini terhadap persentase rekaman yang berhasil dicocokkan.

- Di bagian **aturan** pada entitas dalam tabel **urutan kecocokan**, Anda akan menemukan persentase rekaman yang berhasil dicocokkan di tingkat aturan. Dengan memilih simbol tabel di sebelah aturan, Anda dapat melihat semua rekaman ini pada tingkat aturan. Sebaiknya Tinjau subset rekaman untuk memvalidasi bahwa rekaman dicocokkan dengan benar.

- Lakukan eksperimen dengan ambang batas presisi yang berbeda di sekitar kondisi Anda untuk mengidentifikasi nilai optimal.

  1. Pilih elipsis (...) untuk aturan pasangan kecocokan yang ingin Anda uji coba dan pilih **Edit**.

  2. Pilih kondisi yang Anda ingin lakukan eksperimen. Setiap kriteria ditunjukkan dengan satu baris di panel **aturan pencocokan**.

  3. Apa yang akan Anda lihat di halaman **pratinjau kriteria** tergantung pada tingkat presisi yang Anda pilih untuk kondisi. Temukan jumlah rekaman yang cocok dan tak cocok untuk kondisi yang dipilih.

     Dapatkan pemahaman yang kaya tentang efek dari tingkat ambang yang berbeda. Anda dapat membandingkan jumlah rekaman yang akan dicocokkan dalam masing-masing tingkat ambang, serta melihat rekaman di bawah setiap pilihan. Pilih masing-masing ubin dan tinjau data di bagian tabel.

## <a name="optimize-your-matches"></a>Optimalkan kecocokan

Tingkatkan kualitas dengan mengonfigurasi ulang beberapa parameter kecocokan Anda:

- **Ubah urutan kecocokan** dengan memilih **Edit** dan Ubah bidang urutan kecocokan.

  > [!div class="mx-imgBorder"]
  > ![Mengedit urutan kecocokan data](media/configure-data-match-order-edit.png "Mengedit urutan kecocokan data")

- **Ubah urutan aturan** jika Anda mendefinisikan beberapa aturan. Anda dapat mengurutkan ulang aturan kecocokan dengan memilih opsi **Pindahkan ke atas** dan **Pindahkan ke bawah** dalam kisi aturan kecocokan.

  > [!div class="mx-imgBorder"]
  > ![Ubah urutan aturan](media/configure-data-change-rule-order.png "Ubah urutan aturan")

- **Gandakan aturan** jika Anda telah menetapkan aturan kecocokan dan ingin membuat aturan serupa dengan modifikasi. Lakukan dengan memilih **Duplikat**.

  > [!div class="mx-imgBorder"]
  > ![Duplikat Aturan](media/configure-data-duplicate-rule.png "Duplikat Aturan")

- **Nonaktifkan aturan** untuk mempertahankan aturan pencocokan sambil mengecualikannya dari proses pencocokan.

  > [!div class="mx-imgBorder"]
  > ![Nonaktifkan aturan](media/configure-data-deactivate-rule.png "Nonaktifkan aturan")

- **Edit aturan** dengan memilih simbol **Edit**. Anda juga dapat menerapkan perubahan berikut:

  - Ubah atribut untuk suatu kondisi: pilih atribut baru dalam baris kondisi tertentu.
  - Ubah ambang batas untuk kondisi: Sesuaikan slider presisi.
  - Ubah metode normalisasi untuk kondisi: Perbarui metode normalisasi.

## <a name="specify-your-custom-match-records"></a>Menentukan rekaman kecocokan kustom

Anda dapat menentukan kondisi yang harus selalu cocok atau tidak pernah cocok dengan rekaman tertentu. Aturan ini dapat diunggah dalam jumlah besar untuk proses pencocokan.

1. Pilih pilihan **pencocokan kustom** di layar **urutan pencocokan**.

   > [!div class="mx-imgBorder"]
   > ![Membuat kecocokan kustom](media/custom-match-create.png "Membuat kecocokan kustom")

2. Jika Anda tidak memiliki entitas yang diupload, Anda akan melihat kotak dialog **kecocokan kustom** baru yang mengharuskan Anda mengisi beberapa detail. Jika Anda telah memberikan rincian ini sebelumnya, Lewati ke langkah 8.

   > [!div class="mx-imgBorder"]
   > ![Kotak dialog kustom pencocokan baru](media/custom-match-new-dialog-box.png "Kotak dialog kustom pencocokan baru")

3. Pilih **isi template** untuk mendapatkan file template yang dapat menentukan rekaman mana dari entitas mana yang harus selalu cocok atau tidak pernah cocok. Anda harus mengisi secara terpisah rekaman "selalu Cocok" dan rekaman "tidak pernah cocok" dalam dua file berbeda.

4. Template berisi bidang untuk menentukan entitas dan nilai kunci primer entitas yang akan digunakan dalam pencocokan kustom. Misalnya, jika Anda ingin kunci primer 12345 dari entitas penjualan agar selalu cocok dengan kunci primer 34567 dari entitas kontak, Anda harus menentukan sebagai berikut:
    - Entity1: Penjualan
    - Entity1Key: 12345
    - Entity2: Kontak
    - Entity2Key: 34567

   File template yang sama dapat menentukan rekaman kecocokan kustom dari beberapa entitas.
   
   Jika Anda ingin menentukan pencocokan kustom untuk deduplikasi pada entitas, berikan entitas yang sama seperti Entity1 dan Entity2 dan atur nilai kunci utama yang berbeda.

5. Setelah menambahkan semua penimpaan yang ingin Anda terapkan, Simpan file template.

6. Buka **data** > **sumber data** dan serap file template sebagai entitas baru. Setelah diserap, Anda dapat menggunakannya untuk menentukan konfigurasi kecocokan.

7. Setelah mengupload file dan entitas yang tersedia, pilih opsi **pencocokan kustom** lagi. Anda akan melihat opsi untuk menentukan entitas yang ingin Anda sertakan. Pilih entitas yang diperlukan dari menu drop-down.

   > [!div class="mx-imgBorder"]
   > ![Timpaan pencocokan kustom](media/custom-match-overrides.png "Timpaan pencocokan kustom")

8. Pilih entitas yang akan digunakan untuk **selalu cocok** dan **tidak pernah cocok**, pilih **selesai**.

9. Pilih **Simpan** pada halaman **pencocokan** untuk konfigurasi kecocokan kustom yang baru saja Anda konfigurasikan.

10. Pilih **Jalankan** di halaman **Kecocokan** untuk memulai proses pencocokan, dan konfigurasi kecocokan kustom akan diterapkan. Aturan sistem yang cocok akan ditimpa oleh set konfigurasi.

11. Setelah pencocokan selesai, Anda dapat memverifikasi entitas **ConflationMatchPair** untuk mengkonfirmasi bahwa penimpaan diterapkan dalam pencocokan penggabungan.

## <a name="next-step"></a>Langkah berikutnya

Setelah menyelesaikan proses pencocokan untuk setidaknya satu pasangan pencocokan, Anda siap menangani kemungkinan kontradiksi dalam data Anda dengan membuka topik [**penggabungan**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]