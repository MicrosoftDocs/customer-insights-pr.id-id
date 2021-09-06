---
title: Panduan sampel prediksi kehilangan pelanggan transaksional
description: Gunakan contoh panduan ini untuk mencoba model prediksi kehilangan pelanggan transaksional bawaan.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 19befa17524aba4543f0d8a5f5f7d6f5a88b2322f1264b88fa0b31641610592a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7029449"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a>Panduan sampel prediksi kehilangan pelanggan transaksional (pratinjau)

Panduan ini akan memandu Anda tentang contoh komprehensif prediksi kehilangan pelanggan transaksional di Customer Insights menggunakan data sampel yang diberikan di bawah ini. Semua data yang digunakan dalam panduan ini bukan data pelanggan nyata dan merupakan bagian dari dataset Contoso yang ditemukan di lingkungan *Demo* dalam Langganan Customer Insights Anda.

## <a name="scenario"></a>Skenario

Contoso adalah perusahaan yang memproduksi mesin kopi dan kopi berkualitas tinggi, yang mereka jual melalui situs web Kopi Contoso mereka. Tujuan mereka adalah untuk mengetahui Pelanggan mana yang biasanya membeli produk mereka secara teratur, yang akan berhenti menjadi pelanggan aktif dalam 60 hari berikutnya. Mengetahui pelanggan mana yang **cenderung pergi**, dapat membantu mereka menyelamatkan upaya pemasaran dengan berfokus pada menjaganya.

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md) di Customer Insights.
- Sebaiknya Anda menerapkan langkah-langkah berikut [di lingkungan baru](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tugas 1- Serap Data

Tinjau artikel [tentang konsumsi data](data-sources.md) dan [mengimpor sumber data menggunakan konektor connector](connect-power-query.md) secara khusus. Informasi berikut ini mengasumsikan bahwa Anda telah mengenal dan menyerap data secara umum. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Menyerap data pelanggan dari platform eCommerce

1. Buat sumber data bernama **eCommerce**, pilih pilihan impor, dan pilih konektor **Text/CSV**.

1. Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasscontacts.

1. Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:

   - **DateOfBirth**: tanggal
   - **CreatedOn**: Tanggal/Waktu/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Mengubah DoB ke Tanggal.":::

1. Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **eCommerceContacts**

1. Simpan Sumber Data.

### <a name="ingest-online-purchase-data"></a>Menyerap Data pembelian online

1. Tambahkan himpunan data lain ke sumber data **eCommerce** yang sama. Pilih konektor **teks/CSV** lagi.

1. Masukkan URL untuk data **pembelian online** https://aka.ms/ciadclassonline.

1. Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:

   - **PurchasedOn**: tanggal/waktu
   - **TotalPrice**: mata uang
   
1. Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **eCommercePurchases**.

1. Simpan Sumber Data.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Menyerap data pelanggan dari skema kesetiaan

1. Buat sumber data bernama **LoyaltyScheme**, pilih pilihan impor, dan pilih konektor **Text/CSV**.

1. Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:

   - **DateOfBirth**: tanggal
   - **RewardsPoints**: Bilangan Cacah
   - **CreatedOn**: Waktu/Tanggal

1. Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **loyCustomers**.

1. Simpan Sumber Data.


## <a name="task-2---data-unification"></a>Tugas 2-penyatuan data

Setelah menyerap data, kita sekarang memulai proses **Memetakan, Mencocokkan, menggabungkan** untuk membuat profil pelanggan terpadu. Untuk informasi selengkapnya, lihat [Penyatuan data](data-unification.md).

### <a name="map"></a>Peta

1. Setelah menyerap data, Petakan kontak dari eCommerce dan data kesetiaan ke jenis data umum. Buka **Data** > **Satukan** > **Petakan**.

1. Pilih entitas yang menunjukkan profil pelanggan- **ecommercecontacts** dan **loycustomer**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="menyatukan sumber data eCommerce dan kesetiaan.":::

1. Pilih **contactid** sebagai kunci primer untuk **ecommercecontacts** dan **loyaltyid** sebagai kunci primer untuk **loycustomer**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Menyatukan LoyaltyId sebagai kunci primer.":::

### <a name="match"></a>Cocokkan

1. Pergi ke tab **Cocokkan** dan pilih **Atur Urutan**.

1. Dalam daftar dropdown **Utama**, pilih **eCommerceContacts: e Commerce** sebagai sumber utama dan sertakan semua rekaman.

1. Dalam daftar dropdown **Entitas 2**, pilih **loyCustomers: LoyaltyScheme** dan sertakan semua rekaman.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Satukan dan cocokkan eCommerce dan Loyalty.":::

1. Pilih **Buat aturan baru**

1. Tambahkan kondisi pertama Anda menggunakan FullName.

   * Untuk eCommerceContacts, pilih **FullName** di dropdown.
   * Untuk loyCustomers, pilih **FullName** di dropdown.
   * Pilih drop-down **normalkan** dan pilih **jenis (telepon, nama, alamat,...)**.
   * Atur **tingkat presisi**: **dasar** dan **nilai**: **tinggi**.

1. Masukkan nama **fullname, email** untuk aturan baru.

   * Tambahkan kondisi kedua untuk alamat email dengan memilih **Tambah kondisi**
   * Untuk entitas eCommerceContacts, pilih **EMail** di dropdown.
   * Untuk entitas loyCustomers, pilih **EMail** di dropdown. 
   * Biarkan Normalkan kosong. 
   * Atur **tingkat presisi**: **dasar** dan **nilai**: **tinggi**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Satukan aturan kecocokan untuk nama dan email.":::

7. Pilih **Simpan** dan **Tutup**.

### <a name="merge"></a>Penggabungan

1. Buka tab **Gabungkan**.

1. Pada entitas **contactid** untuk **loycustomer**, ubah nama tampilan ke **contactidloyalty** untuk membedakannya dari id lain yang diserap.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Ubah nama contactid dari Loyalty id.":::

1. Pilih **Simpan** dan **Jalankan** untuk memulai proses penggabungan.



## <a name="task-3---configure-transaction-churn-prediction"></a>Tugas 3-konfigurasi prediksi kehilangan pelanggan transaksi

Dengan profil pelanggan terpadu di tempatnya, kini kita dapat menjalankan prediksi kehilangan pelanggan langganan. Untuk langkah rinci, lihat artikel [prediksi kehilangan pelanggan langganan](predict-subscription-churn.md) (pratinjau). 

1. Buka **intelijen** > **Temukan** dan pilih untuk menggunakan **model kehilangan pelanggan**.

1. Pilih pilihan **Transaksional** dan pilih **Mulai**.

1. Namai model **prediksi kehilangan pelanggan transaksi eCommerce OOB** dan entitas output **OOBeCommerceChurnPrediction**.

1. Tentukan dua kondisi untuk model kehilangan pelanggan:

   * **Jendela prediksi**: minimal **60** hari. Pengaturan ini menentukan seberapa jauh ke masa depan kita ingin memprediksi kehilangan pelanggan.

   * **Definisi kehilangan pelanggan**: **minimal 60** hari. Durasi tanpa pembelian yang mana setelah itu pelanggan dianggap hilang.

     :::image type="content" source="media/model-levers.PNG" alt-text="pilih jendela prediksi pengungkit model dan definisi kehilangan pelanggan.":::

1. Pilih **Riwayat Pembelian (diperlukan)** dan pilih **Tambah data** untuk Riwayat pembelian.

1. Tambahkan entitas **eCommercePurchases : eCommerce** dan Petakan bidang dari eCommerce ke bidang terkait yang diperlukan oleh model.

1. Gabungkan entitas **ecommercepurchases: eCommerce** dengan **ecommercecontacts: eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Bergabung dengan entitas e-commerce.":::

1. Pilih **berikutnya** untuk mengatur jadwal model.

   Model harus dilatih secara teratur untuk mempelajari pola baru bila ada data baru yang terserap. Untuk contoh ini, pilih **bulanan**.

1. Setelah meninjau semua rincian, pilih **Simpan dan jalankan**.

## <a name="task-4---review-model-results-and-explanations"></a>Tugas 4-TInjau hasil dan penjelasan model

Biarkan model menyelesaikan pelatihan dan penilaian data. Anda sekarang dapat meninjau penjelasan model kehilangan pelanggan langganan. Untuk informasi lebih lanjut, lihat [meninjau status dan hasil prediksi](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tugas 5-membuat segmen pelanggan berisiko kehilangan tinggi

Menjalankan model produksi membuat entitas baru yang dapat Anda lihat di **data** > **entitas**.   

Anda dapat membuat segmen baru berdasarkan entitas yang dibuat oleh model.

1.  Buka **Segmen**. Pilih **baru** lalu pilih **buat dari** > **intelijen**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Membuat segmen dengan output model.":::

1. Pilih titik akhir **OOBSubscriptionChurnPrediction** dan tentukan segmen: 
   - Bidang: ChurnScore
   - Operator: Lebih besar dari
   - Nilai: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Siapkan segmen kehilangan pelangganlangganan.":::

Anda sekarang memiliki segmen yang diperbarui secara dinamis yang mengidentifikasi pelanggan berisiko kehilangan pelanggantinggi untuk bisnis langganan ini.

Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
