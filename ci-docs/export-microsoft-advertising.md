---
title: Mengekspor segmen ke Microsoft Advertising (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Microsoft Advertising.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca37159ec6473ad5c331a0ce1aa8424d277529ff
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082807"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Mengekspor segmen ke Microsoft Advertising (pratinjau)

Ekspor segmen Customer Insights ke Microsoft Advertising untuk membuat audiens Customer Match. Gunakan audiens ini untuk kampanye iklan Anda.

## <a name="prerequisites"></a>Prasyarat

-   [Akun Microsoft Advertising](https://ads.microsoft.com/) dan kredensial administrator terkait.
-   Anda telah menerima ketentuan penggunaan Customer Match. 
-   [Segmen yang](segments.md) dikonfigurasi di Customer Insights.
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang dengan alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Anda dapat mengekspor hingga 500.000 profil pelanggan per ekspor ke Microsoft Advertising.
- Mengekspor ke Microsoft Advertising terbatas pada segmen.
- Mengekspor hingga 500.000 profil pelanggan ke Microsoft Advertising dapat berlangsung selama 10 menit. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Siapkan sambungan ke Microsoft Advertising

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Microsoft Advertising** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Default-nya adalah administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi ke Microsoft Advertising.

1. Pilih **Autentikasi dengan Microsoft Advertising** dan berikan kredensial admin Anda untuk Microsoft Advertising.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Microsoft Advertising. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Pilih segmen yang akan diekspor. Audiens Customer Match di Microsoft Advertising secara otomatis dibuat dengan nama segmen yang dipilih untuk diekspor. Setiap segmen akan menghasilkan audiens Customer Match terpisah. 

1. Masukkan **ID Pelanggan Microsoft Advertising dan ID Akun** Anda. Anda dapat menemukan ID Pelanggan (`cid`) dan ID Akun (`aid`) dalam parameter URL saat Anda masuk ke Microsoft Advertising.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang dengan alamat email pelanggan. Segmen harus diekspor ke Microsoft Advertising.

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Microsoft Advertising, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa Microsoft Advertising memenuhi kewajiban privasi atau keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.
