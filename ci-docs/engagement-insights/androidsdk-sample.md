---
title: Sampel SDK Android
description: Contoh proyek untuk mempelajari tentang SDK Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229922"
---
# <a name="run-the-android-sdk-sample"></a>Jalankan sampel SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Proyek sampel Android ini membantu Anda memahami cara kerja SDK dalam aplikasi. Anda tidak harus menulis kode. Cukup tambahkan kunci penyerapan dan Anda dapat langsung melihat aktivitas di ruang kerja.

## <a name="prerequisites"></a>Prasyarat

- [Android Studio](https://developer.android.com/studio)
- [Kunci penyerapan](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Unduh sampel SDK Android

1. [Unduh sampel Android SDK wawasan keterlibatan](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Bongkar zip file terkompresi `ei-android-sample.zip`.
1. Buka folder yang di-zip di Android Studio.
1. Pada file `AndroidManifest.xml`, ganti string `"Your-Ingestion-Key"` dengan kunci penyerapan ruang kerja Anda dari wawasan keterlibatan dalam **Admin** > **Ruang Kerja** > **panduan Penginstalan**. 

   > [!NOTE]
   > Anda tidak perlu mengganti bagian `${applicationId}` tersebut. Ini akan secara otomatis diisi.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Untuk memulai proyek sampel, pilih **Jalankan**.
1. Melihat aktivitas di ruang kerja Anda.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
