---
title: Skenario SDK web lanjutan
description: Skenario lanjutan untuk dipertimbangkan saat menginstrumentasi situs web Anda dengan SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036332"
---
# <a name="advanced-web-sdk-instrumentation"></a>Instrumentasi SDK web lanjutan

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Artikel ini memandu Anda melalui skenario lanjutan untuk dipertimbangkan saat melakukan [instrumentasi situs web Anda](instrument-website.md) dengan SDK kemampuan wawasan keterlibatan Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Mengatur rincian pengguna untuk aktivitas Anda

SDK memungkinkan Anda menentukan informasi pengguna yang dapat dikirim dengan setiap aktivitas. Anda dapat menentukan rincian pengguna di properti yang disebut `user` (data yang diharapkan untuk properti ini adalah objek `IUser`), yang mirip dengan `src`, `name` dan `cfg` dalam konfigurasi cuplikan kode.

Objek `IUser` berisi properti string berikut:

- **localId**: ID lokal pengguna.
- **authId**: ID pengguna terotentikasi.
- **authType**: Jenis otentikasi yang digunakan untuk mendapatkan ID pengguna terotentikasi.
- **name**: Nama pengguna.
- **email**: Alamat email pengguna.
    
Contoh berikut menampilkan cuplikan kode yang mengirim informasi pengguna. Bila Anda melihat Fungsi yang ditunjukkan oleh *, ganti dengan penerapan pemanggilan nilai tersebut:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Anda juga dapat menentukan informasi pengguna dengan menghubungi API `setUser(user: IUser)` di SDK. Telemetri yang dikirim setelah memanggil `setUser API` akan berisi informasi pengguna.

## <a name="adding-custom-properties-for-each-event"></a>Menambahkan properti kustom untuk setiap aktivitas

SDK memungkinkan Anda menentukan properti kustom yang dapat dikirim dengan setiap aktivitas. Anda dapat menentukan properti kustom sebagai objek yang berisi pasangan nilai kunci (nilai dapat dari jenis `string | number | boolean`). Objek dapat ditambahkan di properti yang disebut `props`, mirip dengan `src`, `name`, dan `cfg` dalam konfigurasi cuplikan kode. 

Contoh berikut menampilkan cuplikan kode yang mengirim properti kustom.

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
    name:"myproject",      
    cfg:{ 
      ingestionKey:<paste your ingestion key>", 
      autoCapture:{ 
        view:true, 
        click:true 
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Anda juga dapat menentukan properti kustom secara terpisah dengan memanggil API `setProperty(name: string, value: string | number | boolean)` di SDK.

## <a name="sending-custom-events"></a>Mengirimkan aktivitas kustom

Anda dapat menggunakan SDK untuk mengirim aktivitas kustom. Anda harus menentukan nama untuk aktivitas dan properti yang akan dikirim dengan aktivitas.

Contoh berikut menampilkan cuplikan kode yang melacak aktivitas kustom. "NAMA" adalah nilai pada kunci `name` dalam konfigurasi cuplikan. Ia juga nama variabel di objek jendela tempat SDK dimuat.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]