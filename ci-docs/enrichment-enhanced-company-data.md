---
title: Perkaya profil perusahaan dengan data perusahaan yang disempurnakan
description: Perkaya dan normalkan data perusahaan dengan model Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 131ef3d1e123628779609ddec368cfef8f4d607e
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054252"
---
# <a name="enrich-company-profiles-with-enhanced-company-data"></a>Perkaya profil perusahaan dengan data perusahaan yang disempurnakan

Gunakan model Microsoft dan data perusahaan yang dikumpulkan untuk memperbaiki, melengkapi, dan menstandarkan profil perusahaan Anda. Kami akan menggunakan [format](/common-data-model/schema/core/applicationcommon/account) Common Data Model untuk akurasi dan wawasan yang lebih baik.

Anda juga [dapat meningkatkan data perusahaan pada sumber](data-sources-enrichment.md) data untuk meningkatkan akurasi kecocokan dalam proses penyatuan data.

Untuk perusahaan publik di Amerika Serikat, informasi seperti pendapatan, ticker saham, industri, dan lainnya tersedia.  

## <a name="how-we-enhance-company-data"></a>Cara kami meningkatkan data perusahaan

Model kami melalui proses dua langkah untuk meningkatkan profil perusahaan. Pertama, menormalkan nama perusahaan. Misalnya, *Microsoft Corp* akan dikoreksi dan distandarisasi ke *Microsoft Corporation*. Ini mencoba menemukan kecocokan dalam data perusahaan yang dikompilasi Microsoft. Jika ditemukan kecocokan, kami memperkaya profil perusahaan dengan informasi dari data perusahaan yang kami kumpulkan, termasuk nama perusahaan.

### <a name="example"></a>Contoh

Informasi perusahaan Anda mungkin tidak mengikuti format standar dan berisi kesalahan ejaan. Model mencoba memperbaiki masalah ini dan membuat informasi yang konsisten.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Pembatasan

Model tidak:

- Konfirmasikan identitas perusahaan. Kami tidak memverifikasi apakah input tersebut adalah organisasi yang sudah ada atau bahwa perusahaan menggunakan output sebagai nama standarnya.
- Secara komprehensif mencakup perusahaan secara global. Data perusahaan yang dikumpulkan Microsoft memiliki cakupan global, tetapi menawarkan sebagian besar cakupan di Australia, Kanada, Inggris, dan Amerika Serikat.
- Standarisasi alamat perusahaan secara global. Saat ini kami mendukung standarisasi alamat di negara atau wilayah ini: Australia, Kanada, Prancis, Jerman, Italia, Jepang, Inggris, dan Amerika Serikat.
- Menjamin akurasi atau kesegaran data. Karena informasi bisnis sering berubah, kami tidak dapat menjamin bahwa data perusahaan yang ditingkatkan yang diberikan selalu tepat atau terkini.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data** saya di petak **peta Data** perusahaan yang disempurnakan.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Petak pengayaan di hub pengayaan untuk data perusahaan.":::

1. Tinjau gambaran umum lalu pilih **Berikutnya**.

1. **Pilih himpunan data** Pelanggan dan pilih profil atau segmen yang ingin Anda perkaya. Entitas Pelanggan *memperkaya semua profil pelanggan Anda sedangkan segmen hanya memperkaya profil pelanggan yang terkandung dalam segmen tersebut*.

1. Pilih jenis bidang mana dari profil perusahaan Anda yang akan digunakan untuk pencocokan dengan data perusahaan yang dikumpulkan Microsoft. Pilihan ini akan memengaruhi bidang pemetaan yang dapat Anda akses di langkah berikutnya.

1. Pilih **Selanjutnya**.

1. Petakan bidang perusahaan Anda ke data perusahaan dari Microsoft. Untuk akurasi kecocokan yang lebih tinggi, tambahkan lebih banyak bidang.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Langkah pemetaan data saat mengonfigurasi pengayaan perusahaan.":::

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Berikan **Nama** untuk pengayaan dan **entitas** Output.

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

1. Pilih **Jalankan** untuk memulai proses pengayaan atau tutup untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Kartu gambaran umum

Petak **gambaran umum** Perubahan pelanggan memperlihatkan detail tentang cakupan pengayaan

- **Perusahaan diproses dan diubah**: Jumlah profil perusahaan pelanggan yang berhasil diperkaya.
- **Perusahaan diproses dan tidak berubah**: Jumlah profil perusahaan pelanggan yang diakui tetapi tidak berubah. Ini biasanya terjadi ketika data input valid dan tidak dapat ditingkatkan dengan pengayaan.
- **Perusahaan tidak diproses dan tidak diubah**: Jumlah profil perusahaan pelanggan yang tidak dikenali. Ini biasanya terjadi untuk data input yang tidak valid atau tidak didukung oleh pengayaan.

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
