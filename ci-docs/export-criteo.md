---
title: Mengekspor segmen ke Criteo (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082786"
---
# <a name="export-segments-to-criteo-preview"></a>Mengekspor segmen ke Criteo (pratinjau)

Ekspor segmen profil pelanggan terpadu untuk menghasilkan kampanye, menyediakan pemasaran email, dan menggunakan grup pelanggan tertentu dengan Criteo.

## <a name="prerequisites-for-connection"></a>Prasyarat untuk koneksi

-   Anda memiliki [akun](https://www.criteo.com/login/) Penargetan Ulang Criteo Dynamics dan kredensial administrator yang sesuai.
-   Anda telah [mengonfigurasi segmen](segments.md).
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil pelanggan per ekspor ke Criteo.
- Mengekspor ke Criteo terbatas pada segmen.
- Mengekspor segmen dengan total 1 juta profil pelanggan dapat berlangsung hingga 30 menit. 
- Jumlah profil pelanggan yang dapat Anda ekspor ke Criteo tergantung dan terbatas pada kontrak Anda dengan Criteo.

## <a name="set-up-connection-to-criteo"></a>Menyiapkan koneksi ke Criteo

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Criteo** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih **Saya setuju** untuk mengonfirmasi **privasi dan kepatuhan** Data dan pilih **Hubungkan** untuk menginisialisasi koneksi ke Criteo.

1. Pilih **Autentikasi dengan Criteo** dan berikan nama pengguna dan kredensial Admin Anda untuk Criteo. 

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Di **bidang Koneksi untuk ekspor**, pilih koneksi dari bagian Criteo. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda. 

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan. 

1. Secara opsional, Anda dapat mengekspor **ID** dan **Nama Pengiklan**

1. Pilih segmen yang ingin diekspor. 

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Ketika Anda memungkinkan Dynamics 365 Customer Insights untuk mengirimkan data ke Criteo, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa Criteo memenuhi kewajiban privasi atau keamanan apa pun yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE[footer-include](includes/footer-banner.md)]
