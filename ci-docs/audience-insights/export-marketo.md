---
title: Ekspor data Customer Insights ke Marketo
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0d5eaa769973c861d89287bba0ed29509ab2efc653bdd8e177cc49b3560c698e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033497"
---
# <a name="export-segments-to-marketo-preview"></a>Mengekspor segmen ke Marketo (pratinjau)

Ekspor segmen profil pelanggan terpadu untuk membuat kampanye, menyediakan pemasaran melalui email, dan gunakan grup pelanggan tertentu dengan Marketo.

## <a name="prerequisites-for-connection"></a>Prasyarat untuk koneksi

-   Anda memiliki [akun Marketo](https://login.marketo.com/) dan kredensial administrator yang sesuai.
-   Daftar sudah ada di Marketo dan id yang sesuai. Untuk informasi lebih lanjut, lihat [daftar Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Anda telah [mengonfigurasi segmen](segments.md).
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil per ekspor ke Marketo.
- Mengekspor ke Marketo terbatas untuk segmen.
- Mengekspor segmen dengan total 1 juta profil dapat memakan waktu hingga 3 jam. 
- Jumlah profil yang dapat Anda ekspor ke Marketo tergantung dan terbatas pada kontrak Anda dengan Marketo.

## <a name="set-up-connection-to-marketo"></a>Konfigurasikan koneksi ke Marketo

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Marketo** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **[ID klien marketo anda, rahasia klien dan Hostname titik akhir REST](https://developers.marketo.com/rest-api/authentication/)**. Hostname titik akhir REST adalah hanya hostname, tanpa `https://`. Contoh:`xyz-abc-123.mktorest.com`. 

1. Pilih **saya setuju** untuk mengkonfirmasi **privasi data dan kepatuhan** dan pilih **Sambungkan** untuk menginisialisasi sambungan ke marketo.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Marketo. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Masukkan **[id daftar marketo Anda](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. ID daftar adalah nilai yang semata-mata numerik. Contohnya, jika ID daftar Marketo Anda adalah ST12345A7, hilangkan karakter sebelum dan setelah angka dan masukkan `12345`. 

1. Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan. 

1. Secara opsional, Anda dapat mengekspor **nama depan**, **nama belakang**, **Kota**, dan **Negara Bagian**, dan **Negara/Kawasan**  untuk membuat email yang lebih dipersonalisasi. Pilih **Tambah atribut** untuk memetakan bidang ini.

1. Pilih segmen yang ingin diekspor. Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke Marketo.

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). Di Marketo, Anda sekarang dapat menemukan segmen Anda dalam [daftar Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Marketo, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Marketo memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
