---
title: Perkaya profil perusahaan dengan Dun & Bradstreet (pratinjau)
description: Informasi umum tentang pengayaan pihak ketiga Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 71b35e4295e19c13edadc6548ac79715555e8183
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196030"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Perkaya profil perusahaan dengan Dun & Bradstreet (pratinjau)

Dun & Bradstreet menyediakan data komersial, analitik, dan wawasan untuk bisnis. Hal ini memungkinkan pelanggan dengan profil pelanggan terpadu untuk perusahaan untuk memperkaya data mereka. Pengayaan mencakup atribut seperti nomor DUNS, ukuran perusahaan, lokasi, industri, dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

- Lisensi Dun & Bradstreet [yang aktif](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Profil](customer-profiles.md) pelanggan terpadu untuk perusahaan.
- Sebuah proyek [Dun &Bradstreet](#set-up-your-dun--bradstreet-project) sedang disiapkan.
- Koneksi Dun &Bradstreet [...](connections.md)[dikonfigurasi](#configure-a-connection-for-dun--bradstreet) oleh administrator.

## <a name="set-up-your-dun--bradstreet-project"></a>Siapkan proyek Dun & Bradstreet Anda

Sebagai pengguna berlisensi Dun & Bradstreet, Anda dapat mengatur proyek di [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Masuk ke [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Untuk mengambil kredensial, [pulihkan kata sandi](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights) Anda.

1. Unduh [file](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) template csv kami yang akan digunakan untuk memetakan bidang Customer Insights ke bidang Dun & Bradstreet yang sesuai.

1. Unggah file di **langkah Unggah data** dari pengalaman pembuatan proyek Dun & Bradstreet.

1. Pilih titik horizontal di bawah sumber **yang relevan** dalam proyek Dun & Bradstreet yang baru dibuat untuk melihat opsi yang tersedia.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Tangkapan layar titik-titik dalam proyek Dun & Bradstreet.":::

1. Pilih **Dapatkan detail** S3. Simpan informasi ini di tempat yang aman. Anda akan memerlukannya untuk [menyiapkan koneksi untuk pengayaan](#configure-a-connection-for-dun--bradstreet) di Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Cuplikan layar pemilihan informasi s3 dalam proyek Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Mengonfigurasi koneksi untuk Dun &Bradstreet

Anda harus menjadi [administrator](permissions.md#admin) di Customer Insights dan memiliki kredensial dari Dun &Bradstreet Connect.

1. Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan atau buka **Koneksi** > **Admin** dan pilih **Siapkan** di ubin Dun & Bradstreet.

1. Masukkan nama untuk koneksi.

1. Berikan kredensial Dun & Bradstreet yang valid dan detail *proyek Dun & Bradstreet Region, Drop folder path, dan Drop folder name*. Anda [mendapatkan informasi](#set-up-your-dun--bradstreet-project) ini dari proyek Dun & Bradstreet.

1. Baca dan berikan persetujuan Anda untuk [privasi dan kesesuaian Data](#data-privacy-and-compliance) dengan memilih **Saya setuju**.

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi lalu pilih **Simpan**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Halaman konfigurasi koneksi Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Ketika Anda memungkinkan Dynamics 365 Customer Insights untuk mengirimkan data ke Dun & Bradstreet, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa Dun & Bradstreet memenuhi kewajiban privasi atau keamanan apa pun yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.

## <a name="supported-countries-or-regions"></a>Negara atau kawasan yang didukung

Saat ini kami mendukung opsi negara/wilayah berikut: Kanada (Inggris) atau Amerika Serikat (Inggris).

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data** saya di **petak peta data** Perusahaan untuk Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Tangkapan layar ubin Dun & Bradstreet.":::

1. Tinjau gambaran umum lalu pilih **Berikutnya**.

1. Pilih koneksi dan konfirmasi. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Pilih **Selanjutnya**.

1. **Pilih himpunan data** Pelanggan dan pilih profil atau segmen yang ingin Anda perkaya dengan data perusahaan dari Dun &Bradstreet. Entitas Pelanggan *memperkaya semua profil pelanggan Anda sedangkan segmen hanya memperkaya profil pelanggan yang terkandung dalam segmen tersebut*.

1. Tentukan jenis bidang mana dari profil terpadu Anda yang akan digunakan untuk mencocokkan data perusahaan dari Dun &Bradstreet. Setidaknya salah satu bidang **Nama dan alamat**, **Telepon**, atau **Email** diperlukan.

1. Pilih **berikutnya**

1. Petakan bidang Anda ke data perusahaan dari Dun & Bradstreet. **Nomor DUNS** atau **Nama bidang perusahaan** dan **Negara** diperlukan.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Panel pemetaan lapangan Dun & Bradstreet.":::

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Berikan **Nama** untuk pengayaan dan **nama** entitas Output.

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

1. Pilih **Jalankan** untuk memulai proses pengayaan atau tutup untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
