---
title: Prediksi nilai selama hubungan dengan pelanggan (CLV)
description: Prediksi potensi pendapatan untuk pelanggan aktif di masa mendatang.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: 07790604b06f21095a9220a6f57727cac80789c5
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355793"
---
# <a name="customer-lifetime-value-clv-prediction"></a>Prediksi nilai selama hubungan dengan pelanggan (CLV)

Perkipkan nilai potensial (pendapatan) yang akan diberikan pelanggan aktif individual ke bisnis Anda hingga periode waktu mendatang yang ditentukan. Fitur ini dapat membantu Anda mencapai berbagai sasaran: 
- Mengidentifikasi pelanggan bernilai tinggi dan memproses wawasan ini
- Membuat segmen pelanggan yang strategis berdasarkan potensi nilainya untuk menjalankan kampanye pribadi dengan upaya penjualan, pemasaran, dan dukungan yang ditargetkan
- Memandu pengembangan produk dengan berfokus pada fitur yang meningkatkan nilai pelanggan
- Mengoptimalkan strategi penjualan atau pemasaran dan mengalokasikan anggaran secara lebih akurat untuk jangkauan pelanggan
- Mengakui dan memberikan penghargaan kepada pelanggan bernilai tinggi melalui program loyalitas atau penghargaan 

## <a name="prerequisites"></a>Prasyarat

Sebelum memulai, cerminkan arti CLV untuk bisnis Anda. Saat ini, kami mendukung prediksi CLV berbasis transaksi. Nilai prediksi pelanggan didasarkan pada riwayat transaksi bisnis. Untuk membuat prediksi, Anda memerlukan minimal izin [kontributor](permissions.md).

Karena mengkonfigurasi dan menjalankan model CLV tidak memerlukan banyak waktu, pertimbangkan untuk membuat beberapa model dengan berbagai preferensi input dan membandingkan hasil model untuk melihat skenario model yang paling sesuai dengan kebutuhan bisnis Anda.

###  <a name="data-requirements"></a>Persyaratan data

Data berikut diperlukan dan jika ditandai opsional, disarankan untuk meningkatkan performa model. Semakin banyak data yang dapat diproses oleh model, semakin akurat prediksinya. Oleh karena itu, sebaiknya Anda menggunakan data aktivitas pelanggan lebih banyak, jika tersedia.

- Pengidentifikasi Pelanggan: Pengidentifikasi unik untuk transaksi yang sesuai dengan pelanggan individual

- Riwayat Transaksi: Log transaksi historis dengan skema data semantis di bawah
    - **ID transaksi**: pengidentifikasi unik setiap transaksi
    - **Tanggal transaksi**: Tanggal, sebaiknya cap waktu untuk setiap transaksi
    - **Jumlah transaksi**: Nilai moneter (contoh: pendapatan atau margin laba) dari setiap transaksi
    - **Label yang ditetapkan untuk hasil** (opsional): Nilai Boolean yang menandakan apakah transaksi adalah hasil 
    - **ID Produk** (opsional): ID Produk dari produk yang terlibat dalam transaksi

- Data tambahan (opsional), misalnya
    - Aktivitas web: riwayat kunjungan situs web, riwayat email
    - Aktivitas loyalitas: akumulasi poin reward loyalitas dan riwayat penukaran
    - Log Layanan pelanggan, panggilan layanan, keluhan, atau riwayat retur
- Data tentang aktivitas pelanggan (opsional):
    - Pengidentifikasi aktivitas untuk membedakan aktivitas dari jenis yang sama
    - Pengidentifikasi pelanggan untuk memetakan aktivitas dengan pelanggan Anda
    - Informasi aktivitas berisi nama dan tanggal aktivitas
    - Skema data semantis untuk aktivitas mencakup: 
        - **Kunci primer**: pengidentifikasi unik untuk aktivitas
        - **Cap waktu**: tanggal dan waktu aktivitas yang diidentifikasi oleh kunci primer
        - **Aktivitas (nama aktivitas)**: Nama aktivitas yang akan digunakan
        - **Rincian (jumlah atau nilai)**: Rincian tentang aktivitas pelanggan

- Karakteristik Data yang Disarankan:
    - Data historis yang memadai: Minimal satu tahun data transaksi. Sebaiknya dua hingga tiga tahun data transaksional untuk memperkirakan CLV selama satu tahun.
    - Beberapa pembelian per pelanggan: Idealnya, minimal dua hingga tiga transaksi per ID pelanggan, sebaiknya di beberapa tanggal.
    - Jumlah pelanggan: Setidaknya 100 pelanggan unik, lebih disukai lebih dari 10.000 pelanggan. Model akan gagal dengan kurang dari 100 pelanggan dan data historis yang tidak mencukupi
    - Kelengkapan data: Kurang dari 20% nilai hilang pada bidang yang diperlukan dalam data input   

> [!NOTE]
> - Model ini memerlukan riwayat transaksi pelanggan Anda. Hanya satu entitas riwayat transaksi yang dapat dikonfigurasi saat ini. Jika ada beberapa entitas pembelian /transaksi, Anda dapat menyatukannya Power Query sebelum konsumsi data.
> - Namun untuk data aktivitas pelanggan tambahan (opsional), Anda dapat menambahkan entitas aktivitas pelanggan sebanyak yang ingin Anda pertimbangkan berdasarkan model.

## <a name="create-a-customer-lifetime-value-prediction"></a>Buat Prediksi nilai selama hubungan dengan pelanggan

1. Di wawasan audiens, buka **Intelijen** > **Prediksi**.

1. Pilih petak **nilai selama hubungan dengan pelanggan** dan pilih **Gunakan model**. 

1. **Di panel Nilai** seumur hidup Pelanggan, pilih **Mulai**.

1. **Namai model ini** dan **nama entitas Output** untuk membedakannya dari model atau entitas lain.

1. Pilih **Selanjutnya**.

### <a name="define-model-preferences"></a>Definisikan Preferensi model

1. Atur **periode waktu prediksi** untuk menentukan seberapa jauh ke masa mendatang yang akan Anda prediksikan CLV-nya.    
   Secara default, unit diatur sebagai bulan. Anda dapat mengubahnya ke tahun untuk melihat lebih lanjut di masa mendatang.

   > [!TIP]
   > Untuk secara akurat memperkirakan CLV selama periode waktu yang Anda tentukan, Anda memerlukan periode data historis yang dapat dibandingkan. Misalnya, jika Anda ingin memperkirakan CLV selama 12 bulan ke depan, sebaiknya Anda memiliki data historis minimal 18 - 24 bulan.

1. Tentukan makna **pelanggan Aktif** untuk bisnis Anda. Atur jangka waktu pelanggan harus memiliki minimal satu transaksi untuk dianggap aktif. Model tersebut hanya akan memperkirakan CLV untuk pelanggan aktif. 
   - **Biarkan model menghitung interval pembelian (disarankan)**: Model akan menganalisis data Anda dan menentukan periode waktu berdasarkan pembelian historis.
   - **Atur interval secara manual**: Jika Anda memiliki definisi bisnis khusus pelanggan aktif, pilih pilihan ini dan atur periode waktu sesuai.

1. Definisikan persentil **pelanggan bernilai tinggi** agar model dapat memberikan hasil yang sesuai dengan definisi bisnis Anda.
    - **Penghitungan model (disarankan)**: Model akan menganalisis data Anda dan menentukan jenis pelanggan bernilai tinggi untuk bisnis Anda berdasarkan riwayat transaksi pelanggan. Model tersebut menggunakan aturan heuristik (yang diilhami oleh aturan 80/20 atau prinsip pareto) untuk menemukan proporsi pelanggan bernilai tinggi. Persentase pelanggan yang berkontribusi pada pendapatan kumulatif 80% untuk bisnis Anda dalam periode historis dianggap pelanggan bernilai tinggi. Biasanya, kurang dari 30-40% pelanggan berkontribusi pada pendapatan kumulatif 80%. Namun, jumlah ini dapat berbeda, tergantung pada bisnis dan industri Anda.    
    - **Persen dari pelanggan aktif teratas**: Menentukan pelanggan bernilai tinggi untuk bisnis Anda sebagai persentil dari pelanggan berbayar aktif teratas. Misalnya, Anda dapat menggunakan pilihan ini untuk menentukan pelanggan bernilai tinggi sebagai 20% pelanggan berbayar teratas di masa mendatang.

    Jika bisnis Anda menentukan pelanggan dengan nilai tinggi dengan cara yang berbeda, [beri tahu kami karena kami ingin mengetahuinya](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Pilih **selanjutnya** untuk lanjut ke langkah berikutnya.

### <a name="add-required-data"></a>Tambahkan data wajib

1. Di langkah **data yang diperlukan**, pilih **Tambah data** untuk **Riwayat transaksi pelanggan** dan pilih entitas yang menyediakan informasi riwayat transaksi/pembelian sebagaimana dijelaskan dalam [prasyarat](#prerequisites).

1. Petakan bidang semantik ke atribut dalam entitas Riwayat Pembelian Anda dan pilih **berikutnya**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Gambar langkah konfigurasi untuk memetakan atribut data untuk data yang diperlukan.":::
 
1. Jika bidang di bawah ini tidak terisi, konfigurasikan relasi dari entitas Riwayat Pembelian Anda ke entitas *pelanggan* dan pilih **simpan**.
    1. Pilih Entitas riwayat transaksi.
    1. Pilih bidang yang mengidentifikasi pelanggan di entitas riwayat pembelian. Ini perlu dikaitkan dengan ID pelanggan utama entitas pelanggan Anda.
    1. Pilih entitas alur kerja yang sesuai dengan entitas pelanggan utama Anda.
    1. Masukkan nama yang mendeskripsikan relasi.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Gambar langkah konfigurasi untuk menentukan relasi dengan entitas pelanggan.":::

1. Pilih **Selanjutnya**.

### <a name="add-optional-data"></a>Tambah data opsional

Data yang mencerminkan interaksi pelanggan utama (seperti web, layanan pelanggan, dan log aktivitas) menambahkan konteks ke rekaman transaksi. Pola lainnya yang ditemukan dalam data aktivitas pelanggan Anda dapat meningkatkan keakuratan prediksi. 

1. Pada langkah **Data tambahan (opsional)**, pilih **Tambah data**. Pilih entitas aktivitas pelanggan yang menyediakan informasi aktivitas pelanggan sebagaimana dijelaskan dalam [prasyarat](#prerequisites).

1. Petakan bidang semantik ke atribut dalam entitas aktivitas pelanggan Anda dan pilih **berikutnya**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Gambar langkah konfigurasi untuk memetakan bidang untuk data tambahan.":::

1. Pilih jenis aktivitas yang sesuai dengan jenis aktivitas pelanggan yang Anda tambahkan. Pilih dari jenis aktivitas yang ada atau tambahkan jenis aktivitas baru.

1. Konfigurasikan relasi dari entitas aktivitas pelanggan Anda ke entitas *Pelanggan*.
    
    1. Pilih bidang yang mengidentifikasi pelanggan di tabel aktivitas pelanggan. Hal ini dapat langsung terkait dengan ID pelanggan utama entitas *pelanggan* Anda.
    1. Pilih entitas *pelanggan* yang cocok dengan entitas *pelanggan* utama Anda.
    1. Masukkan nama yang mendeskripsikan relasi.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Gambar langkah dalam alur konfigurasi untuk menambahkan data tambahan dan mengkonfigurasi aktivitas dengan contoh yang diisi.":::

1. Pilih **Simpan**.    
    Tambahkan data lainnya jika ada aktivitas pelanggan lain yang ingin Anda sertakan.

1. Pilih **Selanjutnya**.

### <a name="set-update-schedule"></a>Atur Jadwal pembaruan

1. Pada langkah **jadwal pembaruan Data**, pilih frekuensi untuk melatih ulang model Anda berdasarkan data terakhir. Pengaturan ini penting untuk memperbarui keakuratan prediksi karena data baru terserap dalam wawasan audiens. Sebagian besar bisnis dapat melatih sekali per bulan dan mendapatkan akurasi yang baik untuk prediksi mereka.

1. Pilih **Selanjutnya**.

### <a name="review-and-run-the-model-configuration"></a>Memeriksa dan menjalankan konfigurasi model

1. Di langkah **Tinjau rincian model Anda**, validasikan konfigurasi prediksi. Anda dapat kembali ke bagian apa pun dari konfigurasi prediksi dengan memilih **Edit** dalam nilai yang ditampilkan. Anda juga dapat memilih langkah konfigurasi dari indikator progres.

1. Jika semua nilai dikonfigurasi dengan benar, pilih **Simpan dan jalankan** untuk mulai menjalankan model. Pada tab **prediksi saya**, Anda dapat melihat status proses prediksi. Proses dapat berlangsung selama beberapa jam hingga selesai, tergantung pada jumlah data yang digunakan dalam prediksi.

## <a name="review-prediction-status-and-results"></a>Memeriksa status prediksi dan hasil

### <a name="review-prediction-status"></a>Memeriksa status prediksi

1.  Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.
2.  Pilih prediksi yang ingin Anda tinjau.

- **Nama prediksi**: nama prediksi yang diberika saat membuatnya.
- **jenis prediksi**: jenis model yang digunakan untuk prediksi
- **Entitas output**: nama entitas untuk menyimpan output dari prediksi. Buka **Data** > **Entitas** untuk menemukan entitas dengan nama ini.
- **bidang terprediksi**: bidang ini hanya diisi untuk beberapa jenis prediksi, dan tidak digunakan dalam prediksi nilai selama hubungan dengan pelanggan.
- **Status**: Status prediksi dijalankan.
    - **mengantri**: prediksi sedang menunggu proses lain untuk diselesaikan.
    - **Menyegarkan**: prediksi saat ini berjalan untuk membuat hasil yang akan mengalir ke entitas output.
    - **gagal**: prediksi yang jalankan gagal. [Tinjau log](manage-predictions.md#troubleshoot-a-failed-prediction) untuk rincian selengkapnya.
    - **berhasil**: prediksi telah berhasil. Pilih **Lihat** di dalam elips vertikal untuk meninjau hasil prediksi.
- **Diedit**: tanggal konfigurasi untuk prediksi telah diubah.
- **Terakhir disegarkan**: tanggal prediksi yang disegarkan dihasilkan dalam entitas output.

### <a name="review-prediction-results"></a>Memeriksa hasil prediksi

1. Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.

1. Pilih prediksi yang hasilnya ingin Anda tinjau.

Terdapat tiga bagian utama data dalam halaman hasil.

- **Performa model pelatihan**: A, B, atau C merupakan kemungkinan peringkat. peringkat ini menunjukkan kinerja prediksi dan dapat membantu Anda membuat keputusan untuk menggunakan hasil yang tersimpan dalam entitas output. Pilih **Pelajari tentang skor ini** untuk lebih memahami metrik performa model dasar dan turunan peringkat performa model final.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Gambar kotak informasi skor model dengan peringkat A.":::

  Dengan menggunakan definisi pelanggan bernilai tinggi yang disediakan saat mengonfigurasikan prediksi, sistem akan menilai performa model AI dalam memperkirakan pelanggan bernilai tinggi dibandingkan model dasar.    

  Peringkat ditentukan berdasarkan aturan berikut:
  - **A** bila model memperkirakan secara akurat setidaknya 5% lebih banyak pelanggan bernilai tinggi dibandingkan dengan model dasar.
  - **B** bila model memperkirakan secara akurat antara 0-5% lebih banyak pelanggan bernilai tinggi dibandingkan dengan model dasar.
  - **C** bila model memperkirakan secara akurat lebih sedikit pelanggan bernilai tinggi dibandingkan dengan model dasar.

  Panel **peringkat Model** menampilkan rincian lebih lanjut tentang kinerja model AI dan model dasar. Model dasar menggunakan pendekatan berbasis non-AI untuk menghitung nilai selama hubungan dengan pelanggan terutama berdasarkan pembelian historis yang dilakukan pelanggan.     
  Rumus standar yang digunakan untuk menghitung CLV berdasarkan model dasar:    

  _**CLV untuk tiap pelanggan** = Pembelian bulanan rata-rata yang dilakukan oleh pelanggan dalam jendela pelanggan aktif * Jumlah bulan dalam periode prediksi CLV * Tingkat retensi keseluruhan semua pelanggan*_

  Model AI dibandingkan dengan model dasar berdasarkan dua metrik performa model.
  
  - **Tingkat keberhasilan dalam memperkirakan pelanggan bernilai tinggi**

    Lihat perbedaan dalam memperkirakan pelanggan bernilai tinggi menggunakan model AI dibandingkan model dasar. Contohnya, tingkat keberhasilan 84% berarti dari semua pelanggan bernilai tinggi dalam data pelatihan, model AI mampu menangkap secara akurat 84%. Selanjutnya kita akan membandingkan tingkat keberhasilan ini dengan tingkat keberhasilan model dasar untuk melaporkan perubahan relatif. Nilai ini digunakan untuk menetapkan peringkat ke model.

  - **Metrik kesalahan**
    
    Metrik lainnya memungkinkan Anda meninjau kinerja model secara keseluruhan dalam hal kesalahan dalam memperkirakan nilai yang akan datang. Kita menggunakan metrik RMSE (Root Mean Squared Error) secara keseluruhan untuk menilai kesalahan ini. RMSE adalah cara standar untuk mengukur kesalahan model dalam memperkirakan data kuantitatif. RMSE model AI dibandingkan RMSE dari model dasar dan perbedaan relatifnya dilaporkan.

  Model AI memprioritaskan peringkat pelanggan yang akurat sesuai dengan nilai yang mereka bawa untuk bisnis Anda. Jadi hanya tingkat keberhasilan yang memperkirakan pelanggan bernilai tinggi yang digunakan untuk memperoleh peringkat model final. Metrik RMSE peka terhadap nilai luar. Dalam skenario bila Anda memiliki persentase kecil pelanggan dengan nilai pembelian yang luar biasa tinggi, metrik RMSE secara keseluruhan mungkin tidak memberikan gambaran lengkap performa model.   

- **Nilai pelanggan berdasarkan persentil**: Menggunakan definisi pelanggan ber nilai tinggi, pelanggan dikelompokkan ke dalam nilai rendah dan bernilai tinggi, berdasarkan prediksi CLV mereka, dan ditampilkan dalam diagram. Dengan mengarahkan kursor ke bilah di histogram, Anda dapat melihat jumlah pelanggan di setiap grup dan CLV rata-rata grup tersebut. Data ini dapat membantu jika Anda ingin [membuat segmen pelanggan](segments.md) berdasarkan prediksi CLV mereka.

- **Faktor paling berpengaruh**: Berbagai faktor dipertimbangkan saat membuat prediksi CLV berdasarkan data input yang diberikan ke model AI. Masing-masing faktor memiliki kepentingan yang diperhitungkan untuk prediksi gabungan yang dibuat model. Anda dapat menggunakan faktor ini untuk membantu memvalidasi hasil prediksi. Faktor-faktor ini juga memberikan wawasan lebih lanjut tentang faktor paling berpengaruh yang berkontribusi terhadap perkiraan CLV di seluruh pelanggan.

## <a name="manage-predictions"></a>Kelola prediksi

Anda dapat mengoptimalkan, memecahkan masalah, menyegarkan, atau menghapus prediksi. Tinjau laporan kegunaan data input untuk mengetahui cara membuat prediksi lebih cepat dan lebih dapat diandalkan. Untuk informasi lebih lanjut, lihat [Kelola prediksi](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
