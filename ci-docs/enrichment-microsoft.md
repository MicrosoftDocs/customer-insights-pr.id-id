---
title: Perkaya profil pelanggan dengan data merek dan minat dari Microsoft (pratinjau)
description: Gunakan data kepemilikan dari Microsoft untuk memperkaya data pelanggan Anda dengan afinitas dan Pangsa Suara.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: e1827adca10a3b193c02a20c4abccacf73194a77
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082702"
---
# <a name="enrich-customer-profiles-with-brands-and-interests-data-from-microsoft-preview"></a>Perkaya profil pelanggan dengan data merek dan minat dari Microsoft (pratinjau)

Gunakan data milik Microsoft untuk memperkaya data pelanggan Anda dengan afinitas merek, afinitas minat, dan Pangsa Suara (SoV). Afinitas dan SoV ini didasarkan pada data dari orang-orang dengan demografi yang mirip dengan pelanggan Anda. Informasi ini membantu Anda untuk lebih memahami dan mengelompokkan pelanggan Anda berdasarkan afinitas atau SoV mereka dengan merek dan minat tertentu.

## <a name="how-we-determine-affinities-and-sov"></a>Bagaimana kami menentukan afinitas dan SoV

Kami menggunakan data pencarian online Microsoft untuk menemukan afinitas dan SoV untuk merek dan minat di berbagai segmen demografis (ditentukan berdasarkan usia, jenis kelamin, atau lokasi). Volume pencarian online untuk merek atau minat membentuk dasar untuk menentukan afinitas atau SoV. Namun, masing-masing memberikan perspektif yang berbeda untuk memahami pelanggan Anda.

- Afinitas adalah komparatif di seluruh segmen demografis. Anda dapat menggunakan informasi ini untuk mengidentifikasi segmen demografis yang memiliki afinitas tertinggi untuk merek atau minat tertentu, dibandingkan dengan segmen lain.

- Pangsa Suara adalah perbandingan di seluruh merek atau minat pilihan Anda. Anda dapat menggunakan informasi ini untuk mengidentifikasi merek atau minat mana yang memiliki pangsa suara tertinggi untuk segmen demografis tertentu, dibandingkan dengan merek atau minat lain yang Anda pilih.

## <a name="affinity-level-and-score"></a>Tingkat afinitas dan skor

Pada setiap profil pelanggan yang diperkaya, kami menyediakan dua nilai terkait, tingkat afinitas dan skor afinitas. Nilai ini akan membantu Anda menentukan seberapa kuat afinitas untuk segmen demografi profil tersebut, untuk merek atau minat, dibandingkan dengan segmen demografi lainnya.

*Tingkat afinitas* terdiri dari empat tingkat dan *skor afinitas* dihitung pada skala 100 poin yang di petakan ke tingkat afinitas.

|Tingkat afinitas |Skor afinitas  |
|---------|---------|
|Sangat tinggi     | 85-100       |
|Sangat Penting     | 70-84        |
|Sedang     | 35-69        |
|Kurang Penting     | 1-34        |

Tergantung pada perincian yang ingin Anda ukur afinitasnya, Anda dapat menggunakan tingkat afinitas atau skor. Skor afinitas memberi Anda kontrol yang lebih akurat.

## <a name="share-of-voice-sov"></a>Pangsa Suara (SoV)

Kami menghitung SoV pada skala 100 poin. Total SoV di semua merek atau minat untuk setiap profil pelanggan yang diperkaya berjumlah hingga 100. Tidak seperti afinitas, SoV relatif terhadap merek dan minat yang Anda pilih. Misalnya, nilai SoV untuk 'Microsoft' dapat berbeda jika merek yang dipilih adalah ('Microsoft', 'GitHub') versus ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Negara/kawasan yang didukung

Saat ini kami mendukung pilihan negara/kawasan berikut: Australia, Kanada (Inggris), Prancis, Jerman, Inggris Raya, atau Amerika Serikat (Inggris).

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

   - Untuk mengonfigurasi afinitas merek dan pengayaan SoV, pilih **Perkaya data** saya di **ubin Merek**.

   - Untuk mengonfigurasi afinitas minat dan pengayaan SoV, pilih **Perkaya data** saya di **ubin Minat**.

   > [!div class="mx-imgBorder"]
   > ![Petak merek dan minat.](media/BrandsInterest-tile-Hub.png "Petak merek dan minat")

1. Tinjau gambaran umum lalu pilih **Berikutnya**.

1. Untuk mengubah negara atau wilayah Anda, pilih **Ubah** di samping **Negara/Kawasan**. **Di panel Pengaturan** negara/wilayah, pilih negara/wilayah [yang](#supported-countriesregions) didukung dan pilih **Terapkan**.

   > [!NOTE]
   > Saat memilih merek Anda sendiri, sistem memberikan saran berdasarkan negara atau kawasan yang dipilih. Saat memilih industri, Anda akan mendapatkan merek atau minat yang paling relevan berdasarkan negara atau kawasan yang dipilih.

1. Pilih hingga lima merek atau minat menggunakan satu atau kedua pilihan ini:

   - **Industri**: Pilih industri dari daftar dropdown, lalu pilih dari merek atau minat teratas untuk industri tersebut.
   - **Pilih sendiri**: Masukkan merek atau minat yang relevan untuk organisasi Anda, lalu pilih dari saran yang sesuai. Jika kami tidak mencantumkan merek atau minat yang Anda Cari, kirim masukan kepada kami menggunakan tautan **Usulkan**.

1. Pilih **Berikutnya** dan tinjau preferensi pengayaan default Anda dan perbarui sesuai kebutuhan.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Cuplikan layar jendela preferensi pengayaan.":::

1. Pilih **Selanjutnya**.

1. **Pilih himpunan data** Pelanggan dan pilih profil atau segmen yang ingin Anda perkaya dengan data dari Microsoft. Entitas Pelanggan *memperkaya semua profil pelanggan Anda sedangkan segmen hanya memperkaya profil pelanggan yang terkandung dalam segmen tersebut*.

1. Pilih **Selanjutnya**.

1. Petakan bidang Anda dari entitas pelanggan terpadu Anda ke data Microsoft.

   > [!NOTE]
   > Setidaknya atribut Tanggal Lahir atau Jenis Kelamin diperlukan. Negara/Wilayah dan setidaknya Kota (dan Negara Bagian/Provinsi) atau kode Pos diperlukan. Sebaiknya tanggal lahir dikonversi ke jenis DateTime selama penyerapan data. Atau, string dapat merupakan string dalam format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "yyyy-MM-dd" atau "yyyy-MM-ddTHH:mm:ss".

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Berikan nama untuk pengayaan. Nama **entitas Output** dipilih secara otomatis.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Halaman peninjauan dan penamaan minat.":::

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

1. Pilih **Jalankan** untuk memulai proses pengayaan atau tutup untuk kembali ke **halaman Pengayaan**.

   Bila memperkaya profil, kami akan memperkaya semua profil pelanggan dengan data yang kami dapatkan untuk merek dan minat tertentu, termasuk profil yang tidak berada di negara atau kawasan tertentu. Misalnya, jika Anda memilih Jerman, kami akan memperkaya profil yang berlokasi di Amerika Serikat jika kami memiliki data yang tersedia untuk merek dan minat yang dipilih di AS.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Pratinjau hasil setelah menjalankan proses pengayaan.":::

Hasilnya termasuk **grafik Affinity Level** atau **Pangsa Suara**.

Entitas yang dibuat dari pengayaan tercantum di bawah **grup Pengayaan** di **Entitas** > **Data**. Data yang diperkaya untuk merek masuk ke **entitas BrandAffinityFromMicrosoft** dan **BrandShareOfVoiceFromMicrosoft**. Data untuk kepentingan ada di **entitas InterestAffinityFromMicrosoft** dan **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Melihat data pengayaan pada kartu pelanggan

Merek dan minat SoV juga dapat dilihat pada kartu pelanggan individu. Buka **pelanggan** dan pilih profil pelanggan. Di kartu pelanggan, Anda akan menemukan bagan untuk merek atau SoV minat berdasarkan orang-orang di profil demografis pelanggan tersebut.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartu pelanggan dengan data yang diperkaya.":::

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
