---
title: Contoh panduan prediksi nilai seumur hidup pelanggan (CLV)
description: Gunakan panduan sampel ini untuk mencoba model prediksi pelanggan nilai seumur hidup.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 2013533ed225a396d21e51e63297d7608ce58ac6
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051641"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Contoh panduan prediksi nilai seumur hidup pelanggan (CLV)

Panduan ini akan menjelaskan kepada Anda contoh komprehensif dari nilai seumur hidup pelanggan (CLV) dalam Customer Insights dengan menggunakan data sampel.

## <a name="scenario"></a>Skenario

Contoso adalah perusahaan yang memproduksi mesin kopi dan kopi berkualitas tinggi. Mereka menjual produk melalui situs web Contoso Coffee mereka. Perusahaan ingin memahami nilai (pendapatan) yang dapat dihasilkan pelanggan mereka dalam 12 bulan ke depan. Mengetahui nilai yang diharapkan dari pelanggan mereka dalam 12 bulan ke depan akan membantu mereka mengarahkan upaya pemasaran mereka pada pelanggan bernilai tinggi.

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md) di Customer Insights.
- Sebaiknya Anda menerapkan langkah-langkah berikut [di lingkungan baru](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tugas 1- Serap Data

Tinjau artikel [tentang penyerapan](data-sources.md) data dan [mengimpor sumber data menggunakan Power Query konektor](connect-power-query.md). Informasi berikut ini mengasumsikan bahwa Anda telah mengenal dan menyerap data secara umum.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Menyerap data pelanggan dari platform eCommerce

1. Buat sumber data bernama  **eCommerce** , pilih pilihan impor, dan pilih konektor **Text/CSV**.

1. Masukkan URL untuk kontak eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Saat mengedit data, pilih  **Ubah**  dan kemudian  **gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **DateOfBirth**: tanggal
   - **CreatedOn**: Tanggal/Waktu/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tanggal lahir sampai saat ini.":::

1. Di bidang ' nama ' pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **eCommerceContacts**

1. **Simpan** Sumber Data.

### <a name="ingest-online-purchase-data"></a>Menyerap Data pembelian online

1. Tambahkan himpunan data lain ke sumber data **eCommerce** yang sama. Pilih konektor **teks/CSV** lagi.

1. Masukkan URL untuk data **pembelian online** https://aka.ms/ciadclassonline.

1. Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **PurchasedOn**: tanggal/waktu
   - **TotalPrice**: mata uang

1. Di bidang **nama** pada panel sisi, ganti nama sumber data dari **kueri** menjadi **eCommercePurchases**.

1. **Simpan** Sumber Data.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Menyerap data pelanggan dari skema kesetiaan

1. Buat sumber data bernama **LoyaltyScheme**, pilih pilihan impor, dan pilih konektor **Text/CSV**.

1. Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **DateOfBirth**: tanggal
   - **RewardsPoints**: Bilangan Cacah
   - **CreatedOn**: Waktu/Tanggal

1. Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **loyCustomers**.

1. **Simpan** Sumber Data.

### <a name="ingest-customer-data-from-website-reviews"></a>Serap data pelanggan dari ulasan situs

1. Buat sumber data bernama **Situs web**, pilih pilihan impor, dan pilih konektor **Text/CSV**.

1. Masukkan URL untuk kontak eCommerce https://aka.ms/CI-ILT/WebReviews.

1. Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:

   - **ReviewRating**: Angka Desimal
   - **ReviewDate**: tanggal

1. Di bidang 'Nama' di panel sebelah kanan, ganti nama sumber data Anda dari **Kueri** menjadi **Ulasan**.

1. **Simpan** Sumber Data.

## <a name="task-2---data-unification"></a>Tugas 2-penyatuan data

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Tugas 3 - Mengonfigurasi prediksi nilai seumur hidup pelanggan

Dengan adanya profil pelanggan terpadu, kita sekarang dapat menjalankan prediksi nilai seumur hidup pelanggan. Untuk langkah-langkah terperinci, lihat [prediksi Nilai Umur Pelanggan](predict-customer-lifetime-value.md).

1. Buka  **Kecerdasan**  > **Prediksi**  dan pilih **model nilai seumur hidup Pelanggan**.

1. Telusuri informasi di panel samping dan pilih **Mulai**.

1. Beri nama model **Prediksi CLV eCommerce OOB** dan entitas output  **OOBeCommerceCLVPrediction**.

1. Tentukan preferensi model untuk model CLV:
   - **Periode waktu prediksi**: **12 bulan atau 1 tahun**. Pengaturan ini menentukan seberapa jauh ke masa depan untuk memprediksi nilai seumur hidup pelanggan.
   - **Pelanggan aktif**: Tentukan apa artinya pelanggan aktif untuk bisnis Anda. Tetapkan jangka waktu historis di mana pelanggan harus memiliki setidaknya satu transaksi untuk dianggap aktif. Model tersebut hanya akan memperkirakan CLV untuk pelanggan aktif. Pilih antara mengizinkan model menghitung periode waktu berdasarkan data transaksi historis atau memberikan informasi jangka waktu. Dalam contoh panduan ini, kami **membiarkan model menghitung interval pembelian**, yang merupakan opsi default.
   - **Pelanggan bernilai tinggi**: Tentukan pelanggan bernilai tinggi sebagai persentil pelanggan membayar teratas. Model ini menggunakan input ini untuk memberikan hasil yang sesuai dengan definisi bisnis Anda tentang pelanggan bernilai tinggi. Anda dapat memilih untuk membiarkan model menentukan pelanggan bernilai tinggi. Ini menggunakan aturan heuristik yang memperoleh persentil. Anda juga dapat mendefinisikan pelanggan bernilai tinggi sebagai persentil pelanggan membayar di masa mendatang. Dalam panduan sampel ini, kami secara manual mendefinisikan pelanggan bernilai tinggi sebagai **30% pelanggan bayar aktif teratas** dan memilih **Berikutnya**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Langkah preferensi dalam pengalaman terpandu untuk model CLV.":::

1. Di langkah **Data yang Diperlukan**, pilih **Tambahkan data** untuk menyediakan data riwayat transaksi.

1. Tambahkan entitas **eCommercePurchases: eCommerce** dan petakan atribut yang diperlukan oleh model:
   - ID Transaksi: eCommerce.eCommercePurchases.PurchaseId
   - Tanggal Transaksi: eCommerce.eCommercePurchases.PurchasedOn
   - Jumlah transaksi: eCommerce.eCommercePurchases.TotalPrice
   - ID Produk: eCommerce.eCommercePurchases.ProductId

1. Pilih **Selanjutnya**.

1. Mengatur hubungan antara entitas **eCommercePurchases: entitas eCommerce** dan  **eCommerceContacts: eCommerce**.

1. Langkah **Data tambahan (opsional)** memungkinkan Anda menambahkan lebih banyak data aktivitas pelanggan. Data ini dapat membantu mendapatkan lebih banyak wawasan untuk interaksi pelanggan dengan bisnis Anda, yang dapat berkontribusi pada CLV. Menambahkan interaksi pelanggan utama seperti log web, log layanan pelanggan, atau riwayat program hadiah dapat meningkatkan akurasi prediksi. Pilih **Tambahkan data** untuk menyertakan lebih banyak data aktivitas pelanggan.

1. Tambahkan entitas aktivitas pelanggan dan petakan nama bidangnya ke bidang terkait yang diperlukan oleh model:
   - Entitas aktivitas pelanggan: Reviews:Website
   - Kunci utama: Website.Reviews.ReviewId
   - Cap waktu: website.reviews.reviewDate
   - Kejadian (nama aktivitas): Website.Reviews.ActivityTypeDisplay
   - Detail (jumlah atau nilai): Website.Reviews.ReviewRating

1. Pilih **Berikutnya** dan konfigurasikan aktivitas dan hubungan antara data transaksi dan data pelanggan:  
   - Jenis aktivitas: Pilih yang ada
   - Label aktivitas: Review
   - Label terkait: Website.Reviews.UserId
   - Entitas pelanggan: eCommerceContacts:eCommerce
   - Relasi: WebsiteReviews

1. Pilih **berikutnya** untuk mengatur jadwal model.

   Model perlu berlatih secara teratur untuk mempelajari pola baru ketika ada data baru yang diserap. Untuk contoh ini, pilih **Bulanan**.

1. Setelah meninjau semua rincian, pilih  **Simpan dan jalankan**.

## <a name="task-4---review-model-results-and-explanations"></a>Tugas 4-TInjau hasil dan penjelasan model

Biarkan model menyelesaikan pelatihan dan penilaian data. Selanjutnya, Anda dapat meninjau hasil dan penjelasan model CLV. Untuk informasi lebih lanjut, lihat [meninjau status dan hasil prediksi](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Tugas 5 - Buat segmen pelanggan bernilai tinggi

Menjalankan model membuat entitas baru, yang tercantum di **Data** > **Entitas**. Anda dapat membuat segmen pelanggan baru berdasarkan entitas yang dibuat oleh model.

1. Buka **Segmen**. 

1. Pilih  **baru** lalu pilih **buat dari** > **intelijen**.

   ![Membuat segmen dengan output model.](media/segment-intelligence.png)

1. Pilih entitas  **OOBeCommerceCLVPrediction** dan tentukan segmen:
  - Bidang: CLVScore
  - Operator: Lebih besar dari
  - Nilai: 1500

1. Pilih **Tinjau** dan **Simpan** segmen.

Anda sekarang memiliki segmen yang mengidentifikasi pelanggan yang diprediksi akan menghasilkan pendapatan lebih dari $1500 dalam 12 bulan ke depan. Segmen ini diperbarui secara dinamis jika lebih banyak data yang diserap.

Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).
