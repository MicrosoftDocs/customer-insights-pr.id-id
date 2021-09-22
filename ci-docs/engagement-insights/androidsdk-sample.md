---
title: Sampel SDK Android
description: Contoh proyek untuk mempelajari tentang SDK Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035830"
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
