---
title: Pengayaan profil perusahaan dengan pengayaan pihak ketiga Leadspace
description: Informasi umum tentang pengayaan pihak ketiga Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895917"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Pengayaan profil perusahaan dengan Leadspace (pratinjau)

Leadspace adalah perusahaan ilmu data yang menyediakan platform data pelanggan B2B. Hal ini memungkinkan pelanggan dengan profil pelanggan terpadu untuk perusahaan untuk memperkaya data mereka. Pengayaan mencakup atribut seperti ukuran perusahaan, lokasi, industri, dan lainnya.

## <a name="prerequisites"></a>Prasyarat

Untuk mengonfigurasikan Leadspace, prasyarat berikut harus dipenuhi:

- Anda memiliki lisensi Leadspace aktif.
- Anda memiliki [profil pelanggan terpadu](customer-profiles.md) untuk perusahaan.
- Koneksi Leadspace telah dikonfigurasi oleh administrator atau Anda memiliki izin [administrator](permissions.md#administrator) dan "kunci abadi" (disebut sebagai **token Leadspace**). Hubungi [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) secara langsung untuk detail tentang produk mereka.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Di wawasan audiens, buka **Data** > **pengayaan**.

1. Pilih **Perkaya data** saya di petak Leadspace dan pilih **Mulai**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Tangkapan layar petak Leadspace.":::

1. Pilih [koneksi](connections.md) dari menu tarik-turun. Hubungi administrator jika tidak ada koneksi yang tersedia. Jika Anda adalah administrator, Anda bisa membuat koneksi dengan memilih **Tambahkan koneksi** dan memilih **Leadspace**. 

1. Pilih **Sambungkan ke Leadspace** untuk mengonfirmasi koneksi.

1. Pilih **Berikutnya** dan pilih **himpunan data Pelanggan** yang ingin Anda perkaya dengan data perusahaan dari Leadspace. Anda dapat memilih entitas **Pelanggan** untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Tangkapan layar saat memilih himpunan data pelanggan.":::

1. Pilih **Berikutnya** dan tentukan bidang mana dari profil terpadu Anda yang digunakan untuk mencari data perusahaan yang cocok dari Leadspace. Bidang **Nama perusahaan** diperlukan. Untuk akurasi kecocokan yang lebih tinggi, hingga dua bidang lainnya, **situs web perusahaan** dan **lokasi perusahaan**, dapat ditambahkan.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel pemetaan bidang leadspace.":::

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Berikan nama untuk pengayaan dan pilih **Simpan pengayaan** setelah meninjau pilihan Anda.


## <a name="configure-the-connection-for-leadspace"></a>Mengonfigurasi koneksi untuk Leadspace 

Anda perlu menjadi administrator untuk mengonfigurasi koneksi. Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan *atau* masuk ke **Admin** > **Koneksi** dan pilih **Konfigurasi** pada petak Leadspace.

1. Pilih **Mulai** 

1. Masukkan nama untuk koneksi dalam kotak **nama tampilan**.

1. Berikan token Leadspace yang valid.

1. Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi.

1. Setelah menyelesaikan verifikasi, pilih **Simpan**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Halaman konfigurasi koneksi Leadspace.":::

## <a name="enrichment-results"></a>Hasil pengayaan

Setelah menyegarkan pengayaan, Anda dapat meninjau data perusahaan yang diperkaya di dalam [pengayaan saya](enrichment-hub.md). Anda dapat menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.

Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.

Untuk informasi lebih lanjut, lihat [api leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Langkah berikutnya

Bangun di atas data pelanggan yang diperkaya. Buat [segmen](segments.md), [tindakan](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan bagi pelanggan Anda.

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Leadspace, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Leadspace memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
