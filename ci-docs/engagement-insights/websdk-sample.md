---
title: Menjalankan sampel SDK web
description: Pelajari cara mempersonalisasikan dan menjalankan sampel SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036607"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Jalankan sampel SDK web untuk kemampuan wawasan keterlibatan Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Pustaka SDK web kemampuan wawasan keterlibatan adalah pustaka JavaScript dengan kode sampel yang dapat Anda gunakan di situs web Anda.

## <a name="prerequisites"></a>Prasyarat

- Instal [Kode Visual Studio](https://code.visualstudio.com/).
- [Instal ekstensi Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) dalam Kode Visual Studio dan kenali cara menjalankan Live Server.
- Anda harus memiliki [kunci penyerapan](instrument-website.md).

## <a name="run-sample"></a>Jalankan sampel

1. [Unduh sampel SDK web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Bongkar zip file terkompresi `ei_websdk_sample.zip`.

1. Buka folder yang di-zip dari Code Visual Studio.

1. Di file `ei_websdk_sample.html`, ganti string "INGESTION_KEY" dengan kunci penyerapan dari portal kemampuan wawasan keterlibatan, dan string "NAME" dengan nama global yang diinginkan agar SDK dipakai di dalamnya. Pastikan Anda mengganti semua kejadian.

1. Buka file `ei_websdk_sample.html` menggunakan Live Server in Code Visual Studio dengan memilih **Tayangkan Langsung** dari bilah status.

1. Saat membuka halaman, aktivitas melihat harus dikirim secara otomatis. Mengklik salah satu tombol pada halaman akan mengirim aktivitas tindakan. Tombol **Lacak Aktivitas** juga akan mengirim aktivitas kustom. Memilih tombol **Buka Bing** akan mengirim aktivitas tindakan sebelum menavigasi ke situs web Bing.

1. Lihat aliran aktivitas saat Anda menavigasi ke ruang kerja Anda. Ruang kerja ini dikaitkan dengan kunci penyerapan pada Langkah 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]