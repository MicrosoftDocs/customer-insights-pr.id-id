---
title: Memulai SDK iOS
description: Pelajari cara mempersonalkan dan menjalankan SDK iOS
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 879a71175a2e7d44a54d25fd8efb9f12927cea5a
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977527"
---
# <a name="get-started-with-the-ios-sdk"></a>Memulai SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tutorial ini akan memandu Anda melalui instrumentasi aplikasi iOS dengan SDK wawasan keterlibatan Dynamics 365 Customer Insights. Anda akan mulai melihat aktivitas di portal dalam lima menit atau lebih cepat.

## <a name="configuration-options"></a>Pilihan Konfigurasi

Pilihan konfigurasi berikut dapat diteruskan ke SDK melalui file `EIConfig.plist` yang diberikan:

- **ingestionKey**: Kunci penyerapan digunakan untuk mengirim aktivitas ke proyek Anda.
- **autocollectAction**: Nilai Boolean untuk mengaktifkan atau menonaktifkan auto-instrumentasi aktivitas tindakan.
- **autocollectView**: Nilai Boolean untuk mengaktifkan atau menonaktifkan auto-instrumentasi aktivitas tampilan.
- **endpointUrl**: Titik akhir URL tempat aktivitas akan diarahkan.

## <a name="prerequisites"></a>Prasyarat

- Xcode versi 9+
- iOS versi 8.2+
- Tombol penyerapan (lihat di bawah ini untuk mendapatkan)

## <a name="integrate-the-sdk-into-your-application"></a>Mengintegrasikan SDK ke aplikasi Anda

Mulai proses dengan memilih ruang kerja untuk bekerja, memilih platform seluler iOS, dan mengunduh SDK.

- Gunakan switcher ruang kerja di panel navigasi kiri untuk memilih ruang kerja Anda.

- Jika Anda tidak memiliki ruang kerja yang lama, pilih  **Ruang Kerja Baru**, lalu ikuti langkah-langkah untuk membuat [ruang kerja baru](create-workspace.md).

- Setelah membuat ruang kerja, buka **Admin** > **Ruang Kerja**, lalu pilih **Panduan penginstalan**.

## <a name="configure-the-sdk"></a>Mengonfigurasi SDK

Setelah mengunduh SDK, Anda dapat menggunakannya di Xcode untuk mengaktifkan dan mendefinisikan aktivitas. Ada dua cara untuk melakukannya

### <a name="option-1-using-cocoapods-recommended"></a>Pilihan 1: Menggunakan CocoaPods (disarankan)
CocoaPods adalah manajer dependensi untuk proyek Swift dan Objective-C Cocoa. Penggunaannya akan memudahkan mengintegrasikan SDK wawasan keterlibatan untuk iOS. CocoaPods juga memungkinkan Anda meningkatkan ke SDK wawasan keterlibatan versi terbaru. Berikut adalah cara menggunakan CocoaPods untuk mengintegrasikan SDK wawasan keterlibatan ke dalam proyek Xcode Anda. 

1. Menginstal CocoaPods. 

1. Buat file baru bernama Podfile di dalam direktori root proyek Anda dan tambahkan pernyataan berikut ke dalamnya. Ganti YOUR_TARGET_PROJECT_NAME dengan nama proyek Xcode Anda. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Konfigurasi pod di atas berisi versi debug dan rilis SDK. Pilih mana yang terbaik untuk proyek Anda.

1. Instal pod dengan menjalankan perintah berikut: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Pilihan 2: Menggunakan tautan unduhan

1. Unduh [SDK iOS wawasan keterlibatan](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip), dan letakkan file `EIObjC.xcframework` dalam folder `Frameworks`.

1. Jika folder `Frameworks` tidak ada, buat folder dalam folder proyek.

## <a name="enable-auto-instrumentation"></a>Aktifkan instrumentasi otomatis
 
Anda dapat mengaktifkan instrumentasi otomatis dengan mudah tanpa pengkodean. Saat proyek berjalan, proyek akan secara otomatis melacak aktivitas `view` dan `action` menggunakan kunci penyerapan yang dikonfigurasi. 

1. Perbarui dan sertakan file `EIConfig.plist` yang diberikan dalam folder direktori proyek untuk bidang berikut:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = YES
    - autocollectAction = YES

2. Kemudian tambahkan file `EIConfig.plist` ke proyek Anda di Xcode. 



Perbarui Bidang Berikut ini Dalam file `EIConfig.plist` yang diberikan dalam folder direktori proyek Anda untuk menonaktifkan instrumentasi otomatis. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Menerapkan aktivitas kustom

1. Buka proyek Anda dalam Xcode, dan navigasi ke pengaturan **Umum**. 
1. Tambahkan ke proyek `EIObjC.xcframework` dalam bagian 'Kerangka Kerja, Pustaka, dan Konten Tertanam'.

1. Impor file header kerangka kerja di AppDelegate.m dengan cuplikan berikut:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inisialisasi SDK wawasan keterlibatan dari application: didFinishLaunchingWithOptions.
1. Salin cuplikan XML dari **panduan Penginstalan**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Lacak aktivitas:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Mengatur rincian pengguna untuk aktivitas Anda

SDK memungkinkan Anda menentukan informasi pengguna yang dapat dikirim dengan setiap aktivitas. Anda dapat menentukan informasi pengguna dengan menghubungi API `setUser:(nonnull EIUser *)user` pada SDK.

Menentukan rincian pengguna di tingkat `Analytics` berarti semua telemetri akan memiliki informasi ini. Namun, jika Anda menentukan pada tingkat aktivitas dengan menghubungi API `setUser:(nonnull EIUser *)user` pada objek EIEvent, hanya aktivitas tertentu itu yang akan berisi informasi.

Kelas data `EIUser` berisi properti string NSString berikut:

- **localId**: ID lokal pengguna.
- **authId**: ID pengguna terotentikasi.
- **authType**: Jenis otentikasi yang digunakan untuk mendapatkan ID pengguna terotentikasi.
- **name**: Nama pengguna.
- **email**: Alamat email pengguna.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
