---
title: Churn transaksi prediksi (berisi video)
description: Prediksi apakah pelanggan berisiko tidak lagi membeli atau layanan Anda.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610516"
---
# <a name="predict-transaction-churn"></a>Memprediksi kehilangan transaksi

Prediksi kehilangan pelanggan transaksional membantu memprediksi apakah pelanggan tidak lagi membeli produk atau layanan Anda di periode waktu tertentu.

Anda harus memiliki pengetahuan bisnis untuk memahami apa arti churn bagi bisnis Anda. Kami mendukung definisi kehilangan pelanggan berdasarkan waktu, yang berarti pelanggan dianggap bergejolak setelah periode tanpa pembelian.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Untuk lingkungan berdasarkan akun bisnis, kita dapat memperkirakan volume transaksional untuk akun, dan juga kombinasi akun, dan tingkat informasi lain seperti kategori produk. Misalnya, menambahkan dimensi dapat membantu menentukan seberapa besar kemungkinan akun "Contoso" akan berhenti membeli kategori produk "alat tulis kantor.". Selain itu, untuk akun bisnis, kita juga dapat menggunakan AI untuk menghasilkan daftar kemungkinan alasan mengapa akun kemungkinan bergolak untuk kategori informasi tingkat kedua.

> [!TIP]
> Coba churn transaksi prediksi menggunakan data sampel: [Panduan sampel churn prediksi transaksi](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md).
- Setidaknya 10 profil pelanggan, lebih disukai lebih dari 1.000 pelanggan unik.
- Pengidentifikasi Pelanggan, pengidentifikasi unik untuk mencocokkan transaksi dengan pelanggan Anda.
- Data transaksi setidaknya dua kali lipat dari jangka waktu yang dipilih seperti dua hingga tiga tahun riwayat transaksi. Idealnya setidaknya dua transaksi per pelanggan. Riwayat transaksi harus mencakup:
  - **ID** Transaksi: Pengidentifikasi unik pembelian atau transaksi.
  - **Tanggal** Transaksi: Tanggal pembelian atau transaksi.
  - **Nilai transaksi**: Mata uang atau jumlah nilai numerik transaksi.
  - **ID** produk unik: ID produk atau layanan yang dibeli jika data Anda berada pada tingkat item baris.
  - **Apakah transaksi ini adalah pengembalian**: Bidang benar/salah yang mengidentifikasi apakah transaksi tersebut adalah pengembalian atau bukan. **Jika Nilai transaksi** negatif, kami menyimpulkan pengembalian.
- Data aktivitas pelanggan:
  - Pengidentifikasi Pelanggan, pengidentifikasi unik untuk memetakan aktivitas kepada pelanggan Anda.
  - **Kunci utama:** Pengidentifikasi unik untuk suatu aktivitas. Misalnya, kunjungan situs web atau rekaman penggunaan yang menunjukkan pelanggan mencoba sampel produk Anda.
  - **Stempel waktu:** Tanggal dan waktu peristiwa yang diidentifikasi oleh kunci utama.
  - **Acara:** Nama acara yang ingin Anda gunakan. Misalnya, bidang yang disebut "UserAction" di toko kelontong mungkin adalah kupon yang digunakan oleh pelanggan.
  - **Rincian:** informasi rinci tentang aktivitas. Misalnya, bidang yang disebut "CouponValue" di toko kelontong mungkin merupakan nilai mata uang kupon.
- Kurang dari 20% nilai yang hilang di bidang data entitas yang disediakan

Untuk akun bisnis (B-to-B), tambahkan data pelanggan yang selaras dengan atribut yang lebih statis untuk memastikan model berkinerja terbaik:
- **CustomerID:** Pengidentifikasi unik untuk pelanggan.
- **Tanggal Dibuat:** Tanggal pelanggan awalnya ditambahkan.
- **Negara Bagian atau Provinsi:** Lokasi negara bagian atau provinsi pelanggan.
- **Negara:** Negara pelanggan.
- **Industri:** Jenis industri pelanggan. Misalnya, bidang yang disebut "Industri" dalam pemanggang kopi dapat menunjukkan apakah pelanggan tersebut adalah pelanggan ritel.
- **Klasifikasi:** Kategorisasi pelanggan untuk bisnis Anda. Contohnya, bidang yang disebut "ValueSegment" dalam mesin pemanggang kopi dapat menjadi tingkat pelanggan berdasarkan ukuran pelanggan.

> [!NOTE]
> Untuk bisnis dengan frekuensi pembelian pelanggan yang tinggi (setiap beberapa minggu) disarankan untuk memilih periode prediksi dan definisi kehilangan yang lebih pendek. Untuk frekuensi pembelian rendah (setiap beberapa bulan atau setahun sekali), pilih periode prediksi dan definisi kehilangan yang lebih panjang.

## <a name="create-a-transaction-churn-prediction"></a>Buat prediksi kehilangan transaksi

1. Pergi ke **Prediksi** > **Intelijen**.

1. Pada tab **Buat**, pilih **Gunakan model** pada **petak peta model** churn Pelanggan.

1. Pilih **Transaksi** untuk jenis churn lalu **Mulai**.

1. **Namai model ini** dan **nama entitas Output** untuk membedakannya dari model atau entitas lain.

1. Pilih **Selanjutnya**.

### <a name="define-customer-churn"></a>Tentukan kehilangan pelanggan

Pilih **Simpan draf** kapan saja untuk menyimpan prediksi sebagai draf. Draf prediksi ditampilkan di tab **Prediksi** saya.

1. Atur jendela **prediksi**. Misalnya, memprediksi risiko kehilangan pelanggan untuk pelanggan Anda selama 90 hari berikutnya untuk menyelaraskan upaya retensi pemasaran Anda. Memprediksi risiko kehilangan pelanggan selama periode waktu yang lebih lama atau lebih singkat dapat membuatnya lebih sulit untuk mengatasi faktor dalam profil risiko kehilangan pelanggan Anda, namun tergantung pada kebutuhan bisnis Anda yang spesifik.

1. Masukkan jumlah hari untuk menentukan churn di **bidang definisi** Churn. Misalnya, jika pelanggan belum melakukan pembelian dalam 30 hari terakhir, mereka mungkin dianggap terombang-ambing untuk bisnis Anda.

1. Pilih **Selanjutnya**.

### <a name="add-purchase-history"></a>Tambah riwayat pembelian

1. Pilih **Tambahkan data** untuk **riwayat transaksi** Pelanggan.

1. Pilih jenis aktivitas semantik, **SalesOrder** atau **SalesOrderLine**, yang berisi informasi riwayat transaksi. Jika aktivitas belum disiapkan, pilih **di sini** dan buat.

1. Di bawah **Aktivitas**, jika atribut aktivitas dipetakan secara semantik saat aktivitas dibuat, pilih atribut atau entitas tertentu yang ingin Anda fokuskan pada perhitungan. Jika pemetaan semantik tidak terjadi, pilih **Edit dan petakan** data Anda.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Panel sisi yang menunjukkan pemilihan aktivitas tertentu dalam jenis semantik.":::

1. Pilih **Berikutnya** dan tinjau atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Tambahkan lebih banyak aktivitas atau pilih **Berikutnya**.

# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Tambahkan data tambahan (opsional)

1. Pilih **Tambahkan data** untuk **aktivitas** Pelanggan.

1. Pilih jenis aktivitas semantik yang berisi data yang ingin Anda gunakan. Jika aktivitas belum disiapkan, pilih **di sini** dan buat.

1. Di bawah **Aktivitas**, jika atribut aktivitas dipetakan secara semantik saat aktivitas dibuat, pilih atribut atau entitas tertentu yang ingin Anda fokuskan pada perhitungan. Jika pemetaan semantik tidak terjadi, pilih **Edit dan petakan** data Anda.

1. Pilih **Berikutnya** dan tinjau atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Pilih **berikutnya**

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

### <a name="select-prediction-level"></a>Pilih Tingkat prediksi

Sebagian besar prediksi dibuat pada tingkat pelanggan. Dalam situasi tertentu, hal tersebut mungkin tidak cukup rinci untuk memenuhi kebutuhan bisnis Anda. Gunakan fitur ini untuk memprediksi churn untuk cabang pelanggan, misalnya, bukan untuk pelanggan secara keseluruhan.

1. Pilih **Pilih entitas untuk tingkat** sekunder. Jika pilihan tidak tersedia, pastikan Anda telah menyelesaikan bagian sebelumnya.

1. Perluas entitas yang akan dipilih tingkat kedua, atau gunakan kotak filter pencarian untuk memfilter pilihan yang dipilih.

1. Pilih atribut yang akan digunakan sebagai tingkat kedua, lalu pilih **Tambah**.

1. Pilih **Selanjutnya**.

> [!NOTE]
> Entitas yang tersedia di bagian ini ditampilkan karena memiliki relasi dengan entitas yang Anda pilih di bagian sebelumnya. Jika Anda tidak melihat entitas yang ingin Anda tambahkan, pastikan entitas memiliki relasi valid yang ada di **Relasi**. Hanya Relasi banyak ke satu dan satu-ke-satu yang valid untuk konfigurasi ini.

### <a name="add-additional-data-optional"></a>Tambahkan data tambahan (opsional)

1. Pilih **Tambahkan data** untuk **aktivitas** Pelanggan.

1. Pilih jenis aktivitas semantik yang berisi data yang ingin Anda gunakan. Jika aktivitas belum disiapkan, pilih **di sini** dan buat.

1. Di bawah **Aktivitas**, jika atribut aktivitas dipetakan secara semantik saat aktivitas dibuat, pilih atribut atau entitas tertentu yang ingin Anda fokuskan pada perhitungan. Jika pemetaan semantik tidak terjadi, pilih **Edit dan petakan** data Anda.

1. Pilih **Berikutnya** dan tinjau atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Pilih **berikutnya**

1. Atau, pilih **Tambah data** untuk **data Pelanggan**.

1. Petakan atribut semantis ke bidang pada data pelanggan Anda sendiri sebagai teridentifikasi. Data pada bidang yang digunakan tidak boleh sering berubah untuk memastikan kinerja terbaik model. Contohnya, memilih bidang untuk "Klasifikasi" yang berubah setiap bulan hanya akan memiliki nilai terakhir yang digunakan di prediksi, meskipun secara historis nilai yang sama mungkin tidak berlaku untuk pelanggan saat membangun pola prediksi baru.

1. Pilih **Selanjutnya**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Memberikan daftar opsional akun tolok ukur

Tambahkan daftar pelanggan bisnis dan akun yang akan digunakan sebagai tolok ukur. Detail [untuk akun](#view-prediction-results) tolok ukur ini mencakup skor churn mereka dan fitur paling berpengaruh yang memengaruhi churn prediksi mereka.

1. Pilih **+ Tambahkan pelanggan**.

1. Pilih pelanggan yang berfungsi sebagai tolok ukur.

1. Pilih **Selanjutnya**.

---

### <a name="set-update-schedule"></a>Atur Jadwal pembaruan

1. **Untuk langkah Pembaruan** data, pilih frekuensi untuk melatih kembali model Anda. Pengaturan ini penting untuk memperbarui keakuratan prediksi karena data baru diserap ke dalam Customer Insights. Sebagian besar bisnis dapat melatih sekali per bulan dan mendapatkan akurasi yang baik untuk prediksi mereka.

1. Pilih **Selanjutnya**.

### <a name="review-and-run-the-model-configuration"></a>Memeriksa dan menjalankan konfigurasi model

Langkah **Tinjau dan jalankan** menunjukkan ringkasan konfigurasi dan memberikan kesempatan untuk membuat perubahan sebelum Anda membuat prediksi.

1. Pilih **Edit** pada salah satu langkah untuk meninjau dan membuat perubahan apa pun.

1. Jika Anda puas dengan pilihan Anda, pilih **Simpan dan jalankan** untuk mulai menjalankan model. Pilih **Selesai**. Tab **Prediksi** saya ditampilkan saat prediksi sedang dibuat. Proses dapat berlangsung selama beberapa jam hingga selesai, tergantung pada jumlah data yang digunakan dalam prediksi.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Lihat hasil prediksi

1. Pergi ke **Prediksi** > **Intelijen**.

1. Di tab **Prediksi** saya, pilih prediksi yang ingin Anda lihat.

# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

Terdapat tiga bagian utama data dalam halaman hasil:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

Terdapat tiga bagian utama data dalam halaman hasil:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

**Halaman informasi analisis** fitur Berpengaruh berisi empat bagian data:

- Di panel kanan, pilih item dari **Pelanggan teratas atau** Pelanggan **tolok** ukur. Kedua daftar tersebut diurutkan dengan mengurangi nilai skor kehilangan, apakah skor hanya untuk pelanggan maupun skor gabungan untuk pelanggan dan tingkat kedua seperti kategori produk. Item yang dipilih menentukan konten di halaman ini.

  - **Pelanggan teratas**: Daftar 10 pelanggan yang memiliki risiko tertinggi pergi dan risiko kehilangan terendah berdasarkan skor kehilangan mereka.
  - **Pelanggan tolok ukur**: Daftar hingga 10 pelanggan yang dipilih saat mengkonfigurasi model.

- **Skor kehilangan:** Menampilkan skor kehilangan untuk item yang dipilih di panel kanan.

- **Distribusi risiko churn:** Menunjukkan distribusi risiko churn di seluruh pelanggan dan persentil tempat pelanggan terpilih berada.

- **Fitur teratas yang meningkatkan dan mengurangi risiko churn:** Mencantumkan lima fitur teratas yang meningkatkan dan mengurangi risiko churn untuk item yang dipilih di panel kanan. Menunjukkan nilai fitur untuk item tersebut dan pengaruhnya terhadap skor churn untuk setiap fitur yang berpengaruh. Nilai rata-rata setiap fitur di segmen kehilangan pelanggan rendah, sedang, dan tinggi juga ditampilkan. Peran ini akan membantu lebih mengkontekstualisasi nilai dari fitur berpengaruh teratas untuk item yang dipilih dan membandingkannya dengan segmen kehilangan pelanggan yang rendah, sedang, dan tinggi.

  - Rendah: akun atau kombinasi akun dan tingkat sekunder dengan skor churn antara 0 dan 0,33.
  - Sedang: akun atau kombinasi akun dan tingkat sekunder dengan skor churn antara 0,33 dan 0,66.
  - Tinggi: akun atau kombinasi akun dan level sekunder dengan skor churn lebih besar dari 0,66.

  Bila Anda memperkirakan kehilangan pada tingkat akun, semua akun akan dipertimbangkan dalam memperoleh nilai fitur rata-rata untuk segmen kehilangan. Untuk prediksi kehilangan pada tingkat kedua untuk setiap akun, turunan segmen kehilangan bergantung pada tingkat kedua item yang dipilih di panel sisi. Misalnya, jika suatu barang memiliki tingkat sekunder kategori produk (perlengkapan kantor), maka hanya barang yang memiliki perlengkapan kantor sebagai kategori produk yang dipertimbangkan ketika memperoleh nilai fitur rata-rata untuk segmen churn. Logika ini diterapkan untuk memastikan perbandingan wajar nilai fitur item dengan nilai rata-rata di segmen rendah, sedang, dan tinggi.

  Pada kasus tertentu, nilai rata-rata segmen kehilangan rendah, sedang, atau tinggi adalah kosong atau tidak tersedia karena tidak ada item yang merupakan milik segmen kehilangan terkait berdasarkan definisi di atas.

  Kategorikan nilai dalam kolom rendah, sedang, dan tinggi rata-rata berbeda untuk fitur kategoris seperti negara atau industri. Karena keterangan tentang nilai fitur "rata-rata" tidak berlaku untuk fitur kategoris, nilai di kolom ini adalah perbandingan pelanggan pada segmen rendah, sedang, atau tinggi yang memiliki nilai sama dengan fitur kategoris dibandingkan item yang dipilih di panel sisi.

---

 > [!NOTE]
 > Dalam entitas output untuk model ini, *ChurnScore* menunjukkan prediksi probabilitas churn dan *IsChurn* adalah label biner berdasarkan *ChurnScore* dengan ambang batas 0,5. Jika ambang batas default ini tidak berfungsi untuk skenario Anda, [buat segmen](segments.md#create-a-segment) baru dengan ambang batas pilihan Anda. Tidak semua pelanggan harus merupakan pelanggan aktif. Beberapa dari mereka mungkin tidak memiliki aktivitas untuk waktu yang lama dan dianggap sudah pergi, berdasarkan definisi kehilangan Anda. Memperkirakan risiko kehilangan bagi pelanggan yang telah pergi tidak berguna karena bukan audiens yang menarik minat.
>
> Untuk melihat skor churn, buka **Entitas** > **Data** dan lihat tab data untuk entitas output yang Anda tentukan untuk model ini.

[!INCLUDE [footer-include](includes/footer-banner.md)]
