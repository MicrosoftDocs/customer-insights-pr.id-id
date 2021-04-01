---
title: Ekspor data Customer Insights ke DotDigital
description: Pelajari cara mengkonfigurasi sambungan ke DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598021"
---
# <a name="connector-for-dotdigital-preview"></a>Konektor untuk DotDigital (pratinjau)

Ekspor segmen profil pelanggan terpadu ke buku alamat DotDigital dan gunakan untuk kampanye, pemasaran email, dan untuk membangun segmen pelanggan dengan DotDigital. 

## <a name="prerequisites"></a>Prasyarat

-   Anda memiliki [akun dotdigital](https://dotdigital.com/) dan kredensial administrator yang sesuai.
-   Buku alamat sudah ada di DotDigital dan id yang sesuai. ID dapat ditemukan di URL saat Anda memilih dan membuka buku alamat. Untuk informasi lebih lanjut, lihat [buku alamat dotdigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="connect-to-dotdigital"></a>Menyambung ke DotDigital

1. Buka **Admin** > **Tujuan ekspor**.

1. Dalam **dotdigital**, pilih **konfigurasi**.

1. Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfigurasi panel untuk ekspor DotDigital.":::

1. Masukkan **nama pengguna dan sandi DotDigital** Anda.

1. Masukkan **[id buku alamat dotdigital Anda](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Sambungkan** untuk menginisialisasi sambungan ke dotdigital.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **berikutnya** untuk mengkonfigurasi ekspor.

## <a name="configure-the-connector"></a>Konfigurasikan konektor

1. Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan. Ulangi langkah yang sama untuk bidang opsional lainnya seperti **nama depan**, **nama belakang**, **nama lengkap**, **jenis kelamin**, dan **kode posting**.

1. Pilih segmen yang ingin diekspor. Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke DotDigital.

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengekspor data

Anda dapat [mengekspor data sesuai permintaan](export-destinations.md). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Di DotDigital, Anda sekarang dapat menemukan segmen dalam [buku alamat dotdigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil per ekspor ke DotDigital.
- Mengekspor ke DotDigital terbatas untuk segmen.
- Mengekspor segmen dengan total 1 juta profil dapat memakan waktu hingga 3 jam karena keterbatasan pada sisi Provider. 
- Jumlah profil yang dapat Anda ekspor ke DotDigital tergantung dan terbatas pada kontrak Anda dengan DotDigital.

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke DotDigital, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa DotDigital memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]