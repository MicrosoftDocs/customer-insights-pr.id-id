---
title: Pengayaan profil perusahaan dengan Dun & Bradstreet
description: Informasi umum tentang pengayaan pihak ketiga Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653784"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Pengayaan profil perusahaan dengan Dun & Bradstreet (pratinjau)

Dun & Bradstreet menyediakan data komersial, analitik, dan wawasan untuk bisnis. Hal ini memungkinkan pelanggan dengan profil pelanggan terpadu untuk perusahaan untuk memperkaya data mereka. Pengayaan termasuk atribut seperti nomor DUNS, ukuran perusahaan, lokasi, industri, dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

Untuk mengonfigurasi pengayaan Dun & Bradstreet, prasyarat berikut harus dipenuhi:

- Anda memiliki lisensi Dun & Bradstreet [yang aktif](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- Anda memiliki [profil pelanggan terpadu](customer-profiles.md) untuk perusahaan.
- Koneksi Dun & Bradstreet [dikonfigurasi](connections.md) oleh administrator. Anda dapat membuatnya jika Anda memiliki [izin administrator](permissions.md#admin) dan kredensial dari Dun & Bradstreet Connect. 

## <a name="setting-up-your-dun--bradstreet-project"></a>Menyiapkan proyek Dun & Bradstreet Anda

Sebagai pengguna berlisensi Dun & Bradstreet, Anda dapat membuat proyek di [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). 


1. Masuk ke [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Untuk mengambil kredensial, [pulihkan kata sandi](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights) Anda.

1. Unduh [file](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) template csv kami yang akan digunakan untuk memetakan bidang wawasan audiens ke bidang Dun & Bradstreet yang sesuai. 

1. Unggah file di **langkah Unggah data** dari pengalaman pembuatan proyek Dun & Bradstreet. 

1. Pilih titik horizontal di bawah sumber **yang relevan** dalam proyek Dun & Bradstreet yang baru dibuat untuk melihat opsi yang tersedia.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Cuplikan layar titik-titik dalam proyek Dun & Bradstreet.":::

1. Pilih **Dapatkan detail** S3. Simpan informasi ini di tempat yang aman. Anda memerlukannya untuk [menyiapkan koneksi untuk pengayaan](#configure-a-connection-for-dun--bradstreet) dalam wawasan audiens. 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Tangkapan layar pemilihan informasi s3 dalam proyek Dun & Bradstreet.":::



## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Di wawasan audiens, buka **Data** > **pengayaan**.

1. Pilih **Perkaya data** saya di ubin Dun & Bradstreet dan pilih **Mulailah**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Tangkapan layar ubin Dun & Bradstreet.":::

1. Pilih [koneksi](connections.md) dari daftar drop-down. Hubungi administrator jika tidak ada koneksi yang tersedia. Jika Anda seorang administrator, Anda dapat membuat koneksi. Pilih **Tambahkan koneksi** dan pilih **Dun & Bradstreet**. 

1. Pilih **Sambungkan ke Dun & Bradstreet** untuk mengonfirmasi koneksi.

1. Pilih **Berikutnya** dan pilih **Pelanggan himpunan data** ingin Anda memperkaya dengan data perusahaan dari Dun & Bradstreet. Anda dapat memilih **entitas Pelanggan** untuk memperkaya semua profil pelanggan Anda atau memilih entitas segmen untuk memperkaya hanya profil pelanggan terpadu yang terdapat dalam segmen tersebut.

1. Pilih **Berikutnya** dan tentukan bidang mana dari profil terpadu Anda yang digunakan untuk mencari data perusahaan yang cocok dari Dun & Bradstreet. Nomor **DUNS** atau **Nama bidang perusahaan** dan **Negara** diperlukan. Bidang negara mendukung [dua atau tiga kode negara huruf, nama](https://www.iso.org/iso-3166-country-codes.html) negara dalam bahasa Inggris, nama negara dalam bahasa asli, dan awalan telepon. Beberapa varian negara yang umum meliputi:

   * AS: Amerika Serikat, Amerika Serikat, Amerika Serikat, Amerika Serikat, Amerika.
   * Ca: Kanada.
   * GB: Inggris, Inggris, Britania Raya, GB, Britania Raya dan Irlandia Utara, Britania Raya.
   * AU: Australia, Persemakmuran Australia.
   * FR: Prancis, Republik Prancis.
   * DE: Jerman, Jerman, Deutschland, Allemagne, Republik Federal Jerman, Republik Jerman.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Panel pemetaan lapangan Dun & Bradstreet.":::

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Berikan nama untuk pengayaan dan pilih **Simpan pengayaan** setelah meninjau pilihan Anda.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Mengonfigurasi koneksi untuk Dun & Bradstreet 

Anda perlu menjadi administrator untuk mengonfigurasi koneksi. Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan *atau* buka **AdminConnections** > **dan** pilih **Siapkan** di ubin Dun & Bradstreet.

1. Pilih **Mulai**. 

1. Masukkan nama untuk koneksi dalam kotak **nama tampilan**.

1. Berikan kredensial Dun & Bradstreet yang valid dan detail *proyek Dun & Bradstreet Wilayah, jalur folder Drop, dan nama* folder Drop. Anda [mendapatkan informasi](#setting-up-your-dun--bradstreet-project) ini dari proyek Dun & Bradstreet.

1. Baca dan berikan persetujuan Anda untuk **privasi dan kesesuaian Data** dengan memilih **Saya setuju**.

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi.

1. Setelah menyelesaikan verifikasi, pilih **Simpan**.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Halaman konfigurasi koneksi Dun & Bradstreet.":::

## <a name="enrichment-results"></a>Hasil pengayaan

Setelah menyegarkan pengayaan, Anda dapat meninjau data perusahaan yang diperkaya di dalam [pengayaan saya](enrichment-hub.md). Anda dapat menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.

Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Dun & Bradstreet, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa Dun & Bradstreet memenuhi kewajiban privasi atau keamanan apa pun yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE[footer-include](includes/footer-banner.md)]
