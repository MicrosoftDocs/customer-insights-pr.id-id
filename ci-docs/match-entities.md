---
title: Kondisi kecocokan untuk penyatuan data
description: Sesuaikan entitas untuk membuat profil pelanggan terpadu.
recommendations: false
ms.date: 10/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bbd2c5f441b85460250c11f02358ea67260278d6
ms.sourcegitcommit: 52ea58c872b10f1e6f9d120be93df93cca1a12dd
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/26/2022
ms.locfileid: "9721525"
---
# <a name="match-conditions-for-data-unification"></a>Kondisi kecocokan untuk penyatuan data

Langkah penyatuan ini mendefinisikan urutan kecocokan dan aturan untuk pencocokan lintas entitas. Langkah ini membutuhkan setidaknya dua entitas.

> [!NOTE]
> Setelah membuat kondisi kecocokan dan memilih **Berikutnya**, Anda tidak dapat menghapus entitas atau atribut yang dipilih. Jika diperlukan, pilih **Kembali** untuk meninjau entitas dan atribut yang dipilih sebelum melanjutkan.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Menyertakan entitas yang diperkaya (pratinjau)

Jika Anda memperkaya entitas di tingkat sumber data untuk membantu meningkatkan hasil penyatuan Anda, pilih entitas tersebut. Untuk informasi selengkapnya, lihat [Pengayaan untuk sumber data](data-sources-enrichment.md). Jika Anda memilih entitas yang **diperkaya pada halaman Catatan** duplikat, Anda tidak perlu memilihnya lagi.

1. **Pada halaman Kondisi** yang cocok, pilih **Gunakan entitas** yang diperkaya di bagian atas halaman.

1. **Dari panel Gunakan entitas yang diperkaya, pilih satu atau beberapa entitas** yang diperkaya.

1. Pilih **Selesai**.

## <a name="specify-the-match-order"></a>Tentukan urutan kecocokan

Setiap kecocokan menggabungkan dua atau beberapa entitas ke dalam satu entitas terkonsolidasi. Pada waktu bersamaan, ia menyimpan rekaman pelanggan unik. Urutan kecocokan menunjukkan urutan di mana sistem mencoba mencocokkan catatan.

> [!IMPORTANT]
> Entitas pertama disebut entitas utama, yang berfungsi sebagai dasar untuk profil terpadu Anda. Entitas tambahan yang dipilih akan ditambahkan ke entitas ini.
>
> Pertimbangan penting:
>
> - Pilih entitas dengan data profil terlengkap dan andal tentang pelanggan Anda sebagai entitas utama.
> - Pilih entitas yang memiliki beberapa atribut yang sama dengan entitas lain (misalnya, nama, nomor telepon, atau alamat email) sebagai entitas utama.

1. **Pada halaman Kondisi** yang cocok, gunakan panah naik dan turun untuk memindahkan entitas dalam urutan yang Anda inginkan, atau seret dan lepas. Misalnya, pilih **eCommerceCustomers sebagai entitas utama dan** loyCustomers **sebagai** entitas kedua.

1. Untuk memiliki setiap rekaman dalam entitas sebagai pelanggan unik terlepas dari apakah kecocokan ditemukan, pilih **Sertakan semua rekaman**. Rekaman apa pun dalam entitas ini yang tidak cocok dengan rekaman di entitas lain disertakan dalam profil terpadu. Rekor yang tidak memiliki kecocokan disebut singletons.
  
Entitas *utama Contacts:eCommerce* dicocokkan dengan entitas *berikutnya CustomerLoyalty:Loyalty*. Himpunan data yang dihasilkan dari langkah pencocokan pertama dicocokkan dengan entitas berikut jika Anda memiliki lebih dari dua entitas.

:::image type="content" source="media/m3_match.png" alt-text="Cuplikan layar urutan kecocokan yang dipilih untuk entitas." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Menentukan aturan untuk pasangan yang cocok

Aturan kecocokan menentukan logika dengan mana sepasang entitas tertentu akan dicocokkan. Aturan terdiri dari satu atau lebih kondisi.

Peringatan di samping nama entitas berarti tidak ada aturan kecocokan yang ditentukan untuk pasangan yang cocok.

1. Pilih **Tambahkan aturan untuk pasangan entitas untuk menentukan aturan** kecocokan.

1. **Di panel Tambahkan aturan, konfigurasikan kondisi untuk aturan** tersebut.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Cuplikan layar panel Tambahkan aturan.":::

   - **Pilih Entitas/Bidang (baris pertama)**: Pilih entitas dan atribut yang kemungkinan unik untuk pelanggan. Contohnya, nomor telepon atau alamat email. Hindari pencocokan menurut atribut jenis aktivitas. Misalnya, ID pembelian kemungkinan tidak akan menemukan kecocokan pada jenis rekaman lain.

   - **Pilih Entitas/Bidang (baris kedua)**: Pilih atribut yang terkait dengan atribut entitas yang ditentukan di baris pertama.

   - **Normalkan**: Pilih dari pilihan normalisasi berikut untuk atribut yang dipilih.
     - **Angka**: Mengonversi sistem angka lain, seperti angka Romawi, menjadi angka Arab. *VIII* menjadi *8*.
     - **Simbol**: Menghapus semua simbol dan karakter khusus. *Head&Shoulder* menjadi *HeadShoulder*.
     - **Teks menjadi huruf kecil: Mengonversi semua karakter menjadi huruf** kecil. *SEMUA KAPITAL dan Huruf Judul* menjadi *semua kapital dan huruf judul*.
     - **Jenis (Telepon, Nama, Alamat, Organisasi)**: Menstandarkan nama, judul, nomor telepon, alamat, dan organisasi.
     - **Unicode ke ASCII: Mengonversi notasi unicode ke karakter ASCII**. */u00B2* menjadi *2*.
     - **Spasi**: Menghapus semua spasi. *Hello   World* menjadi *Hello World*.

   - **Presisi**: Atur tingkat presisi untuk diterapkan untuk kondisi ini.
     - **Dasar**: Pilih dari *Rendah (30%), Sedang (60%), Tinggi (80%),* *·* *dan* *Tepat (100%).* Pilih **Persis** untuk hanya mencocokkan rekaman yang cocok 100 persen.
     - **Kustom**: Atur persentase yang harus cocok dengan rekaman. Sistem hanya akan mencocokkan rekaman yang melewati ambang batas ini.

   - **Nama: Nama** untuk aturan.

1. Untuk mencocokkan entitas hanya jika atribut memenuhi beberapa kondisi, pilih **Tambahkan Tambahkan** > **kondisi untuk menambahkan lebih banyak kondisi** ke aturan kecocokan. Kondisi terhubung dengan operator AND logis dan dengan demikian hanya dijalankan jika semua kondisi terpenuhi.

1. Secara opsional, pertimbangkan opsi lanjutan seperti [pengecualian atau](#add-exceptions-to-a-rule) kondisi [kecocokan](#specify-custom-match-conditions) kustom.

1. Pilih **Selesai** untuk menyelesaikan aturan.

1. Atau, [tambahkan aturan lainnya](#add-rules-to-a-match-pair).

1. Klik **Berikutnya**.

> [!div class="nextstepaction"]
> [Langkah berikutnya: Menyatukan bidang](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Menambahkan aturan ke pasangan yang cocok

Aturan kecocokan menunjukkan rangkaian kondisi. Untuk mencocokkan entitas berdasarkan kondisi berdasarkan beberapa atribut, tambahkan lebih banyak aturan.

1. Pilih **Tambahkan aturan** pada entitas yang ingin Anda tambahkan aturannya.

1. Ikuti langkah-langkah dalam [Menentukan aturan untuk pasangan yang cocok](#define-rules-for-match-pairs).

> [!NOTE]
> Urutan aturan itu penting. Algoritme pencocokan mencoba mencocokkan catatan pelanggan tertentu berdasarkan aturan pertama Anda dan berlanjut ke aturan kedua hanya jika tidak ada kecocokan yang diidentifikasi dengan aturan pertama.

## <a name="advanced-options"></a>Pilihan tingkat lanjut

### <a name="add-exceptions-to-a-rule"></a>Menambahkan pengecualian ke aturan

Dalam kebanyakan kasus, pencocokan entitas mengarah ke profil pelanggan unik dengan data terkonsolidasi. Untuk mengatasi kasus positif palsu dan negatif palsu yang jarang terjadi, tentukan pengecualian untuk aturan kecocokan. Pengecualian diterapkan setelah memproses aturan pertandingan dan menghindari pencocokan semua catatan, yang memenuhi kriteria pengecualian.

Misalnya, jika aturan kecocokan Anda menggabungkan nama belakang, kota, dan tanggal lahir, sistem akan mengidentifikasi anak kembar dengan nama belakang yang sama yang tinggal di kota yang sama dengan profil yang sama. Anda dapat menentukan pengecualian yang tidak cocok dengan profil jika nama depan di entitas yang Anda gabungkan tidak sama.

1. **Di panel Edit aturan**, pilih **Tambahkan** > **pengecualian**.

1. Tentukan kriteria pengecualian.

1. Untuk menyimpan aturan, pilih **Selesai**.

### <a name="specify-custom-match-conditions"></a>Menentukan kondisi kecocokan kustom

Tentukan kondisi yang menimpa logika kecocokan default. Ada empat opsi yang tersedia:

|Opsi  |Description |Contoh  |
|---------|---------|---------|
|Selalu cocok     | Menentukan nilai untuk kunci utama yang selalu cocok.         |  Selalu cocokkan baris dengan kunci utama 12345 *dengan baris dengan kunci* *utama 54321*.       |
|Tidak pernah cocok     | Menentukan nilai untuk kunci utama yang tidak pernah cocok.        | Jangan pernah mencocokkan baris dengan kunci utama 12345 dengan baris dengan kunci *utama* 54321 *.*        |
|Lewati            | Menentukan nilai yang harus selalu diabaikan oleh sistem dalam fase pertandingan. |  Abaikan nilai *11111* dan *Tidak Diketahui* selama pertandingan.        |
|Pemetaan alias    | Mendefinisikan nilai yang harus dipertimbangkan sistem sebagai nilai yang sama.         | Anggaplah *Joe* setara dengan *Joseph*.        |

1. Pilih **Kustom**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Tombol kustom":::

1. Pilih Jenis **kustom** dan pilih **Unduh templat**. Ganti nama templat tanpa menggunakan spasi. Gunakan template terpisah untuk setiap opsi pertandingan.

1. Buka file template yang diunduh dan isi detailnya. Template berisi bidang untuk menentukan entitas dan nilai kunci primer entitas yang akan digunakan dalam pencocokan kustom. Nama entitas peka huruf besar/kecil. Misalnya, jika Anda menginginkan kunci utama *12345* dari entitas *Penjualan* agar selalu cocok dengan kunci utama *34567* dari entitas *Kontak*, isi template:
   - Entity1: Penjualan
   - Entity1Key: 12345
   - Entity2: Kontak
   - Entity2Key: 34567

   File template yang sama dapat menentukan rekaman kecocokan kustom dari beberapa entitas.

   > [!NOTE]
   > Jika Anda ingin menentukan pencocokan kustom untuk deduplikasi pada entitas, berikan entitas yang sama seperti Entity1 dan Entity2 dan atur nilai kunci utama yang berbeda. Anda harus menentukan setidaknya satu aturan deduplikasi ke entitas untuk menggunakan pencocokan kustom.

1. Setelah menambahkan semua override, simpan file template.

1. Buka **data** > **sumber data** dan serap file template sebagai entitas baru.

1. Setelah mengunggah file, pilih **opsi Kustom** lagi. Pilih entitas yang diperlukan dari menu tarik-turun dan pilih **Selesai**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Cuplikan layar dialog untuk memilih menimpa skenario kecocokan kustom.":::

1. Menerapkan kecocokan kustom tergantung pada opsi pencocokan yang ingin Anda gunakan.

   - Untuk **Selalu cocok atau** Jangan pernah **cocok**, lanjutkan ke langkah berikutnya.
   - Untuk **Pemetaan** bypass **atau Alias, pilih** Edit **pada aturan kecocokan yang sudah ada atau** buat aturan baru. Di menu tarik-turun Normalisasi, pilih opsi Bypass **kustom atau** pemetaan **Alias dan pilih** **Selesai**.

1. Pilih **Selesai** pada **panel Kustom** untuk menerapkan konfigurasi pencocokan kustom.

   Setiap file template yang diserap adalah sumber data sendiri. Jika ditemukan catatan yang memerlukan perlakuan pencocokan khusus, perbarui sumber data yang sesuai. Pembaruan akan digunakan selama proses penyatuan berikutnya. Misalnya, Anda mengidentifikasi anak kembar dengan nama yang hampir sama yang tinggal di alamat yang sama yang telah digabungkan sebagai satu orang. Perbarui sumber data untuk mengidentifikasi si kembar sebagai catatan unik yang terpisah.

> [!div class="nextstepaction"]
> [Langkah berikutnya: Menyatukan bidang](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
