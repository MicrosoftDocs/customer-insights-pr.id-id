---
title: Mengekspor data Customer Insights ke LinkedIn Ads
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 948a7e980df5714034009c92282e78cf2bdcb231
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618295"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Mengekspor segmen ke LinkedIn Ads (pratinjau)

Ekspor segmen profil pelanggan terpadu ke Iklan LinkedIn untuk membuat audiens yang cocok. Gunakan Matched Audiences untuk penargetan perusahaan dan penargetan kontak.

## <a name="prerequisites"></a>Prasyarat

-   Anda memiliki [akun LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) dan kredensial administrator terkait.
-   Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.
-   Profil pelanggan di segmen yang diekspor berisi bidang dengan alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Anda dapat mengekspor hingga 100K profil pelanggan per ekspor ke LinkedIn Ads.
- Mengekspor ke LinkedIn Ads terbatas pada segmen.
- Mengekspor hingga 100K profil pelanggan ke LinkedIn Ads dapat berlangsung selama 10 menit. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Siapkan sambungan ke LinkedIn Ads

1. Dalam audiens wawasan, buka **Koneksi** > **Admin**.

1. Pilih **Tambahkan koneksi** dan pilih **LinkedIn Ads** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan [ID Akun LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270) Anda.

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi ke Campaign Monitor.

1. Pilih **Autentikasi dengan LinkedIn** dan berikan kredensial admin Anda untuk LinkedIn Campaign Manager.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian LinkedIn Ads. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Pilih apakah Anda ingin mengekspor data untuk melakukan [penargetan kontak](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) atau [penargetan perusahaan](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) di LinkedIn. 

1. Di bagian **Pencocokan data**, untuk penargetan kontak, pilih sekurangnya satu bidang yang menunjukkan alamat email pelanggan, ID Iklan Apple, ID Iklan Google, ID Pengguna Google, atau nama depan dan belakang. Jika Anda memilih penargetan perusahaan, pilih sekurangnya satu bidang yang menunjukkan nama perusahaan, domain email, URL halaman LinkedIn, simbol Stock, atau Situs Web. Bidang tambahan dapat dipilih untuk menentukan ekspor lebih lanjut. 

1. Pilih segmen yang ingin diekspor. Audiens yang cocok di LinkedIn Campaign Manager akan secara otomatis dibuat dengan nama segmen yang Anda pilih untuk diekspor. Setiap segmen akan menghasilkan audiens yang cocok terpisah. 

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke LinkedIn Ads, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa LinkedIn Ads memenuhi kewajiban privasi atau keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.
