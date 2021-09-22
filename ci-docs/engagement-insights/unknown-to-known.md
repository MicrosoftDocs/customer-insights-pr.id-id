---
title: Mengenali aktivitas web dari pengunjung terotentikasi sebelumnya dengan yang tidak dikenal menjadi dikenal
description: Fitur tidak dikenal menjadi dikenal memungkinkan Anda mengaitkan aktivitas di situs web dengan pengunjung yang terotentikasi sebelumnya.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036787"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Mengenali aktivitas web dari pengunjung terotentikasi sebelumnya

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Fitur **tidak dikenal menjadi dikenal** dalam kemampuan wawasan keterlibatan memungkinkan mengaitkan aktivitas di situs web dengan pengunjung yang terotentikasi sebelumnya. Jika fitur dinonaktifkan, pengunjung yang diautentikasi selama kunjungan sebelumnya, kemudian pergi, tidak akan diidentifikasi jika mereka tidak mengautentikasi lagi saat kembali. 

Misalnya, seseorang yang mengunjungi situs web minggu lalu, masuk ke akun pengguna mereka di situs, dan menelusuri katalog produk. Orang itu kembali pekan berikutnya untuk menelusuri produk lainnya tanpa masuk ke akun mereka. Pemilik situs yang menggunakan fitur **tidak dikenal menjadi dikenal** akan mengetahui bahwa orang yang sama telah kembali dan apa yang telah mereka lakukan di situs. Hal ini memungkinkan pelaporan dan analisis aktivitas situs web yang lebih akurat.

## <a name="enable-unknown-to-known"></a>Tidak dikenal menjadi dikenal

Anda harus menjadi [admin ruang kerja](user-roles.md) untuk mengaktifkan fitur ini. 

1. Dalam wawasan keterlibatan, buka **Admin** > **Ruang Kerja**. 
2. Pilih tab **Pengaturan**.
3. Di bagian **tidak dikenal menjadi dikenal**, atur pengalih ke **Diaktifkan**.

![Tidak dikenal menjadi dikenal](media/U2Ktoggle.png "Tidak dikenal menjadi dikenal")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Menambahkan kode JavaScript ke cuplikan pelacakan situs Anda

Situs web dapat mengambil **authId pengguna** dengan sampel JavaScript berikut menggunakan [SDK web wawasan keterlibatan](advanced-SDK-implementation.md). Agar fitur **tidak dikenal menjadi dikenal** berfungsi, Anda harus mengambil authId *dan* mengaktifkan userMapping:True di cuplikan JavaScript seperti pada sampel di bawah.

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
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
