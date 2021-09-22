---
title: Mengelola cookie dan persetujuan pengguna untuk menyimpan data pengguna
description: Pahami cara penggunaan cookie dan persetujuan pengguna untuk mengidentifikasi pengunjung situs web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036742"
---
# <a name="manage-cookies-and-user-consent"></a>Mengelola cookie dan izin pengguna

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Kemampuan wawasan keterlibatan Dynamics 365 Customer Insights menggunakan cookie dan penyimpanan lokal (`localStorage`) untuk mengidentifikasi pengunjung situs web.

Cookie adalah file kecil yang menyimpan penggalan informasi tentang interaksi pengguna dengan situs web. Semuanya disimpan di browser web. Ketika pengguna mengunjungi situs web yang mana pengguna menyimpan cookie, browser akan mengirimkan informasi tersebut ke server, yang mengembalikan informasi unik pengguna. Ini adalah teknologi yang memungkinkan, misalnya, keranjang belanja online untuk tetap menyimpan item yang dipilih di dalamnya meskipun pengguna tidak lagi menelusuri situs web itu.

## <a name="user-consent"></a>Izin Pengguna

[Peraturan Perlindungan Data Umum (GDPR)](/dynamics365/get-started/gdpr/) adalah peraturan Uni Eropa (UE) yang mengamanatkan bagaimana organisasi harus menangani privasi dan keamanan penggunanya. Cookie sering menyimpan atau mengumpulkan "data pribadi", seperti pengidentifikasi online, yang tercakup oleh GDPR. Jika bisnis Anda mempekerjakan dan/atau menjual ke subjek data UE, GDPR akan mempengaruhi Anda. [Pelajari lebih lanjut tentang cara Microsoft dapat membantu Anda mematuhi GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Untuk memungkinkan SDK wawasan keterlibatan menyimpan cookie atau informasi sensitif lainnya, Anda harus menentukan apakah pengguna telah menyetujui. Hal ini terjadi pada inisialisasi SDK.

Jika Anda menunjukkan bahwa tidak ada persetujuan pengguna, SDK tidak akan menyimpan data apa pun dan tidak akan mengirim aktivitas yang dapat digunakan untuk melacak perilaku pengguna. Data yang tersimpan sebelumnya akan dihapus dari browser.

Jika tidak ada nilai persetujuan pengguna yang ditentukan, SDK akan mengasumsikan bahwa pengguna telah menyetujui. Ini berarti bahwa jika Anda (sebagai pelanggan kami) tidak menentukan nilai untuk persetujuan pengguna dalam SDK, data akan dikumpulkan. Namun, jika Anda menetapkan bahwa nilai untuk persetujuan pengguna harus "benar", data tidak akan dikumpulkan jika pengguna menolak atau gagal memberikan persetujuan eksplisit.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Penyimpanan data pengunjung dalam kemampuan wawasan keterlibatan

### <a name="cookies"></a>Cookies

- _msei
    - Menyimpan ID pengguna anonim. Cookie ini ditetapkan di domain pelanggan dan kedaluwarsa dalam 365 hari.

### <a name="local-storage"></a>Penyimpanan lokal

Kemampuan wawasan keterlibatan juga memanfaatkan penyimpanan lokal (`localStorage`) untuk melacak data yang tidak sensitif. Data ini sepenuhnya disimpan di browser itu sendiri, tanpa lalu lintas yang dikirim ke atau dari server Anda.

- *EISession.Id* 
    - Menyimpan informasi tentang sesi pengguna yang sedang berlangsung, seperti ID sesi, saat dimulai, dan waktu berakhir.
- *EISession.Previous*
    - Menyimpan URL halaman yang dikunjungi sebelumnya pada sesi saat ini.
    
Kunci dalam penyimpanan lokal tidak kedaluwarsa secara otomatis. Semua akan direset selama sesi berikutnya oleh SDK.

## <a name="deleting-cookies"></a>Menghapus cookie

Pelanggan Anda dapat menghapus cookie dan kunci penyimpanan lokal secara manual kapan pun melalui pengaturan browser mereka.


[!INCLUDE[footer-include](../includes/footer-banner.md)]