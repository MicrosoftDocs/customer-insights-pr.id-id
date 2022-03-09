---
title: Peningkatan data perusahaan
description: Memperkaya dan menormalkan data perusahaan dengan model Microsoft.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7a576621c71b925bd1563827aca10cad4ef9b4eb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229407"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Pengayaan profil perusahaan dengan data perusahaan yang disempurnakan

Gunakan model Microsoft dan data perusahaan yang dikompilasi untuk memperbaiki, melengkapi, dan menstandardisasi profil perusahaan Anda. Kami akan menggunakan [format](/common-data-model/schema/core/applicationcommon/account) Common Data Model untuk akurasi dan wawasan yang lebih baik.

## <a name="how-we-enhance-company-data"></a>Bagaimana kami meningkatkan data perusahaan

Model kami melalui proses dua langkah untuk meningkatkan profil perusahaan. Pertama, menormalkan nama perusahaan. Misalnya, *Microsoft Corp* akan diperbaiki dan distandarisasi ke *Microsoft Corporation*. Ini mencoba untuk menemukan kecocokan dalam data perusahaan Microsoft yang dikompilasi. Jika kecocokan ditemukan, kami memperkaya profil perusahaan dengan informasi dari data perusahaan kami yang dikompilasi, termasuk nama perusahaan.


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

Ada beberapa batasan dengan data yang disempurnakan. Item dalam daftar di bawah ini tidak didukung oleh model.

1.  Konfirmasi identitas perusahaan. Kami tidak memverifikasi apakah input adalah organisasi yang ada atau bahwa perusahaan menggunakan output sebagai nama standarnya.
2.  Secara komprehensif mencakup perusahaan secara global. Data perusahaan Microsoft yang dikompilasi memiliki cakupan global, tetapi menawarkan sebagian besar cakupan di Australia, Kanada, Inggris, dan Amerika Serikat.
3.  Standarisasi alamat perusahaan secara global. Saat ini kami mendukung standarisasi alamat di negara atau wilayah tersebut: Australia, Kanada, Prancis, Jerman, Italia, Jepang, Inggris, dan Amerika Serikat.
4.  Menjamin keakuratan atau kesegaran data. Karena informasi bisnis sering berubah, kami tidak dapat menjamin bahwa data perusahaan yang disempurnakan yang diberikan selalu tepat atau terkini.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka **Data** > **Pengayaan**.

1. Pilih **Perkaya data** saya pada ubin data **perusahaan yang** disempurnakan.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Ubin pengayaan di hub pengayaan untuk data perusahaan.":::

1. Pilih **himpunan data Pelanggan** dan pilih entitas berisi alamat yang akan diperkaya. Anda dapat memilih entitas *Pelanggan* untuk memperkaya alamat di semua profil pelanggan atau memilih entitas segmen untuk memperkaya alamat hanya dalam profil pelanggan yang terdapat dalam segmen tersebut.

1. Pilih jenis bidang dari profil perusahaan Anda yang harus digunakan untuk pencocokan dengan data perusahaan yang dikompilasi Microsoft. Pilihan ini akan memengaruhi bidang pemetaan yang dapat Anda akses di langkah berikutnya.

1.  Petakan bidang perusahaan dari entitas pelanggan terpadu Anda. Semakin banyak pengidentifikasi dan bidang utama yang Anda petakan, semakin besar kemungkinan tingkat kecocokan yang lebih tinggi.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Langkah pemetaan data saat mengonfigurasi pengayaan perusahaan.":::

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Berikan nama untuk pengayaan dan entitas output.

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

## <a name="enrichment-results"></a>Hasil pengayaan

Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah. Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab). Waktu pemrosesan tergantung pada ukuran data pelanggan Anda.

Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan baru yang diperkaya di dalam **pengayaan saya**. Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.

Anda dapat melihat sampel data yang diperkaya di **ubin pratinjau** pelanggan yang diperkaya. Pilih **Lihat selengkapnya** **dan pilih tab Data** untuk mengakses tampilan terperinci dari setiap profil yang diperkaya.

### <a name="overview-card"></a>Kartu Gambaran Umum

Kartu ikhtisar menunjukkan detail tentang cakupan pengayaan. 

* **Perusahaan diproses dan diubah**: Jumlah profil perusahaan pelanggan yang berhasil diperkaya.

* **Perusahaan diproses dan tidak berubah**: Jumlah profil perusahaan pelanggan yang diakui tetapi tidak berubah. Ini biasanya terjadi ketika data input valid dan tidak dapat ditingkatkan dengan pengayaan.

* **Perusahaan tidak diproses dan tidak berubah**: Jumlah profil perusahaan pelanggan yang tidak diakui. Ini biasanya terjadi untuk data input yang tidak valid atau tidak didukung oleh pengayaan.

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
