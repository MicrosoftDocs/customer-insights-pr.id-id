---
title: Perkaya profil pelanggan dengan data dari Microsoft
description: Gunakan data kepemilikan dari Microsoft untuk memperkaya data pelanggan Anda dengan afinitas merek dan minat.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305160"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Memperkaya profil pelanggan dengan merek dan afinitas minat (pratinjau)

Gunakan data kepemilikan dari Microsoft untuk memperkaya data pelanggan Anda dengan afinitas merek dan minat. Afinitas ini didasarkan pada data dari orang-orang dengan demografi yang serupa dengan pelanggan Anda. Informasi ini membantu Anda lebih memahami dan menyegmentasikan pelanggan berdasarkan minat mereka terhadap merek dan minat tertentu.

Di wawasan audiens, buka **data** > **pengayaan** untuk [mengkonfigurasi dan melihat pengayaan](enrichment-hub.md).

Untuk mengkonfigurasi pengayaan afinitas merek, buka tab **temukan** dan pilih **Perkaya data saya** di ubin **merek**.

Untuk mengkonfigurasi pengayaan afinitas minat, buka tab **temukan** dan pilih **Perkaya data saya** di ubin **minat**.

   > [!div class="mx-imgBorder"]
   > ![Petak merek dan minat](media/BrandsInterest-tile-Hub.png "Petak merek dan minat")

## <a name="how-we-determine-affinities"></a>Bagaimana kami menentukan afinitas

Kami menggunakan data pencarian online Microsoft untuk menemukan afinitas untuk merek dan minat di berbagai segmen demografis (didefinisikan berdasarkan usia, jenis kelamin, atau lokasi). Volume pencarian online untuk merek atau minat menentukan seberapa besar afinitas yang dimiliki segmen demografis, dibandingkan dengan segmen lain, atas merek atau minat tersebut.

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

Pilih **Entitas yang diperkaya** dan pilih himpunan data yang ingin Anda perkaya dengan data perusahaan dari Microsoft. Anda dapat memilih entitas Pelanggan untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.

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

> [!TIP]
> Ada [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies). Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan. Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda akan menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, serta semua kesalahan dan peringatan yang terkait dengan tugas.

## <a name="enrichment-results"></a>Hasil pengayaan

Setelah menjalankan proses pengayaan, buka **Pengayaan saya** untuk meninjau total jumlah pelanggan yang diperkaya dan perincian merek atau minat atas profil pelanggan yang diperkaya.

:::image type="content" source="media/my-enrichments.png" alt-text="Pratinjau hasil setelah menjalankan proses pengayaan":::

Tinjau data yang diperkaya dengan memilih **Lihat data yang diperkaya** di diagram. Data yang diperkaya untuk merek beralih ke entitas **BrandAffinityFromMicrosoft**. Data untuk minat ada di entitas **InterestAffinityFromMicrosoft**. Anda juga akan menemukan entitas yang tercantum di grup **pengayaan** dalam **data** > **entitas**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Melihat data pengayaan pada kartu pelanggan

afinitas Merek dan minat juga dapat dilihat pada kartu Pelanggan perorangan. Buka **pelanggan** dan pilih profil pelanggan. Di kartu pelanggan, Anda akan menemukan diagram untuk merek atau minat yang dimiliki afinitasnya oleh orang dalam profil demografi pelanggan.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartu pelanggan dengan data yang diperkaya":::

## <a name="next-steps"></a>Langkah-langkah berikutnya

Bangun di atas data pelanggan yang diperkaya. Buat [segmen](segments.md) dan [ukuran](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman pribadi kepada pelanggan Anda.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
