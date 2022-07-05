---
title: Mengekspor segmen ke Sendinblue (pratinjau)
description: Pelajari lebih lanjut cara mengkonfigurasi sambungan dan mengekspor ke Sendinblue.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f6550b5c57866702631b4c294bb059279461bd6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083080"
---
# <a name="export-segments-to-sendinblue-preview"></a>Mengekspor segmen ke Sendinblue (pratinjau)

Ekspor segmen profil pelanggan terpadu untuk membuat kampanye, menyediakan pemasaran melalui email, dan menggunakan grup pelanggan tertentu dengan Sendinblue.

## <a name="prerequisites-for-connection"></a>Prasyarat untuk koneksi

-   Anda memiliki [akun Sendinblue](https://www.sendinblue.com/) dan kredensial administrator yang terkait.
-   Ada daftar lama di Sendinblue dan ID yang terkait.
-   Anda telah [mengonfigurasi segmen](segments.md).
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil pelanggan per ekspor ke Sendinblue.
- Mengekspor ke Sendinblue terbatas pada segmen.
- Mengekspor segmen dengan total 1 juta profil pelanggan dapat berlangsung hingga 90 menit. 
- Jumlah profil pelanggan yang dapat Anda ekspor ke Sendinbluetergantung dan dibatasi oleh kontrak Anda dengan Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Konfigurasikan sambungan ke Sendinblue

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambah koneksi** dan pilih **Sendinblue** untuk mengkonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan kunci **[API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Pilih **Saya setuju** untuk mengkonfirmasi **privasi dan kesesuaian Data**, lalu pilih **Sambungkan** untuk menginisialisasi sambungan ke Sendinblue.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Di bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Sendinblue. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Masukkan **ID daftar Sendinblue** Anda 

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan. 

1. Atau, Anda dapat mengekspor **nama depan**, **nama belakang**, dan **Telepon**  untuk membuat email yang lebih dipersonalisasi. Pilih **Tambah atribut** untuk memetakan bidang ini.

1. Pilih segmen yang ingin diekspor. 

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mentransmisikan data ke Sendinblue, Anda mengizinkan transfer data di luar batas kesesuaian untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mengalihkan data tersebut berdasarkan instruksi Anda, namun Anda bertanggung jawab untuk memastikan bahwa Sendinblue memenuhi privasi atau jaminan keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE [footer-include](includes/footer-banner.md)]
