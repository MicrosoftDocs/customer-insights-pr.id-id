---
title: Gunakan wawasan audiens untuk memfilter laporan wawasan keterlibatan
description: Gunakan wawasan audiens dalam analisis interaktif mengenai data perilaku yang diambil melalui wawasan keterlibatan di situs web pelanggan.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230490"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Gunakan wawasan audiens untuk memfilter laporan wawasan keterlibatan

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dengan wawasan keterlibatan, Anda dapat menggunakan wawasan audiens dalam analisis interaktif mengenai data perilaku yang diambil melalui wawasan keterlibatan.

## <a name="prerequisite"></a>Prasyarat

- Lingkungan wawasan keterlibatan di mana Anda memiliki data segmen wawasan audiens yang ditautkan ke lingkungan wawasan audiens tempat segmen dan profil pelanggan dibuat. Informasi lebih lanjut, lihat [Membuat tautan antara wawasan audiens dan wawasan keterlibatan](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Membuat segmen wawasan audiens 

> [!IMPORTANT]
> Untuk wawasan audiens yang akan ditampilkan dalam wawasan keterlibatan, Anda harus [menjalankan terlebih dulu proses penggabungan dan hilir](../audience-insights/merge-entities.md). Proses hilir penting karena menghasilkan tabel unik yang menyiapkan segmen wawasan audiens untuk dibagikan dengan wawasan keterlibatan. (Jika refresh sistem dijadwalkan, refresh sistem akan secara otomatis mencakup proses hilir.)

Anda dapat menggunakan segmen wawasan audiens dalam laporan default wawasan keterlibatan atau laporan kustom yang Telah Anda buat. Untuk informasi lebih lanjut, buka [laporan profil default](profile-reports.md) dan [Buat dan edit laporan kustom](custom-reports.md).

**untuk menggunakan wawasan audiens di laporan wawasan keterlibatan**

1. Dari halaman **Ruang Kerja**, pilih **Data**, lalu pilih tab **Segmen**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Pilih tab segmen.":::

   >[!NOTE]
   > Memilih segmen wawasan audiens akan membawa Anda ke wawasan audiens, sehingga Anda dapat mengetahui cara segmen tersebut dibuat dalam hal aturan dan logika. Untuk informasi lebih lanjut tentang segmen wawasan audiens, buka [Lihat dan buat segmen](../audience-insights/segments.md).

2. Pilih laporan default atau [buat laporan kustom](custom-reports.md), lalu pilih **Tambah kondisi**. (Untuk contoh ini, kami memilih laporan **Tampilan halaman**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Tambahkan kondisi.":::

3. Pilih **Filter berdasarkan segmen**, perluas daftar **Jenis segmen**, lalu pilih **Demografis**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Pilih jenis segmen Demografis.":::

4. Perluas daftar **nama segmen**, lalu pilih segmen wawasan audiens.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Pilih segmen.":::

5. Anda dapat menerapkan satu atau beberapa segmen, termasuk segmen perilaku (wawasan keterlibatan) dan demografis (wawasan audiens). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Laporan tampilan halaman dibatasi ke pelanggan Amerika Serikat dan segmen Beranda.":::

Pada gambar sebelumnya, **pelanggan Amerika Serikat** dan segmen **Beranda** telah dipilih, yang membatasi laporan **tampilan Halaman** untuk menampilkan hanya dua segmen tersebut. 


>[!NOTE]
> Anda dapat menggunakan segmen wawasan audiens untuk memfilter laporan default, laporan kustom, dan corong di wawasan keterlibatan. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]