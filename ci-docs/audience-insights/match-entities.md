---
title: Sesuaikan entitas untuk penyatuan data
description: Sesuaikan entitas untuk membuat profil pelanggan terpadu.
ms.date: 11/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
ms.openlocfilehash: 253c1614725252eb4c794d77669a00b401f0198d
ms.sourcegitcommit: 740e41ec965cee2229592a6d2610c12def116311
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/24/2021
ms.locfileid: "7863815"
---
# <a name="match-entities"></a>Pencocokan Entitas

Fase pencocokan menentukan cara menggabungkan kumpulan data menjadi himpunan data profil pelanggan terpadu. Setelah menyelesaikan [langkah peta](map-entities.md) dalam proses penyatuan data, Anda siap untuk mencocokkan entitas Anda. Fase pencocokan memerlukan setidaknya dua entitas yang dipetakan.

Halaman kecocokan terdiri dari tiga bagian: 
- Metrik kunci yang meringkas jumlah rekaman yang cocok
- Cocokkan urutan dan aturan untuk pencocokan antar-entitas
- Aturan untuk deduplikasi entitas kecocokan

## <a name="specify-the-match-order"></a>Tentukan urutan kecocokan

Buka **Data** > **Satukan** > **Cocokkan**, lalu pilih **Atur urutan** untuk memulai fase pencocokan.

Setiap kecocokan menggabungkan dua atau beberapa entitas ke dalam satu entitas terkonsolidasi. Pada waktu bersamaan, ia menyimpan rekaman pelanggan unik. Contohnya, kami memilih dua entitas: **eCommerce:eCommerceContacts** sebagai entitas utama dan **LoyaltyScheme:loyCustomers** sebagai entitas kedua. Urutan entitas menentukan dalam urutan mana sistem akan mencoba mencocokkan rekaman.

:::image type="content" source="media/match-page.png" alt-text="Tangkapan layar halaman Kecocokan di area Satukan pada proses penyatuan data.":::
  
Entitas utama *eCommerce:e CommerceContacts* cocok dengan entitas berikutnya *LoyaltyScheme:loyCustomers*. Set data yang dihasilkan oleh langkah kecocokan pertama cocok dengan entitas berikut jika Anda memiliki lebih dari dua entitas.

> [!IMPORTANT]
> Entitas yang Anda pilih sebagai entitas utama akan berfungsi sebagai dasar untuk himpunan data profil terpadu Anda. Entitas tambahan yang dipilih selama fase pencocokan akan ditambahkan ke entitas ini. Ini tidak berarti bahwa entitas terpadu akan mencakup *semua* data yang tercakup dalam entitas ini.
>
> Ada dua pertimbangan yang dapat membantu Anda memilih hierarki entitas Anda:
>
> - Pilih entitas dengan data profil paling lengkap dan terpercaya tentang pelanggan Anda sebagai entitas utama.
> - Pilih entitas yang memiliki beberapa atribut yang sama dengan entitas lain (misalnya, nama, nomor telepon, atau alamat email) sebagai entitas utama.

Setelah menentukan urutan kecocokan, Anda akan melihat pasangan kecocokan yang ditentukan di bagian **Rincian rekaman yang cocok** di **Data** > **Satukan** > **Cocokkan**. Metrik kunci akan kosong hingga proses kecocokan selesai.

## <a name="define-rules-for-match-pairs"></a>Menentukan aturan untuk pasangan yang cocok

Aturan kecocokan menentukan logika dengan mana sepasang entitas tertentu akan dicocokkan.

Peringatan **Memerlukan aturan** di sebelah nama entitas menunjukkan bahwa tidak ada aturan kecocokan yang ditentukan untuk pasangan yang cocok. 

:::image type="content" source="media/match-rule-add.png" alt-text="Tangkapan layar dari bagian Rincian rekaman yang cocok dengan kontrol untuk menambahkan aturan disorot.":::

1. Pilih **Tambah aturan** di dalam entitas di bagian **Rincian rekaman yang cocok** untuk menentukan aturan yang cocok.

1. Di panel **Buat aturan**, konfigurasikan kondisi untuk aturan.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Cuplikan layar aturan kecocokan yang dibuka dengan kondisi ditambahkan.":::

   - **Entitas/Bidang (baris pertama)**: Pilih entitas terkait dan atribut untuk menentukan properti rekaman yang kemungkinan unik bagi pelanggan. Contohnya, nomor telepon atau alamat email. Hindari pencocokan menurut atribut jenis aktivitas. Misalnya, ID pembelian kemungkinan tidak akan menemukan kecocokan pada jenis rekaman lain.

   - **Entitas/Bidang (baris kedua)**: Pilih atribut yang terkait dengan atribut entitas yang ditentukan di baris pertama.

   - **Normalkan**: Pilih dari pilihan normalisasi berikut untuk atribut yang dipilih. 
     - White space: Menghilangkan semua spasi. *Hello   World* menjadi *Hello World*.
     - Simbol: Menghilangkan semua simbol dan karakter khusus. *Head&Shoulder* menjadi *HeadShoulder*.
     - Teks ke huruf kecil: Mengkonversi semua karakter ke huruf kecil. *SEMUA KAPITAL dan Huruf Judul* menjadi *semua kapital dan huruf judul*.
     - Unicode ke ASCII: Mengkonversikan notasi unicode ke karakter ASCII. */u00B2* menjadi *2*.
     - Angka: Mengkonversi sistem angka lain, seperti angka Romawi, ke angka Arab. *VIII* menjadi *8*.
     - Jenis semantis: Membuat standar nama, judul, nomor telepon, alamat, dll. 

   - **Presisi**: Atur tingkat presisi untuk diterapkan untuk kondisi ini. 
     - **Dasar**: Pilih dari *Rendah*, *Sedang*, *Tinggi*, dan *Persis*. Pilih **tepat** untuk hanya mencocokkan rekaman yang cocok 100 persen. Pilih salah satu tingkat lainnya untuk mencocokkan rekaman yang bukan 100 persen identik.
     - **Kustom**: Atur persentase yang harus cocok dengan rekaman. Sistem hanya akan mencocokkan rekaman yang melewati ambang batas ini.

1. Masukkan **Nama** untuk aturan tersebut.

1. [Tambahkan kondisi lainnya](#add-conditions-to-a-rule) atau pilih **Selesai** untuk menyelesaikan aturan.

1. Atau, [tambahkan aturan lainnya](#add-rules-to-a-match-pair).

1. Pilih **Simpan** untuk menerapkan perubahan.

### <a name="add-conditions-to-a-rule"></a>Tambahkan kondisi pada aturan

Untuk mencocokkan entitas hanya jika atribut memenuhi beberapa kondisi, tambahkan lebih banyak kondisi ke aturan kecocokan. Kondisi terhubung dengan operator AND logis dan dengan demikian hanya dijalankan jika semua kondisi terpenuhi.

1. Buka **Data** > **Satukan** > **Cocokkan**, lalu pilih **Edit** pada aturan yang akan ditambahkan kondisinya.

1. Di panel **Edit aturan**, pilih **Tambah kondisi**.

1. Untuk menyimpan aturan, pilih **Selesai**.

### <a name="add-rules-to-a-match-pair"></a>Menambahkan aturan ke pasangan yang cocok

Aturan kecocokan menunjukkan rangkaian kondisi. Untuk mencocokkan entitas menurut kondisi berdasarkan beberapa atribut, tambahkan aturan lainnya

1.  Buka **Data** > **Satukan** > **Cocokkan**, lalu pilih **Tambahkan aturan** pada entitas yang akan ditambahkan aturannya.

2. Ikuti langkah-langkah dalam [Menentukan aturan untuk pasangan yang cocok](#define-rules-for-match-pairs).

> [!NOTE]
> Urutan aturan itu penting. Algoritme yang cocok akan berusaha mencocokkan berdasarkan aturan pertama Anda dan terus ke aturan kedua hanya jika tidak ada kecocokan yang diidentifikasi dengan aturan pertama.

### <a name="change-the-entity-order-in-match-rules"></a>Mengubah urutan entitas dalam aturan kecocokan

Anda dapat mengurutkan ulang entitas untuk aturan kecocokan untuk mengubah urutan prosesnya. Aturan yang bertentangan karena urutan yang diubah akan dihilangkan. Anda harus membuat ulang aturan yang dihilangkan dengan konfigurasi yang diperbarui.

1. Buka **Data** > **Satukan** > **Kecocokan**, lalu pilih **Edit**.

1. Di panel **Edit aturan**, pilih kontrol **Pindahkan ke atas/bawah** atau tarik dan lepaskan entitas untuk mengubah urutan.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Pilihan untuk mengubah entitas urutan diproses dalam fase kecocokan.":::

1. Untuk menyimpan aturan, pilih **Selesai**.

## <a name="define-deduplication-on-a-match-entity"></a>Menentukan deduplikasi pada entitas kecocokan

Selain [aturan kecocokan antar-entitas](#define-rules-for-match-pairs), Anda juga dapat menentukan aturan deduplikasi. *Duplikasi* adalah proses lain saat mencocokkan rekaman. Ia mengidentifikasi rekaman duplikat dan menggabungkannya ke dalam satu rekaman. Rekaman sumber ditautkan ke rekaman gabungan dengan ID alternatif.

Rekaman yang dideduplikasi akan digunakan dalam proses pencocokan lintas entitas. Deduplikasi terjadi pada entitas individual dan dapat dikonfigurasi setiap entitas yang digunakan pada pasangan yang cocok.

Menentukan aturan deduplikasi tidak wajib. Jika tidak ada aturan yang dikonfigurasi, aturan yang ditentukan sistem akan diterapkan. Mereka menggabungkan semua rekaman ke satu rekaman sebelum meneruskan data entitas ke pencocokan antar-entitas untuk peningkatan performa.

### <a name="add-deduplication-rules"></a>Menambahkan aturan deduplikasi

1. Buka **Data** > **Satukan** > **Cocokkan**.

1. Di Bagian **duplikat yang digabungkan**, pilih **Atur entitas**. Jika aturan deduplikasi telah dibuat, pilih **Edit**.

1. Di panel **preferensi penggabungan**, pilih entitas yang akan dijalankan deduplikasinya.

1. Tentukan cara menggabungkan rekaman duplikat dan memilih salah satu dari tiga pilihan:
   - **Paling terisi**: mengidentifikasi rekaman dengan bidang atribut yang paling banyak diisi sebagai rekaman pemenang. Ini adalah pilihan penggabungan default.
   - **Terbaru** : mengidentifikasi rekaman pemenang berdasarkan keterkinian. Memerlukan tanggal atau bidang numerik untuk menentukan keterkinian.
   - **Paling lama** : mengidentifikasi rekaman pemenang berdasarkan keterkinian terlama. Memerlukan tanggal atau bidang numerik untuk menentukan keterkinian.
 
   > [!div class="mx-imgBorder"]
   > ![Aturan deduplikasi langkah 1.](media/match-selfconflation.png "Aturan deduplikasi langkah 1")
 
1. Setelah entitas dipilih dan preferensi penggabungan mereka diatur, pilih **Tambahkan aturan** untuk menentukan aturan deduplikasi pada tingkat entitas.
   - **Pilih bidang** mencantumkan semua bidang yang tersedia dari entitas tersebut. Pilih bidang yang ingin Anda periksa duplikatnya. Pilih bidang yang mungkin unik untuk setiap pelanggan. Contohnya, alamat email, atau kombinasi nama, kota, dan nomor telepon.
   - Tentukan pengaturan normalisasi dan presisi.
   - Tentukan kondisi lainnya dengan memilih **Tambah kondisi**.
 
   > [!div class="mx-imgBorder"]
   > ![Aturan deduplikasi langkah 2.](media/match-selfconflation-rules.png "Aturan deduplikasi langkah 2")

  Anda dapat membuat beberapa aturan deduplikasi untuk suatu entitas. 

1. Menjalankan proses pencocokan sekarang mengelompokkan rekaman berdasarkan kondisi yang ditentukan dalam aturan deduplikasi. Setelah mengelompokkan rekaman, kebijakan gabungan diterapkan untuk mengidentifikasi rekaman pemenang.

1. Rekaman pemenang ini kemudian diteruskan ke pencocokan lintas entitas, bersama dengan rekaman non-pemenang (misalnya, ID alternatif) untuk meningkatkan kualitas pencocokan.

1. Aturan kecocokan kustom yang ditentukan akan menimpa aturan deduplikasi. Jika aturan deduplikasi mengidentifikasi rekaman yang cocok dan aturan kecocokan kustom diatur untuk tidak pernah cocok dengan rekaman tersebut, maka kedua rekaman tersebut tidak akan dicocokkan.

1. Setelah [menjalankan proses pencocokan](#run-the-match-process), Anda akan melihat status deduplikasi dalam petak metrik utama.

### <a name="deduplication-output-as-an-entity"></a>Output deduplikasi sebagai entitas

Proses deduplikasi membuat entitas baru untuk setiap entitas dari pasangan yang cocok untuk mengidentifikasi rekaman yang dideduplikasi. Entitas ini dapat ditemukan bersama dengan **ConflationMatchPairs:CustomerInsights** di bagian **Sistem** di halaman **Entitas**, dengan nama **Deduplication_DataSource_Entity**.

Entitas output deduplikasi berisi informasi berikut:
- ID/Kunci
  - Bidang kunci utama dan bidang ID alternatif. Bidang ID alternatif terdiri dari semua ID alternatif yang diidentifikasi untuk rekaman.
  - Bidang Deduplication_GroupId menunjukkan grup atau kluster yang diidentifikasi dalam entitas yang mengelompokkan semua rekaman serupa berdasarkan bidang deduplikasi yang ditentukan. Ini digunakan untuk tujuan pemrosesan sistem. Jika tidak ada aturan deduplikasi manual yang ditentukan dan aturan deduplikasi yang didefinisikan sistem berlaku, Anda tidak dapat menemukan bidang ini dalam entitas output deduplikasi.
  - Deduplication_WinnerId: Bidang ini berisi ID pemenang dari grup atau kluster yang teridentifikasi. Jika Deduplication_WinnerId sama dengan nilai kunci Utama untuk rekaman, berarti rekaman adalah rekaman pemenang.
- Bidang yang digunakan untuk mendefinisikan aturan deduplikasi.
- Bidang Aturan dan Skor untuk menunjukkan aturan deduplikasi mana yang diterapkan dan skor yang dihasilkan oleh algoritme yang cocok.
   
## <a name="run-the-match-process"></a>Jalankan proses Kecocokan

Dengan aturan kecocokan yang dikonfigurasikan, termasuk aturan pencocokan entitas silang dan deduplikasi, Anda dapat menjalankan proses pencocokan. 

Buka **Data** > **Satukan** > **Cocokkan**, lalu pilih **Jalankan** untuk memulai proses. Algoritme yang cocok memerlukan waktu untuk diselesaikan dan Anda tidak dapat mengubah konfigurasi hingga selesai. Untuk membuat perubahan, Anda dapat membatalkan penjalanan. Pilih status pekerjaan, lalu pilih **Batalkan pekerjaan** pada panel **Rincian progres**.

Anda akan menemukan hasil penjalanan yang sukses,entitas profil pelanggan terpadu, pada halaman **Entitas**. Entitas pelanggan terpadu Anda disebut **Pelanggan** di bagian **Profil**. Keberhasilan menjalankan kecocokan pertama akan membuat entitas *Pelanggan* terpadu. Semua penjalanan kecocokan berikutnya memperluas entitas tersebut.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Tinjau dan validasi kecocokan Anda

Buka **Data** > **Satukan** > **Cocokkan** untuk mengevaluasi kualitas pasangan kecocokan dan menyempurnakannya jika perlu.

Petak di atas halaman menampilkan metrik kunci, meringkas jumlah rekaman yang cocok dan duplikat.

:::image type="content" source="media/match-KPIs.png" alt-text="Tangkapan layar yang dipotong untuk metrik kunci pada halaman Cocokkan dengan angka dan rincian.":::

- **Rekaman sumber unik** menampilkan jumlah rekaman sumber individual yang diproses dalam penjalanan kecocokan terakhir.
- **Rekaman yang cocok dan tidak cocok** akan menyorot jumlah rekaman unik yang tersisa setelah memproses aturan kecocokan.
- **Hanya Rekaman yang cocok** menampilkan jumlah kecocokan di semua pasangan kecocokan.

Anda dapat menilai hasil tiap pasangan yang cocok dan aturannya di tabel **rincian rekaman yang cocok**. Bandingkan jumlah rekaman yang berasal dari pasangan yang cocok dengan persentase rekaman yang berhasil dicocokkan.

Tinjau aturan pasangan yang cocok untuk melihat persentase rekaman yang berhasil dicocokkan di tingkat aturan. Pilih elipsis (...) dan kemudian pilih **Pratinjau kecocokan** untuk melihat semua rekaman ini pada tingkat aturan. Sebaiknya lihat beberapa rekaman untuk memvalidasi kecocokannya dengan benar.

Coba ambang batas presisi yang berbeda pada kondisi untuk menemukan nilai optimal.

  1. Pilih elipsis (...) untuk aturan yang akan dicoba, lalu pilih **Edit**.

  2. Ubah nilai presisi dalam kondisi yang akan direvisi.

  3. Pilih **pratinjau**, jadi lihat jumlah rekaman yang cocok dan tidak cocok untuk kondisi yang dipilih.

## <a name="manage-match-rules"></a>Kelola aturan kecocokan

Anda dapat mengkonfigurasi ulang dan menyempurnakan sebagian besar parameter kecocokan.

:::image type="content" source="media/match-rules-management.png" alt-text="Cuplikan layar menu dropdown dengan pilihan aturan yang kecocokan.":::

- **Ubah urutan aturan** jika Anda mendefinisikan beberapa aturan. Anda dapat mengurutkan ulang aturan kecocokan dengan memilih opsi **Pindahkan ke atas** dan **Pindahkan ke bawah** atau dengan menarik dan menjatuhkan.

- **Ubah kondisi aturan** dengan memilih **Edit** dan pilih bidang yang berbeda.

- **Nonaktifkan aturan** untuk mempertahankan aturan pencocokan sambil mengecualikannya dari proses pencocokan.

- **Duplikasikan aturan** jika Anda telah menetapkan aturan kecocokan dan ingin membuat aturan serupa dengan modifikasi, pilih **Duplikat**.

- **Hapus aturan** dengan memilih simbol **Hapus**.

## <a name="specify-custom-match-conditions"></a>Menentukan kondisi kecocokan kustom

Anda dapat menentukan kondisi yang menimpa logika pertandingan default. Ada empat pilihan yang tersedia: 

|Opsi  |Deskripsi |Contoh  |
|---------|---------|---------|
|Selalu cocok     | Mendefinisikan nilai-nilai yang selalu cocok.         |  Selalu cocok *dengan Mike* dan *MikeR*.       |
|Tidak pernah cocok     | Mendefinisikan nilai-nilai yang tidak pernah cocok.        | Tidak pernah cocok *dengan John* dan *Jonathan*.        |
|Bypass kustom     | Mendefinisikan nilai-nilai yang harus selalu diabaikan sistem dalam fase pertandingan. |  Abaikan nilai *11111* dan Tidak Dikenal selama *pertandingan*.        |
|Pemetaan alias    | Mendefinisikan nilai-nilai yang harus dipertimbangkan sistem sebagai nilai yang sama.         | Pertimbangkan *Joe untuk menjadi setara dengan* *Joseph*.        |

1. Buka **Data** > **Satukan** > **Cocokkan**, lalu pilih **Kecocokan kustom** di bagian **rincian rekaman yang cocok**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Tangkapan layar dari bagian aturan kecocokan dengan kontrol kecocokan kustom disorot.":::

1. Di **panel** Kustom, buka **tab** Catatan.

1. Pilih opsi pencocokan kustom dari **dropdown tipe kustom** dan pilih Unduh **templat**. Anda memerlukan template terpisah untuk setiap opsi pertandingan.

1. Sebuah file template download. Buka dan isi detailnya. Template berisi bidang untuk menentukan entitas dan nilai kunci primer entitas yang akan digunakan dalam pencocokan kustom. Misalnya, jika Anda menginginkan kunci utama *12345* dari entitas *Penjualan* agar selalu cocok dengan kunci utama *34567* dari entitas *Kontak*, isi template:
    - Entity1: Penjualan
    - Entity1Key: 12345
    - Entity2: Kontak
    - Entity2Key: 34567

   File template yang sama dapat menentukan rekaman kecocokan kustom dari beberapa entitas.
   
   Jika Anda ingin menentukan pencocokan kustom untuk deduplikasi pada entitas, berikan entitas yang sama seperti Entity1 dan Entity2 dan atur nilai kunci utama yang berbeda.

1. Setelah menambahkan semua overrides, simpan file template.

1. Buka **data** > **sumber data** dan serap file template sebagai entitas baru.

1. Setelah mengupload file dan entitas yang tersedia, pilih opsi **pencocokan kustom** lagi. Anda akan melihat opsi untuk menentukan entitas yang ingin Anda sertakan. Pilih entitas yang diperlukan dari menu dropdown dan pilih **Selesai**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Cuplikan layar dialog untuk memilih menimpa skenario kecocokan kustom.":::

1. Menerapkan kecocokan khusus tergantung pada opsi pertandingan yang ingin Anda gunakan. 

   - Untuk **Selalu cocok atau tidak pernah** **cocok**, lanjutkan ke langkah berikutnya.
   - Untuk **bypass Kustom atau pemetaan** **Alias**, pilih Edit pada aturan pertandingan **yang ada atau buat aturan** baru. Dalam dropdown Normalisasi, pilih **opsi** bypass kustom atau **pemetaan Alias dan pilih Selesai** **·**.

1. Pilih **Simpan** pada halaman **Cocokkan** untuk menerapkan konfigurasi kecocokan kustom.

1. Pilih **Jalankan** pada halaman **Cocokkan** untuk memulai proses pencocokan. Aturan kecocokan tertentu lainnya ditimpa oleh konfigurasi kecocokan kustom.

### <a name="known-issues"></a>Masalah yang diketahui

- Self-conflation tidak menunjukkan data yang dinormalisasi dalam entitas deduplication. Namun, itu menerapkan normalisasi secara internal selama deduplication. Ini dengan desain untuk semua normalisasi. 
- Jika pengaturan tipe semantik dihapus dalam **fase Peta ketika aturan pertandingan menggunakan pemetaan Alias atau bypass** Kustom, normalisasi tidak akan diterapkan. Itu hanya terjadi jika Anda menghapus jenis semantik setelah mengkonfigurasi normalisasi dalam aturan pertandingan karena jenis semantik akan tidak diketahui.


## <a name="next-step"></a>Langkah selanjutnya

Setelah menyelesaikan proses pertandingan untuk setidaknya satu pasangan pertandingan, lanjutkan ke [**·**](merge-entities.md) langkah Merge.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
