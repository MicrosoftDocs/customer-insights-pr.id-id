---
title: Kelola cookie dan persetujuan pengguna untuk menyimpan data pengguna di Dynamics 365 Customer Insights
description: Pahami cara penggunaan cookie dan persetujuan pengguna untuk mengidentifikasi pengunjung situs web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c824e50b723fe7f3b421048bb6ab96b7a9efc31f
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558875"
---
# <a name="manage-cookies-and-user-consent"></a>Mengelola cookie dan izin pengguna

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Kemampuan wawasan keterlibatan Dynamics 365 Customer Insights menggunakan cookie dan kunci (`localStorage`) untuk mengidentifikasi pengunjung situs web.

Cookie adalah file kecil yang menyimpan penggalan informasi tentang interaksi pengguna dengan situs web. Semuanya disimpan di browser web. Ketika pengguna mengunjungi situs web yang mana pengguna menyimpan cookie, browser akan mengirimkan informasi tersebut ke server, yang mengembalikan informasi unik pengguna. Ini adalah teknologi yang memungkinkan, misalnya, keranjang belanja online untuk tetap menyimpan item yang dipilih di dalamnya meskipun pengguna tidak lagi menelusuri situs web itu.

## <a name="user-consent"></a>Izin Pengguna

[Peraturan Perlindungan Data Umum (GDPR)](/dynamics365/get-started/gdpr/) adalah peraturan Uni Eropa (UE) yang mengamanatkan bagaimana organisasi harus menangani privasi dan keamanan penggunanya. Cookie sering menyimpan atau mengumpulkan "data pribadi", seperti pengidentifikasi online, yang tercakup oleh GDPR. Jika bisnis Anda mempekerjakan dan/atau menjual ke subjek data UE, GDPR akan mempengaruhi Anda. [Pelajari lebih lanjut tentang cara Microsoft dapat membantu Anda mematuhi GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Untuk memungkinkan SDK wawasan keterlibatan menyimpan cookie atau informasi sensitif lainnya, Anda harus menentukan apakah pengguna telah menyetujui. Hal ini terjadi pada inisialisasi SDK dengan mengatur bidang `userConsent` dalam konfigurasi.

Jika Anda menunjukkan bahwa tidak ada persetujuan pengguna, SDK tidak akan menyimpan data apa pun dan tidak akan mengirim aktivitas yang dapat digunakan untuk melacak perilaku pengguna. Data yang tersimpan sebelumnya akan dihapus dari browser.

Jika tidak ada nilai persetujuan pengguna yang ditentukan, SDK akan mengasumsikan bahwa pengguna telah menyetujui. Ini berarti bahwa jika Anda (sebagai pelanggan kami) tidak menentukan nilai untuk persetujuan pengguna dalam SDK, data akan dikumpulkan. Namun, jika Anda menetapkan bahwa nilai untuk persetujuan pengguna harus "benar", data tidak akan dikumpulkan jika pengguna menolak atau gagal memberikan persetujuan eksplisit.

Di bawah ini adalah cuplikan kode menginisialisasi SDK web dengan persetujuan pengguna:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Penyimpanan data pengunjung dalam kemampuan wawasan keterlibatan

### <a name="cookies"></a>Cookies

- _msei
    - Menyimpan ID pengguna anonim. Cookie ini ditetapkan di domain pelanggan dan kedaluwarsa dalam 365 hari.

### <a name="local-storage"></a>Penyimpanan lokal

Kemampuan wawasan keterlibatan juga memanfaatkan kunci (`localStorage`) untuk melacak data yang tidak sensitif. Data ini sepenuhnya disimpan di browser itu sendiri, tanpa lalu lintas yang dikirim ke atau dari server Anda.

- *EISession.Id*
    - Menyimpan informasi tentang sesi pengguna yang sedang berlangsung, seperti ID sesi, saat dimulai, dan waktu berakhir.
- *EISession.Previous*
    - Menyimpan URL halaman yang dikunjungi sebelumnya pada sesi saat ini.

Kunci dalam penyimpanan lokal tidak kedaluwarsa secara otomatis, dan tombol akan diatur ulang selama sesi SDK berikutnya.

## <a name="deleting-cookies"></a>Menghapus cookie

Pelanggan Anda dapat menghapus cookie dan kunci penyimpanan lokal secara manual kapan pun melalui pengaturan browser mereka.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
