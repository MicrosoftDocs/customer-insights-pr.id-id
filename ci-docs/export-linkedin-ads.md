---
title: Mengekspor segmen ke LinkedIn Ads (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 06eb915e352ad545f95e96e6108be0f81f43a451
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725312"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Mengekspor segmen ke LinkedIn Ads (pratinjau)

Ekspor segmen profil pelanggan terpadu ke Iklan LinkedIn untuk membuat audiens yang cocok. Gunakan Matched Audiences untuk penargetan perusahaan dan penargetan kontak.

## <a name="prerequisites"></a>Prasyarat

- Akun [LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) dan kredensial administrator yang sesuai.
- ID [LinkedIn Campaign Manager Akun](https://www.linkedin.com/help/lms/answer/a424270).
- [Segmen yang](segments.md) dikonfigurasi di Customer Insights.
- Segmen yang diekspor memerlukan setidaknya satu bidang tertentu tergantung apakah Anda memilih [penargetan kontak atau](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) penargetan [perusahaan](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) di LinkedIn. Bidang yang mungkin tercantum dalam **langkah Pencocokan** data saat [mengonfigurasi ekspor](#configure-an-export).

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Tautan pribadi yang dikombinasikan dengan Bring your own storage (BYOS) tidak didukung.
- Hingga 100.000 profil pelanggan per ekspor ke Iklan LinkedIn, yang dapat memakan waktu hingga 10 menit untuk diselesaikan.
- Segmen saja. Segmen harus berisi setidaknya 300 profil unik.

## <a name="set-up-connection-to-linkedin-ads"></a>Menyiapkan koneksi ke Iklan LinkedIn

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Iklan** LinkedIn.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan ID Akun Anda LinkedIn Campaign Manager.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **Autentikasi dengan LinkedIn** dan berikan kredensial admin Anda untuk LinkedIn Campaign Manager.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian LinkedIn Ads. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Pilih apakah Anda ingin mengekspor data untuk melakukan [penargetan kontak](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) atau [penargetan perusahaan](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) di LinkedIn.

1. Di bagian **Pencocokan data**, untuk penargetan kontak, pilih sekurangnya satu bidang yang menunjukkan alamat email pelanggan, ID Iklan Apple, ID Iklan Google, ID Pengguna Google, atau nama depan dan belakang. Jika Anda memilih penargetan perusahaan, pilih sekurangnya satu bidang yang menunjukkan nama perusahaan, domain email, URL halaman LinkedIn, simbol Stock, atau Situs Web.

1. Secara opsional, tambahkan bidang untuk menentukan ekspor Anda lebih lanjut. Pilih **Tambah atribut** untuk memetakan bidang ini.

1. Pilih segmen yang ingin diekspor. Audiens yang cocok di LinkedIn Campaign Manager akan secara otomatis dibuat dengan nama segmen yang Anda pilih untuk diekspor. Setiap segmen akan menghasilkan audiens yang cocok terpisah.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
