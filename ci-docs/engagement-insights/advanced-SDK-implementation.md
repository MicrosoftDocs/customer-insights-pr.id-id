---
title: Skenario SDK web lanjutan
description: Skenario lanjutan untuk dipertimbangkan saat menginstrumentasi situs web Anda dengan SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227202"
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

Contoh berikut menampilkan cuplikan kode yang mengirim informasi pengguna. Bila Anda melihat fungsi yang didahului oleh simbol tanda bintang *, ganti fungsi dengan implementasi kustom Anda:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
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

Anda juga dapat menentukan informasi pengguna dengan memanggil API `setUser(user: IUser)`. Telemetri yang dikirim setelah memanggil API `setUser` akan berisi informasi pengguna.

## <a name="adding-custom-properties-for-each-event"></a>Menambahkan properti kustom untuk setiap aktivitas

SDK memungkinkan Anda menentukan properti kustom yang dapat dikirim dengan setiap aktivitas. Anda dapat menentukan properti kustom sebagai objek yang berisi pasangan nilai kunci (nilai dapat dari jenis `string | number | boolean`). Anda dapat menambahkan objek di properti yang disebut `props`, mirip dengan `src`, `name`, dan `cfg` dalam konfigurasi cuplikan kode.

Contoh berikut menampilkan cuplikan kode yang mengirim properti kustom.

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
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

Anda juga dapat menentukan properti kustom secara individual dengan memanggil API `setProperty(name: string, value: string | number | boolean)`.

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
