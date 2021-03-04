---
title: Pengayaan profil perusahaan dengan pengayaan pihak ketiga Leadspace
description: Informasi umum tentang pengayaan pihak ketiga Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269426"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Pengayaan profil perusahaan dengan Leadspace (pratinjau)

Leadspace adalah perusahaan ilmu data yang menyediakan platform data pelanggan B2B. Hal ini memungkinkan pelanggan dengan profil pelanggan terpadu untuk perusahaan untuk memperkaya data mereka. Pengayaan mencakup atribut tambahan seperti ukuran perusahaan, lokasi, industri, dan lainnya.

## <a name="prerequisites"></a>Prasyarat

Untuk mengonfigurasikan Leadspace, prasyarat berikut harus dipenuhi:

- Anda memiliki lisensi Leadspace aktif dan "kunci permanen" (disebut sebagai **token leadspace**). Hubungi langsung [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) untuk rincian tentang produk mereka.
- Anda memiliki izin [administratif](permissions.md#administrator).
- Anda memiliki [profil pelanggan terpadu](customer-profiles.md) untuk perusahaan.

## <a name="configuration"></a>Konfigurasi

1. Di wawasan audiens, buka **Data** > **pengayaan**.

1. Pilih **Perkaya data saya** di ubin Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Tangkapan layar petak Leadspace.":::

1. Pilih **persiapan,** lalu masukkan **token leadspace** aktif (kunci permanen). Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**. Konfirmasikan kedua input dengan memilih **Sambungkan ke Leadspace**.

1. Pilih **Petakan data** dan pilih himpunan data yang anda ingin perkaya dengan data perusahaan dari Leadspace. Anda dapat memilih entitas *Pelanggan* untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Pilih antara profil pelanggan dan pengayaan segmen.":::

1. Klik **selanjutnya** dan tentukan bidang mana dari profil terpadu yang Anda harus gunakan untuk mencari data perusahaan yang cocok dari leadspace. Bidang **Nama perusahaan** diperlukan. Untuk akurasi kecocokan yang lebih tinggi, hingga dua bidang lainnya, **situs web perusahaan** dan **lokasi perusahaan**, dapat ditambahkan.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel pemetaan bidang leadspace.":::
   
1. Pilih **Terapkan** untuk menyelesaikan pemetaan bidang.

1. Pilih **Jalankan** untuk memperkaya profil perusahaan. Berapa lama pengayaan diperlukan tergantung pada jumlah profil pelanggan terpadu.

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