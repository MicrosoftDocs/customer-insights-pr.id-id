---
title: Mengekspor segmen ke DotDigital (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: af0cce4edb9d47247c79ae08491366349da98b1c
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082933"
---
# <a name="export-segments-to-dotdigital-preview"></a>Mengekspor segmen ke DotDigital (pratinjau)

Ekspor segmen profil pelanggan terpadu ke buku alamat DotDigital dan gunakan untuk kampanye, pemasaran email, dan untuk membangun segmen pelanggan dengan DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk koneksi

-   Anda memiliki [akun DotDigital](https://dotdigital.com/) dan membuat [pengguna API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Anda harus menggunakan kredensial pengguna API untuk membuat sambungan
-   Buku alamat sudah ada di DotDigital dan id yang sesuai. ID dapat ditemukan di URL saat Anda memilih dan membuka buku alamat. Untuk informasi lebih lanjut, lihat [buku alamat dotdigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Anda telah [mengonfigurasi segmen](segments.md) di Customer Insights.
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil pelanggan per ekspor ke DotDigital.
- Mengekspor ke DotDigital terbatas untuk segmen.
- Mengekspor segmen dengan total 1 juta profil pelanggan dapat berlangsung hingga 3 jam karena keterbatasan pada sisi penyedia. 
- Jumlah profil pelanggan yang dapat Anda ekspor ke DotDigital tergantung dan dibatasi oleh kontrak Anda dengan DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Konfigurasikan koneksi ke DotDigital

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **DotDigital** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **nama pengguna dan sandi API DotDigital** Anda. 

1. Masukkan **[id buku alamat dotdigital Anda](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Sambungkan** untuk menginisialisasi sambungan ke dotdigital.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi. 

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian DotDigital. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.


1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan. Ulangi langkah yang sama untuk bidang opsional lainnya seperti **nama depan**, **nama belakang**, **nama lengkap**, **jenis kelamin**, dan **kode posting**.

1. Pilih segmen yang ingin diekspor. Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke DotDigital.

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 
 
Di DotDigital, Anda sekarang dapat menemukan segmen dalam [buku alamat dotdigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke DotDigital, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa DotDigital memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE [footer-include](includes/footer-banner.md)]
