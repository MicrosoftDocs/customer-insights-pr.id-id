---
title: Contoh panduan prediksi nilai seumur hidup pelanggan (CLV)
description: Gunakan panduan sampel ini untuk mencoba model prediksi pelanggan nilai seumur hidup.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609642"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Contoh panduan prediksi nilai seumur hidup pelanggan (CLV)

Panduan ini memandu Anda melalui contoh end-to-end dari nilai umur pelanggan (CLV) prediksi di Customer Insights menggunakan data sampel. Kami menyarankan Anda mencoba prediksi [ini di lingkungan baru](manage-environments.md).

## <a name="scenario"></a>Skenario

Contoso adalah perusahaan yang memproduksi mesin kopi dan kopi berkualitas tinggi. Mereka menjual produk melalui situs web Contoso Coffee mereka. Perusahaan ingin memahami nilai (pendapatan) yang dapat dihasilkan pelanggan mereka dalam 12 bulan ke depan. Mengetahui nilai yang diharapkan dari pelanggan mereka dalam 12 bulan ke depan akan membantu mereka mengarahkan upaya pemasaran mereka pada pelanggan bernilai tinggi.

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md).

## <a name="task-1---ingest-data"></a>Tugas 1- Serap Data

Tinjau artikel [tentang penyerapan](data-sources.md) data dan [menghubungkan ke Power Query sumber data](connect-power-query.md). Informasi berikut mengasumsikan Anda terbiasa menelan data secara umum.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Menyerap data pelanggan dari platform eCommerce

1. Buat Power Query sumber data bernama **eCommerce** dan pilih **konektor Text/CSV**.

1. Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasscontacts.

1. Saat mengedit data, pilih **Transformasi** lalu **Gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **DateOfBirth**: tanggal
   - **CreatedOn**: Tanggal/Waktu/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tanggal lahir sampai saat ini.":::

1. **Di bidang Nama** di panel sebelah kanan, ganti nama sumber data Anda menjadi **eCommerceContacts**

1. **Simpan** Sumber Data.

### <a name="ingest-online-purchase-data"></a>Menyerap Data pembelian online

1. Tambahkan himpunan data lain ke sumber data **eCommerce** yang sama. Pilih konektor **teks/CSV** lagi.

1. Masukkan URL untuk data **pembelian online** https://aka.ms/ciadclassonline.

1. Saat mengedit data, pilih **Transformasi** lalu **Gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **PurchasedOn**: tanggal/waktu
   - **TotalPrice**: mata uang

1. **Di bidang Nama** di panel samping, ganti nama sumber data Anda menjadi **eCommercePurchases**.

1. **Simpan** Sumber Data.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Menyerap data pelanggan dari skema kesetiaan

1. Buat sumber data bernama **LoyaltyScheme** dan pilih **konektor Text/CSV**.

1. Masukkan URL untuk pelanggan https://aka.ms/ciadclasscustomerloyalty loyalitas.

1. Saat mengedit data, pilih **Transformasi** lalu **Gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **DateOfBirth**: tanggal
   - **RewardsPoints**: Bilangan Cacah
   - **CreatedOn**: Waktu/Tanggal

1. **Di bidang Nama** di panel sebelah kanan, ganti nama sumber data Anda menjadi **loyCustomers**.

1. **Simpan** Sumber Data.

### <a name="ingest-customer-data-from-website-reviews"></a>Serap data pelanggan dari ulasan situs

1. Buat sumber data bernama **Situs Web** dan pilih **konektor Teks/CSV**.

1. Masukkan URL untuk ulasan https://aka.ms/CI-ILT/WebReviews situs web.

1. Saat mengedit data, pilih **Transformasi** lalu **Gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **ReviewRating**: Angka Desimal
   - **ReviewDate**: tanggal

1. **Di bidang Nama** di panel sebelah kanan, ganti nama sumber data Anda menjadi **Ulasan**.

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

1. Tambahkan aktivitas lain dan petakan nama bidangnya ke bidang terkait:
   - **Entitas aktivitas**: Ulasan:Situs web
   - **Kunci** utama: ReviewId
   - **Stempel** waktu: ReviewDate
   - **Aktivitas** acara: ActivityTypeDisplay
   - **Detail** tambahan: ReviewRating
   - **Jenis aktivitas**: Ulasan

1. Jalankan aktivitas.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Tugas 4 - Mengonfigurasi prediksi nilai seumur hidup pelanggan

Dengan profil pelanggan terpadu di tempat dan aktivitas yang dibuat, jalankan prediksi nilai seumur hidup pelanggan (CLV). Untuk langkah-langkah mendetail, lihat [prediksi](predict-customer-lifetime-value.md) Nilai Umur Pelanggan.

1. Pergi ke **Prediksi** > **Intelijen**.

1. Pada tab **Buat**, pilih **Gunakan model** pada petak **nilai** seumur hidup Pelanggan.

1. Pilih **Mulai**.

1. Beri nama model **Prediksi CLV eCommerce OOB** dan entitas output  **OOBeCommerceCLVPrediction**.

1. Tentukan preferensi model:
   - **prediksi periode** waktu: **12 bulan atau 1 tahun** untuk menentukan seberapa jauh ke masa depan untuk memprediksi CLV.
   - **Pelanggan** aktif: **Biarkan model menghitung interval** pembelian yang merupakan jangka waktu di mana pelanggan harus memiliki setidaknya satu transaksi untuk dianggap aktif.
   - **Pelanggan bernilai** tinggi: secara manual mendefinisikan pelanggan bernilai tinggi sebagai **30% pelanggan aktif teratas**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Langkah preferensi dalam pengalaman terpandu untuk model CLV.":::

1. Pilih **Selanjutnya**.

1. Di langkah **Data yang Diperlukan**, pilih **Tambahkan data** untuk menyediakan data riwayat transaksi.

    :::image type="content" source="media/clv-model-required.png" alt-text="Tambahkan langkah data yang diperlukan dalam pengalaman terpandu untuk model CLV.":::

1. Pilih **SalesOrderLine** dan entitas eCommercePurchases dan pilih **Berikutnya**. Data yang diperlukan secara otomatis diisi dari aktivitas. Pilih **Simpan** lalu **Berikutnya**.

1. Langkah **Data tambahan (opsional)** memungkinkan Anda menambahkan lebih banyak data aktivitas pelanggan untuk mendapatkan lebih banyak wawasan untuk interaksi pelanggan. Untuk contoh ini, pilih **Tambahkan data** dan tambahkan aktivitas peninjauan web.

1. Pilih **Selanjutnya**.

1. **Di langkah Pembaruan** data, pilih **Bulanan** untuk jadwal model.

1. Pilih **Selanjutnya**.

1. Setelah meninjau semua rincian, pilih **Simpan dan jalankan**.

## <a name="task-5---review-model-results-and-explanations"></a>Tugas 5-TInjau hasil dan penjelasan model

Biarkan model menyelesaikan pelatihan dan penilaian data. [Tinjau hasil dan penjelasan](predict-customer-lifetime-value.md#view-prediction-results) model CLV.

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Tugas 6 - Buat segmen pelanggan bernilai tinggi

Menjalankan model membuat entitas baru, yang tercantum di **Data** > **Entitas**. Anda dapat membuat segmen pelanggan baru berdasarkan entitas yang dibuat oleh model.

1. Pada halaman hasil, pilih **Buat segmen**.

1. Buat aturan menggunakan **entitas OOBeCommerceCLVPrediction** dan tentukan segmennya:
   - **Bidang**: CLVScore
   - **Operator**: lebih besar dari
   - **Nilai**: 1500

1. Pilih **Simpan** dan **Jalankan** segmen.

Anda sekarang memiliki segmen yang mengidentifikasi pelanggan yang diprediksi akan menghasilkan pendapatan lebih dari $1500 dalam 12 bulan ke depan. Segmen ini diperbarui secara dinamis jika lebih banyak data yang diserap. Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).

> [!TIP]
> Anda juga dapat membuat segmen untuk model prediksi dari **halaman Segmen** dengan **memilih Baru** dan memilih **Buat dari** > **Kecerdasan**. Untuk informasi selengkapnya, lihat [Membuat segmen baru dengan segmen](segment-quick.md) cepat.

[!INCLUDE [footer-include](includes/footer-banner.md)]
