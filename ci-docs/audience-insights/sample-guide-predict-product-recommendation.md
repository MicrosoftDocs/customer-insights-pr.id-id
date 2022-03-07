---
title: Panduan sampel prediksi Rekomendasi produk
description: Gunakan contoh panduan ini untuk mencoba model prediksi rekomendasi produk siap pakai.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 8ba54cfd466049c8df99c15f34626ab1914234f1
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354651"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Panduan sampel prediksi Rekomendasi produk

Kami akan menjelaskan kepada Anda contoh akhir dari prediksi rekomendasi produk menggunakan data sampel yang diberikan di bawah ini.

## <a name="scenario"></a>Skenario

Aswono adalah perusahaan yang memproduksi mesin kopi dan kopi berkualitas tinggi, yang dijual melalui situs web Kopi Aswono. Tujuan mereka adalah untuk memahami produk yang harus mereka rekomendasikan kepada pelanggan berulang mereka. Mengetahui pelanggan **lebih cenderung membeli** dapat membantu mereka menghemat upaya pemasaran dengan berfokus pada item tertentu.

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md) di Customer Insights.
- Sebaiknya Anda menerapkan langkah-langkah berikut [di lingkungan baru](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tugas 1- Serap Data

Tinjau artikel [tentang konsumsi](data-sources.md) data dan [impor sumber data menggunakan Power Query konektor](connect-power-query.md) secara khusus. Informasi berikut ini mengasumsikan bahwa Anda telah mengenal dan menyerap data secara umum.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Menyerap data pelanggan dari platform eCommerce

1. Buat sumber data bernama **eCommerce**, pilih pilihan impor, dan pilih konektor **Text/CSV**.

1. Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasscontacts.

1. Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **DateOfBirth**: tanggal
   - **CreatedOn**: Tanggal/Waktu/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tanggal lahir sampai saat ini.":::

5. Di bidang ' nama ' pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **eCommerceContacts**

6. **Simpan** Sumber Data.

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

## <a name="task-2---data-unification"></a>Tugas 2-penyatuan data

Setelah menyerap data, kami sekarang memulai proses penyatuan data untuk membuat profil pelanggan terpadu. Untuk informasi selengkapnya, lihat [Penyatuan data](data-unification.md).

### <a name="map"></a>Peta

1. Setelah menyerap data, Petakan kontak dari eCommerce dan data kesetiaan ke jenis data umum. Buka **Data** > **Satukan** > **Petakan**.

2. Pilih entitas yang menunjukkan profil pelanggan- **ecommercecontacts** dan **loycustomer**.

   ![menyatukan sumber data eCommerce dan kesetiaan.](media/unify-ecommerce-loyalty.png)

3. Pilih **contactid** sebagai kunci primer untuk **ecommercecontacts** dan **loyaltyid** sebagai kunci primer untuk **loycustomer**.

   ![Menyatukan LoyaltyId sebagai kunci primer.](media/unify-loyaltyid.png)

### <a name="match"></a>Cocokkan

1. Pergi ke tab **Cocokkan** dan pilih **Atur Urutan**.

2. Dalam daftar dropdown **Utama**, pilih **eCommerceContacts: e Commerce** sebagai sumber utama dan sertakan semua rekaman.

3. Dalam daftar dropdown **Entitas 2**, pilih **loyCustomers: LoyaltyScheme** dan sertakan semua rekaman.

   ![Satukan dan cocokkan eCommerce dan Loyalty.](media/unify-match-order.png)

4. Pilih **Buat aturan baru**

5. Tambahkan kondisi pertama Anda menggunakan FullName.

   - Untuk eCommerceContacts, pilih **FullName** di dropdown.
   - Untuk loyCustomers, pilih **FullName** di dropdown.
   - Pilih drop-down **normalkan** dan pilih **jenis (telepon, nama, alamat,...)**.
   - Atur **tingkat presisi**: **dasar** dan **nilai**: **tinggi**.

6. Masukkan nama **fullname, email** untuk aturan baru.

   - Tambahkan kondisi kedua untuk alamat email dengan memilih **Tambah kondisi**
   - Untuk entitas eCommerceContacts, pilih **EMail** di dropdown.
   - Untuk entitas loyCustomers, pilih **EMail** di dropdown.
   - Biarkan Normalkan kosong.
   - Atur **tingkat presisi**: **dasar** dan **nilai**: **tinggi**.

   ![Satukan aturan kecocokan untuk nama dan email.](media/unify-match-rule.png)

7. Pilih **Simpan** dan **Tutup**.

### <a name="merge"></a>Penggabungan

1. Buka tab **Gabungkan**.

1. Pada entitas **contactid** untuk **loycustomer**, ubah nama tampilan ke **contactidloyalty** untuk membedakannya dari id lain yang diserap.

   ![Ubah nama contactid dari Loyalty id.](media/unify-merge-contactid.png)

1. Pilih **Simpan** dan **Jalankan** untuk memulai proses penggabungan.

## <a name="task-3---configure-product-recommendation-prediction"></a>Tugas 3 - Mengkonfigurasi prediksi rekomendasi produk

Dengan profil pelanggan terpadu di tempatnya, kini kita dapat menjalankan prediksi kehilangan pelanggan langganan.

1. Buka **Inteligensi** > **prediksi** pilih **Rekomendasi produk**.

1. Pilih **Mulai**.

1. Namai **Prediksi model rekomendasi produk OOB** dan entitas output **OOBProductRecommendationModelPrediction**.

1. Tentukan tiga kondisi untuk model:

   - **Jumlah produk**: Atur nilai ini ke **5**. Pengaturan ini menentukan seberapa banyak produk yang ingin Anda rekomendasikan kepada pelanggan.

   - **Ulangi pembelian yang diharapkan**: Pilih **Ya** untuk menunjukkan bahwa Anda ingin menyertakan produk dalam rekomendasi yang telah dibeli pelanggan Anda sebelumnya.

   - **Periode lihat kembali:** Pilih sekurangnya **365 hari**. Pengaturan ini menentukan berapa lama model akan melihat kembali aktivitas pelanggan untuk menggunakannya sebagai input untuk rekomendasi mereka.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferensi model untuk model rekomendasi produk.":::

1. Pilih **Data yang diperlukan** dan pilih **Tambah data** untuk Riwayat pembelian.

1. Tambahkan entitas **eCommercePurchases : eCommerce** dan Petakan bidang dari eCommerce ke bidang terkait yang diperlukan oleh model.

1. Gabungkan entitas **ecommercepurchases: eCommerce** dengan **ecommercecontacts: eCommerce**.

   ![Bergabung dengan entitas e-commerce.](media/model-purchase-join.png)

1. Pilih **berikutnya** untuk mengatur jadwal model.

   Model harus dilatih secara teratur untuk mempelajari pola baru bila ada data baru yang terserap. Untuk contoh ini, pilih **bulanan**.

1. Setelah meninjau semua rincian, pilih **Simpan dan jalankan**.


## <a name="task-4---review-model-results-and-explanations"></a>Tugas 4-TInjau hasil dan penjelasan model

Biarkan model menyelesaikan pelatihan dan penilaian data. Anda sekarang dapat meninjau penjelasan model rekomendasi produk. Untuk informasi lebih lanjut, lihat [meninjau status dan hasil prediksi](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tugas 5 - Membuat segmen produk dengan pembelian tinggi

Menjalankan model produksi membuat entitas baru yang dapat Anda lihat di **data** > **entitas**.

Anda dapat membuat segmen baru berdasarkan entitas yang dibuat oleh model.

1. Buka **Segmen**. Pilih **baru** lalu pilih **buat dari** > **intelijen**.

   ![Membuat segmen dengan output model.](media/segment-intelligence.png)

1. Pilih titik akhir **OOBProductRecommendationModelPrediction** dan tentukan segmen:

   - Bidang: ProductID
   - Operator: Nilai
   - Nilai: Pilih tiga ID produk teratas

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Membuat segmen dari hasil model.":::

Anda sekarang memiliki segmen yang secara dinamis diperbarui dan mengidentifikasi pelanggan yang lebih ingin membeli tiga produk yang paling direkomendasikan 

Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
