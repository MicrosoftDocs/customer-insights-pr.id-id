---
title: Ekspor data Customer Insights ke Autopilot
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Autopilot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4cceb64484e8e257a90b8cbaedff4419659bb399
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618433"
---
# <a name="export-segments-to-autopilot-preview"></a>Mengekspor segmen ke Autopilot (pratinjau)

Ekspor segmen profil pelanggan terpadu ke Autopilot dan gunakan untuk pemasaran email di Autopilot. 

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk koneksi

-   Anda memiliki [akun Autopilot](https://www.autopilothq.com/) dan kredensial administrator yang sesuai.
-   Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Anda dapat mengekspor hingga 100.000 profil pelanggan secara total ke Autopilot.
- Mengekspor ke Autopilot terbatas untuk segmen.
- Mengekspor hingga 100.000 profil pelanggan ke Autopilot dapat berlangsung selama beberapa jam. 
- Jumlah profil pelanggan yang dapat Anda ekspor ke Autopilot tergantung dan dibatasi oleh kontrak Anda dengan Autopilot.

## <a name="set-up-connection-to-autopilot"></a>Konfigurasikan koneksi ke Autopilot

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Mailchimp** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan [kunci API Autopilot](https://autopilot.docs.apiary.io/#) Anda.

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Sambungkan** untuk menginisialisasi sambungan ke Autopilot.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Autopilot. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan. Ulangi langkah yang sama untuk bidang opsional lainnya seperti **nama depan**, **nama belakang**.

1. Pilih segmen yang ingin diekspor. Kami sangat **menyarankan untuk tidak mengekspor lebih dari 100'000 profil pelanggan secara total** ke Autopilot. 

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Autopilot, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Autopilot memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
