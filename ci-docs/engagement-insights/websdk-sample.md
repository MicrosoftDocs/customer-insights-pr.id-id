---
title: Menjalankan sampel SDK web
description: Pelajari cara mempersonalisasikan dan menjalankan sampel SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225335"
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
