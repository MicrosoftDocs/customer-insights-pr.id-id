---
title: Memulai SDK Android
description: Pelajari cara mempersonalkan dan menjalankan SDK Android
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a060ac60db71a7b0fb8c0d7a3b0e266004fbee6a
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494279"
---
# <a name="get-started-with-the-android-sdk"></a>Memulai SDK Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tutorial ini akan memandu Anda melalui proses penyiapan instrumen aplikasi Android dengan SDK wawasan keterlibatan Dynamics 365 Customer Insights. Anda akan mulai melihat aktivitas di portal dalam lima menit atau lebih cepat.

## <a name="configuration-options"></a>Pilihan Konfigurasi
Pilihan konfigurasi berikut dapat dilewatkan ke SDK:

- **ingestionKey**: Kunci penyerapan digunakan untuk mengirim aktivitas ke ruang kerja Anda.

## <a name="prerequisites"></a>Prasyarat

- Android Studio

- Tingkat API Android Minimum: 16 (Jelly Bean)

- Tombol penyerapan (lihat di bawah ini untuk petunjuk cara mendapatkan)

## <a name="integrate-the-sdk-into-your-application"></a>Mengintegrasikan SDK ke aplikasi Anda
Mulai proses dengan memilih ruang kerja, memilih platform seluler Android, dan mengunduh SDK Android.

- Gunakan switcher ruang kerja di panel navigasi kiri untuk memilih ruang kerja Anda.

- Jika Anda tidak memiliki ruang kerja yang lama, pilih  **Ruang Kerja Baru**, lalu ikuti langkah-langkah untuk membuat [ruang kerja baru](create-workspace.md).

- Setelah membuat ruang kerja, buka **Admin** > **Ruang Kerja**, lalu pilih  **Panduan penginstalan**. 

## <a name="configure-the-sdk"></a>Mengonfigurasi SDK

Setelah mengunduh SDK, Anda dapat menggunakannya di Android Studio untuk mengaktifkan dan mendefinisikan aktivitas. Ada dua cara untuk melakukannya:
### <a name="option-1-using-jitpack-recommended"></a>Pilihan 1: Menggunakan JitPack (disarankan)
1. Tambahkan penyimpanan JitPack ke root `build.gradle` Anda:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Tambahkan dependensi:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-using-download-link"></a>Pilihan 2: Menggunakan tautan unduhan
1. Unduh [SDK Android wawasan keterlibatan](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip), dan letakkan file `eiandroidsdk-debug.aar` dalam folder `libs`.

1. Buka file `build.gradle` tingkat proyek Anda, lalu tambahkan cuplikan berikut:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Tambah izin untuk jaringan dan internet di file `AndroidManifest.xml` yang terletak di dalam folder `manifests`. 
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```
    
1. Konfigurasi SDK wawasan keterlibatan melalui file `AndroidManifest.xml` Anda. 

## <a name="enable-auto-instrumentation"></a>Aktifkan instrumentasi otomatis
1. Salin cuplikan XML dari **panduan Penginstalan**. `Your-Ingestion-Key` seharusnya secara otomatis diisi.

   > [!NOTE]
   > Anda tidak perlu mengganti bagian `${applicationId}` tersebut. Ini akan secara otomatis diisi.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Aktifkan atau nonaktifkan pengambilan otomatis aktivitas `View` dengan mengatur bidang `autoCapture` ke `true` atau `false`. Aktivitas `Action` saat ini harus ditambahkan secara manual.

1. (Opsional) Konfigurasi lain mencakup pengaturan URL pengumpul titik akhir. Semua dapat ditambahkan dalam metadata kunci penyerapan di `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="implement-custom-events"></a>Menerapkan aktivitas kustom

Setelah menginisialisasi SDK, Anda dapat bekerja dengan aktivitas dan propertinya di lingkungan `MainActivity`.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Atur properti untuk semua aktivitas (opsional)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Jenis berikut didukung untuk properti aktivitas konteks:
- String
- Tanggal
- Ganda
- Panjang
- Boolean
- UUID

### <a name="track-an-event"></a>Lacak aktivitas

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Mengatur rincian pengguna untuk aktivitas Anda (opsional)

SDK memungkinkan Anda menentukan informasi pengguna yang dapat dikirim dengan setiap aktivitas. Anda dapat menentukan informasi pengguna dengan menghubungi API `setUser(user: User)` pada tingkat `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Kelas data `User` berisi properti string berikut:

- **localId**: ID lokal pengguna.
- **authId**: ID pengguna terotentikasi.
- **authType**: Jenis otentikasi yang digunakan untuk mendapatkan ID pengguna terotentikasi.
- **name**: Nama pengguna.
- **email**: Alamat email pengguna.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
