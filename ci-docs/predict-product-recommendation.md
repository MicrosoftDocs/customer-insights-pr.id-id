---
title: Prediksikan Rekomendasi produk
description: Memperkirakan produk yang mungkin dibeli atau berinteraksi dengan pelanggan.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610286"
---
# <a name="predict-product-recommendations"></a>Prediksikan Rekomendasi produk

Model rekomendasi produk membuat rangkaian rekomendasi produk prediktif. Rekomendasi didasarkan pada perilaku pembelian sebelumnya dan pelanggan dengan pola pembelian yang serupa. Model ini untuk konsumen individu (B-to-C).

Anda harus memiliki pengetahuan bisnis tentang berbagai jenis produk untuk bisnis Anda dan bagaimana pelanggan Anda berinteraksi dengan mereka. Kami mendukung rekomendasi produk yang telah dibeli sebelumnya oleh pelanggan atau rekomendasi untuk produk baru.

Rekomendasi produk dapat dipengaruhi oleh hukum dan peraturan setempat dan harapan pelanggan, yang modelnya tidak dibangun untuk memperhitungkan secara khusus. Oleh karena itu, **Anda harus meninjau rekomendasi sebelum mengirimkannya kepada pelanggan** Anda untuk memastikan bahwa Anda mematuhi hukum atau peraturan yang berlaku, dan harapan pelanggan atas apa yang mungkin Anda rekomendasikan.

Output dari model ini memberikan rekomendasi berdasarkan ID produk. Mekanisme pengiriman Anda harus memetakan ID produk yang diprediksi ke konten yang sesuai bagi pelanggan Anda untuk memperhitungkan pelokalan, konten gambar, dan konten atau perilaku khusus bisnis lainnya.

> [!TIP]
> Coba rekomendasi produk prediksi menggunakan data sampel: [Rekomendasi produk prediksi panduan sampel](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Prasyarat

- Setidaknya [izin kontributor](permissions.md)
- Setidaknya 100 pelanggan, lebih disukai lebih dari 10.000 pelanggan.
- Pengidentifikasi Pelanggan, pengidentifikasi unik untuk mencocokkan transaksi dengan pelanggan individu
- Setidaknya satu tahun data transaksional, lebih disukai dua hingga tiga tahun untuk memasukkan beberapa musiman. Idealnya, setidaknya tiga transaksi atau lebih per ID Pelanggan. Riwayat transaksi harus mencakup:
  - **ID** Transaksi: Pengidentifikasi unik pembelian atau transaksi.
  - **Tanggal transaksi**: Tanggal pembelian atau transaksi.
  - **Nilai transaksi**: Nilai numerik pembelian atau transaksi.
  - **ID** produk unik: ID produk atau layanan yang dibeli jika data Anda berada pada tingkat item baris.
  - **Pembelian atau pengembalian**: Nilai benar/salah boolean di mana *true* mengidentifikasi bahwa transaksi adalah pengembalian. Jika data Pembelian atau Pengembalian tidak disediakan dalam model dan **Nilai transaksi** negatif, kami menyimpulkan pengembalian.
- Entitas data katalog produk untuk digunakan sebagai filter produk.

> [!NOTE]
> - Model ini memerlukan riwayat transaksi pelanggan Anda di mana transaksi adalah data apa pun yang menggambarkan interaksi pengguna-produk. Misalnya, membeli produk, mengikuti kelas, atau menghadiri acara.
> - Hanya satu entitas riwayat transaksi yang dapat dikonfigurasi. Jika ada beberapa entitas pembelian, gabungkan sebelum Power Query penyerapan data.
> - Jika detail pesanan dan pesanan adalah entitas yang berbeda, gabunglah mereka sebelum digunakan dalam model. Model tidak hanya berfungsi dengan ID pesanan atau ID tanda terima dalam entitas.

## <a name="create-a-product-recommendation-prediction"></a>buat prediksi Rekomendasi produk

Pilih **Simpan draf** kapan saja untuk menyimpan prediksi sebagai draf. Draf prediksi ditampilkan di tab **Prediksi** saya.

1. Pergi ke **Prediksi** > **Intelijen**.

1. Pada tab **Buat**, pilih **Gunakan model** pada petak **Peta rekomendasi produk (pratinjau**).

1. Pilih **Mulai**.

1. **Namai model ini** dan **nama entitas Output** untuk membedakannya dari model atau entitas lain.

1. Pilih **Selanjutnya**.

### <a name="define-product-recommendation-preferences"></a>Tentukan preferensi rekomendasi produk

1. **Atur Jumlah produk** yang akan direkomendasikan kepada pelanggan. Nilai ini tergantung pada cara metode pengiriman Anda mengisi data.

1. Pilih apakah Anda ingin menyertakan produk yang sebelumnya telah dibeli pelanggan di **bidang Pembelian berulang yang diharapkan**.

1. Atur jendela **Lihat ke** belakang dengan jangka waktu yang dipertimbangkan model sebelum merekomendasikan produk kepada pengguna lagi. Misalnya, tunjukkan pelanggan membeli laptop setiap dua tahun. Model melihat riwayat pembelian selama dua tahun terakhir, dan jika menemukan item, item tersebut difilter dari rekomendasi.

1. Pilih **berikutnya**

### <a name="add-purchase-history"></a>Tambah riwayat pembelian

1. Pilih **Tambahkan data** untuk **riwayat transaksi** Pelanggan.

1. Pilih jenis **aktivitas semantik SalesOrderLine** yang berisi informasi riwayat transaksi atau pembelian yang diperlukan. Jika aktivitas belum disiapkan, pilih **di sini** dan buat.

1. Di bawah **Aktivitas**, jika atribut aktivitas dipetakan secara semantik saat aktivitas dibuat, pilih atribut atau entitas tertentu yang ingin Anda fokuskan pada perhitungan. Jika pemetaan semantik tidak terjadi, pilih **Edit dan petakan** data Anda.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Panel sisi yang menunjukkan pemilihan aktivitas tertentu dalam jenis semantik.":::

1. Pilih **Berikutnya** dan tinjau atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Pilih **Selanjutnya**.

### <a name="add-product-information-and-filters"></a>Menambahkan informasi dan filter produk

Terkadang, hanya produk tertentu yang bermanfaat atau sesuai untuk jenis prediksi yang Anda bangun. Gunakan filter produk untuk mengidentifikasi subset produk dengan karakteristik tertentu untuk direkomendasikan kepada pelanggan Anda. Model ini akan menggunakan semua produk yang tersedia untuk mempelajari pola tetapi hanya menggunakan produk yang cocok dengan filter produk dalam outputnya.

1. Tambahkan entitas katalog produk Anda yang berisi informasi untuk setiap produk. Petakan informasi yang diperlukan dan pilih **Simpan**.

1. Pilih **Selanjutnya**.

1. Pilih **Filter produk**:

   - **Tidak ada filter**: Gunakan semua produk dalam prediksi rekomendasi produk.

   - **Tentukan filter produktertentu**: Gunakan produk tertentu dalam prediksi rekomendasi produk. Di **panel Atribut** katalog produk, pilih atribut dari entitas katalog produk yang ingin Anda sertakan dalam filter.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Panel samping ditampilkan diatribusikan dalam entitas katalog produk untuk memilih filter produk.":::

1. Pilih apakah Anda ingin filter produk digunakan **dan** atau **atau** secara logis menggabungkan pilihan atribut Anda dari katalog produk.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Contoh konfigurasi filter produk dikombinasikan dengan konektor AND logis.":::

1. Pilih **Selanjutnya**.

### <a name="set-update-schedule"></a>Atur Jadwal pembaruan

1. Pilih frekuensi untuk melatih kembali model Anda. Pengaturan ini penting untuk memperbarui keakuratan prediksi karena data baru diserap ke dalam Customer Insights. Sebagian besar bisnis dapat melatih sekali per bulan dan mendapatkan akurasi yang baik untuk prediksi mereka.

1. Pilih **Selanjutnya**.

### <a name="review-and-run-the-model-configuration"></a>Memeriksa dan menjalankan konfigurasi model

Langkah **Tinjau dan jalankan** menunjukkan ringkasan konfigurasi dan memberikan kesempatan untuk membuat perubahan sebelum Anda membuat prediksi.

1. Pilih **Edit** pada salah satu langkah untuk meninjau dan membuat perubahan apa pun.

1. Jika Anda puas dengan pilihan Anda, pilih **Simpan dan jalankan** untuk mulai menjalankan model. Pilih **Selesai**. Tab **Prediksi** saya ditampilkan saat prediksi sedang dibuat. Proses dapat berlangsung selama beberapa jam hingga selesai, tergantung pada jumlah data yang digunakan dalam prediksi.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Lihat hasil prediksi

1. Pergi ke **Prediksi** > **Intelijen**.

1. Di tab **Prediksi** saya, pilih prediksi yang ingin Anda lihat.

Ada lima bagian utama data dalam halaman hasil.

- **Performa model:** Nilai A, B, atau C menunjukkan performa prediksi dan dapat membantu Anda membuat keputusan untuk menggunakan hasil yang disimpan dalam entitas output.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Gambar hasil kinerja model dengan grade A.":::

  Peringkat ditentukan berdasarkan aturan berikut:
  - **A** ketika metrik "Success @ K" setidaknya 10% lebih banyak dari baseline.
  - **B** ketika metrik "Success @ K" adalah 0% hingga 10% lebih tinggi dari baseline.
  - **C** ketika metrik "Sukses @ K" kurang dari garis dasar.
  - **Baseline**: Produk teratas yang paling direkomendasikan berdasarkan jumlah pembelian di semua pelanggan + aturan yang dipelajari yang diidentifikasi oleh model = serangkaian rekomendasi untuk pelanggan. Selanjutnya, prediksi akan dibandingkan dengan produk teratas, sebagaimana dihitung menurut jumlah pelanggan yang membeli produk tersebut. Jika pelanggan memiliki minimal satu produk dalam produk rekomendasinya yang juga terlihat di produk pembelian teratas, maka produk tersebut dianggap sebagai bagian dari dasar. Misalnya, jika 10 dari pelanggan ini memiliki produk yang direkomendasikan yang dibeli dari 100 total pelanggan, baseline-nya adalah 10%.
  - **Berhasil @ K**: Rekomendasi dibuat untuk semua pelanggan dan dibandingkan dengan serangkaian validasi periode waktu transaksi. Misalnya, dalam periode 12 bulan, bulan 12 disisihkan sebagai kumpulan data validasi. Jika model memperkirakan sekurangnya satu hal yang akan Anda beli dalam bulan 12 berdasarkan apa yang ia pelajari dari 11 bulan sebelumnya, pelanggan akan meningkatkan metrik "Berhasil @ K".

- **Sebagian besar produk yang disarankan (dengan tally):** Lima produk teratas yang diprediksi untuk pelanggan Anda.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Grafik yang menampilkan 5 produk rekomendasi teratas.":::

- **Faktor rekomendasi utama**: Model menggunakan riwayat transaksi pelanggan untuk membuat rekomendasi produk. Ini mempelajari pola berdasarkan pembelian sebelumnya dan menemukan kesamaan antara pelanggan dan produk. Kesamaan ini kemudian digunakan untuk menghasilkan rekomendasi produk.
  Faktor-faktor berikut dapat mempengaruhi rekomendasi produk yang dihasilkan oleh model.
  - **Transaksi** sebelumnya: Produk yang direkomendasikan didasarkan pada pola pembelian sebelumnya. Misalnya, model dapat merekomendasikan *Surface Arc Mouse* jika seseorang baru saja membeli *Surface Book 3* dan *Surface Pen*. Model ini mengetahui bahwa secara historis, banyak pelanggan telah membeli *Surface Arc Mouse* setelah membeli *Surface Book 3* dan *Surface Pen*.
  - **Kesamaan pelanggan**: Produk yang direkomendasikan secara historis dibeli oleh pelanggan lain yang menunjukkan pola pembelian serupa. Misalnya, John direkomendasikan *Surface Headphones 2* karena Jennifer dan Brad baru-baru ini membeli *Surface Headphones 2*. Model ini percaya John mirip dengan Jennifer dan Brad karena mereka secara historis memiliki pola pembelian yang sama.
  - **Kesamaan produk**: Produk yang direkomendasikan mirip dengan produk lain yang dibeli pelanggan sebelumnya. Model ini menganggap dua produk mirip jika dibeli bersama atau oleh pelanggan serupa. Misalnya, seseorang mendapatkan rekomendasi untuk *Drive Penyimpanan USB* karena mereka sebelumnya membeli *Adaptor USB-C ke USB* dan model percaya bahwa *Drive Penyimpanan USB* mirip dengan *Adaptor USB-C ke USB* berdasarkan pola pembelian historis.

  Setiap rekomendasi produk dipengaruhi oleh satu atau lebih faktor-faktor ini. Persentase rekomendasi di mana setiap faktor yang mempengaruhi memainkan peran divisualisasikan dalam bagan. Dalam contoh berikut, 100% dari rekomendasi dipengaruhi oleh transaksi sebelumnya, 60% oleh kesamaan pelanggan dan 22% berdasarkan kesamaan produk. Arahkan kursor ke bilah di bagan untuk melihat persentase yang tepat di mana faktor yang memengaruhi berkontribusi.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Faktor rekomendasi utama yang dipelajari oleh model untuk menghasilkan rekomendasi produk.":::

- **Statistik data**: Gambaran umum jumlah transaksi, pelanggan, dan produk yang dipertimbangkan model. Hal ini didasarkan pada data input yang digunakan untuk mempelajari pola dan menghasilkan rekomendasi produk.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Statistik data seputar data input yang digunakan oleh model untuk mempelajari pola.":::
  
  Model ini menggunakan semua data yang tersedia untuk mempelajari pola. Oleh karena itu, jika Anda menggunakan pemfilteran produk dalam konfigurasi model, bagian ini menunjukkan jumlah total produk yang dianalisis model untuk mempelajari pola, yang mungkin berbeda dari jumlah produk yang cocok dengan kriteria pemfilteran yang ditentukan. Pemfilteran berlaku pada output yang dihasilkan oleh model.

- **Contoh rekomendasi produk:** Sampel rekomendasi yang diyakini model kemungkinan akan dibeli oleh pelanggan. Jika katalog produk ditambahkan, ID produk akan diganti dengan nama produk.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Daftar yang menampilkan saran dengan keyakinan tinggi untuk rangkaian pelanggan individual tertentu.":::

> [!NOTE]
> Dalam entitas output untuk model ini, *Skor* menunjukkan ukuran kuantitatif rekomendasi. Model ini merekomendasikan produk dengan skor yang lebih tinggi atas produk dengan skor yang lebih rendah. Untuk melihat skor, buka **Entitas** > **Data** dan lihat tab data untuk entitas output yang Anda tentukan untuk model ini.

[!INCLUDE [footer-include](includes/footer-banner.md)]
