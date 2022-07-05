---
title: Mengekspor segmen ke Campaign Monitor (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Campaign Monitor.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ea7431d4df5143724b5ecf2a2d747ed164fe2c29
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082891"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Mengekspor segmen ke Campaign Monitor (pratinjau)

Ekspor segmen profil pelanggan terpadu ke Campaign Monitor dan gunakan untuk aktivitas pemasaran.

## <a name="prerequisites"></a>Prasyarat

-   Anda memiliki [akun Campaign Monitor](https://www.campaignmonitor.com/) dan kredensial administrator terkait.
-   Anda telah [mengonfigurasi segmen](segments.md) di Customer Insights.
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Anda dapat mengekspor hingga 1 juta profil pelanggan per ekspor ke Campaign Monitor.
- Mengekspor ke Campaign Monitor terbatas pada segmen.
- Mengekspor hingga 1 juta profil pelanggan ke Campaign Monitor dapat berlangsung selama 20 menit. 
- Jumlah profil pelanggan yang dapat Anda ekspor ke Campaign Monitor tergantung dan dibatasi oleh kontrak Anda dengan Campaign Monitor.

## <a name="set-up-connection-to-campaign-monitor"></a>Konfigurasikan koneksi ke Campaign Monitor

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Campaign Monitor** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi ke Campaign Monitor.

1. Pilih **Autentikasi dengan Campaign Monitor** dan berikan kredensial admin Anda untuk Campaign Monitor.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Campaign Monitor. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Masukkan [**ID daftar Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Buat kunci API](https://www.campaignmonitor.com/api/getting-started/) dari **Pengaturan Akun** di Campaign Monitor terlebih dahulu untuk melihat ID daftar API.  

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan. Segmen harus diekspor ke Campaign Monitor.

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Campaign Monitor, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa Campaign Monitor memenuhi kewajiban privasi atau keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.
