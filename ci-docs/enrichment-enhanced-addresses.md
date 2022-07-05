---
title: Perkaya profil pelanggan dengan alamat yang disempurnakan (berisi video)
description: Perkaya dan normalisasi informasi alamat profil pelanggan dengan model Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082072"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Perkaya profil pelanggan dengan alamat yang disempurnakan

Alamat pada data dapat tidak terstruktur, tidak lengkap, atau salah. Gunakan model Microsoft untuk menormalkan dan memperkaya alamat Anda ke dalam [format Common Data Model](/common-data-model/schema/core/applicationcommon/address) untuk keakuratan dan wawasan yang lebih baik.

Anda juga [dapat memperkaya alamat pada sumber](data-sources-enrichment.md) data untuk meningkatkan akurasi kecocokan dalam proses penyatuan data. 

## <a name="how-we-enhance-addresses"></a>Cara kami meningkatkan alamat

Model kami melalui proses dua langkah untuk meningkatkan alamat. Pertama, ia mengurai alamat untuk mengidentifikasi komponennya dan memasukkannya ke dalam format terstruktur. Selanjutnya, kami akan menggunakan AI untuk mengoreksi, menyelesaikan, dan membuat standar nilai di alamat.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

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

Alamat yang disempurnakan hanya berfungsi dengan nilai yang sudah ada di data alamat yang Anda konsumsi. Model tidak:

1. Memverifikasikan apakah alamat tersebut adalah alamat yang valid.
2. Memverifikasikan apakah salah satu nilai, seperti kode ZIP atau nama jalan, valid.
3. Mengubah nilai yang tidak dikenali.

Model menggunakan teknik berbasis pembelajaran mesin untuk meningkatkan alamat. Seperti halnya model berbasis pembelajaran mesin lainnya, akurasi 100 persen tidak dijamin.

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

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data saya** pada ubin **Alamat yang disempurnakan**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Tangkapan layar ubin Alamat yang Disempurnakan.":::

1. Tinjau gambaran umum lalu pilih **Berikutnya**.

1. **Pilih himpunan data** Pelanggan dan pilih profil atau segmen yang ingin Anda perkaya. Entitas Pelanggan *memperkaya semua profil pelanggan Anda sedangkan segmen hanya memperkaya profil pelanggan yang terkandung dalam segmen tersebut*.

1. Pilih format alamat dalam himpunan data Anda. Pilih **Alamat atribut tunggal** jika alamat di data Anda menggunakan satu bidang. Pilih **Beberapa atribut Alamat** jika alamat di data Anda menggunakan lebih dari satu bidang data.

1. Pilih **Berikutnya** dan petakan bidang alamat dari entitas pelanggan terpadu Anda.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Halaman pemetaan bidang alamat yang disempurnakan.":::

   > [!NOTE]
   > Negara/Kawasan adalah wajib di alamat atribut tunggal dan beberapa atribut. Alamat yang tidak berisi nilai negara/kawasan yang valid atau yang didukung tidak akan diperkaya.

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Berikan **Nama** untuk pengayaan dan **entitas** Output.

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Jumlah **pelanggan yang diperkaya oleh lapangan** memberikan penelusuran ke dalam cakupan setiap bidang yang diperkaya.

### <a name="overview-card"></a>Kartu gambaran umum

Kartu **ikhtisar** perubahan Pelanggan menunjukkan detail tentang cakupan pengayaan:

- **Alamat diproses dan diubah**: Jumlah profil pelanggan dengan alamat yang berhasil diperkaya.
- **Alamat diproses dan tidak diubah**: Jumlah profil pelanggan dengan alamat yang dikenali tetapi tidak diubah. Ini biasanya terjadi ketika data input valid dan tidak dapat ditingkatkan dengan pengayaan.
- **Alamat tidak diproses dan tidak diubah**: Jumlah profil dengan alamat yang tidak dikenali. Biasanya untuk input data yang tidak valid atau tidak didukung oleh pengayaan tersebut.

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
