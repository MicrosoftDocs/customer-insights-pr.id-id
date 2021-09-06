---
title: Ekspor data Customer Insights ke AdRoll
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e48f67ec21bb9b883dd30544ccf4dcfbf487acb1abaf0a0557764bc3d955e41a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032075"
---
# <a name="export-segments-to-adroll-preview"></a>Mengekspor segmen ke AdRoll (pratinjau)

Mengekspor segmen profil pelanggan terpadu ke AdRoll dan menggunakannya untuk iklan. 

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk koneksi

-   Anda memiliki [akun AdRoll](https://www.adroll.com/) dan kredensial administrator yang sesuai.
-   Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Anda dapat mengekspor hingga 250.000 profil sekaligus ke AdRoll.
- Anda tidak dapat mengekspor segmen dengan kurang dari 100 profil ke AdRoll. 
- Mengekspor ke AdRoll terbatas untuk segmen.
- Mengekspor hingga 250.000 profil ke AdRoll dapat berlangsung hingga 10 menit untuk menyelesaikannya. 
- Jumlah profil yang dapat Anda ekspor ke AdRoll tergantung pada kontrak Anda dengan AdRoll.

## <a name="set-up-connection-to-adroll"></a>Konfigurasikan koneksi ke AdRoll

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **AdRoll** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Sambungkan** untuk menginisialisasi sambungan ke AdRoll.

1. Pilih **autentikasi dengan AdRoll** dan berikan kredensial admin Anda untuk AdRoll. 

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian AdRoll. Jika Anda tidak melihat nama bagian ini, maka tidak ada sambungan dari jenis ini yang tersedia untuk Anda.

1. Masukkan **ID Pengiklan AdRoll** Anda. Untuk informasi lebih lanjut, lihat [Profil Pemilik Iklan AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan. Ini harus diekspor ke AdRoll.

1. Pilih segmen yang ingin diekspor. Pilih segmen dengan minimal 100 anggota. Anda tidak dapat mengekspor segmen yang lebih kecil. Selain itu, ukuran maksimum segmen untuk diekspor adalah 250.000 anggota per ekspor. 

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). 

Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke AdRoll, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa AdRoll memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.
