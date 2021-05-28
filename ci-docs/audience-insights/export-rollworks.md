---
title: Mengekspor data Customer Insights ke RollWorks
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760558"
---
# <a name="export-segment-lists-to-rollworks-preview"></a>Mengekspor daftar segmen ke RollWorks (pratinjau)

Ekspor segmen profil pelanggan terpadu ke RollWorks dan gunakan untuk periklanan. 

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk koneksi

-   Anda memiliki [akun RollWorks](https://www.rollworks.com/) dan kredensial administrator terkait.
-   Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Anda dapat mengekspor hingga 250.000 profil per ekspor ke RollWorks.
- Anda tidak dapat mengekspor segmen dengan kurang dari 100 profil ke RollWorks. 
- Mengekspor ke RollWorks terbatas pada segmen.
- Mengekspor hingga 250.000 profil ke RollWorks dapat memakan waktu hingga 10 menit untuk diselesaikan. 
- Jumlah profil yang dapat Anda ekspor ke RollWorks tergantung dan terbatas pada kontrak Anda dengan RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Konfigurasikan koneksi ke RollWorks

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **RollWorks** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi ke RollWorks.

1. Pilih **Autentikasi dengan RollWorks** dan berikan kredensial admin Anda untuk RollWorks.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian RollWorks. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Masukkan **ID Pengiklan RollWorks** [RollWorks yang Dapat Diiklankan](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan. Segmen harus diekspor ke RollWorks.

1. Pilih segmen yang ingin diekspor. Pilih segmen dengan minimal 100 anggota. Anda tidak dapat mengekspor segmen yang lebih kecil. Selain itu, ukuran maksimum segmen untuk diekspor adalah 250.000 anggota per ekspor. 

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke RollWorks, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa RollWorks memenuhi kewajiban privasi atau keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.