---
title: Memperkaya profil pelanggan dengan Microsoft graph
description: Gunakan data kepemilikan dari Microsoft graph untuk memperkaya data pelanggan Anda dengan merek dan keterikatan minat.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406047"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Memperkaya profil pelanggan dengan merek dan afinitas minat (pratinjau)

Gunakan data kepemilikan dari Microsoft graph untuk memperkaya data pelanggan Anda dengan merek dan keterikatan minat. Afinitas ini ditentukan berdasarkan data dari orang yang memiliki demografi serupa dengan pelanggan Anda. Informasi ini membantu Anda lebih memahami dan menyegmentasikan pelanggan berdasarkan minat mereka terhadap merek dan minat tertentu.

Di wawasan audiens, buka **data** > **pengayaan** untuk [mengkonfigurasi dan melihat pengayaan](enrichment-hub.md).

Untuk mengkonfigurasi pengayaan afinitas merek, buka tab **temukan** dan pilih **Perkaya data saya** di ubin **merek**.

Untuk mengkonfigurasi pengayaan afinitas minat, buka tab **temukan** dan pilih **Perkaya data saya** di ubin **minat**.

   > [!div class="mx-imgBorder"]
   > ![Ubin Merek & minat](media/BrandsInterest-tile-Hub.png "Ubin Merek & minat")

## <a name="about-microsoft-graph"></a>Tentang Microsoft Graph

Kita menggunakan data pencarian online dari Microsoft Graph untuk menemukan minat terhadap merek dan minat di berbagai segmen demografis (ditentukan berdasarkan usia, jenis kelamin, atau lokasi). Volume pencarian online untuk merek atau minat menentukan seberapa besar afinitas yang dimiliki segmen demografis, dibandingkan dengan segmen lain, atas merek atau minat tersebut.

[Selengkapnya tentang Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Skor afinitas dan keyakinan

**Skor afinitas** dihitung pada skala 100-poin, dengan 100 mewakili segmen yang memiliki afinitas tertinggi untuk merek atau minat.

**Keyakinan afinitas** juga dihitung pada skala 100 poin. Ini menunjukkan tingkat kepercayaan sistem bahwa segmen memiliki afinitas atas merek atau minat. Tingkat keyakinan didasarkan pada ukuran segmen dan perincian segmen. Ukuran segmen ditentukan berdasarkan jumlah data yang kita miliki untuk segmen tertentu. Perincian segmen ditentukan berdasarkan jumlah atribut (usia, jenis kelamin, lokasi) yang tersedia di profil.

Kita tidak menormalkan Skor untuk kumpulan data Anda. Akibatnya, Anda mungkin tidak melihat semua nilai Skor afinitas yang mungkin untuk himpunan data Anda. Misalnya, mungkin tidak ada profil pelanggan yang diperkaya dengan Skor afinitas 100 di data Anda. Mungkin tidak ada pelanggan yang ada di segmen demografis yang mencetak skor 100 untuk merek atau minat tertentu.

> [!TIP]
> Saat [membuat segmen](segments.md) menggunakan Skor afinitas, Tinjau distribusi Skor afinitas untuk kumpulan data Anda sebelum menentukan ambang batas Skor yang sesuai. Misalnya, Skor afinitas 10 dapat dianggap signifikan dalam kumpulan data yang memiliki Skor afinitas tertinggi hanya 25 untuk merek atau minat tertentu.

## <a name="supported-countriesregions"></a>Negara/kawasan yang didukung

Saat ini kami mendukung pilihan negara/kawasan berikut: Australia, Kanada (Inggris), Prancis, Jerman, Inggris Raya, atau Amerika Serikat (Inggris).

Untuk memilih negara, buka **pengayaan merek** atau **pengayaan mina**, lalu pilih **Ubah** di samping **negara/kawasan**. Di panel **pengaturan negara/kawasan**, pilih pilihan, lalu pilih **Terapkan**.

### <a name="implications-related-to-country-selection"></a>Implikasi terkait pemilihan negara

- Saat [memilih merek Anda sendiri](#define-your-brands-or-interests), kami akan memberikan saran berdasarkan negara/kawasan yang dipilih.

- Saat [memilih industri](#define-your-brands-or-interests), kami akan mengidentifikasi merek atau minat yang paling relevan berdasarkan negara/kawasan yang dipilih.

- Saat [memetakan bidang Anda](#map-your-fields), jika bidang negara/kawasan tidak dipetakan, kami akan menggunakan data Microsoft Graph dari negara/kawasan yang dipilih untuk memperkaya profil pelanggan Anda. Kami juga akan menggunakan pilihan tersebut untuk memperkaya profil pelanggan Anda yang tidak memiliki data negara/kawasan.

- Saat [memperkaya profil](#refresh-enrichment), kami akan memperkaya semua profil pelanggan yang memiliki data Microsoft graph yang tersedia untuk merek dan minat tertentu, termasuk profil yang tidak ada di negara/kawasan yang dipilih. Misalnya, jika Anda memilih Jerman, kami akan memperkaya profil yang terletak di Amerika Serikat jika kami memiliki data Microsoft graph yang tersedia untuk merek dan minat tertentu di AS.

## <a name="configure-enrichment"></a>Konfigurasi pengayaan

Mengkonfigurasi pengayaan minat atau merek terdiri dari dua langkah:

### <a name="define-your-brands-or-interests"></a>Definisikan merek atau minat Anda

pilih salah satu dari opsi berikut ini:

- **Industri**: sistem mengidentifikasi merek atau minat teratas yang relevan dengan industri Anda dan memperkaya data pelanggan Anda dengannya.
- **Pilih punya Anda sendiri**: Pilih hingga lima item dari daftar merek atau minat yang paling relevan dengan organisasi Anda.

Untuk menambahkan merek atau minat, masukkan di area input untuk mendapatkan saran berdasarkan persyaratan kecocokan. Jika kami tidak mencantumkan merek atau minat yang Anda Cari, kirim masukan kepada kami menggunakan tautan **Usulkan**.

### <a name="map-your-fields"></a>Petakan bidang Anda

Petakan bidang dari entitas pelanggan terpadu ke minimal dua atribut untuk menentukan segmen demografi yang akan kami gunakan untuk memperkaya data pelanggan Anda. Pilih **Edit** untuk menentukan pemetaan bidang, lalu pilih **Terapkan** setelah selesai. Pilih **Simpan** untuk menyelesaikan pemetaan bidang.

Format dan nilai berikut didukung, nilai tidak peka terhadap besar huruf:

- **Tanggal lahir**: sebaiknya tanggal lahir dikonversi ke jenis datetime selama proses transfer data. Atau, dapat berupa string dalam format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "yyyy-MM-dd" atau "yyyy-MM-ddTHH:mm:ssZ."
- **Jenis kelamin**: laki-laki, perempuan, tidak diketahui
- **Kode pos**: lima digit kode pos untuk AS, kode pos standar di tempat lainnya
- **Kota**: nama kota dalam bahasa Inggris
- **Negara bagian/propinsi**: singkatan dua huruf untuk AS dan Kanada. Dua atau tiga huruf singkatan untuk Australia. Tidak berlaku untuk Prancis, Jerman, atau Inggris.
- **Negara/Kawasan**:

  - AS: Amerika Serikat, USA, AS, Amerika
  - CA: Kanada, CA
  - GB: Inggris, Inggris, Britania Raya, GB, Britania Raya dan Irlandia Utara, Inggris Raya
  - AU: Australia, AU, Persemakmuran Australia
  - FR: Prancis, Republik Prancis
  - DE: Jerman, Jerman, Deutschland, Allemagne, DE, Republik Federal Jerman, Republik Jerman

## <a name="refresh-enrichment"></a>Segarkan pengayaan

Jalankan pengayaan setelah mengonfigurasi merek, minat, dan pemetaan bidang untuk demografi. Untuk memulai proses, pilih **Jalankan** pada halaman konfigurasi merek atau minat. Selain itu, Anda dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari penyegaran terjadwal.
Tergantung pada ukuran data pelanggan Anda, diperlukan waktu beberapa menit untuk pengayaan yang dijalankan untuk diselesaikan.

> [!TIP]
> Ada [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies). Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan. Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.

## <a name="enrichment-results"></a>Hasil pengayaan

Setelah menjalankan proses pengayaan, buka **Pengayaan saya** untuk meninjau total jumlah pelanggan yang diperkaya dan perincian merek atau minat atas profil pelanggan yang diperkaya.

:::image type="content" source="media/my-enrichments.png" alt-text="Pratinjau hasil setelah menjalankan proses pengayaan":::

Tinjau data yang diperkaya dengan memilih **Lihat data yang diperkaya** di diagram. Data yang diperkaya untuk merek beralih ke entitas **BrandAffinityFromMicrosoft**. Data untuk minat ada di entitas **InterestAffinityFromMicrosoft**. Anda juga akan menemukan entitas yang tercantum di grup **pengayaan** dalam **data** > **entitas**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Melihat data pengayaan pada kartu pelanggan

afinitas Merek dan minat juga dapat dilihat pada kartu Pelanggan perorangan. Buka **pelanggan** dan pilih profil pelanggan. Di kartu pelanggan, Anda akan menemukan diagram untuk merek atau minat yang dimiliki afinitasnya oleh orang dalam profil demografi pelanggan.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartu pelanggan dengan data yang diperkaya":::

## <a name="next-steps"></a>Langkah-langkah berikutnya

Bangun di atas data pelanggan yang diperkaya. Buat [segmen](segments.md), [tindakan](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan bagi pelanggan Anda.
