---
title: Mengekspor segmen ke Microsoft Advertising (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196536"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Mengekspor segmen ke Microsoft Advertising (pratinjau)

Ekspor segmen Customer Insights ke Microsoft Advertising untuk membuat audiens Customer Match. Gunakan audiens ini untuk kampanye iklan Anda.

## <a name="prerequisites"></a>Prasyarat

- Akun [Periklanan](https://ads.microsoft.com/) Microsoft dan kredensial administrator yang sesuai.
- ID Pelanggan dan ID Akun Iklan Microsoft. Temukan ID Pelanggan (`cid`) dan ID Akun (`aid`) dalam parameter URL saat Anda masuk ke Periklanan Microsoft.
- Ketentuan penggunaan Customer Match diterima.
- [Segmen yang](segments.md) dikonfigurasi di Customer Insights.
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 500.000 profil pelanggan per ekspor ke Microsoft Advertising, yang dapat memakan waktu hingga 10 menit.
- Segmen saja.

## <a name="set-up-connection-to-microsoft-advertising"></a>Menyiapkan koneksi ke Periklanan Microsoft

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Periklanan Microsoft**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Default-nya adalah administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **ID** Pelanggan Periklanan Microsoft.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **Autentikasi dengan Microsoft Advertising** dan berikan kredensial admin Anda untuk Microsoft Advertising.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Microsoft Advertising. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Pilih segmen yang akan diekspor. Audiens Customer Match di Microsoft Advertising secara otomatis dibuat dengan nama segmen yang dipilih untuk diekspor. Setiap segmen akan menghasilkan audiens Customer Match terpisah.

1. Masukkan **ID Pelanggan Microsoft Advertising dan ID Akun** Anda.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang dengan alamat email pelanggan.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
