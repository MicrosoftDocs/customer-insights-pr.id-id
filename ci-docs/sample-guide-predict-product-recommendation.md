---
title: Panduan sampel prediksi Rekomendasi produk
description: Gunakan contoh panduan ini untuk mencoba model prediksi rekomendasi produk siap pakai.
ms.date: 05/16/2022
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
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762690"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Panduan sampel prediksi Rekomendasi produk

Kami akan menjelaskan kepada Anda contoh akhir dari prediksi rekomendasi produk menggunakan data sampel yang diberikan di bawah ini.

## <a name="scenario"></a>Skenario

Aswono adalah perusahaan yang memproduksi mesin kopi dan kopi berkualitas tinggi, yang dijual melalui situs web Kopi Aswono. Tujuan mereka adalah untuk memahami produk yang harus mereka rekomendasikan kepada pelanggan berulang mereka. Mengetahui pelanggan **lebih cenderung membeli** dapat membantu mereka menghemat upaya pemasaran dengan berfokus pada item tertentu.

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md) di Customer Insights.
- Sebaiknya Anda menerapkan langkah-langkah berikut [di lingkungan baru](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tugas 1- Serap Data

Tinjau artikel [tentang penyerapan](data-sources.md) data dan [mengimpor sumber data menggunakan Power Query konektor](connect-power-query.md) secara khusus. Informasi berikut ini mengasumsikan bahwa Anda telah mengenal dan menyerap data secara umum.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Menyerap data pelanggan dari platform eCommerce

1. Buat sumber data bernama **eCommerce**, pilih pilihan impor, dan pilih konektor **Text/CSV**.

1. Masukkan URL untuk kontak eCommerce: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **DateOfBirth**: tanggal
   - **CreatedOn**: Tanggal/Waktu/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tanggal lahir sampai saat ini.":::

1. Di bidang ' nama ' pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **eCommerceContacts**

1. **Simpan** Sumber Data.

### <a name="ingest-online-purchase-data"></a>Menyerap Data pembelian online

1. Tambahkan himpunan data lain ke sumber data **eCommerce** yang sama. Pilih konektor **teks/CSV** lagi.

1. Masukkan url untuk **data Pembelian** Online [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **PurchasedOn**: tanggal/waktu
   - **TotalPrice**: mata uang

1. Di bidang **nama** pada panel sisi, ganti nama sumber data dari **kueri** menjadi **eCommercePurchases**.

1. **Simpan** Sumber Data.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Menyerap data pelanggan dari skema kesetiaan

1. Buat sumber data bernama **LoyaltyScheme**, pilih pilihan impor, dan pilih konektor **Text/CSV**.

1. Masukkan URL untuk kontak eCommerce [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **DateOfBirth**: tanggal
   - **RewardsPoints**: Bilangan Cacah
   - **CreatedOn**: Waktu/Tanggal

1. Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **loyCustomers**.

1. **Simpan** Sumber Data.

## <a name="task-2---data-unification"></a>Tugas 2-penyatuan data

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Tugas 3 - Mengkonfigurasi prediksi rekomendasi produk

Dengan profil pelanggan terpadu di tempat, kami sekarang dapat menjalankan rekomendasi produk prediksi.

1. Buka **Inteligensi** > **prediksi** pilih **Rekomendasi produk**.

1. Pilih **Mulai**.

1. Namai **Prediksi model rekomendasi produk OOB** dan entitas output **OOBProductRecommendationModelPrediction**.

1. Tentukan tiga kondisi untuk model:

   - **Jumlah produk**: Atur nilai ini ke **5**. Pengaturan ini menentukan seberapa banyak produk yang ingin Anda rekomendasikan kepada pelanggan.

   - **Ulangi pembelian yang diharapkan**: Pilih **Ya** untuk menunjukkan bahwa Anda ingin menyertakan produk dalam rekomendasi yang telah dibeli pelanggan Anda sebelumnya.

   - **Periode lihat kembali:** Pilih sekurangnya **365 hari**. Pengaturan ini menentukan berapa lama model akan melihat kembali aktivitas pelanggan untuk menggunakannya sebagai input untuk rekomendasi mereka.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferensi model untuk model rekomendasi produk.":::

1. **Di langkah Tambahkan data** yang diperlukan, pilih **Tambahkan data**.

1. **Di panel Tambahkan data**, pilih **SalesOrderLine** sebagai entitas riwayat pembelian. Pada titik ini, kemungkinan belum dikonfigurasi. Buka link di panel untuk membuat aktivitas dengan langkah-langkah berikut:
   1. **Masukkan nama** Aktivitas dan pilih *eCommercePurchases:eCommerce* sebagai **entitas** Aktivitas. Kunci **utama** adalah *PurchaseId*.
   1. Tentukan dan beri nama hubungan dengan *entitas* eCommerceContacts:eCommerce dan pilih **ContactId** sebagai kunci asing.
   1. Untuk penyatuan Aktivitas, tetapkan **aktivitas** Acara sebagai *TotalPrice* dan Stempel Waktu ke *PurchasedOn*. Anda dapat menentukan bidang lainnya seperti yang diuraikan dalam [aktivitas](activities.md) Pelanggan.
   1. Untuk **jenis** Aktivitas, pilih *SalesOrderLine*. Memetakan bidang aktivitas berikut:
      - ID baris pesanan: PurchaseId
      - ID Pesanan: PurchaseId
      - Data pesanan: PurchasedOn
      - ID Produk: ProductId
      - Jumlah: TotalPrice
   1. Tinjau dan selesaikan aktivitas sebelum kembali ke konfigurasi model.

1. Kembali ke **langkah Pilih aktivitas**, pilih aktivitas yang baru dibuat di **bagian Aktivitas**. Pilih **Berikutnya** dan pemetaan atribut sudah diisi. Pilih **Simpan**.

1. Dalam panduan sampel ini, kami melewati **kumpulan Tambahkan informasi** produk dan **filter** Produk karena kami tidak memiliki data informasi produk.

1. Pada langkah **Pembaruan** data, atur jadwal model.

   Model harus dilatih secara teratur untuk mempelajari pola baru bila ada data baru yang terserap. Untuk contoh ini, pilih **bulanan**.

1. Setelah meninjau semua rincian, pilih **Simpan dan jalankan**. Ini akan memakan waktu beberapa menit untuk menjalankan model pertama kali.

## <a name="task-4---review-model-results-and-explanations"></a>Tugas 4-TInjau hasil dan penjelasan model

Biarkan model menyelesaikan pelatihan dan penilaian data. Anda sekarang dapat meninjau penjelasan model rekomendasi produk. Untuk informasi lebih lanjut, lihat [meninjau status dan hasil prediksi](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tugas 5 - Membuat segmen produk dengan pembelian tinggi

Menjalankan model produksi membuat entitas baru yang dapat Anda lihat di **data** > **entitas**.

Anda dapat membuat segmen baru berdasarkan entitas yang dibuat oleh model.

1. Buka **Segmen**. Pilih **Baru** dan pilih **Buat dari Kecerdasan**.

   ![Membuat segmen dengan output model.](media/segment-intelligence.png)

1. Pilih titik akhir **OOBProductRecommendationModelPrediction** dan tentukan segmen:

   - Bidang: ProductID
   - Nilai: Pilih tiga ID produk teratas

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Membuat segmen dari hasil model.":::

Anda sekarang memiliki segmen yang diperbarui secara dinamis yang mengidentifikasi pelanggan yang mungkin tertarik untuk membeli tiga produk yang paling direkomendasikan.

Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
