---
title: Panduan sampel prediksi Rekomendasi produk
description: Gunakan contoh panduan ini untuk mencoba model prediksi rekomendasi produk siap pakai.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610148"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Panduan sampel prediksi Rekomendasi produk

Panduan ini memandu Anda melalui contoh end-to-end rekomendasi produk prediksi menggunakan data sampel. Kami menyarankan Anda mencoba prediksi [ini di lingkungan baru](manage-environments.md).

## <a name="scenario"></a>Skenario

Contoso adalah perusahaan yang memproduksi mesin kopi dan kopi berkualitas tinggi. Mereka menjual produk melalui situs web Contoso Coffee mereka. Tujuan mereka adalah untuk memahami produk yang harus mereka rekomendasikan kepada pelanggan berulang mereka. Mengetahui apa yang lebih **mungkin dibeli** pelanggan dapat membantu mereka menghemat upaya pemasaran dengan berfokus pada item tertentu.

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md) di Customer Insights.

## <a name="task-1---ingest-data"></a>Tugas 1- Serap Data

Tinjau artikel [tentang penyerapan](data-sources.md) data dan [menghubungkan ke Power Query sumber data](connect-power-query.md). Informasi berikut mengasumsikan Anda terbiasa menelan data secara umum.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Menyerap data pelanggan dari platform eCommerce

1. Buat Power Query sumber data bernama **eCommerce** dan pilih **konektor Text/CSV**.

1. Masukkan URL untuk kontak eCommerce:https://aka.ms/ciadclasscontacts.

1. Saat mengedit data, pilih **Transformasi** lalu **Gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **DateOfBirth**: tanggal
   - **CreatedOn**: Tanggal/Waktu/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tanggal lahir sampai saat ini.":::

1. **Di bidang Nama** di panel sebelah kanan, ganti nama sumber data Anda menjadi **eCommerceContacts**.

1. **Simpan** Sumber Data.

### <a name="ingest-online-purchase-data"></a>Menyerap Data pembelian online

1. Tambahkan himpunan data lain ke sumber data **eCommerce** yang sama. Pilih konektor **teks/CSV** lagi.

1. Masukkan URL untuk data pembelian online https://aka.ms/ciadclassonline.

1. Saat mengedit data, pilih **Transformasi** lalu **Gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **PurchasedOn**: tanggal/waktu
   - **TotalPrice**: mata uang

1. **Di bidang Nama** di panel samping, ganti nama sumber data Anda menjadi **eCommercePurchases**.

1. **Simpan** Sumber Data.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Menyerap data pelanggan dari skema kesetiaan

1. Buat sumber data bernama **LoyaltyScheme** dan pilih **konektor Text/CSV**.

1. Masukkan URL untuk pelanggan setia https://aka.ms/ciadclasscustomerloyalty.

1. Saat mengedit data, pilih **Transformasi** lalu **Gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **DateOfBirth**: tanggal
   - **RewardsPoints**: Bilangan Cacah
   - **CreatedOn**: Waktu/Tanggal

1. **Di bidang Nama** di panel sebelah kanan, ganti nama sumber data Anda menjadi **loyCustomers**.

1. **Simpan** Sumber Data.

## <a name="task-2---data-unification"></a>Tugas 2-penyatuan data

Tinjau artikel [tentang penyatuan](data-unification.md) data. Informasi berikut mengasumsikan Anda sudah terbiasa dengan penyatuan data secara umum.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tugas 3 - Membuat aktivitas riwayat transaksi

Tinjau artikel [tentang aktivitas](activities.md) pelanggan. Informasi berikut mengasumsikan Anda terbiasa membuat kegiatan secara umum.

1. Buat aktivitas yang disebut **eCommercePurchases** dengan *entitas eCommercePurchases:eCommerce* dan kunci utamanya, **PurchaseId**.

1. Buat hubungan antara *eCommercePurchases:eCommerce* dan *eCommerceContacts:eCommerce* dengan **ContactID** sebagai kunci asing untuk menghubungkan kedua entitas.

1. Pilih **TotalPrice** untuk **EventActivity** dan **PurchasedOn** untuk **TimeStamp**.

1. Pilih **SalesOrderLine** untuk **Jenis** Aktivitas dan petakan data aktivitas secara semantik.

1. Jalankan aktivitas.

## <a name="task-4---configure-product-recommendation-prediction"></a>Tugas 4 - Mengkonfigurasi prediksi rekomendasi produk

Dengan profil pelanggan terpadu di tempat dan aktivitas yang dibuat, jalankan rekomendasi produk prediksi.

1. Pergi ke **Prediksi** > **Intelijen**.

1. Pada tab **Buat**, pilih **Gunakan model** pada petak **Peta rekomendasi produk (pratinjau**).

1. Pilih **Mulai**.

1. Namai **Prediksi model rekomendasi produk OOB** dan entitas output **OOBProductRecommendationModelPrediction**.

1. Pilih **Selanjutnya**.

1. Tentukan preferensi model:
   - **Jumlah produk**: **5** untuk menentukan berapa banyak produk yang ingin Anda rekomendasikan kepada pelanggan Anda.
   - **Pembelian berulang yang diharapkan**: **Ya** untuk menyertakan produk yang dibeli sebelumnya dalam rekomendasi.
   - **Lihat ke belakang jendela:** **365 hari** untuk menentukan seberapa jauh model akan melihat ke belakang sebelum merekomendasikan produk lagi.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferensi model untuk model rekomendasi produk.":::

1. Pilih **Selanjutnya**.

1. **Di langkah Tambahkan riwayat** pembelian, pilih **Tambahkan data**.

1. Pilih **SalesOrderLine** dan entitas eCommercePurchases dan pilih **Berikutnya**. Data yang diperlukan secara otomatis diisi dari aktivitas. Pilih **Simpan** lalu **Berikutnya**.

1. Lewati langkah-langkah **Tambahkan informasi** produk dan **Filter** produk karena kami tidak memiliki data informasi produk.

1. **Di langkah Pembaruan** data, pilih **Bulanan** untuk jadwal model.

1. Pilih **Selanjutnya**.

1. Setelah meninjau semua rincian, pilih **Simpan dan jalankan**.

## <a name="task-5---review-model-results-and-explanations"></a>Tugas 5-TInjau hasil dan penjelasan model

Biarkan model menyelesaikan pelatihan dan penilaian data. [Tinjau penjelasan](predict-transactional-churn.md#view-prediction-results) model rekomendasi produk.

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Tugas 6 - Membuat segmen produk dengan pembelian tinggi

Menjalankan model membuat entitas baru, yang tercantum di **Data** > **Entitas**. Anda dapat membuat segmen baru berdasarkan entitas yang dibuat oleh model.

1. Pada halaman hasil, pilih **Buat segmen**.

1. Buat aturan menggunakan **entitas OOBProductRecommendationModelPrediction** dan tentukan segmen:
   - **Bidang**: ProductID
   - **Nilai**: Pilih tiga ID produk teratas

1. Pilih **Simpan** dan **Jalankan** segmen.

Anda sekarang memiliki segmen yang diperbarui secara dinamis yang mengidentifikasi pelanggan yang mungkin tertarik untuk membeli lima produk yang paling direkomendasikan. Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).

> [!TIP]
> Anda juga dapat membuat segmen untuk model prediksi dari **halaman Segmen** dengan **memilih Baru** dan memilih **Buat dari** > **Kecerdasan**. Untuk informasi selengkapnya, lihat [Membuat segmen baru dengan segmen](segment-quick.md) cepat.

[!INCLUDE [footer-include](includes/footer-banner.md)]
