---
title: Prediksikan nilai selama hubungan dengan pelanggan (CLV)
description: Prediksi potensi pendapatan untuk pelanggan aktif di masa mendatang.
ms.date: 09/30/2022
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
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610378"
---
# <a name="predict-customer-lifetime-value-clv"></a>Prediksikan nilai selama hubungan dengan pelanggan (CLV)

Perkipkan nilai potensial (pendapatan) yang akan diberikan pelanggan aktif individual ke bisnis Anda hingga periode waktu mendatang yang ditentukan. Ini prediksi membantu Anda:

- Identifikasi pelanggan bernilai tinggi dan proses wawasan ini.
- Buat segmen pelanggan yang strategis berdasarkan nilai potensial mereka untuk menjalankan kampanye yang dipersonalisasi dengan upaya penjualan, pemasaran, dan dukungan yang ditargetkan.
- Pandu pengembangan produk dengan berfokus pada fitur yang meningkatkan nilai pelanggan.
- Optimalkan strategi penjualan atau pemasaran dan alokasikan anggaran secara lebih akurat untuk penjangkauan pelanggan.
- Kenali dan beri penghargaan kepada pelanggan bernilai tinggi melalui program loyalitas atau penghargaan.

Tentukan apa arti CLV bagi bisnis Anda. Kami mendukung prediksi CLV berbasis transaksi. Nilai yang diprediksi dari pelanggan didasarkan pada sejarah transaksi bisnis. Pertimbangkan untuk membuat beberapa model dengan preferensi input yang bervariasi dan bandingkan hasil model untuk melihat skenario model mana yang paling sesuai dengan kebutuhan bisnis Anda.

> [!TIP]
> Coba clv prediksi menggunakan data sampel: [Panduan sampel prediksi nilai umur pelanggan (CLV)](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Prasyarat

- Setidaknya [izin kontributor](permissions.md)
- Setidaknya 100 pelanggan unik, lebih disukai lebih dari 10.000 pelanggan
- Pengidentifikasi Pelanggan, pengidentifikasi unik untuk mencocokkan transaksi dengan pelanggan individu
- Setidaknya satu tahun riwayat transaksi, lebih disukai dua hingga tiga tahun. Idealnya, setidaknya dua hingga tiga transaksi per ID pelanggan, lebih disukai di beberapa tanggal. Riwayat transaksi harus mencakup:
  - **ID transaksi**: pengidentifikasi unik setiap transaksi
  - **Tanggal transaksi**: Tanggal atau stempel waktu setiap transaksi
  - **Jumlah transaksi**: Nilai moneter (contoh: pendapatan atau margin laba) dari setiap transaksi
  - **Label yang ditetapkan untuk pengembalian**: Nilai true/false Boolean yang menandakan apakah transaksi tersebut adalah pengembalian
  - **ID** Produk: ID Produk produk yang terlibat dalam transaksi
- Data tentang aktivitas pelanggan:
  - **Kunci** utama: Pengidentifikasi unik untuk suatu aktivitas
  - **Stempel** waktu: Tanggal dan waktu peristiwa yang diidentifikasi oleh kunci utama
  - **Acara (nama aktivitas)**: Nama acara yang ingin Anda gunakan
  - **Rincian (jumlah atau nilai)**: Rincian tentang aktivitas pelanggan
- Data tambahan seperti:
  - Aktivitas web: Riwayat kunjungan situs web atau riwayat email
  - Aktivitas loyalitas: Akrual poin reward loyalitas dan riwayat penukaran
  - Layanan pelanggan log: Panggilan layanan, keluhan, atau riwayat pengembalian
  - Informasi profil pelanggan
- Kurang dari 20% nilai yang hilang di bidang wajib diisi

> [!NOTE]
> Hanya satu entitas riwayat transaksi yang dapat dikonfigurasi. Jika ada beberapa entitas pembelian atau transaksi, gabungkan entitas tersebut Power Query sebelum penyerapan data.

## <a name="create-a-customer-lifetime-value-prediction"></a>Buat Prediksi nilai selama hubungan dengan pelanggan

Pilih **Simpan draf** kapan saja untuk menyimpan prediksi sebagai draf. Draf prediksi ditampilkan di tab **Prediksi** saya.

1. Pergi ke **Prediksi** > **Intelijen**.

1. Pada tab **Buat**, pilih **Gunakan model** pada petak **nilai** seumur hidup Pelanggan.

1. Pilih **Mulai**.

1. **Namai model ini** dan **nama entitas Output** untuk membedakannya dari model atau entitas lain.

1. Pilih **Selanjutnya**.

### <a name="define-model-preferences"></a>Definisikan Preferensi model

1. Atur **periode waktu prediksi** untuk menentukan seberapa jauh ke masa mendatang yang akan Anda prediksikan CLV-nya. Secara default, unit diatur sebagai bulan.

   > [!TIP]
   > Untuk memprediksi CLV secara akurat untuk periode waktu yang ditetapkan, diperlukan periode data historis yang sebanding. Misalnya, jika Anda ingin memprediksi CLV selama 12 bulan ke depan, miliki setidaknya 18 – 24 bulan data historis.

1. Atur jangka waktu pelanggan harus memiliki minimal satu transaksi untuk dianggap aktif. Model ini hanya memprediksi CLV untuk **pelanggan** Aktif.
   - **Biarkan model menghitung interval pembelian (disarankan)**: Model menganalisis data Anda dan menentukan periode waktu berdasarkan pembelian historis.
   - **Atur interval secara manual**: Periode waktu untuk definisi Anda tentang pelanggan aktif.

1. Tentukan persentil **pelanggan** bernilai tinggi.
    - **Perhitungan model (disarankan)**: Model menggunakan aturan 80/20. Persentase pelanggan yang berkontribusi pada pendapatan kumulatif 80% untuk bisnis Anda dalam periode historis dianggap pelanggan bernilai tinggi. Biasanya, kurang dari 30-40% pelanggan berkontribusi pada pendapatan kumulatif 80%. Namun, jumlah ini dapat berbeda, tergantung pada bisnis dan industri Anda.
    - **Persentase pelanggan** aktif teratas: Persentil spesifik untuk pelanggan bernilai tinggi. Misalnya, masukkan **25** untuk menentukan pelanggan bernilai tinggi sebagai 25% teratas dari pelanggan yang membayar di masa mendatang.

    Jika bisnis Anda menentukan pelanggan dengan nilai tinggi dengan cara yang berbeda, [beri tahu kami karena kami ingin mengetahuinya](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Pilih **Selanjutnya**.

### <a name="add-required-data"></a>Tambahkan data wajib

1. Pilih **Tambahkan data** untuk **riwayat transaksi** Pelanggan.

1. Pilih jenis aktivitas semantik, **SalesOrder** atau **SalesOrderLine**, yang berisi riwayat transaksi. Jika aktivitas belum disiapkan, pilih **di sini** dan buat.

1. Di bawah **Aktivitas**, jika atribut aktivitas dipetakan secara semantik saat aktivitas dibuat, pilih atribut atau entitas tertentu yang ingin Anda fokuskan pada perhitungan. Jika pemetaan semantik tidak terjadi, pilih **Edit dan petakan** data Anda.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Menambahkan data yang diperlukan untuk model CLV":::

1. Pilih **Berikutnya** dan tinjau atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Tambahkan lebih banyak aktivitas atau pilih **Berikutnya**.

### <a name="add-optional-activity-data"></a>Menambahkan data aktivitas opsional

Data yang mencerminkan interaksi pelanggan utama (seperti web, layanan pelanggan, dan log aktivitas) menambahkan konteks ke rekaman transaksi. Pola lainnya yang ditemukan dalam data aktivitas pelanggan Anda dapat meningkatkan keakuratan prediksi.

1. Pilih **Tambahkan data** di bawah **Tingkatkan wawasan model dengan data** aktivitas tambahan.

1. Pilih jenis aktivitas yang sesuai dengan jenis aktivitas pelanggan yang Anda tambahkan. Jika aktivitas belum disiapkan, pilih **di sini** dan buat.

1. Di bawah **Aktivitas**, jika atribut aktivitas dipetakan saat aktivitas dibuat, pilih atribut atau entitas tertentu yang ingin Anda fokuskan pada perhitungan. Jika pemetaan tidak terjadi, pilih **Edit** dan petakan data Anda.

1. Pilih **Berikutnya** dan tinjau atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Pilih **Selanjutnya**.

1. [Tambahkan data](#add-optional-customer-data) pelanggan opsional atau pilih **Berikutnya** dan buka [Atur jadwal](#set-update-schedule) pembaruan.

### <a name="add-optional-customer-data"></a>Menambahkan data pelanggan opsional

Pilih dari 18 atribut profil pelanggan yang umum digunakan untuk disertakan sebagai input ke model. Atribut ini dapat menghasilkan hasil model yang lebih dipersonalisasi, relevan, dan dapat ditindaklanjuti untuk kasus penggunaan bisnis Anda.

Misalnya: Contoso Coffee ingin memprediksi nilai seumur hidup pelanggan untuk menargetkan pelanggan bernilai tinggi dengan penawaran yang dipersonalisasi terkait dengan peluncuran mesin espresso baru mereka. Contoso menggunakan model CLV dan menambahkan semua 18 atribut profil pelanggan untuk melihat faktor mana yang memengaruhi pelanggan dengan nilai tertinggi. Mereka menemukan lokasi pelanggan adalah faktor yang paling berpengaruh bagi pelanggan ini.
Dengan informasi ini, mereka menyelenggarakan acara lokal untuk peluncuran mesin espresso dan bermitra dengan vendor lokal untuk penawaran yang dipersonalisasi dan pengalaman khusus di acara tersebut. Tanpa informasi ini, Contoso mungkin hanya mengirim email pemasaran generik dan melewatkan kesempatan untuk mempersonalisasi segmen lokal pelanggan bernilai tinggi mereka ini.

1. Pilih **Tambahkan data** di bawah **Tingkatkan wawasan model lebih jauh lagi dengan data** pelanggan tambahan.

1. Untuk **Entitas**, pilih **Pelanggan: CustomerInsights** untuk memilih profil pelanggan terpadu yang memetakan ke data atribut pelanggan. Untuk **ID** Pelanggan, pilih **System.Customer.CustomerId**.

1. Petakan lebih banyak bidang jika data tersedia di profil pelanggan terpadu Anda.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Contoh bidang yang dipetakan untuk data profil pelanggan.":::

1. Pilih **Simpan**.

1. Pilih **Selanjutnya**.

### <a name="set-update-schedule"></a>Atur Jadwal pembaruan

1. Pilih frekuensi untuk melatih kembali model Anda berdasarkan data terbaru. Pengaturan ini penting untuk memperbarui keakuratan prediksi karena data baru diserap ke dalam Customer Insights. Sebagian besar bisnis dapat melatih sekali per bulan dan mendapatkan akurasi yang baik untuk prediksi mereka.

1. Pilih **Selanjutnya**.

### <a name="review-and-run-the-model-configuration"></a>Memeriksa dan menjalankan konfigurasi model

Langkah **Tinjau dan jalankan** menunjukkan ringkasan konfigurasi dan memberikan kesempatan untuk membuat perubahan sebelum Anda membuat prediksi.

1. Pilih **Edit** pada salah satu langkah untuk meninjau dan membuat perubahan apa pun.

1. Jika Anda puas dengan pilihan Anda, pilih **Simpan dan jalankan** untuk mulai menjalankan model. Pilih **Selesai**. Tab **Prediksi** saya ditampilkan saat prediksi sedang dibuat. Proses dapat berlangsung selama beberapa jam hingga selesai, tergantung pada jumlah data yang digunakan dalam prediksi.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Lihat hasil prediksi

1. Pergi ke **Prediksi** > **Intelijen**.

1. Di tab **Prediksi** saya, pilih prediksi yang ingin Anda lihat.

Terdapat tiga bagian utama data dalam halaman hasil.

- **Performa model pelatihan**: Nilai A, B, atau C menunjukkan kinerja prediksi dan dapat membantu Anda membuat keputusan untuk menggunakan hasil yang disimpan dalam entitas output.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Gambar kotak informasi skor model dengan peringkat A.":::

  Customer Insights menilai bagaimana kinerja model AI dalam memprediksi pelanggan bernilai tinggi dibandingkan dengan model dasar.

  Peringkat ditentukan berdasarkan aturan berikut:
  - **A** bila model memperkirakan secara akurat setidaknya 5% lebih banyak pelanggan bernilai tinggi dibandingkan dengan model dasar.
  - **B** bila model memperkirakan secara akurat antara 0-5% lebih banyak pelanggan bernilai tinggi dibandingkan dengan model dasar.
  - **C** bila model memperkirakan secara akurat lebih sedikit pelanggan bernilai tinggi dibandingkan dengan model dasar.
  
  Pilih [**Pelajari tentang skor**](#learn-about-the-score) ini untuk membuka **panel Peringkat** model yang memperlihatkan detail lebih lanjut tentang performa model AI dan model dasar. Ini akan membantu Anda lebih memahami metrik kinerja model yang mendasarinya dan bagaimana tingkat kinerja model akhir diturunkan. Model dasar menggunakan pendekatan berbasis non-AI untuk menghitung nilai selama hubungan dengan pelanggan terutama berdasarkan pembelian historis yang dilakukan pelanggan.

- **Nilai pelanggan berdasarkan persentil**: Pelanggan bernilai rendah dan bernilai tinggi ditampilkan dalam bagan. Arahkan kursor ke bilah di histogram untuk melihat jumlah pelanggan di setiap grup dan CLV rata-rata grup tersebut. Secara opsional, [buat segmen pelanggan](prediction-based-segment.md) berdasarkan prediksi CLV mereka.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Nilai pelanggan berdasarkan persentil untuk model CLV":::

- **Faktor paling berpengaruh**: Berbagai faktor dipertimbangkan saat membuat prediksi CLV berdasarkan data input yang diberikan ke model AI. Masing-masing faktor memiliki kepentingan yang diperhitungkan untuk prediksi gabungan yang dibuat model. Gunakan faktor-faktor ini untuk membantu memvalidasi hasil prediksi Anda. Faktor-faktor ini juga memberikan wawasan lebih lanjut tentang faktor paling berpengaruh yang berkontribusi terhadap perkiraan CLV di seluruh pelanggan.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Faktor paling berpengaruh untuk model CLV":::

### <a name="learn-about-the-score"></a>Pelajari tentang skor

Rumus standar yang digunakan untuk menghitung CLV berdasarkan model dasar:

 _**CLV untuk setiap pelanggan** = Rata-rata pembelian bulanan yang dilakukan oleh pelanggan di jendela pelanggan aktif * Jumlah bulan dalam periode prediksi CLV * Tingkat retensi keseluruhan semua pelanggan_

Model AI dibandingkan dengan model dasar berdasarkan dua metrik performa model.
  
- **Tingkat keberhasilan dalam memperkirakan pelanggan bernilai tinggi**

  Lihat perbedaan dalam memperkirakan pelanggan bernilai tinggi menggunakan model AI dibandingkan model dasar. Contohnya, tingkat keberhasilan 84% berarti dari semua pelanggan bernilai tinggi dalam data pelatihan, model AI mampu menangkap secara akurat 84%. Selanjutnya kita akan membandingkan tingkat keberhasilan ini dengan tingkat keberhasilan model dasar untuk melaporkan perubahan relatif. Nilai ini digunakan untuk menetapkan peringkat ke model.

- **Metrik kesalahan**

  Lihat kinerja keseluruhan model dalam hal kesalahan dalam memprediksi nilai masa depan. Kita menggunakan metrik RMSE (Root Mean Squared Error) secara keseluruhan untuk menilai kesalahan ini. RMSE adalah cara standar untuk mengukur kesalahan model dalam memperkirakan data kuantitatif. RMSE model AI dibandingkan RMSE dari model dasar dan perbedaan relatifnya dilaporkan.

Model AI memprioritaskan peringkat pelanggan yang akurat sesuai dengan nilai yang mereka bawa untuk bisnis Anda. Jadi hanya tingkat keberhasilan yang memperkirakan pelanggan bernilai tinggi yang digunakan untuk memperoleh peringkat model final. Metrik RMSE peka terhadap nilai luar. Dalam skenario bila Anda memiliki persentase kecil pelanggan dengan nilai pembelian yang luar biasa tinggi, metrik RMSE secara keseluruhan mungkin tidak memberikan gambaran lengkap performa model.

[!INCLUDE [footer-include](includes/footer-banner.md)]
