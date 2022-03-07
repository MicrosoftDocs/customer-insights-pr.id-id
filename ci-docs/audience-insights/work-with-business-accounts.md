---
title: Memulai akun bisnis sebagai audiens target utama
description: Pelajari tentang akun bisnis sebagai audiens target utama Dynamics 365 Customer Insights.
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
ms.openlocfilehash: 88882dc727c37262c9f204fbc8049abe17bd21a3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353547"
---
# <a name="work-with-business-accounts-in-audience-insights"></a>Bekerja dengan akun bisnis di wawasan audiens

Kemampuan audiens di Dynamics 365 Customer Insights memungkinkan Anda mengkonfigurasi lingkungan untuk audiens target utama yang berbeda: konsumen perorangan (B to C) dan akun bisnis (B to B). Dalam skenario B to C, data dipusatkan di sekitar individu. Untuk B to B, target utama audiens adalah akun - organisasi atau perusahaan - dan kontak. Artikel ini membantu Anda memulai lingkungan untuk akun bisnis. Fitur ini mencantumkan perbedaan untuk area fitur dalam wawasan audiens Anda, tergantung pada fokus lingkungan Anda. Untuk informasi lebih lanjut tentang perbedaan, lihat dokumen area fitur. 

## <a name="create-an-environment-for-business-accounts"></a>Membuat lingkungan untuk akun bisnis

Administrator dapat [membuat lingkungan di organisasi yang ada](create-environment.md). Langkah dalam proses pembuatan lingkungan baru akan meminta administrator untuk audiens target utama lingkungan. Jika ini merupakan konfigurasi awal wawasan audiens setelah membeli lisensi, pengalaman terpandu akan membantu pembuatan lingkungan pertama.

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

