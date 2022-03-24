---
title: Pengayaan profil perusahaan dengan pengayaan pihak ketiga Leadspace
description: Informasi umum tentang pengayaan pihak ketiga Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 0db0c984f6bf9f7ded0704b6fa0caf39c7dace3a
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376788"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Pengayaan profil perusahaan dengan Leadspace (pratinjau)

Leadspace adalah perusahaan ilmu data yang menyediakan Platform Data Pelanggan B-to-B. Ini memungkinkan lingkungan dengan profil pelanggan terpadu berdasarkan akun untuk memperkaya data mereka. Perkaya *profil pelanggan* dengan atribut seperti ukuran perusahaan, lokasi, atau industri. Perkaya *Profil kontak* dengan atribut seperti judul, persona, atau verifikasi email.

## <a name="prerequisites"></a>Prasyarat

Untuk mengonfigurasikan Leadspace, prasyarat berikut harus dipenuhi:

- Anda memiliki lisensi Leadspace aktif.
- Anda memiliki [profil pelanggan terpadu](customer-profiles.md) berdasarkan akun.
- Koneksi Leadspace telah dikonfigurasi oleh administrator atau Anda memiliki izin [administrator](permissions.md#admin) dan "kunci abadi" (disebut sebagai **token Leadspace**). Hubungi [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) secara langsung untuk detail tentang produk mereka.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Di wawasan audiens, buka **Data** > **pengayaan**.

1. Pilih **Perkaya data** saya di petak Leadspace dan pilih **Mulai**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Tangkapan layar petak Leadspace.":::

1. Pilih [koneksi](connections.md) dari daftar drop-down. Hubungi administrator jika tidak ada koneksi yang tersedia. Jika Anda adalah administrator, Anda bisa membuat koneksi dengan memilih **Tambahkan koneksi** dan memilih **Leadspace**. 

1. Pilih **Sambungkan ke Leadspace** untuk mengonfirmasi koneksi.

1. Pilih **Berikutnya** dan pilih **himpunan data Pelanggan** yang ingin Anda perkaya dengan data perusahaan dari Leadspace. Anda dapat memilih entitas **Pelanggan** untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Tangkapan layar saat memilih himpunan data pelanggan.":::

1. Pilih **Berikutnya** dan tentukan bidang mana dari profil terpadu Anda yang digunakan untuk mencari data perusahaan yang cocok dari Leadspace. Bidang **Nama perusahaan** diperlukan. Untuk akurasi kecocokan yang lebih tinggi, hingga dua bidang lainnya, **situs web perusahaan** dan **lokasi perusahaan**, dapat ditambahkan.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel pemetaan bidang leadspace.":::

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Pilih kotak centang jika Anda memiliki *profil Kontak* yang akan di perkaya. Wawasan Audiens akan secara otomatis memetakan bidang yang diperlukan.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Pengayaan rekaman kontak Leadspace.":::
 
1. Berikan nama untuk pengayaan dan pilih **Simpan pengayaan** setelah meninjau pilihan Anda.


## <a name="configure-the-connection-for-leadspace"></a>Mengonfigurasi koneksi untuk Leadspace 

Anda perlu menjadi administrator untuk mengonfigurasi koneksi. Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan *atau* masuk ke **Admin** > **Koneksi** dan pilih **Konfigurasi** pada petak Leadspace.

1. Pilih **Mulai**. 

1. Masukkan nama untuk koneksi dalam kotak **nama tampilan**.

1. Berikan token Leadspace yang valid.

1. Baca dan berikan persetujuan Anda untuk **privasi dan kesesuaian Data** dengan memilih **Saya setuju**.

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi.

1. Setelah menyelesaikan verifikasi, pilih **Simpan**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Halaman konfigurasi koneksi Leadspace.":::

## <a name="enrichment-results"></a>Hasil pengayaan

Setelah menyegarkan pengayaan, Anda dapat meninjau data perusahaan yang diperkaya di dalam [pengayaan saya](enrichment-hub.md). Anda dapat menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.

Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.

Untuk informasi lebih lanjut, lihat [api leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Langkah berikutnya


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Leadspace, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Leadspace memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
