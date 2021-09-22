---
title: Jalankan sampel SDK iOS
description: Contoh proyek untuk mempelajari tentang SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036832"
---
# <a name="run-the-ios-sdk-sample"></a>Jalankan sampel SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Proyek sampel iOS ini membantu Anda memahami cara kerja SDK dalam aplikasi. Anda tidak harus menulis kode. Cukup tambahkan kunci penyerapan dan Anda dapat langsung melihat aktivitas di ruang kerja.

## <a name="prerequisites"></a>Prasyarat

- [Xcode versi 9+](https://developer.apple.com/xcode/downloads/)
- [Kunci penyerapan](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Unduh sampel SDK iOS

1. [Unduh sampel SDK iOS wawasan keterlibatan](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Bongkar zip file terkompresi `ei-ios-sample.zip`.
1. Buka proyek aplikasi sampel di Xcode.
1. Pada file `EIConfig.plist`, ganti string `“YOUR-INGESTION-KEY”` di bidang `ingestionKey` dengan kunci penyerapan ruang kerja Anda dari wawasan keterlibatan dalam **Admin** > **Ruang Kerja** > **panduan Penginstalan**.
1. Untuk memulai proyek sampel, pilih **Jalankan**.
1. Melihat aktivitas di ruang kerja Anda.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
