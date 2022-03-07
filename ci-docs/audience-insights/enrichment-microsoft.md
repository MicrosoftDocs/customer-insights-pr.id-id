---
title: Perkaya profil pelanggan dengan data dari Microsoft
description: Gunakan data eksklusif dari Microsoft untuk memperkaya data pelanggan Anda dengan afinitas dan Pangsa Suara.
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
ms.openlocfilehash: 12704ec46832e9463e6115db6c4df64e72bf4f97
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/02/2022
ms.locfileid: "8372677"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Memperkaya profil pelanggan dengan afinitas dan Pangsa Suara (pratinjau)

Gunakan data milik Microsoft untuk memperkaya data pelanggan Anda dengan afinitas merek, afinitas minat, dan Pangsa Suara (SoV). Afinitas dan SoV ini didasarkan pada data dari orang-orang dengan demografi yang mirip dengan pelanggan Anda. Informasi ini membantu Anda untuk lebih memahami dan mengelompokkan pelanggan Anda berdasarkan afinitas atau SoV mereka dengan merek dan minat tertentu.

Di wawasan audiens, buka **data** > **pengayaan** untuk [mengkonfigurasi dan melihat pengayaan](enrichment-hub.md).

Untuk mengonfigurasi afinitas merek dan pengayaan SoV, buka **tab Temukan** dan pilih **Perkaya data** saya di **ubin Merek**.

Untuk mengonfigurasi afinitas minat dan pengayaan SoV, buka **tab Temukan** dan pilih **Perkaya data** saya di **ubin Minat**.

   > [!div class="mx-imgBorder"]
   > ![Petak merek dan minat.](media/BrandsInterest-tile-Hub.png "Petak merek dan minat")

## <a name="how-we-determine-affinities-and-sov"></a>Bagaimana kita menentukan afinitas dan SoV

Kami menggunakan data pencarian online Microsoft untuk menemukan afinitas dan SoV untuk merek dan minat di berbagai segmen demografis (ditentukan berdasarkan usia, jenis kelamin, atau lokasi). Volume pencarian online untuk merek atau minat membentuk dasar untuk menentukan afinitas atau SoV. Namun, masing-masing memberikan perspektif yang berbeda untuk memahami pelanggan Anda.

- Afinitas adalah perbandingan di seluruh segmen demografis. Anda dapat menggunakan informasi ini untuk mengidentifikasi segmen demografis yang memiliki afinitas tertinggi untuk merek atau minat tertentu, dibandingkan dengan segmen lain.

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

Kami menghitung SoV pada skala 100 poin. Total SoV di semua merek atau minat untuk setiap profil pelanggan yang diperkaya menambahkan hingga 100. Tidak seperti afinitas, SoV relatif terhadap merek dan minat yang Anda pilih. Misalnya, nilai SoV untuk 'Microsoft' bisa berbeda jika merek yang dipilih adalah ('Microsoft', 'GitHub') versus ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Negara/kawasan yang didukung

Saat ini kami mendukung pilihan negara/kawasan berikut: Australia, Kanada (Inggris), Prancis, Jerman, Inggris Raya, atau Amerika Serikat (Inggris).

Untuk memilih negara atau kawasan, buka **Pengayaan Merek** atau **Pengayaan minat** dan pilih **Ubah** di sebelah **Negara/Kawasan**. Di panel **pengaturan negara/kawasan**, pilih pilihan, lalu pilih **Terapkan**.

### <a name="implications-related-to-country-selection"></a>Implikasi terkait pemilihan negara

- Saat [memilih merek Anda sendiri](#define-your-brands-or-interests), sistem memberikan saran berdasarkan negara atau kawasan yang dipilih.

- Saat [memilih industri](#define-your-brands-or-interests), Anda akan mendapatkan merek atau minat yang paling relevan berdasarkan negara atau kawasan yang dipilih.

- Bila [memperkaya profil](#refresh-enrichment), kami akan memperkaya semua profil pelanggan dengan data yang kami dapatkan untuk merek dan minat tertentu, termasuk profil yang tidak berada di negara atau kawasan tertentu. Misalnya, jika Anda memilih Jerman, kami akan memperkaya profil yang berlokasi di Amerika Serikat jika kami memiliki data yang tersedia untuk merek dan minat yang dipilih di AS.

## <a name="configure-enrichment"></a>Konfigurasi pengayaan

Pengalaman terpandu membantu Anda melalui konfigurasi pengayaan. 

### <a name="define-your-brands-or-interests"></a>Definisikan merek atau minat Anda

Pilih hingga lima merek atau minat menggunakan satu atau kedua pilihan ini:

- **Industri**: Pilih industri dari daftar dropdown, lalu pilih dari merek atau minat teratas untuk industri tersebut.
- **Pilih sendiri**: Masukkan merek atau minat yang relevan untuk organisasi Anda, lalu pilih dari saran yang sesuai. Jika kami tidak mencantumkan merek atau minat yang Anda Cari, kirim masukan kepada kami menggunakan tautan **Usulkan**.

### <a name="review-enrichment-preferences"></a>Tinjau Preferensi pengayaan

Tinjau preferensi pengayaan default dan perbarui jika diperlukan.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Cuplikan layar jendela preferensi pengayaan.":::

### <a name="select-entity-to-enrich"></a>Pilih entitas yang akan diperkaya

Pilih **Entitas** yang diperkaya dan pilih himpunan data yang ingin Anda perkayakan dengan data dari Microsoft. Anda dapat memilih entitas Pelanggan untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.

### <a name="map-your-fields"></a>Petakan bidang Anda

Petakan bidang dari entitas pelanggan terpadu untuk menentukan segmen demografi yang akan digunakan sistem untuk memperkaya data pelanggan. Petakan Negara/Kawasan dan sekurangnya atribut Tanggal Lahir atau Jenis Kelamin. Atau, Anda harus memetakan minimal satu Kota (dan Negara Bagian/Provinsi) atau Kode Pos. Pilih **Edit** untuk menentukan pemetaan bidang, lalu pilih **Terapkan** setelah selesai. Pilih **Simpan** untuk menyelesaikan pemetaan bidang.

Format dan nilai berikut didukung, (nilai tidak peka terhadap besar huruf):

- **Tanggal lahir**: sebaiknya tanggal lahir dikonversi ke jenis datetime selama proses transfer data. Atau, string dapat merupakan string dalam format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "yyyy-MM-dd" atau "yyyy-MM-ddTHH:mm:ss".
- **Jenis kelamin**: laki-laki, perempuan, tidak diketahui.
- **Kode pos**: Kode ZIP lima digit untuk Amerika Serikat, kode pos standar di mana pun.
- **Kota**: nama kota dalam bahasa Inggris.
- **Negara bagian/propinsi**: singkatan dua huruf untuk AS dan Kanada. Dua atau tiga huruf singkatan untuk Australia. Tidak berlaku untuk Prancis, Jerman, atau Inggris.
- **Negara/Kawasan**:

  - AS: Amerika Serikat, USA, AS, Amerika
  - CA: Kanada, CA
  - GB: Inggris, Inggris, Britania Raya, GB, Britania Raya dan Irlandia Utara, Inggris Raya
  - ID: Australia, ID, Commonwealth di Australia
  - FR: Prancis, Republik Prancis
  - DE: Jerman, Jerman, Deutschland, Allemagne, DE, Republik Federal Jerman, Republik Jerman

## <a name="review-and-name-the-enrichment"></a>Tinjau dan beri nama pengayaan

Akhirnya, Anda dapat meninjau informasi dan memberikan nama untuk pengayaan.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Halaman peninjauan dan penamaan minat.":::

## <a name="refresh-enrichment"></a>Segarkan pengayaan

Jalankan pengayaan setelah mengonfigurasi merek, minat, dan pemetaan bidang untuk demografi. Untuk memulai proses, pilih **Jalankan** pada halaman konfigurasi merek atau minat. Selain itu, Anda dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari penyegaran terjadwal.

Tergantung pada ukuran data pelanggan Anda, diperlukan waktu beberapa menit untuk pengayaan yang dijalankan untuk diselesaikan.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Hasil pengayaan

Setelah menjalankan proses pengayaan, buka **Pengayaan saya** untuk meninjau total jumlah pelanggan yang diperkaya dan perincian merek atau minat atas profil pelanggan yang diperkaya.

:::image type="content" source="media/my-enrichments.png" alt-text="Pratinjau hasil setelah menjalankan proses pengayaan.":::

Anda akan menemukan bagan dengan jumlah profil pelanggan yang diperkaya dari waktu ke waktu dan pratinjau entitas yang diperkaya. Tinjau data yang diperkaya dengan **memilih Lihat selengkapnya** **di bagan Tingkat** Afinitas atau **Pangsa Suara**. Data yang diperkaya untuk merek masuk ke **entitas BrandAffinityFromMicrosoft** dan **BrandShareOfVoiceFromMicrosoft**. Data untuk kepentingan ada di **entitas InterestAffinityFromMicrosoft** dan **InterestShareOfVoiceFromMicrosoft**. Anda juga akan menemukan entitas yang tercantum di grup **pengayaan** dalam **data** > **entitas**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Melihat data pengayaan pada kartu pelanggan

Merek dan minat SoV juga dapat dilihat pada kartu pelanggan individu. Buka **pelanggan** dan pilih profil pelanggan. Di kartu pelanggan, Anda akan menemukan bagan untuk merek atau minat SoV berdasarkan orang-orang di profil demografis pelanggan tersebut.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartu pelanggan dengan data yang diperkaya.":::

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
