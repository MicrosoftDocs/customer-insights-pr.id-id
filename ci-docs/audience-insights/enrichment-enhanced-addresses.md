---
title: Pengayaan peningkatan alamat
description: Perkaya dan normalisasi informasi alamat profil pelanggan dengan model Microsoft.
ms.date: 07/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 65db6ce05f4d6f7f7b08ada172fec057027dd310
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692257"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Pengayaan profil pelanggan dengan alamat yang disempurnakan

Alamat pada data dapat tidak terstruktur, tidak lengkap, atau salah. Gunakan model Microsoft untuk menormalkan dan memperkaya alamat Anda ke dalam [format Common Data Model](/common-data-model/schema/core/applicationcommon/address) untuk keakuratan dan wawasan yang lebih baik.

## <a name="how-we-enhance-addresses"></a>Cara kami meningkatkan alamat

Model kami melalui proses dua langkah untuk meningkatkan alamat. Pertama, ia mengurai alamat untuk mengidentifikasi komponennya dan memasukkannya ke dalam format terstruktur. Selanjutnya, kami akan menggunakan AI untuk mengoreksi, menyelesaikan, dan membuat standar nilai di alamat.

### <a name="example"></a>Contoh

Informasi alamat mungkin berada dalam format nonstandard dan berisi kesalahan ejaan. Model dapat memperbaiki masalah ini dan membuat alamat yang konsisten di profil pelanggan terpadu.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Pembatasan

Alamat yang disempurnakan hanya berfungsi dengan nilai yang sudah ada di data alamat yang diserap. Model tidak: 

1. Memverifikasikan apakah alamat tersebut adalah alamat yang valid.
2. Memverifikasikan apakah salah satu nilai, seperti kode ZIP atau nama jalan, valid.
3. Mengubah nilai yang tidak dikenali.

Model menggunakan teknik berbasis pembelajaran mesin untuk meningkatkan alamat. Meskipun kami menerapkan ambang batas keyakinan tinggi bila model mengubah nilai input, seperti model berbasis pembelajaran mesin, keakuratan 100 persen tidak dijamin.

## <a name="supported-countries-or-regions"></a>Negara atau kawasan yang didukung

Saat ini kami mendukung pengayaan alamat di negara atau kawasan berikut: 

- Australia
- Kanada
- Prancis
- Jerman
- Italia
- Jepang
- Inggris Raya
- Amerika Serikat

Alamat harus berisi nilai negara/kawasan. Kami tidak memproses alamat untuk negara atau kawasan yang tidak didukung dan alamat yang tidak memiliki negara atau kawasan yang disediakan.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka **Data** > **Pengayaan**.

1. Pilih **Perkaya data saya** pada ubin **Alamat yang disempurnakan**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Tangkapan layar ubin Alamat yang Disempurnakan.":::

1. Pilih **himpunan data Pelanggan** dan pilih entitas berisi alamat yang akan diperkaya. Anda dapat memilih entitas *Pelanggan* untuk memperkaya alamat di semua profil pelanggan atau memilih entitas segmen untuk memperkaya alamat hanya dalam profil pelanggan yang terdapat dalam segmen tersebut.

1. Pilih format alamat dalam himpunan data Anda. Pilih **Alamat atribut tunggal** jika alamat di data Anda menggunakan satu bidang. Pilih **Beberapa atribut Alamat** jika alamat di data Anda menggunakan lebih dari satu bidang data.

   > [!NOTE]
   > Negara/Kawasan adalah wajib di alamat atribut tunggal dan beberapa atribut. Alamat yang tidak berisi nilai negara/kawasan yang valid atau yang didukung tidak akan diperkaya.

1.  Petakan bidang alamat dari entitas pelanggan terpadu Anda.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Halaman pemetaan bidang alamat yang disempurnakan.":::

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Berikan nama untuk pengayaan dan entitas output.

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

## <a name="enrichment-results"></a>Hasil pengayaan

Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah. Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab). Waktu pemrosesan tergantung pada ukuran data pelanggan Anda.

Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan baru yang diperkaya di dalam **pengayaan saya**. Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.

Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.

## <a name="next-steps"></a>Langkah berikutnya

Bangun di atas data pelanggan yang diperkaya. Buat [segmen](segments.md) dan [ukuran](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman pribadi kepada pelanggan Anda.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
