---
title: Menggunakan dimensi demografis untuk memecah data perilaku (dimensi pilihan)
description: Gunakan dimensi pilihan profil terpadu untuk mengaktifkan properti profil pelanggan wawasan audiens.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8a3d7f9276330a6daacbe9428d84a371b81bbefe
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466352"
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
