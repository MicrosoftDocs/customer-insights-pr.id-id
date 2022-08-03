---
title: Personalisasi pengalaman Anda dengan data tentang pengguna yang dikenal dan tidak dikenal
description: Gabungkan informasi tentang pengguna yang sebelumnya tidak dikenal ketika Anda mengetahui identitas mereka.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: ff99721bef0004bc8cae1ec14ff9df16cbb0682e
ms.sourcegitcommit: ece8ff732490ecd3b3421ab273f331e6fd46a7f7
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/19/2022
ms.locfileid: "9173818"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Personalisasi pengalaman Anda dengan data tentang pengguna yang dikenal dan tidak dikenal

Mengelola data pelanggan bukanlah tantangan baru, tetapi semakin sulit karena pengguna menavigasi berbagai saluran digital yang ditawarkan merek. Pengguna yang dikenal (diautentikasi) di satu saluran menjadi tidak dikenal (tidak diautentikasi) di saluran lain jika tidak masuk. Masalahnya sering kali adalah bahwa pengguna yang tidak diautentikasi (tidak dikenal) tidak memiliki ID umum. Ini dapat digunakan untuk mengaitkan atribut profil yang bermakna dan menghasilkan profil pelanggan terpadu. Customer Insights membantu memecahkan masalah ini dengan menyerap data dari metode pelacakan pada sistem sumber Anda. Profil terkonsolidasi yang tidak diketahui dan diketahui memberi organisasi tampilan lengkap tentang profil terbaru dan transaksi historis, perilaku, dan demografi mereka. Bahkan melangkah lebih jauh dengan memberikan resolusi identitas yang memungkinkan Anda untuk menyatukan aktivitas pelanggan di berbagai saluran, termasuk situs web Anda, pembelian di dalam toko, program loyalitas, dan sebagainya.

## <a name="sample-scenario"></a>Contoh Skenario

Mari kita pikirkan tentang rantai kopi, yang memiliki basis pelanggan yang luas yang membeli kopi dan makanan di toko-toko dan memesan produk secara online. Seringkali, pengunjung online tidak diautentikasi saat menjelajahi produk, menjadikannya "pengguna yang tidak dikenal". Sulit bagi rantai kopi untuk memberikan penawaran dan pengalaman yang dipersonalisasi jika pengguna tidak dikenal. Di sisi lain, pelanggan dapat masuk ke akun mereka dan menjadi "pengguna yang dikenal" ke perusahaan dengan bergabung dengan sistem loyalitas, yang pada gilirannya memungkinkan pengalaman yang lebih personal. Customer Insights dapat membantu rantai kopi mendapatkan wawasan tentang pengguna yang dikenal dan sebelumnya tidak dikenal.

Dengan Customer Insights, perusahaan dapat menggabungkan profil pelanggan dengan data aktivitas dari sesi yang tidak diautentikasi (tidak diketahui) setelah pengguna masuk dan menjadi dikenal. Rantai kopi dapat membawa data dari sumber data lain menggunakan konektor bawaan ke Customer Insights untuk menggabungkan identitas bagi pelanggan dari berbagai saluran.

## <a name="prerequisites"></a>Prasyarat

- Data web dikumpulkan dan berisi "ID pengunjung" untuk semua pengunjung.
- Data web berisi "ID pengguna yang diautentikasi" untuk pengunjung yang masuk. ID ini terkait dengan sistem loyalitas.
- Data peristiwa bernilai tinggi seperti "Tampilan produk" dan "Checkout" ditentukan dan disertakan dalam data sumber bersama dengan stempel waktu peristiwa dan ID peristiwa.

Tabel berikut menunjukkan contoh yang disederhanakan bagaimana peristiwa web bernilai tinggi dapat ditangkap.

|EventID|EventTimeStamp|UserID|LoyalitasID|Nama Acara|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Tampilan produk|
|2|07-23-2022 10:05:00|abc123|707|Masuk loyalitas|
|3|07-23-2022 10:10:00|abc123|707|Selesai|
|4|07-23-2022 10:20:00|xyz789|--|Tampilan produk|

## <a name="data-ingestion"></a>Penyerapan data

Data tentang pelanggan dapat berasal dari situs web Anda sebagai data peristiwa dan dapat disimpan di layanan analitik data internal atau pihak ketiga Anda sendiri. Data web berisi pengguna yang dikenal dan tidak dikenal jika situs web memiliki alur autentikasi yang terintegrasi dengan layanan autentikasi. Misalnya, sistem eCommerce yang mengharuskan pengguna untuk memberikan detail lengkap mereka untuk menyelesaikan transaksi pembelian. Atau sistem loyalitas yang memerlukan autentikasi untuk mengonfirmasi penerima diskon hadiah yang valid.

Data peristiwa dalam contoh kami di atas berisi ID profil yang berbeda dari pengguna yang dikenal dan tidak dikenal. Dalam hal 1 dan 4, pengguna tidak dikenal saat dalam acara 2 dan 3 pengguna dengan ID abc123 mendaftar ke program loyalitas.

:::image type="content" source="media/website-data-source.png" alt-text="Sumber data termasuk situs web Contoso.":::

Untuk informasi selengkapnya tentang opsi yang tersedia untuk penyerapan data, lihat [Gambaran umum sumber data](data-sources.md).

## <a name="data-unification"></a>Penyatuan data

Menyatukan identitas yang tidak dikenal dengan identitas yang diketahui membantu memungkinkan personalisasi berdasarkan perilaku pengguna, terlepas dari status profil mereka (diketahui atau tidak diketahui). Konten yang dipersonalisasi untuk semua pengguna membantu pelanggan dengan cepat mendapatkan produk atau layanan paling relevan yang mereka minati saat itu.

Karena beberapa pengguna dalam data kami diketahui, kami dapat menggunakan Customer Insights untuk menggabungkan data tersebut dengan profil pengguna. Untuk informasi selengkapnya tentang menyatukan profil pelanggan, lihat [Gambaran umum penyatuan data](data-unification.md).

1. Pilih bidang sumber dari entitas data web. Gunakan data profil yang disimpan dalam data web Anda dan pilih bidang yang mewakili Id dengan data demografis.

   :::image type="content" source="media/website-source-fields.png" alt-text="Bidang sumber untuk sumber data web.":::

1. Tambahkan aturan untuk menggabungkan rekaman duplikat. Untuk data web, pilih data yang paling banyak diisi.

1. Konfigurasikan aturan dan kondisi kecocokan. Data peristiwa profil web dalam contoh ini akan dicocokkan pada ID dengan profil dari sumber data lain yang berisi informasi pelanggan. Siapkan aturan pencocokan persis pada ID sebagai aturan terpisah dengan masing-masing entitas profil lain yang memiliki kunci utama atau kecocokan ID yang sesuai. Dalam contoh, data profil peristiwa web digunakan sebagai entitas pencocokan terakhir sehingga data profil lainnya digabungkan terlebih dahulu.
   1. Tidak mencentang **Sertakan semua catatan** membuat profil terpadu untuk pengguna yang dikenal dan menyertakan ID pengguna tidak dikenal yang sesuai. Ini sangat membantu dalam skenario ketika Anda tertarik untuk melihat aktivitas perilaku masa lalu dari pengguna yang dikenal ketika mereka masih belum diketahui.
   1. Mencentang **Sertakan Semua catatan** akan membuat catatan profil terpisah untuk pengguna yang tidak dikenal. Pengguna tidak dikenal mendapatkan ID pelanggan yang unik. Di masa depan ketika profil yang diketahui dikaitkan dalam data profil peristiwa web, maka perjalanan pengguna yang baru dikenal dapat dilihat dan digunakan untuk personalisasi berdasarkan data perilaku yang tidak diketahui sebelumnya juga.

:::image type="content" source="media/website-match-rule.png" alt-text="Aturan pertandingan untuk entitas sumber data situs web.":::

## <a name="get-insights"></a>Dapatkan wawasan

Jika profil pelanggan dibuat untuk pengguna yang tidak dikenal dan dikenal, data peristiwa web bernilai tinggi dapat digunakan sebagai [aktivitas](activities.md). Kegiatan ini dapat digunakan untuk menciptakan lebih banyak wawasan. Misalnya, pelanggan yang mengunjungi situs web enam bulan lalu (ketika mereka masih belum dikenal) atau pelanggan yang tidak memiliki ID loyalitas tidak pernah menyelesaikan checkout.

:::image type="content" source="media/website-known-unknown.png" alt-text="Cuplikan layar halaman pelanggan dengan pelanggan yang dikenal dan tidak dikenal.":::

[Perkaya](enrichment-hub.md) data Anda, buat [langkah-langkah](measures.md), dan buat [segmen](segments.md) untuk aktivasi lebih lanjut.

Misalnya, Anda dapat membuat segmen pengguna yang dikenal yang melihat beberapa produk tetapi tidak pernah menyelesaikan checkout.

Untuk informasi selengkapnya, lihat [Gambaran umum segmen](segments.md).

## <a name="activate-insights"></a>Aktifkan wawasan

Ada beberapa cara untuk mengekspor data Anda dan mengambil tindakan berdasarkan wawasan yang mendasarinya.

Untuk informasi selengkapnya, lihat [Gambaran umum ekspor](export-destinations.md).
