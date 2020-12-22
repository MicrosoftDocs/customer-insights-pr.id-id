---
title: Ekspor data Customer Insights ke Google Ads
description: Pelajari cara mengkonfigurasi sambungan ke Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568454"
---
# <a name="connector-for-google-ads-preview"></a>Konektor untuk Google Ads (pratinjau)

Ekspor segmen profil pelanggan terpadu ke daftar audiens Google Ads dan gunakan untuk beriklan di Google Search, Gmail, YouTube, dan Google Display Network. 

## <a name="prerequisites"></a>Prasyarat

-   Anda memiliki [akun Google Ads](https://ads.google.com/) dan kredensial administrator yang sesuai.
-   Audiens sudah ada di Google Ads dan id yang sesuai. Untuk informasi lebih lanjut, lihat [audiens Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Anda telah [mengonfigurasi segmen](segments.md)
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email, nama depan, dan nama belakang

## <a name="connect-to-google-ads"></a>Sambungkan ke Google Ads

1. Buka **Admin** > **Tujuan ekspor**.

1. Di dalam **Google Ads**, pilih **konfigurasi**.

1. Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.

1. Masukkan **[ID pelanggan Google Ads](https://support.google.com/google-ads/answer/1704344)** Anda.

1. Masukkan **[token Developer yang disetujui Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Masukkan **[ID audiens dan google ads anda](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**, lalu pilih **sambungkan** untuk menginisialisasi sambungan ke google ads.

1. Pilih **autentikasi dengan Google Ads** dan berikan kredensial Google Ads Anda.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Mengekspor tangkapan layar untuk sambungan Google Ads":::

1. Pilih **berikutnya** untuk mengkonfigurasi ekspor.

## <a name="configure-the-connector"></a>Konfigurasikan konektor

1. Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan. Ulangi langkah yang sama untuk bidang **nama depan** dan **nama belakang**.

1. Pilih segmen yang ingin diekspor. Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke Google Ads.

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengekspor data

Anda dapat [mengekspor data sesuai permintaan](export-destinations.md). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Di Google Ads, Anda sekarang dapat menemukan segmen Anda dalam [audiens Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil per ekspor ke Google Ads.
- Mengekspor ke Google Ads.terbatas untuk segmen.
- Mengekspor segmen dengan total 1 juta profil dapat memakan waktu hingga 5 menit karena keterbatasan pada sisi Provider. 
- Pencocokan di Google Ads dapat berlangsung hingga 48 jam.

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Google Ads, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Google Ads memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.
