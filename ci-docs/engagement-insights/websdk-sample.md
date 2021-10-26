---
title: Menjalankan sampel SDK web
description: Pelajari cara mempersonalisasikan dan menjalankan sampel SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606225"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Jalankan sampel SDK web untuk kemampuan wawasan keterlibatan Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Pustaka SDK web kemampuan wawasan keterlibatan adalah pustaka JavaScript dengan kode sampel yang dapat Anda gunakan di situs web Anda.

## <a name="prerequisites"></a>Prasyarat

- Instal [Kode Visual Studio](https://code.visualstudio.com/).
- [Instal ekstensi Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) dalam Kode Visual Studio dan kenali cara menjalankan Live Server.
- Anda harus memiliki [ruang kerja wawasan keterlibatan](create-workspace.md).

## <a name="run-sample"></a>Jalankan sampel

1. [Unduh sampel SDK web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Bongkar zip file terkompresi `ei_websdk_sample.zip`.

1. Buka folder yang di-zip dari Code Visual Studio.

1. Buka portal wawasan keterlibatan untuk ruang kerja Anda. Pilih **admin** > **Ruang Kerja**  lalu **Panduan penginstalan**. Ikuti pilihan pertama, lalu pilih **Salin kode** untuk menyalin cuplikan kode JavaScript.

1. Di file `ei_websdk_sample.html`, rekatkan cuplikan kode yang baru saja Anda salin di bawah baris ini:

   - <-- REKATKAN CUPlIKAN KODE JAVASCRIPT DARI PORTAL WAWASAN KETERLIBATAN DI BAWAH BARIS INI -->

1. Buka file `ei_websdk_sample.html` menggunakan Live Server in Code Visual Studio dengan memilih **Tayangkan Langsung** dari bilah status.

1. Saat membuka halaman, aktivitas melihat harus dikirim secara otomatis. Mengklik salah satu tombol pada halaman akan mengirim aktivitas tindakan. Tombol **Lacak Aktivitas** juga akan mengirim aktivitas kustom. Memilih tombol **Buka Bing** akan mengirim aktivitas tindakan sebelum menavigasi ke situs web Bing.

1. Lihat aliran aktivitas saat Anda menavigasi ke ruang kerja Anda. Ruang kerja ini dikaitkan dengan kunci penyerapan pada Langkah 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
