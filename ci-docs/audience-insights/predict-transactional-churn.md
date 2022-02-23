---
title: Transaksi churn prediksi (berisi video)
description: Prediksi apakah pelanggan berisiko tidak lagi membeli atau layanan Anda.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 602a86a67006925faac00add8e089d28f7071c14
ms.sourcegitcommit: 15b1521041149716f8031cfa6d0dc61a56a5e2ff
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967751"
---
# <a name="transaction-churn-prediction-preview"></a>prediksi kehilangan transaksi (Pratinjau)

Prediksi kehilangan pelanggan transaksional membantu memprediksi apakah pelanggan tidak lagi membeli produk atau layanan Anda di periode waktu tertentu. Anda dapat membuat prediksi kehilangan pelanggan yang baru di **intelijen** > **prediksi**. Pilih **prediksi saya** untuk melihat prediksi lain yang Anda buat. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Untuk lingkungan berdasarkan akun bisnis, kita dapat memperkirakan volume transaksional untuk akun, dan juga kombinasi akun, dan tingkat informasi lain seperti kategori produk. Menambahkan dimensi dapat membantu mengetahui seberapa mungkin akun "Contoso" akan berhenti membeli kategori produk "alat tulis kantor". Selain itu, untuk akun bisnis, kita juga dapat menggunakan AI untuk menghasilkan daftar kemungkinan alasan mengapa akun kemungkinan bergolak untuk kategori informasi tingkat kedua.

> [!TIP]
> Coba tutorial untuk prediksi kehilangan transaksi dengan menggunakan data sampel: [Panduan sampel prediksi kehilangan transaksi (pratinjau)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Prasyarat

# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

- Sekurangnya [izin kontributor](permissions.md) di Customer Insights.
- Pengetahuan bisnis untuk memahami apa arti kehilangan untuk bisnis Anda. Kami mendukung definisi kehilangan pelanggan berdasarkan waktu, yang berarti pelanggan dianggap bergejolak setelah periode tanpa pembelian.
- Data tentang transaksi/pembelian dan Riwayat mereka:
    - Pengidentifikasi transaksi untuk membedakan pembelian/transaksi.
    - Pengidentifikasi pelanggan untuk mencocokkan transaksi dengan pelanggan Anda.
    - Tanggal aktivitas transaksi, yang menentukan tanggal terjadinya transaksi.
    - Skema data semantik untuk pembelian/transaksi memerlukan informasi berikut:
        - **ID transaksi**: pengidentifikasi unik pembelian atau transaksi.
        - **Tanggal transaksi**: tanggal pembelian atau transaksi.
        - **Nilai transaksi**: mata uang/nilai numerik dari transaksi/item.
        - (Opsional) **ID Produk unik**: id produk atau layanan yang dibeli jika data Anda berada pada tingkat item baris.
        - (Opsional) **Apakah transaksi ini adalah retur**: bidang benar/salah yang mengidentifikasi apakah transaksi tersebut merupakan retur atau tidak. Jika **nilai transaksi** negatif, kita juga akan menggunakan informasi ini untuk menyimpulkan retur.
- (Opsional) Data tentang aktivitas pelanggan:
    - Pengidentifikasi aktivitas untuk membedakan aktivitas dari jenis yang sama.
    - Pengidentifikasi pelanggan untuk memetakan aktivitas dengan pelanggan Anda.
    - Informasi aktivitas berisi nama dan tanggal aktivitas.
    - Skema data semantik untuk aktivitas pelanggan mencakup:
        - **Kunci primer:** pengidentifikasi unik untuk aktivitas. Misalnya, kunjungan situs web atau rekaman penggunaan yang menunjukkan pelanggan mencoba sampel produk Anda.
        - **Cap waktu:** tanggal dan waktu aktivitas yang diidentifikasi oleh kunci primer.
        - **Aktivitas**: nama aktivitas yang ingin Anda gunakan. Misalnya, bidang yang disebut "UserAction" di toko kelontong mungkin adalah kupon yang digunakan oleh pelanggan.
        - **Rincian:** informasi rinci tentang aktivitas. Misalnya, bidang yang disebut "CouponValue" di toko kelontong mungkin merupakan nilai mata uang kupon.

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

- Sekurangnya [izin kontributor](permissions.md) di Customer Insights.
- Pengetahuan bisnis untuk memahami apa arti kehilangan untuk bisnis Anda. Kami mendukung definisi kehilangan pelanggan berdasarkan waktu, yang berarti pelanggan dianggap bergejolak setelah periode tanpa pembelian.
- Data tentang transaksi/pembelian dan Riwayat mereka:
    - Pengidentifikasi transaksi untuk membedakan pembelian/transaksi.
    - Pengidentifikasi pelanggan untuk mencocokkan transaksi dengan pelanggan Anda.
    - Tanggal aktivitas transaksi, yang menentukan tanggal terjadinya transaksi.
    - Skema data semantik untuk pembelian/transaksi memerlukan informasi berikut:
        - **ID transaksi**: pengidentifikasi unik pembelian atau transaksi.
        - **Tanggal transaksi**: tanggal pembelian atau transaksi.
        - **Nilai transaksi**: mata uang/nilai numerik dari transaksi/item.
        - (Opsional) **ID Produk unik**: id produk atau layanan yang dibeli jika data Anda berada pada tingkat item baris.
        - (Opsional) **Apakah transaksi ini adalah retur**: bidang benar/salah yang mengidentifikasi apakah transaksi tersebut merupakan retur atau tidak. Jika **nilai transaksi** negatif, kita juga akan menggunakan informasi ini untuk menyimpulkan retur.
- (Opsional) Data tentang aktivitas pelanggan:
    - Pengidentifikasi aktivitas untuk membedakan aktivitas dari jenis yang sama.
    - Pengidentifikasi pelanggan untuk memetakan aktivitas dengan pelanggan Anda.
    - Informasi aktivitas berisi nama dan tanggal aktivitas.
    - Skema data semantik untuk aktivitas pelanggan mencakup:
        - **Kunci primer:** pengidentifikasi unik untuk aktivitas. Misalnya, kunjungan situs web atau rekaman penggunaan yang menunjukkan pelanggan mencoba sampel produk Anda.
        - **Cap waktu:** tanggal dan waktu aktivitas yang diidentifikasi oleh kunci primer.
        - **Aktivitas**: nama aktivitas yang ingin Anda gunakan. Misalnya, bidang yang disebut "UserAction" di toko kelontong mungkin adalah kupon yang digunakan oleh pelanggan.
        - **Rincian:** informasi rinci tentang aktivitas. Misalnya, bidang yang disebut "CouponValue" di toko kelontong mungkin merupakan nilai mata uang kupon.
- (Opsional) Data tentang pelanggan Anda:
    - Data ini hharus selaras terhadap atribut lebih statis untuk memastikan model berkinerja terbaik.
    - Skema data semantis untuk data pelanggan mencakup:
        - **CustomerID:** Pengidentifikasi unik untuk pelanggan.
        - **Tanggal Dibuat:** Tanggal awal pelanggan ditambahkan.
        - **Negara Bagian atau Provinsi:** Lokasi negara bagian atau provinsi pelanggan.
        - **Negara:** Negara pelanggan.
        - **Industri:** Jenis industri pelanggan. Misalnya, bidang yang disebut "Industri" dalam pemanggang kopi dapat menunjukkan apakah pelanggan tersebut adalah pelanggan ritel.
        - **Klasifikasi:** Kategorisasi pelanggan untuk bisnis Anda. Contohnya, bidang yang disebut "ValueSegment" dalam mesin pemanggang kopi dapat menjadi tingkat pelanggan berdasarkan ukuran pelanggan.

---

- Karakteristik Data yang Disarankan:
    - Data historis yang memadai: Data transaksi untuk setidaknya dua kali lipat dari periode waktu yang dipilih. Sebaiknya, dua hingga tiga tahun riwayat transaksi. 
    - Beberapa pembelian per pelanggan: Idealnya setidaknya dua transaksi per Pelanggan.
    - Jumlah pelanggan: Setidaknya 10 profil pelanggan, lebih disukai lebih dari 1.000 pelanggan unik. Model akan gagal dengan kurang dari 10 pelanggan dan data historis yang tidak mencukupi.
    - Kelengkapan data: Kurang dari 20% nilai yang hilang di bidang data entitas yang disediakan.

> [!NOTE]
> Untuk bisnis dengan frekuensi pembelian pelanggan yang tinggi (setiap beberapa minggu) disarankan untuk memilih periode prediksi dan definisi kehilangan yang lebih pendek. Untuk frekuensi pembelian rendah (setiap beberapa bulan atau setahun sekali), pilih periode prediksi dan definisi kehilangan yang lebih panjang.

## <a name="create-a-transaction-churn-prediction"></a>Buat prediksi kehilangan transaksi

1. Di Customer Insights, buka **Intelijen** > **Prediksi**.

1. Pilih petak **model kehilangan pelanggan (pratinjau)** dan pilih **gunakan model ini**.

1. Di **panel model churn Pelanggan (pratinjau),** pilih Transaksi dan **pilih** **Mulai**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Tangkapan layar dengan pilihan transaksi yang dipilih dalam panel model kehilangan pelanggan.":::
 
### <a name="name-model"></a>Beri nama model

1. Berikan nama model untuk membedakannya dari model lain.

1. Berikan nama untuk entitas output hanya menggunakan huruf dan angka, tanpa spasi. Itulah nama yang akan digunakan oleh entitas model. 

1. Pilih **Selanjutnya**.

### <a name="define-customer-churn"></a>Tentukan kehilangan pelanggan

1. Atur **jendela prediksi**. Misalnya, memprediksi risiko kehilangan pelanggan untuk pelanggan Anda selama 90 hari berikutnya untuk menyelaraskan upaya retensi pemasaran Anda. Memprediksi risiko kehilangan pelanggan selama periode waktu yang lebih lama atau lebih singkat dapat membuatnya lebih sulit untuk mengatasi faktor dalam profil risiko kehilangan pelanggan Anda, namun tergantung pada kebutuhan bisnis Anda yang spesifik.
   >[!TIP]
   > Anda dapat memilih **Simpan draf** kapan saja untuk menyimpan prediksi sebagai draf. Anda akan menemukan draf prediksi dalam tab **prediksi saya** untuk melanjutkan.

1. Masukkan jumlah hari untuk menentukan churn di **bidang definisi** Churn. Contohnya, jika pelanggan tidak melakukan pembelian dalam 30 hari terakhir, maka pelanggan dapat dianggap pergi dari bisnis Anda. 

1. Untuk melanjutkan, klik **Berikutnya**.

### <a name="add-required-data"></a>Tambahkan data wajib

1. Pilih **Tambah data** dan pilih jenis aktivitas pada panel sisi yang berisi informasi transaksi atau riwayat pembelian yang diperlukan.

1. Di bawah **Pilih** aktivitas, pilih aktivitas tertentu dari tipe aktivitas yang dipilih yang ingin anda fokuskan.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Panel sisi yang menunjukkan pemilihan aktivitas tertentu dalam jenis semantik.":::

   Jika Anda belum memetakan aktivitas ke jenis semantis, pilih **Edit** untuk melakukannya. Pengalaman terpandu untuk memetakan aktivitas semantis akan terbuka. Petakan data Anda ke bidang terkait di jenis aktivitas yang dipilih.

1. Petakan atribut semantis ke bidang yang diperlukan untuk menjalankan model. Jika bidang di bawah ini tidak terisi, konfigurasikan relasi dari entitas Riwayat Pembelian Anda ke entitas *pelanggan*. Pilih **Simpan**.

1. Dalam **langkah Tambahkan data yang** diperlukan, pilih **Berikutnya untuk melanjutkan jika Anda tidak ingin menambahkan lebih banyak** aktivitas.


# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Tambahkan data tambahan (opsional)

Konfigurasikan relasi dari entitas aktivitas pelanggan Anda ke entitas *Pelanggan*.

1. Pilih bidang yang mengidentifikasi pelanggan di tabel aktivitas pelanggan. Hal ini dapat langsung terkait dengan ID pelanggan utama entitas *pelanggan* Anda.

1. Pilih entitas yang merupakan entitas *Pelanggan* utama Anda.

1. Masukkan nama yang mendeskripsikan relasi.

#### <a name="customer-activities"></a>Aktivitas pelanggan

1. Atau, pilih **Tambah data** untuk **aktivitas pelanggan**.

1. Pilih jenis aktivitas semantis berisi data yang akan digunakan, lalu pilih satu atau beberapa aktivitas dalam bagian **Aktivitas**.

1. Pilih jenis aktivitas yang cocok dengan jenis aktivitas Pelanggan yang Anda konfigurasikan. Pilih **Buat baru** dan pilih jenis aktivitas yang tersedia atau buat jenis baru.

1. Pilih **Berikutnya** lalu **Simpan**.

1. Jika Anda memiliki aktivitas pelanggan lain yang ingin Anda masukkan, ulangi langkah di atas.

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

### <a name="select-prediction-level"></a>Pilih Tingkat prediksi

Sebagian besar prediksi dibuat pada tingkat pelanggan. Dalam situasi tertentu, hal tersebut mungkin tidak cukup rinci untuk memenuhi kebutuhan bisnis Anda. Anda dapat menggunakan fitur ini untuk memperkirakan kehilangan cabang pelanggan, misalnya, dan bukan untuk pelanggan secara keseluruhan.

1. Untuk membuat prediksi pada tingkat lebih rinci dari pelanggan, **pilih entitas untuk tingkat kedua**. Jika pilihan tidak tersedia, pastikan Anda telah menyelesaikan bagian sebelumnya.

1. Perluas entitas yang akan dipilih tingkat kedua, atau gunakan kotak filter pencarian untuk memfilter pilihan yang dipilih.

1. Pilih atribut yang akan digunakan sebagai tingkat kedua, lalu pilih **Tambah**.

1. Pilih **Selanjutnya**.

> [!NOTE]
> Entitas yang tersedia di bagian ini ditampilkan karena memiliki relasi dengan entitas yang Anda pilih di bagian sebelumnya. Jika Anda tidak melihat entitas yang ingin Anda tambahkan, pastikan entitas memiliki relasi valid yang ada di **Relasi**. Hanya Relasi banyak ke satu dan satu-ke-satu yang valid untuk konfigurasi ini.

### <a name="add-additional-data-optional"></a>Tambahkan data tambahan (opsional)

Konfigurasikan relasi dari entitas aktivitas pelanggan Anda ke entitas *Pelanggan*.

1. Pilih bidang yang mengidentifikasi pelanggan di tabel aktivitas pelanggan. Hal ini dapat langsung terkait dengan ID pelanggan utama entitas *pelanggan* Anda.

1. Pilih entitas yang merupakan entitas *Pelanggan* utama Anda.

1. Masukkan nama yang mendeskripsikan relasi.

#### <a name="customer-activities"></a>Aktivitas pelanggan

1. Atau, pilih **Tambah data** untuk **aktivitas pelanggan**.

1. Pilih jenis aktivitas semantis berisi data yang akan digunakan, lalu pilih satu atau beberapa aktivitas dalam bagian **Aktivitas**.

1. Pilih jenis aktivitas yang cocok dengan jenis aktivitas Pelanggan yang Anda konfigurasikan. Pilih **Buat baru** dan pilih jenis aktivitas yang tersedia atau buat jenis baru.

1. Pilih **Berikutnya** lalu **Simpan**.

1. Jika Anda memiliki aktivitas pelanggan lain yang ingin Anda masukkan, ulangi langkah di atas.

#### <a name="customers-data"></a>Data pelanggan

1. Atau, pilih **Tambah data** untuk **data Pelanggan**.

1. Petakan atribut semantis ke bidang pada data pelanggan Anda sendiri sebagai teridentifikasi. Data pada bidang yang digunakan tidak boleh sering berubah untuk memastikan kinerja terbaik model. Contohnya, memilih bidang untuk "Klasifikasi" yang berubah setiap bulan hanya akan memiliki nilai terakhir yang digunakan di prediksi, meskipun secara historis nilai yang sama mungkin tidak berlaku untuk pelanggan saat membangun pola prediksi baru.

1. Pilih **Selanjutnya**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Memberikan daftar opsional akun tolok ukur

Tambahkan daftar pelanggan bisnis dan akun yang akan digunakan sebagai tolok ukur. Anda akan mendapatkan [rincian untuk akun tolok ukur ini](#review-a-prediction-status-and-results) termasuk skor kehilangan dan fitur paling berpengaruh yang mempengaruhi prediksi kehilangannya.

1. Pilih **+ Tambahkan pelanggan**.

1. Pilih pelanggan yang berfungsi sebagai tolok ukur.

1. Untuk melanjutkan, klik **Berikutnya**.

---

### <a name="set-schedule-and-review-configuration"></a>Mengatur konfigurasi jadwal dan ulasan

1. Atur frekuensi untuk melatih ulang model Anda. Pengaturan ini penting untuk memperbarui keakuratan prediksi karena data baru terserap. Sebagian besar bisnis dapat melatih sekali per bulan dan mendapatkan akurasi yang baik untuk prediksi mereka.

1. Pilih **Selanjutnya**.

1. Tinjau konfigurasi prediksi. Anda dapat kembali ke langkah sebelumnya dengan memilih **Edit** di dalam nilai yang ditampilkan. Atau Anda dapat memilih langkah konfigurasi dari indikator progres.

1. Jika semua nilai dikonfigurasi dengan benar, pilih **Simpan dan jalankan** untuk memulai proses prediksi. Pada **tab prediksi saya**, Anda dapat melihat status prediksi Anda. Proses dapat berlangsung selama beberapa jam hingga selesai, tergantung pada jumlah data yang digunakan dalam prediksi.

## <a name="review-a-prediction-status-and-results"></a>Meninjau status dan hasil prediksi

1. Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.

1. Pilih prediksi yang ingin Anda tinjau.
   - **Nama prediksi**: nama prediksi yang diberika saat membuatnya.
   - **jenis prediksi**: jenis model yang digunakan untuk prediksi
   - **Entitas output**: nama entitas untuk menyimpan output dari prediksi. Anda dapat menemukan entitas dengan nama ini pada **data** > **entitas**.
     Dalam entitas output, *ChurnScore* adalah probabilitas kehilangan yang diprediksi dan *IsChurn* adalah label biner berdasarkan *ChurnScore* dengan ambang batas 0,5. Ambang batas default mungkin tidak berfungsi untuk skenario Anda. [Buat segmen baru](segments.md#create-a-new-segment) dengan ambang batas pilihan Anda.
     Tidak semua pelanggan harus merupakan pelanggan aktif. Beberapa dari mereka mungkin tidak memiliki aktivitas untuk waktu yang lama dan dianggap sudah pergi, berdasarkan definisi kehilangan Anda. Memperkirakan risiko kehilangan bagi pelanggan yang telah pergi tidak berguna karena bukan audiens yang menarik minat.
   - **Bidang terprediksi**: bidang ini hanya diisi untuk beberapa jenis prediksi, dan tidak digunakan dalam prediksi kehilangan pelanggan.
   - **Status**: Status prediksi dijalankan.
        - **mengantri**: prediksi sedang menunggu proses lain untuk dijalankan.
        - **Menyegarkan**: prediksi saat ini berjalan untuk menghasilkan hasil yang akan mengalir ke entitas output.
        - **gagal**: prediksi yang jalankan gagal. [Tinjau log](manage-predictions.md#troubleshoot-a-failed-prediction) untuk rincian selengkapnya.
        - **berhasil**: prediksi telah berhasil. Pilih **Lihat** di bawah elips vertikal untuk meninjau prediksi
   - **Diedit**: tanggal konfigurasi untuk prediksi telah diubah.
   - **Terakhir disegarkan**: tanggal prediksi yang disegarkan dihasilkan dalam entitas output.

1. Pilih elips vertikal di samping prediksi yang ingin Anda tinjau hasilnya dan pilih **Lihat**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="lihat kontrol untuk melihat hasil prediksi.":::

# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

1. Terdapat tiga bagian utama data dalam halaman hasil:
   - **Performa model pelatihan**: A, B, atau C adalah Skor yang mungkin. Skor ini menunjukkan performa prediksi, dan dapat membantu Anda membuat keputusan untuk menggunakan hasil yang tersimpan di entitas output. Skor ditentukan berdasarkan aturan berikut: 
        - **A** bila model ini secara akurat memprediksi minimal 50% dari total prediksi, dan bila persentase prediksi yang akurat untuk pelanggan yang pergi lebih besar dari tingkat dasar setidaknya 10%.
            
        - **B** bila model ini secara akurat memprediksi minimal 50% dari total prediksi, dan bila persentase prediksi yang akurat untuk pelanggan yang pergi adalah hingga 10% lebih besar dari tingkat dasar.
            
        - **C** bila model ini secara akurat memprediksi kurang 50% dari total prediksi, atau bila persentase prediksi yang akurat untuk pelanggan yang pergi kurang dari tingkat dasar.
               
        - **Dasar** memerlukan input periode waktu prediksi untuk model (misalnya, satu tahun) dan model membuat pecahan waktu yang berbeda dengan membaginya dengan 2 hingga mencapai satu bulan atau kurang. Ia menggunakan pecahan ini untuk membuat aturan bisnis untuk pelanggan yang belum membeli dalam jangka waktu ini. Pelanggan ini dianggap sebagai pergi. Aturan bisnis berbasis waktu dengan kemampuan tertinggi untuk memprediksi siapa yang cenderung pergi dipilih sebagai model dasar.
            
    - **Kecenderungan untuk kehilangan (jumlah pelanggan)**: grup pelanggan berdasarkan prediksi risiko kehilangan. Data ini dapat membantu Anda nanti jika Anda ingin membuat segmen pelanggan dengan risiko kehilangan tinggi. Segmen tersebut membantu memahami tempat batas Anda untuk keanggotaan segmen.
       
    - **Faktor yang paling berpengaruh**: ada banyak faktor yang diperhitungkan saat membuat prediksi. Masing-masing faktor memiliki kepentingan yang dihitung untuk membuat prediksi model agregat. Anda dapat menggunakan faktor-faktor tersebut untuk membantu memvalidasi prediksi hasil, atau Anda dapat menggunakan informasi ini nanti untuk [membuat segmen](segments.md) yang dapat membantu mempengaruhi risiko kehilangan untuk para pelanggan.


# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

1. Terdapat tiga bagian utama data dalam halaman hasil:
   - **Performa model pelatihan**: A, B, atau C adalah Skor yang mungkin. Skor ini menunjukkan performa prediksi, dan dapat membantu Anda membuat keputusan untuk menggunakan hasil yang tersimpan di entitas output. Skor ditentukan berdasarkan aturan berikut: 
        - **A** bila model ini secara akurat memprediksi minimal 50% dari total prediksi, dan bila persentase prediksi yang akurat untuk pelanggan yang pergi lebih besar dari tingkat dasar setidaknya 10%.
            
        - **B** bila model ini secara akurat memprediksi minimal 50% dari total prediksi, dan bila persentase prediksi yang akurat untuk pelanggan yang pergi adalah hingga 10% lebih besar dari tingkat dasar.
            
        - **C** bila model ini secara akurat memprediksi kurang 50% dari total prediksi, atau bila persentase prediksi yang akurat untuk pelanggan yang pergi kurang dari tingkat dasar.
               
        - **Dasar** memerlukan input periode waktu prediksi untuk model (misalnya, satu tahun) dan model membuat pecahan waktu yang berbeda dengan membaginya dengan 2 hingga mencapai satu bulan atau kurang. Ia menggunakan pecahan ini untuk membuat aturan bisnis untuk pelanggan yang belum membeli dalam jangka waktu ini. Pelanggan ini dianggap sebagai pergi. Aturan bisnis berbasis waktu dengan kemampuan tertinggi untuk memprediksi siapa yang cenderung pergi dipilih sebagai model dasar.
            
    - **Kecenderungan untuk kehilangan (jumlah pelanggan)**: grup pelanggan berdasarkan prediksi risiko kehilangan. Data ini dapat membantu Anda nanti jika Anda ingin membuat segmen pelanggan dengan risiko kehilangan tinggi. Segmen tersebut membantu memahami tempat batas Anda untuk keanggotaan segmen.
       
    - **Faktor yang paling berpengaruh**: ada banyak faktor yang diperhitungkan saat membuat prediksi. Masing-masing faktor memiliki kepentingan yang dihitung untuk membuat prediksi model agregat. Anda dapat menggunakan faktor-faktor tersebut untuk membantu memvalidasi prediksi hasil, atau Anda dapat menggunakan informasi ini nanti untuk [membuat segmen](segments.md) yang dapat membantu mempengaruhi risiko kehilangan untuk para pelanggan.


1. Untuk akun bisnis, Anda akan menemukan halaman informasi **analisis fitur berpengaruh**. Ini berisi empat bagian data:

    - Item yang dipilih di panel kanan menentukan konten pada halaman ini. Memilih item dari **pelanggan Atas** atau **pelanggan Tolok ukur**. Kedua daftar tersebut diurutkan dengan mengurangi nilai skor kehilangan, apakah skor hanya untuk pelanggan maupun skor gabungan untuk pelanggan dan tingkat kedua seperti kategori produk.
        
        - **Pelanggan teratas**: Daftar 10 pelanggan yang memiliki risiko tertinggi pergi dan risiko kehilangan terendah berdasarkan skor kehilangan mereka. 
        - **Pelanggan tolok ukur**: Daftar hingga 10 pelanggan yang dipilih saat mengkonfigurasi model.
 
    - **Skor kehilangan:** Menampilkan skor kehilangan untuk item yang dipilih di panel kanan.
    
    - **Distribusi risiko kehilangan:** Menunjukkan distribusi risiko kehilangan di seluruh pelanggan dan persentil tempat pelanggan yang dipilih berada. 
    
    - **Fitur teratas yang meningkatkan dan mengurangi risiko kehilangan**: Untuk item yang dipilih di panel kanan, terdapat lima fitur teratas yang meningkatkan dan mengurangi risiko kehilangan. Untuk setiap fitur yang berpengaruh, Anda akan menemukan nilai fitur untuk item tersebut dan pengaruhnya pada skor kehilangan. Nilai rata-rata setiap fitur di segmen kehilangan pelanggan rendah, sedang, dan tinggi juga ditampilkan. Peran ini akan membantu lebih mengkontekstualisasi nilai dari fitur berpengaruh teratas untuk item yang dipilih dan membandingkannya dengan segmen kehilangan pelanggan yang rendah, sedang, dan tinggi.

       - Rendah: akun atau kombinasi akun dan tingkat kedua dengan skor kehilangan antara 0 hingga 0,33
       - Sedang: akun atau kombinasi akun dan tingkat kedua dengan skor kehilangan antara 0,33 hingga 0,66
       - Tinggi: akun atau kombinasi akun dan tingkat kedua dengan skor kehilangan lebih dari 0,66
    
       Bila Anda memperkirakan kehilangan pada tingkat akun, semua akun akan dipertimbangkan dalam memperoleh nilai fitur rata-rata untuk segmen kehilangan. Untuk prediksi kehilangan pada tingkat kedua untuk setiap akun, turunan segmen kehilangan bergantung pada tingkat kedua item yang dipilih di panel sisi. Misalnya, jika item memiliki tingkat kedua dari kategori produk = perlengkapan kantor, maka hanya item yang memiliki perlengkapan kantor karena kategori produk yang dipertimbangkan bila mengambil nilai fitur rata-rata untuk segmen kehilangan. Logika ini diterapkan untuk memastikan perbandingan wajar nilai fitur item dengan nilai rata-rata di segmen rendah, sedang, dan tinggi.

       Pada kasus tertentu, nilai rata-rata segmen kehilangan rendah, sedang, atau tinggi adalah kosong atau tidak tersedia karena tidak ada item yang merupakan milik segmen kehilangan terkait berdasarkan definisi di atas.
       
       > [!NOTE]
       > Kategorikan nilai dalam kolom rendah, sedang, dan tinggi rata-rata berbeda untuk fitur kategoris seperti negara atau industri. Karena keterangan tentang nilai fitur "rata-rata" tidak berlaku untuk fitur kategoris, nilai di kolom ini adalah perbandingan pelanggan pada segmen rendah, sedang, atau tinggi yang memiliki nilai sama dengan fitur kategoris dibandingkan item yang dipilih di panel sisi.

---

## <a name="manage-predictions"></a>Kelola prediksi

Anda dapat mengoptimalkan, memecahkan masalah, menyegarkan, atau menghapus prediksi. Tinjau laporan kegunaan data input untuk mengetahui cara membuat prediksi lebih cepat dan lebih dapat diandalkan. Untuk informasi lebih lanjut, buka [Kelola prediksi](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
