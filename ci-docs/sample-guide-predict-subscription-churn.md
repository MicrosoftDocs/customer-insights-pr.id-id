---
title: Panduan sampel prediksi kehilangan pelanggan langganan
description: Gunakan contoh panduan ini untuk mencoba model prediksi kehilangan pelanggan langganan bawaan.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610010"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Panduan sampel prediksi kehilangan pelanggan langganan

Panduan ini akan menjelaskan kepada Anda contoh akhir ke ujung churn langganan prediksi menggunakan data sampel. Kami menyarankan Anda mencoba prediksi [ini di lingkungan baru](manage-environments.md).

## <a name="scenario"></a>Skenario

Contoso adalah perusahaan yang memproduksi mesin kopi dan kopi berkualitas tinggi. Mereka menjual produk melalui situs web Contoso Coffee mereka. Mereka baru saja memulai bisnis langganan untuk pelanggan mereka agar mendapatkan kopi secara teratur. Tujuan mereka adalah untuk memahami pelanggan berlangganan mana yang mungkin membatalkan langganan mereka dalam beberapa bulan ke depan. Mengetahui pelanggan **mana yang kemungkinan akan bergejolak** dapat membantu mereka menghemat upaya pemasaran dengan berfokus pada mempertahankannya.

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md) di Customer Insights.

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

1. Simpan Sumber Data.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Menyerap data pelanggan dari skema kesetiaan

1. Buat sumber data bernama **LoyaltyScheme** dan pilih **konektor Text/CSV**.

1. Masukkan URL untuk pelanggan https://aka.ms/ciadclasscustomerloyalty loyalitas.

1. Saat mengedit data, pilih **Transformasi** lalu **Gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **DateOfBirth**: tanggal
   - **RewardsPoints**: Bilangan Cacah
   - **CreatedOn**: Waktu/Tanggal

1. **Di bidang Nama** di panel sebelah kanan, ganti nama sumber data Anda menjadi **loyCustomers**.

1. Simpan Sumber Data.

### <a name="ingest-subscription-information"></a>Serap Informasi Langganan

1. Buat sumber data bernama **SubscriptionHistory** dan pilih **konektor Text/CSV**.

1. Masukkan URL untuk langganan https://aka.ms/ciadchurnsubscriptionhistory.

1. Saat mengedit data, pilih **Transformasi** lalu **Gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **SubscriptioID**: Bilangan Cacah
   - **SubscriptionAmount**: Mata uang
   - **SubscriptionEndDate**: tanggal waktu
   - **SubscriptionStartDate**: Date/Time
   - **TransactionDate**: Date/Time
   - **IsRecurring**: Benar/salah
   - **Is_auto_renew**: Benar/Salah
   - **RecurringFrequencyInMonths**: Bilangan Cacah

1. **Di bidang Nama** di panel sebelah kanan, ganti nama sumber data Anda menjadi **SubscriptionHistory**.

1. Simpan Sumber Data.

### <a name="ingest-customer-data-from-website-reviews"></a>Serap data pelanggan dari ulasan situs

1. Buat sumber data bernama **Situs Web** dan pilih **konektor Teks/CSV**.

1. Masukkan URL untuk ulasan https://aka.ms/ciadclasswebsite situs web.

1. Saat mengedit data, pilih **Transformasi** lalu **Gunakan baris pertama sebagai header**.

1. Perbarui DataType untuk kolom yang tercantum di bawah ini:
   - **Bilangan Bulat**: Bilangan Cacah
   - **ReviewDate**: tanggal

1. **Di bidang Nama** di panel sebelah kanan, ganti nama sumber data Anda menjadi **webReviews**.

## <a name="task-2---data-unification"></a>Tugas 2-penyatuan data

Tinjau artikel [tentang penyatuan](data-unification.md) data. Informasi berikut mengasumsikan Anda sudah terbiasa dengan penyatuan data secara umum.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tugas 3 - Membuat aktivitas riwayat transaksi

Tinjau artikel [tentang aktivitas](activities.md) pelanggan. Informasi berikut mengasumsikan Anda terbiasa membuat kegiatan secara umum.

1. Buat aktivitas yang disebut **SubscriptionHistory** dengan *entitas Langganan* dan kunci utamanya, **CustomerId**.

1. Buat hubungan antara *SubscriptionHistory:Subscription* dan *eCommerceContacts:eCommerce* dengan **CustomerID** sebagai kunci asing untuk menghubungkan kedua entitas.

1. Pilih **SubscriptionType** untuk **EventActivity** dan **SubscriptionEndDate** untuk **TimeStamp**.

1. Pilih **Langganan** untuk **Jenis** Aktivitas dan petakan data aktivitas secara semantik.

1. Jalankan aktivitas.

1. Tambahkan aktivitas lain dan petakan nama bidangnya ke bidang terkait:
   - Entitas aktivitas pelanggan: Reviews:Website
   - Kunci utama: Website.Reviews.ReviewId
   - Cap waktu: website.reviews.reviewDate
   - Kejadian (nama aktivitas): Website.Reviews.ActivityTypeDisplay
   - Detail (jumlah atau nilai): Website.Reviews.ReviewRating

1. Jalankan aktivitas.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Tugas 4-konfigurasi prediksi kehilangan pelanggan langganan

Dengan profil pelanggan terpadu di tempat dan aktivitas yang dibuat, jalankan churn langganan prediksi. Untuk langkah-langkah mendetail, lihat [Churn prediksi langganan](predict-subscription-churn.md).

1. Pergi ke **Prediksi** > **Intelijen**.

1. Pada tab **Buat**, pilih **Gunakan model** pada **petak peta model** churn Pelanggan.

1. Pilih **Langganan** untuk jenis churn lalu **Mulai**.

1. Namai model **prediksi kehilangan pelanggan langganan oob** dan entitas output **OOBSubscriptionChurnPrediction**.

1. Tentukan preferensi model:
   - **Hari sejak langganan berakhir**: **60** hari untuk menunjukkan bahwa pelanggan dianggap terombang-ambing jika mereka tidak memperpanjang langganan dalam periode ini setelah langganan mereka berakhir.
   - **Hari untuk menyelidiki masa depan untuk memprediksi churn**: **93** hari yang merupakan durasi model memprediksi pelanggan mana yang mungkin bergejolak. Semakin jauh di masa depan Anda melihat, semakin kurang tepat hasilnya.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Pilih preferensi model dan definisi churn.":::

1. Pilih **Selanjutnya**.

1. Di langkah Data **yang** Diperlukan, pilih **Tambahkan data** untuk memberikan riwayat langganan.

1. Pilih **Langganan** dan entitas SubscriptionHistory dan pilih **Berikutnya**. Data yang diperlukan secara otomatis diisi dari aktivitas. Pilih **Simpan**.

1. Di bawah Aktivitas Pelanggan, pilih **Tambahkan data**.

1. Untuk contoh ini, tambahkan aktivitas peninjauan web.

1. Pilih **Selanjutnya**.

1. **Di langkah Pembaruan** data, pilih **Bulanan** untuk jadwal model.

1. Setelah meninjau semua rincian, pilih **Simpan dan jalankan**.

## <a name="task-5---review-model-results-and-explanations"></a>Tugas 5-TInjau hasil dan penjelasan model

Biarkan model menyelesaikan pelatihan dan penilaian data. Tinjau penjelasan model churn langganan. Untuk informasi selengkapnya, lihat [Menampilkan hasil](predict-subscription-churn.md#view-prediction-results) prediksi.

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tugas 6-membuat segmen pelanggan berisiko kehilangan tinggi

Menjalankan model membuat entitas baru, yang tercantum di **Data** > **Entitas**. Anda dapat membuat segmen baru berdasarkan entitas yang dibuat oleh model.

1. Pada halaman hasil, pilih **Buat segmen**.

1. Buat aturan menggunakan **entitas OOBSubscriptionChurnPrediction** dan tentukan segmennya:
   - **Bidang**: ChurnScore
   - **Operator**: lebih besar dari
   - **Nilai**: 0,6

1. Pilih **Simpan** dan **Jalankan** segmen.

Anda sekarang memiliki segmen yang diperbarui secara dinamis yang mengidentifikasi pelanggan berisiko kehilangan pelanggantinggi untuk bisnis langganan ini. Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).

> [!TIP]
> Anda juga dapat membuat segmen untuk model prediksi dari **halaman Segmen** dengan **memilih Baru** dan memilih **Buat dari** > **Kecerdasan**. Untuk informasi selengkapnya, lihat [Membuat segmen baru dengan segmen](segment-quick.md) cepat.

[!INCLUDE [footer-include](includes/footer-banner.md)]
