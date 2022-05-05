---
title: Panduan sampel prediksi kehilangan pelanggan langganan
description: Gunakan contoh panduan ini untuk mencoba model prediksi kehilangan pelanggan langganan bawaan.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2aea6c62421b308705899e4f8af64f64bfcb2d3d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643579"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Panduan sampel prediksi kehilangan pelanggan langganan

Kami akan menjelaskan kepada Anda contoh akhir dari prediksi kehilangan pelanggan langganan menggunakan data sampel yang diberikan di bawah ini. 

## <a name="scenario"></a>Skenario

Aswono adalah perusahaan yang memproduksi mesin kopi dan kopi berkualitas tinggi, yang dijual melalui situs web Kopi Aswono. Mereka baru saja memulai bisnis langganan untuk pelanggan mereka agar mendapatkan kopi secara teratur. Tujuannya adalah untuk memahami, pelanggan langganan mana yang dapat membatalkan langganan dalam beberapa bulan ke depan. Mengetahui pelanggan mana yang **cenderung pergi**, dapat membantu mereka menyelamatkan upaya pemasaran dengan berfokus pada menjaganya.

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md) di Customer Insights.
- Sebaiknya Anda menerapkan langkah-langkah berikut [di lingkungan baru](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tugas 1- Serap Data

Tinjau artikel [tentang penyerapan](data-sources.md) data dan [mengimpor sumber data menggunakan Power Query konektor](connect-power-query.md) secara khusus. Informasi berikut ini mengasumsikan bahwa Anda telah mengenal dan menyerap data secara umum. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Menyerap data pelanggan dari platform eCommerce

1. Buat sumber data bernama **eCommerce**, pilih pilihan impor, dan pilih konektor **Text/CSV**.

1. Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasscontacts.

1. Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:

   - **DateOfBirth**: tanggal
   - **CreatedOn**: Tanggal/Waktu/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tanggal lahir sampai saat ini.":::

1. Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **eCommerceContacts**

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

### <a name="ingest-subscription-information"></a>Serap Informasi Langganan

1. Buat sumber data bernama **subscriptionhistory**, pilih pilihan impor, dan pilih konektor **Text/CSV**.

1. Masukkan URL untuk kontak eCommerce https://aka.ms/ciadchurnsubscriptionhistory.

1. Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:

   - **SubscriptioID**: Bilangan Cacah
   - **SubscriptionAmount**: Mata uang
   - **SubscriptionEndDate**: tanggal waktu
   - **SubscriptionStartDate**: Date/Time
   - **TransactionDate**: Date/Time
   - **IsRecurring**: Benar/salah
   - **Is_auto_renew**: Benar/Salah
   - **RecurringFrequencyInMonths**: Bilangan Cacah

1. Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **subscriptionhistory**.

1. Simpan Sumber Data.

### <a name="ingest-customer-data-from-website-reviews"></a>Serap data pelanggan dari ulasan situs

1. Buat sumber data bernama **Situs web**, pilih pilihan impor, dan pilih konektor **Text/CSV**.

1. Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasswebsite.

1. Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:

   - **Bilangan Bulat**: Bilangan Cacah
   - **ReviewDate**: tanggal

1. Di bidang ' nama ' pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **webReviews**.

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


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Tugas 3-konfigurasi prediksi kehilangan pelanggan langganan

Dengan profil pelanggan terpadu di tempatnya, kini kita dapat menjalankan prediksi kehilangan pelanggan langganan. Untuk langkah-langkah mendetail, lihat [artikel prediksi churn langganan](predict-subscription-churn.md). 

1. Buka **intelijen** > **Temukan** dan pilih untuk menggunakan **model kehilangan pelanggan**.

1. Pilih pilihan **langganan** dan pilih **Mulai**.

1. Namai model **prediksi kehilangan pelanggan langganan oob** dan entitas output **OOBSubscriptionChurnPrediction**.

1. Tentukan dua kondisi untuk model kehilangan pelanggan:

   * **Hari sejak langganan berakhir**: **minimal 60** hari. Jika pelanggan tidak memperpanjang langganan dalam periode setelah langganan berakhir, mereka dianggap telah pergi. 

   * **Definisi kehilangan pelanggan**: **minimal 93** hari. Durasi yang diprediksi model tentang pelanggan mana yang mungkin pergi. Semakin jauh di masa depan Anda melihat, semakin kurang tepat hasilnya.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="pilih jendela prediksi pengungkit model dan definisi kehilangan pelanggan.":::

1. Pilih **Tambah data yang diperlukan** dan pilih **Tambah data** untuk Riwayat langganan.

1. Tambahkan entitas **langganan: SubscriptionHistory** dan Petakan bidang dari eCommerce ke bidang terkait yang diperlukan oleh model.

1. Bergabung dengan entitas **langganan: SubscriptionHistory** dengan **ecommercecontacts: eCommerce**, namai relasi **ecommercesubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Bergabung dengan entitas e-commerce.":::

1. Dalam aktivitas pelanggan, tambahkan entitas **webreview: situs web** dan petakan bidang dari webreview ke bidang terkait yang diperlukan oleh model. 
   - Kunci utama: ReviewId
   - Tanda Waktu: ReviewDate
   - aktivitas: ReviewRating

1. Konfigurasikan aktivitas untuk ulasan situs. Pilih aktivitas **peninjauan** dan gabung dengan entitas **Webreview: website** dengan **Ecommercecontacts: eCommerce**.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]