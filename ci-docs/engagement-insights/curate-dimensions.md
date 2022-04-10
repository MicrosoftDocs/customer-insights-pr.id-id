---
title: Menggunakan dimensi demografis untuk memecah data perilaku (dimensi pilihan)
description: Gunakan dimensi pilihan profil terpadu untuk mengaktifkan properti profil pelanggan wawasan audiens.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8233051"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Menggunakan dimensi demografis untuk memecah data perilaku

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dengan menggunakan dimensi metrik profil terpadu, pengguna wawasan keterlibatan dapat mengakses properti profil wawasan audiens. Selanjutnya Anda dapat menggunakan properti ini dalam analisis interaktif data perilaku, termasuk data yang diambil melalui wawasan keterlibatan di situs web atau aplikasi seluler Anda.

>[!NOTE]
> Wawasan keterlibatan mencakup dimensi standar untuk properti aktivitas. Informasi selengkapnya: [Melihat dan membuat dimensi](dimensions.md)

## <a name="prerequisite"></a>Prasyarat

- Lingkungan wawasan keterlibatan dengan data profil pelanggan Anda yang ditautkan ke lingkungan wawasan audiens tempat profil pelanggan dibuat. Informasi lebih lanjut, lihat [Membuat tautan antara wawasan audiens dan wawasan keterlibatan](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Setelah membuat tautan antara lingkungan audiens dan wawasan keterlibatan, Anda hanya memerlukan data khusus untuk properti profil pelanggan yang dapat berguna sebagai dimensi dalam wawasan keterlibatan. Untuk informasi lebih lanjut, buka [Aktifkan atribut dan segmen profil terpadu wawasan audiens](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Buat laporan baru kustom

1. Pada panel kiri, pilih **Kustom** > **laporan Baru**, lalu pilih metrik yang diinginkan. (Untuk contoh ini, kami memilih **Tampilan halaman berdasarkan Jam**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Pilih sebuah metrik.":::

2. Di editor Visualisasi, pilih **Dimensi**, lalu pilih **Demografis** dalam menu dropdown **Jenis Dimensi**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Pilih demografis.":::

3. Pilih dimensi **Signal.Customer.*xxx***. (Contoh ini menunjukkan Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Pilih dimensi.":::
  
## <a name="limitations"></a>Pembatasan

Saat ini Anda hanya menggunakan dimensi demografis untuk memecah data perilaku.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
