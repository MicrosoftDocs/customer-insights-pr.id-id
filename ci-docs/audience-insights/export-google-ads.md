---
title: Ekspor data Customer Insights ke Google Ads
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976322"
---
# <a name="export-segments-to-google-ads-preview"></a>Mengekspor segmen ke Google Ads (pratinjau)

Ekspor segmen profil pelanggan terpadu ke daftar audiens Google Ads dan gunakan untuk beriklan di Google Search, Gmail, YouTube, dan Google Display Network. 

## <a name="prerequisites-for-connection"></a>Prasyarat untuk koneksi

-   Anda memiliki [akun Google Ads](https://ads.google.com/) dan kredensial administrator yang sesuai.
-   Anda memiliki [token Pengembang Google Ads yang disetujui](https://developers.google.com/google-ads/api/docs/first-call/dev-token) 
-   Anda memenuhi persyaratan [Kebijakan Customer Match](https://support.google.com/adspolicy/answer/6299717)
-   Anda memenuhi persyaratan [ukuran daftar pemasaran ulang](https://support.google.com/google-ads/answer/7558048) 

-   Audiens sudah ada di Google Ads dan id yang sesuai. Untuk informasi lebih lanjut, lihat [audiens Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Anda telah [mengonfigurasi segmen](segments.md)
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email, nama depan, dan nama belakang

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil per ekspor ke Google Ads.
- Mengekspor ke Google Ads.terbatas untuk segmen.
- Mengekspor segmen dengan total 1 juta profil dapat memakan waktu hingga 5 menit karena keterbatasan pada sisi Provider. 
- Pencocokan di Google Ads dapat berlangsung hingga 48 jam.

## <a name="set-up-connection-to-google-ads"></a>Konfigurasikan koneksi ke Google Ads

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Google Ads** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **[ID pelanggan Google Ads](https://support.google.com/google-ads/answer/1704344)** Anda.

1. Masukkan **[token Developer yang disetujui Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **autentikasi dengan Google Ads** dan berikan kredensial Google Ads Anda.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi. 

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Google Ads. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Masukkan **[ID audiens dan google ads anda](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**, lalu pilih **sambungkan** untuk menginisialisasi sambungan ke google ads.

1. Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan. Ulangi langkah yang sama untuk bidang **nama depan** dan **nama belakang**.

1. Pilih segmen yang ingin diekspor. Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke Google Ads.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Google Ads, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Google Ads memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]