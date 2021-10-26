---
title: Mengekspor data Customer Insights ke Klaviyo
description: Pelajari lebih lanjut cara mengkonfigurasi sambungan dan mengekspor ke Klaviyo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5f7c91afed8eeb1f767f1efc58dceb7782c37bb4
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/08/2021
ms.locfileid: "7619077"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Mengekspor daftar segmen ke Klaviyo (pratinjau)

Mengekspor segmen profil pelanggan terpadu ke Klaviyo dan menggunakannya untuk aktivitas pemasaran.

## <a name="prerequisites"></a>Prasyarat

-   Anda memiliki [akun Klaviyo](https://www.klaviyo.com/) dan kredensial administrator yang terkait.
-   Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Anda dapat mengekspor hingga 100.000 profil pelanggan per ekspor ke Klaviyo.
- Mengekspor ke Klaviyo terbatas pada segmen.
- Mengekspor hingga 1 juta profil pelanggan ke Klaviyo dapat berlangsung selama 20 menit. 
- Jumlah profil pelanggan yang dapat Anda ekspor ke Klaviyo tergantung dan dibatasi oleh kontrak Anda dengan Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>Konfigurasikan sambungan ke Klaviyo

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambah koneksi** dan pilih **Klaviyo** untuk mengkonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan [kunci Api Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) untuk lanjut masuk. 

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Sambungkan** untuk memulai koneksi ke Klaviyo.

1. Pilih **Autentikasi dengan Klaviyo** dan berikan kredensial admin Anda untuk Klaviyo.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Di bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Klaviyo. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Masukkan [**ID daftar Klaviyo**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID) Anda.     

3. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan. Mengekspor segmen ke Klaviyo harus dilakukan.

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mentransmisikan data ke Klaviyo, Anda mengizinkan transfer data di luar batas kesesuaian untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mengalihkan data tersebut berdasarkan instruksi Anda, namun Anda bertanggung jawab untuk memastikan bahwa Klaviyo memenuhi privasi atau jaminan keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.
