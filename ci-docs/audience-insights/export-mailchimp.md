---
title: Ekspor data Customer Insights ke Mailchimp
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Mailchimp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 94a9fead56ce8c40b35d4eb41ebdc0d672798dce
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618617"
---
# <a name="export-segments-to-mailchimp-preview"></a>Mengekspor segmen ke Mailchimp (pratinjau)

Ekspor segmen profil pelanggan terpadu ke MailChimp untuk membuat kampanye newsletter dan email.

## <a name="prerequisites-for-connection"></a>Prasyarat untuk koneksi

-   Anda memiliki [akun Mailchimp](https://mailchimp.com/) dan kredensial administrator yang sesuai.
-   Audiens sudah ada di Mailchimp dan id yang sesuai. Untuk informasi lebih lanjut, lihat [audiens Mailchimp](https://mailchimp.com/help/create-audience/).
-   Anda telah [mengonfigurasi segmen](segments.md)
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil pelanggan per ekspor ke Mailchimp.
- Mengekspor ke Mailchimp terbatas untuk segmen.
- Mengekspor segmen dengan 1 juta profil pelanggan dapat berlangsung hingga tiga jam. 
- Jumlah profil pelanggan yang dapat Anda ekspor ke Mailchimp tergantung dan dibatasi oleh kontrak Anda dengan Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Konfigurasikan koneksi ke Mailchimp

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambah koneksi** dan pilih **Mailchimp** untuk mengkonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi ke Mailchimp.

1. Pilih **autentikasi dengan Mailchimp** dan berikan kredensial Mailchimp Anda.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi. 

## <a name="configure-the-connector"></a>Konfigurasikan konektor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data**> **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Mailchimp. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Masukkan **[ID audiens Mailchimp](https://mailchimp.com/help/find-audience-id/)**

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan. 

1. Secara opsional, Anda dapat mengekspor **nama depan** dan **nama belakang** untuk membuat email yang lebih dipersonalisasi. Pilih **Tambah atribut** untuk memetakan bidang ini.

1. Pilih segmen yang ingin diekspor. Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke Mailchimp.

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Mailchimp, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Mailchimp memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
