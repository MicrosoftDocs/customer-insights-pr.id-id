---
title: Menangani akun bisnis
description: Pelajari tentang akun bisnis sebagai target utama audiens di Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: 9bf91671b744198b2f37391edc7abf58eca3c820
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053117"
---
# <a name="work-with-business-accounts"></a>Menangani akun bisnis

Ini Dynamics 365 Customer Insights memungkinkan Anda mengonfigurasi lingkungan Anda untuk audiens target utama yang berbeda: konsumen individu (B-to-C) dan akun bisnis (B-to-B). Dalam skenario B to C, data dipusatkan di sekitar individu. Untuk B to B, target utama audiens adalah akun - organisasi atau perusahaan - dan kontak. Artikel ini membantu Anda memulai lingkungan untuk akun bisnis. Ini mencantumkan perbedaan untuk area fitur di Customer Insights, tergantung pada fokus lingkungan Anda. Untuk informasi lebih lanjut tentang perbedaan, lihat dokumen area fitur. 

## <a name="create-an-environment-for-business-accounts"></a>Membuat lingkungan untuk akun bisnis

Administrator dapat [membuat lingkungan di organisasi yang ada](create-environment.md). Langkah dalam proses pembuatan lingkungan baru akan meminta administrator untuk audiens target utama lingkungan. Jika ini adalah pengaturan awal setelah membeli lisensi, pengalaman terpandu membantu menciptakan lingkungan pertama.

Selanjutnya Anda [menyerap data](data-sources.md) untuk akun bisnis dan kontak terkait sebagai sumber data dari semua sumber yang didukung.

Setelah menyatukan data, [tentukan hierarki akun](relationships.md#set-up-account-hierarchies) sebagai bagian dari konfigurasi relasi. Anda juga dapat [mengkonfigurasi pemetaan semantis](semantic-mappings.md) untuk menghubungkan entitas kontak dan akun. 

## <a name="switch-between-primary-target-audience"></a>Beralih di antara target audiens utama

Jika organisasi Anda memelihara lingkungan untuk pelanggan perorangan dan akun bisnis, Anda dapat menggunakan pengalih di panel kiri untuk memilih audiens target utama.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Pengalih untuk mengubah audiens target utama antara pelanggan individual dan akun bisnis.":::

## <a name="supported-feature-areas"></a>Area Fitur yang didukung

- [Aktivitas](activities.md): Dukungan untuk akun dan kontak terkait untuk membuat aktivitas dan menampilkannya di timeline.
- [Relasi](relationships.md): Wizard aktivitas membantu Relasi antara entitas sehingga tampilan akun dapat menampilkan semua aktivitas dari kontak. Kontak dapat menelusuri hingga detail untuk melihat tampilan kontak dan hierarki dapat digunakan untuk agregasi aktivitas akun.
- [ukuran](measures.md): Mendukung ukuran yang dibuat dari pembuat ukuran dengan satu perhitungan. Pengaturan opsional memungkinkan roll-up untuk sub-akun saat membuat pengukuran.
- [Segmen](segments.md): Mendukung segmen yang dibuat dari awal dengan pembuat segmen. Operator baru memungkinkan penggabungan hierarki akun saat membangun segmen.
- [Penyerapan data](data-sources.md): Semua fitur di area ini sama untuk akun bisnis dan pelanggan individual.
- [Penyatuan data](data-unification.md): Semua fitur di area ini sama untuk akun bisnis dan pelanggan individual.
- [Pengayaan](enrichment-hub.md): Beberapa jenis pengayaan hanya tersedia untuk skenario pelanggan individual, sedangkan lainnya tersedia secara eksklusif untuk akun bisnis.
- [Model prediksi dan bawaan](predictions-overview.md): prediksi kehilangan transaksi berisi langkah-langkah tambahan untuk akun bisnis. Prediksi lainnya hanya tersedia untuk pelanggan individual.
- [Aktivasi dan ekspor](export-destinations.md): Ekspor tersedia untuk akun bisnis dan pelanggan individual. Sejumlah ekspor memerlukan konfigurasi tambahan dan informasi kontak yang diproyeksikan dalam segmen dasar agar valid untuk akun bisnis.
- [Pengaturan sistem](system.md) dan [manajemen pengguna](permissions.md): Semua fitur di area ini sama untuk akun bisnis dan pelanggan individual.

