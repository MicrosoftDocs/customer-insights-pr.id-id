---
title: Analisis sentimen untuk umpan balik pelanggan (pratinjau)
description: Pelajari cara menggunakan model analisis sentimen pada umpan balik pelanggan di Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: af1afd3eff8a795a9e199b1c1d411b79dc2841b4
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055540"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Menganalisis sentimen dalam umpan balik pelanggan (pratinjau)

Pelanggan mengharapkan produk, layanan, dan pengalaman berkualitas tinggi akhir-akhir ini. Terutama pelanggan yang membagikan umpan balik mereka. Sangat menantang bagi organisasi untuk menganalisis peningkatan volume data tanpa menurunkan akurasi dan biaya tenaga kerja yang lebih tinggi. Dynamics 365 Customer Insights menawarkan model analisis sentimen untuk umpan balik pelanggan yang memungkinkan organisasi untuk menganalisis data mereka dengan lebih akurat dan dengan biaya lebih rendah.

Analisis sentimen memungkinkan Anda untuk mensintesis sentimen pelanggan dan mengidentifikasi aspek bisnis sebagai peluang untuk perbaikan. Fitur Customer Insights ini membantu Anda memahami apa yang bekerja dengan baik dan apa yang perlu Anda tangani. Fokus pada bidang bisnis yang paling relevan dan berdampak untuk meningkatkan pengalaman bagi pelanggan Anda. Pada akhirnya, ini dapat membantu Anda untuk mendorong tindakan bisnis yang memungkinkan pengalaman yang menghasilkan kepuasan dan loyalitas pelanggan yang tinggi.

## <a name="overview"></a>Gambaran Umum

Fitur analisis sentimen menghasilkan dua wawasan turunan per ID pelanggan. Skor sentimen (-5 hingga 5) dan daftar aspek bisnis yang berlaku (bidang bisnis) bersama-sama membantu Anda lebih memahami umpan balik pelanggan. 

Informasi ini dapat membantu Anda mencapai hasil berikut: 
- Dapatkan gambaran umum tentang sentimen pelanggan terhadap merek atau organisasi
- Identifikasi pelanggan dengan sentimen negatif untuk memfokuskan kampanye dan keterlibatan Anda dan optimalkan untuk pengembalian yang lebih tinggi  
- Identifikasi aspek bisnis dengan masalah yang ditunjukkan oleh pelanggan  
- Segmentasikan pelanggan berdasarkan sentimen mereka untuk menjalankan kampanye yang dipersonalisasi dengan upaya penjualan, pemasaran, dan dukungan yang ditargetkan
- Mengoptimalkan operasi bisnis dengan menangani area yang menjadi perhatian atau peluang yang disebutkan oleh pelanggan
- Kenali aspek bisnis yang berjalan dengan baik dan beri penghargaan kepada pelanggan yang bahagia melalui program loyalitas dan promosi

Untuk memastikan bahwa Anda dapat mempercayai hasil model, kami memberikan informasi transparan tentang bagaimana model membuat keputusan. Anda akan mendapatkan daftar kata-kata yang memengaruhi keputusan model untuk menetapkan skor sentimen atau aspek bisnis tertentu ke komentar umpan balik.  

Kami menggunakan dua **model** Natural Language Processing (NLP): Yang pertama menetapkan setiap komentar umpan balik skor sentimen. Model kedua mengaitkan setiap umpan balik dengan semua aspek bisnis yang berlaku. Model-model tersebut dilatih pada data publik dari sumber-sumber di media sosial, ritel, restoran, produk konsumen, dan industri otomotif.    
  
Aspek bisnis yang telah ditentukan sebelumnya agar model dapat dikaitkan dengan data umpan balik meliputi:
-   Manajemen akun
-   Selesai dan pembayaran
-   Dukungan pelanggan
-   Pengambilan di toko
-   Pengemasan pengiriman dan pengambilan
-   Pra-pemesanan
-   Harga
-   Privasi dan keamanan
-   Promosi dan hadiah
-   Tanda terima dan garansi
-   Pengembalian penukaran dan pembatalan
-   Akurasi pemenuhan
-   Kualitas situs web/aplikasi

> [!NOTE]
> Saat ini, kami hanya mendukung analisis sentimen pada umpan balik pelanggan bahasa Inggris. Lebih banyak bahasa akan didukung di masa mendatang. Jika umpan balik dalam bahasa lain diunggah, model akan tetap mengembalikan hasil. Namun, hasil ini tidak akan akurat. 

## <a name="prerequisites"></a>Prasyarat

Analisis sentimen didasarkan pada data umpan balik teks yang telah melalui proses penyatuan [data](data-unification.md). Kami sangat menyarankan agar Anda [mengonfigurasi entitas data umpan balik Anda sebagai entitas](map-entities.md#select-primary-key-and-semantic-type-for-attributes) aktivitas tipe semantik (jenis Umpan Balik) sebelumnya. 

Untuk mengonfigurasi model analisis sentimen, Anda memerlukan setidaknya [kontributor izin](permissions.md).

Customer Insights dapat memproses hingga 10 juta catatan umpan balik untuk satu model yang dijalankan. Model ini dapat menganalisis komentar umpan balik hingga 128 kata. Jika komentar umpan balik lebih panjang, analisis hanya mempertimbangkan 128 kata pertama.

### <a name="data-requirements"></a>Persyaratan data
  
Atribut data berikut diperlukan:
- Id Pelanggan Terpadu (UCID) untuk mencocokkan catatan data umpan balik teks dengan pelanggan individu. ID ini adalah hasil dari proses [penyatuan](data-unification.md) data.
- ID tanggapan
- Stempel waktu umpan balik
- Teks tanggapan   

> [!TIP]
> Analisis sentimen membutuhkan umpan balik teks dari pelanggan Anda. Hanya satu entitas umpan balik yang dapat dikonfigurasi saat ini. Jika ada beberapa entitas umpan balik, Anda dapat menyatukan mereka Power Query sebelum penyerapan data dimulai.

## <a name="configure-a-sentiment-analysis"></a>Mengonfigurasi analisis sentimen 

1. Di Customer Insights, buka **Intelijen** > **Prediksi**.

1. Pada petak **peta Analisis** sentimen pelanggan, pilih **Gunakan model**.

1. Di **panel Analisis sentimen pelanggan (pratinjau**), pilih **Mulai**.

1. **Di langkah Nama** model, berikan **Nama** untuk analisis Anda. 

1. **Berikan nama entitas output aspek Bisnis dan** nama **entitas** output skor Sentimen, lalu pilih **Berikutnya**.

1. **Di langkah Data yang diperlukan**, pilih **Tambahkan data**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Tambahkan aliran data dalam model analisis sentimen.":::

1. **Di panel Tambahkan data**, pilih tipe **semantik Umpan Balik** dari daftar.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Langkah konfigurasi untuk memilih aktivitas umpan balik untuk analisis sentimen.":::

1. Pilih aktivitas yang akan digunakan untuk analisis sentimen ini, lalu pilih **Berikutnya**.
 
1. Petakan atribut dalam data Anda ke atribut model. Pilih **Simpan** untuk menerapkan pilihan Anda. 

1. Anda melihat status pemetaan data. Untuk melanjutkan, klik **Berikutnya**. 

1. **Dalam langkah Tinjau detail** model Anda, validasi konfigurasi analisis sentimen Anda. Anda dapat kembali ke bagian mana pun dari konfigurasi prediksi. Pilih **Simpan dan jalankan** untuk memulai analisis. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Tinjau langkah untuk model sentimen yang menampilkan semua item yang dikonfigurasi.":::

1. Pilih **Selesai** untuk meninggalkan pengalaman konfigurasi. Proses ini mungkin memakan waktu beberapa jam untuk diselesaikan tergantung pada jumlah data yang digunakan. 

## <a name="review-analysis-status"></a>Tinjau status analisis

1.  Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.
2.  Pilih prediksi yang ingin Anda tinjau.
- **Nama prediksi**: nama prediksi yang diberika saat membuatnya.
- **prediksi:** Jenis model yang digunakan untuk prediksi.
- **Entitas output**: nama entitas untuk menyimpan output dari prediksi. Buka **Data** > **Entitas** untuk menemukan entitas dengan nama ini.
- **bidang terprediksi**: bidang ini hanya diisi untuk beberapa jenis prediksi, dan tidak digunakan dalam prediksi nilai selama hubungan dengan pelanggan.
- **Status**: Status prediksi dijalankan.
  - **mengantri**: prediksi sedang menunggu proses lain untuk diselesaikan.
  - **Menyegarkan**: prediksi saat ini berjalan untuk membuat hasil yang akan mengalir ke entitas output.
  - **gagal**: prediksi yang jalankan gagal. Tinjau log untuk rincian selengkapnya.
  - **berhasil**: prediksi telah berhasil. Pilih Lihat di dalam elips vertikal untuk meninjau hasil prediksi.
- **Diedit**: tanggal konfigurasi untuk prediksi telah diubah.
- **Terakhir disegarkan**: Tanggal prediksi telah menyegarkan hasil di entitas output.

## <a name="manage-sentiment-analysis"></a>Mengelola analisis sentimen

Anda dapat mengoptimalkan, memecahkan masalah, menyegarkan, atau menghapus prediksi. Tinjau laporan kegunaan data input untuk mengetahui cara membuat prediksi lebih cepat dan lebih dapat diandalkan. Untuk informasi lebih lanjut, lihat [Kelola prediksi](manage-predictions.md).

## <a name="review-analysis-results"></a>Tinjau hasil analisis
 
1. Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**. 
1. Pilih nama prediksi yang ingin Anda tinjau hasilnya. Dalam hal ini, pilih analisis sentimen yang ingin Anda tinjau. 

### <a name="summary-tab"></a>tab Ringkasan

Ada empat bagian utama data dalam halaman hasil. 

- **Skor** sentimen rata-rata: Membantu Anda memahami sentimen keseluruhan di semua pelanggan. Skor sentimen dikelompokkan dalam tiga kategori: 
  1.    Negatif (-5 > 2)
  2.    Netral (-1 > 1)
  3.    Positif (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Representasi visual dari sentimen pelanggan secara keseluruhan.":::

- **Distribusi pelanggan berdasarkan skor** sentimen: Pelanggan dikategorikan ke dalam kelompok negatif, netral, dan positif berdasarkan skor sentimen mereka. Arahkan kursor ke bilah di histogram untuk melihat jumlah pelanggan dan skor sentimen rata-rata di setiap grup. Data ini dapat membantu Anda [membuat segmen pelanggan](segments.md) berdasarkan skor sentimen mereka.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="diagram batang menunjukkan sentimen pelanggan di ketiga kelompok sentimen tersebut.":::

- **Skor sentimen rata-rata dari waktu ke waktu**: Sentimen pelanggan dapat berubah seiring waktu. Kami menyediakan tren sentimen pelanggan Anda untuk rentang waktu data Anda. Tampilan ini dapat membantu Anda mengukur efek promosi musiman, peluncuran produk, atau intervensi terikat waktu lainnya pada sentimen pelanggan. Lihat grafik dengan memilih tahun yang diinginkan dari menu tarik-turun. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="bagan riwayat dengan skor sentimen dari waktu ke waktu yang diwakili sebagai garis.":::
 
- **Sentimen di seluruh aspek** bisnis: Tabel ini mencantumkan sentimen rata-rata di seluruh aspek bisnis. Ini dapat membantu Anda mengukur aspek mana dari bisnis Anda yang sudah memuaskan pelanggan atau aspek yang membutuhkan lebih banyak perhatian. Catatan umpan balik yang tidak selaras dengan aspek bisnis yang didukung dikategorikan di bawah **Lainnya**. Tabel diurutkan menurut abjad secara default. Anda dapat mengubah pengurutan dengan memilih header tabel.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Daftar aspek bisnis dengan nilai sentimen terkait dan jumlah pelanggan yang menyebutkannya.":::
 
  Pilih nama aspek bisnis untuk melihat informasi tambahan bagaimana aspek bisnis diidentifikasi oleh model. Ada dua bagian di panel ini: 

  - **Kata-kata** yang berpengaruh: Menunjukkan kata-kata teratas yang memengaruhi identifikasi model AI tentang aspek bisnis dalam umpan balik pelanggan. 
    **Tampilkan kata-kata** yang menyinggung: Memungkinkan Anda menyertakan kata-kata yang menyinggung dalam daftar dari data umpan balik pelanggan asli. Secara default, ini dinonaktifkan.  Masking kata yang menyinggung didukung oleh model AI dan mungkin tidak mendeteksi semua kata yang menyinggung. Kami terus melakukan iterasi dan melatih pengklasifikasi untuk kinerja yang optimal. Jika Anda mendeteksi kata menyinggung yang tidak difilter seperti yang diharapkan, beri tahu kami. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Daftar kata-kata berpengaruh dengan sakelar untuk menampilkan atau menyembunyikan kata-kata yang menyinggung.":::
 
  - **Sampel** umpan balik: Menampilkan catatan umpan balik aktual dalam data Anda. Kata-kata diberi kode warna sesuai dengan pengaruhnya terhadap identifikasi aspek bisnis. 


### <a name="influential-words-analysis-tab"></a>Tab analisis kata yang berpengaruh

Ada tiga bagian informasi tambahan yang menjelaskan cara kerja model sentimen.
  
1. **Kata-kata teratas yang berkontribusi pada sentimen** positif: Menunjukkan kata-kata teratas yang memengaruhi identifikasi model AI tentang sentimen positif dalam umpan balik pelanggan.  
2. **Kata-kata teratas yang berkontribusi pada sentimen** negatif: Menunjukkan kata-kata teratas yang memengaruhi identifikasi model AI tentang sentimen negatif dalam umpan balik pelanggan.  
3. **Sampel** umpan balik: Menampilkan catatan umpan balik aktual, satu dengan sentimen negatif dan satu dengan sentimen positif. Kata-kata dalam catatan umpan balik disorot sesuai dengan kontribusinya terhadap skor sentimen yang ditetapkan. Kata-kata yang berkontribusi pada skor sentimen positif disorot dengan warna hijau. Kata-kata yang berkontribusi pada skor negatif disorot dengan warna merah.
   Pilih **Lihat selengkapnya** untuk memuat lebih banyak sampel umpan balik yang memberikan lebih banyak informasi dan konteks tentang cara kerja model sentimen.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Contoh analisis sentimen pada umpan balik pelanggan.":::
 
**Tampilkan kata-kata** yang menyinggung: Memungkinkan Anda menyertakan kata-kata yang menyinggung dalam daftar dari data umpan balik pelanggan asli. Secara default, ini dinonaktifkan.  Masking kata yang menyinggung didukung oleh model AI dan mungkin tidak mendeteksi semua kata yang menyinggung. Kami terus melakukan iterasi dan melatih pengklasifikasi untuk kinerja yang optimal. Jika Anda mendeteksi kata menyinggung yang tidak difilter seperti yang diharapkan, beri tahu kami. 

## <a name="act-on-analysis-results"></a>Bertindak berdasarkan hasil analisis

Anda dapat dengan mudah mulai membuat segmen pelanggan baru dari halaman hasil analisis sentimen dengan **memilih Buat segmen** di bagian atas halaman hasil model.

:::image type="content" source="media/create-segment-model.png" alt-text="Bilah perintah dengan opsi pada model prediksi.":::
 
## <a name="potential-bias"></a>Potensi bias

Seperti halnya fitur apa pun yang menggunakan kecerdasan buatan prediktif, Anda harus menyadari potensi bias dalam data yang Anda gunakan untuk memprediksi sentimen pelanggan. Misalnya, jika Anda hanya mengumpulkan umpan balik secara digital, Anda dapat melewatkan umpan balik dari pelanggan yang terutama melakukan bisnis dengan Anda secara langsung, yang dapat memengaruhi output fitur tersebut.

Karena fitur ini menggunakan cara otomatis untuk mengevaluasi data dan membuat prediksi berdasarkan data tersebut, oleh karena itu fitur ini memiliki kemampuan untuk digunakan sebagai metode pembuatan profil, karena istilah tersebut didefinisikan oleh Peraturan Perlindungan Data Umum ("GDPR"). Penggunaan fitur ini oleh Anda untuk memproses data mungkin diatur dalam GDPR atau hukum atau peraturan lainnya. Anda bertanggung jawab untuk memastikan bahwa penggunaan Dynamics 365 Customer Insights Anda atas, termasuk analisis sentimen, mematuhi semua hukum dan peraturan yang berlaku, termasuk undang-undang yang terkait dengan privasi, data pribadi, data biometrik, perlindungan data, dan kerahasiaan komunikasi.

[!INCLUDE [footer-include](includes/footer-banner.md)]

