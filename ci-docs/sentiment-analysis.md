---
title: Analisis sentimen untuk umpan balik pelanggan (pratinjau)
description: Pelajari cara menggunakan model analisis sentimen pada umpan balik pelanggan di Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610470"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Menganalisis sentimen dalam umpan balik pelanggan (pratinjau)

Analisis sentimen memungkinkan Anda untuk mensintesis sentimen pelanggan dan mengidentifikasi aspek bisnis sebagai peluang untuk perbaikan. Fitur Customer Insights ini membantu Anda memahami apa yang bekerja dengan baik dan apa yang perlu Anda tangani. Ini dapat membantu Anda mendorong tindakan bisnis yang memungkinkan pengalaman yang menghasilkan kepuasan dan loyalitas pelanggan yang tinggi.

## <a name="overview"></a>Gambaran Umum

Fitur analisis sentimen menghasilkan dua wawasan turunan per ID pelanggan. Skor sentimen (-5 hingga 5) dan daftar aspek bisnis yang berlaku (bidang bisnis) yang bersama-sama membantu Anda lebih memahami umpan balik pelanggan.

Analisis ini membantu Anda:
- Dapatkan gambaran umum tentang sentimen pelanggan terhadap merek atau organisasi
- Identifikasi pelanggan dengan sentimen negatif untuk memfokuskan kampanye dan keterlibatan Anda dan optimalkan untuk pengembalian yang lebih tinggi  
- Identifikasi aspek bisnis dengan masalah yang ditunjukkan oleh pelanggan  
- Segmentasikan pelanggan berdasarkan sentimen mereka untuk menjalankan kampanye yang dipersonalisasi dengan upaya penjualan, pemasaran, dan dukungan yang ditargetkan
- Mengoptimalkan operasi bisnis dengan menangani area yang menjadi perhatian atau peluang yang disebutkan oleh pelanggan
- Kenali aspek bisnis yang berjalan dengan baik dan beri penghargaan kepada pelanggan yang bahagia melalui program loyalitas dan promosi

Model ini menyediakan daftar kata-kata yang memengaruhi keputusan model untuk menetapkan skor sentimen atau aspek bisnis tertentu untuk komentar umpan balik.  

Kami menggunakan dua **model** Natural Language Processing (NLP): Yang pertama menetapkan setiap komentar umpan balik skor sentimen. Model kedua mengaitkan setiap umpan balik dengan semua aspek bisnis yang berlaku. Model-model tersebut dilatih pada data publik dari sumber-sumber di media sosial, ritel, restoran, produk konsumen, dan industri otomotif.
  
Aspek bisnis yang telah ditentukan sebelumnya agar model dapat dikaitkan dengan data umpan balik meliputi:
- Manajemen akun
- Selesai dan pembayaran
- Dukungan pelanggan
- Pengambilan di toko
- Pengemasan pengiriman dan pengambilan
- Pra-pemesanan
- Harga
- Privasi dan keamanan
- Promosi dan hadiah
- Tanda terima dan garansi
- Pengembalian penukaran dan pembatalan
- Akurasi pemenuhan
- Kualitas situs web/aplikasi

> [!NOTE]
> Saat ini, kami hanya mendukung analisis sentimen pada umpan balik pelanggan bahasa Inggris. Lebih banyak bahasa akan didukung di masa mendatang. Jika umpan balik dalam bahasa lain diunggah, model akan tetap mengembalikan hasil. Namun, hasil ini tidak akan akurat.

## <a name="prerequisites"></a>Prasyarat

- Setidaknya [izin kontributor](permissions.md)
- [Data umpan balik teks terpadu](data-unification.md). Kami sangat menyarankan agar Anda [mengonfigurasi entitas data umpan balik Anda sebagai entitas aktivitas tipe semantik (jenis](map-entities.md#select-primary-key-and-semantic-type-for-attributes) Umpan Balik).
- ID Pelanggan Terpadu (UCID) dari penyatuan data untuk mencocokkan catatan data umpan balik teks dengan pelanggan individu.
- ID tanggapan
- Stempel waktu umpan balik
- Teks tanggapan

Customer Insights dapat memproses hingga 10 juta catatan umpan balik untuk satu model yang dijalankan. Model ini dapat menganalisis komentar umpan balik hingga 128 kata. Jika komentar umpan balik lebih panjang, analisis hanya mempertimbangkan 128 kata pertama.

> [!NOTE]
> Hanya satu entitas umpan balik yang dapat dikonfigurasi. Jika ada beberapa entitas umpan balik, gabungkan entitas tersebut Power Query sebelum penyerapan data.

## <a name="configure-a-sentiment-analysis"></a>Mengonfigurasi analisis sentimen

1. Pergi ke **Prediksi** > **Intelijen**.

1. Pada tab **Buat**, pilih **Gunakan model** pada petak **peta Analisis sentimen pelanggan (pratinjau**).

1. Pilih **Mulai**.

1. **Beri** nama analisis dan berikan **nama entitas output aspek Bisnis dan** nama **entitas** output skor Sentimen.

1. Pilih **Selanjutnya**.

1. Pilih **Tambahkan data** untuk **umpan balik** Pelanggan.

1. Pilih jenis **aktivitas semantik Umpan balik** yang berisi data umpan balik. Jika aktivitas belum disiapkan, pilih **di sini** dan buat.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Langkah konfigurasi untuk memilih aktivitas umpan balik untuk analisis sentimen.":::

1. Pilih aktivitas yang akan digunakan untuk analisis sentimen ini, lalu pilih **Berikutnya**.

1. Petakan atribut dalam data Anda ke atribut model. 

1. Pilih **Simpan**.

1. Pilih **Selanjutnya**. Langkah **Tinjau dan jalankan** menunjukkan ringkasan konfigurasi dan memberikan kesempatan untuk membuat perubahan sebelum Anda membuat analisis.

1. Pilih **Edit** pada salah satu langkah untuk meninjau dan membuat perubahan apa pun.

1. Jika Anda puas dengan pilihan Anda, pilih **Simpan dan jalankan** untuk mulai menjalankan model. Pilih **Selesai**. Tab **Prediksi** saya ditampilkan saat prediksi sedang dibuat. Proses dapat berlangsung selama beberapa jam hingga selesai, tergantung pada jumlah data yang digunakan dalam prediksi.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Lihat hasil analisis

1. Pergi ke **Prediksi** > **Intelijen**.

1. Di tab **Prediksi** saya, pilih prediksi yang ingin Anda lihat.

Ada dua tab hasil.

### <a name="sumary-tab"></a>Tab Sumary

Ada empat bagian utama data dalam halaman hasil.

- **Skor** sentimen rata-rata: Skor sentimen membantu Anda memahami sentimen keseluruhan di semua pelanggan.
  - **Negatif** (-5 > 2)
  - **Netral** (-1 > 1)
  - **Positif** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Representasi visual dari sentimen pelanggan secara keseluruhan.":::

- **Distribusi pelanggan berdasarkan skor** sentimen: Pelanggan dikategorikan ke dalam kelompok negatif, netral, dan positif berdasarkan skor sentimen mereka. Arahkan kursor ke bilah di histogram untuk melihat jumlah pelanggan dan skor sentimen rata-rata di setiap grup. Data ini dapat membantu Anda [membuat segmen pelanggan](prediction-based-segment.md) berdasarkan skor sentimen mereka.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="diagram batang menunjukkan sentimen pelanggan di ketiga kelompok sentimen tersebut.":::

- **Skor sentimen rata-rata dari waktu ke waktu**: Sentimen pelanggan dapat berubah seiring waktu. Kami menyediakan tren sentimen pelanggan Anda untuk rentang waktu data Anda. Tampilan ini membantu Anda mengukur efek promosi musiman, peluncuran produk, atau intervensi terikat waktu lainnya pada sentimen pelanggan. Lihat grafik dengan memilih tahun yang diinginkan dari menu tarik-turun.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="bagan riwayat dengan skor sentimen dari waktu ke waktu yang diwakili sebagai garis.":::

- **Sentimen di seluruh aspek** bisnis: Sentimen rata-rata di seluruh aspek bisnis membantu Anda mengukur aspek mana dari bisnis Anda yang sudah memuaskan pelanggan atau membutuhkan lebih banyak perhatian. Catatan umpan balik yang tidak selaras dengan aspek bisnis yang didukung dikategorikan di bawah **Lainnya**. Urutkan data dengan memilih kolom apa pun.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Daftar aspek bisnis dengan nilai sentimen terkait dan jumlah pelanggan yang menyebutkannya.":::

  Pilih nama aspek bisnis untuk melihat bagaimana aspek bisnis diidentifikasi oleh model:

  - **Kata-kata** berpengaruh: Kata-kata teratas yang memengaruhi identifikasi model AI tentang aspek bisnis dalam umpan balik pelanggan.
    **Tampilkan kata-kata** yang menyinggung: Memungkinkan Anda menyertakan kata-kata yang menyinggung dalam daftar dari data umpan balik pelanggan asli. Secara default, ini dinonaktifkan.  Masking kata yang menyinggung didukung oleh model AI dan mungkin tidak mendeteksi semua kata yang menyinggung. Jika Anda mendeteksi kata menyinggung yang tidak difilter seperti yang diharapkan, beri tahu kami.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Daftar kata-kata berpengaruh dengan sakelar untuk menampilkan atau menyembunyikan kata-kata yang menyinggung.":::

  - **Sampel umpan** balik: Catatan umpan balik aktual dalam data Anda. Kata-kata diberi kode warna sesuai dengan pengaruhnya terhadap identifikasi aspek bisnis.

### <a name="influential-words-analysis-tab"></a>Tab analisis kata yang berpengaruh

Ada tiga bagian informasi tambahan yang menjelaskan cara kerja model sentimen.
  
- **Kata-kata teratas yang berkontribusi pada sentimen** positif: Kata-kata teratas yang memengaruhi identifikasi model AI tentang sentimen positif dalam umpan balik pelanggan.  

- **Kata-kata teratas yang berkontribusi pada sentimen** negatif: Kata-kata teratas yang memengaruhi identifikasi model AI tentang sentimen negatif dalam umpan balik pelanggan.

- **Sampel** umpan balik: Catatan umpan balik aktual, satu dengan sentimen negatif dan satu dengan sentimen positif. Kata-kata dalam catatan umpan balik disorot sesuai dengan kontribusinya terhadap skor sentimen yang ditetapkan. Kata-kata yang berkontribusi pada skor sentimen positif disorot dengan warna hijau. Kata-kata yang berkontribusi pada skor negatif disorot dengan warna merah.
   Pilih **Lihat lainnya** untuk memuat lebih banyak sampel umpan balik.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Contoh analisis sentimen pada umpan balik pelanggan.":::

**Tampilkan kata-kata** yang menyinggung: Memungkinkan Anda menyertakan kata-kata yang menyinggung dalam daftar dari data umpan balik pelanggan asli. Secara default, ini dinonaktifkan.  Masking kata yang menyinggung didukung oleh model AI dan mungkin tidak mendeteksi semua kata yang menyinggung. Jika Anda mendeteksi kata menyinggung yang tidak difilter seperti yang diharapkan, beri tahu kami.

## <a name="act-on-analysis-results"></a>Bertindak berdasarkan hasil analisis

Untuk membuat segmen baru pelanggan dari hasil analisis sentimen, pilih **Buat segmen** di bagian atas halaman hasil model.

## <a name="potential-bias"></a>Potensi bias

Seperti halnya fitur apa pun yang menggunakan kecerdasan buatan prediktif, mungkin ada potensi bias dalam data yang Anda gunakan untuk memprediksi sentimen pelanggan. Misalnya, jika Anda hanya mengumpulkan umpan balik secara digital, Anda mungkin melewatkan umpan balik dari pelanggan yang terutama melakukan bisnis dengan Anda secara langsung, yang memengaruhi output fitur tersebut.

Karena fitur ini menggunakan cara otomatis untuk mengevaluasi data dan membuat prediksi berdasarkan data tersebut, oleh karena itu fitur ini memiliki kemampuan untuk digunakan sebagai metode pembuatan profil, karena istilah tersebut didefinisikan oleh Peraturan Perlindungan Data Umum ("GDPR"). Penggunaan fitur ini oleh Anda untuk memproses data mungkin diatur dalam GDPR atau hukum atau peraturan lainnya. Anda bertanggung jawab untuk memastikan bahwa penggunaan Dynamics 365 Customer Insights Anda atas, termasuk analisis sentimen, mematuhi semua hukum dan peraturan yang berlaku, termasuk undang-undang yang terkait dengan privasi, data pribadi, data biometrik, perlindungan data, dan kerahasiaan komunikasi.

[!INCLUDE [footer-include](includes/footer-banner.md)]

