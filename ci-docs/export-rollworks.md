---
title: Mengekspor segmen ke RollWorks (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d857bf5d11de86521c4a9d4fc665c020496d89d2
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725129"
---
# <a name="export-segments-to-rollworks-preview"></a>Mengekspor segmen ke RollWorks (pratinjau)

Ekspor segmen profil pelanggan terpadu ke RollWorks dan gunakan untuk periklanan.

## <a name="prerequisites"></a>Prasyarat

- Akun [RollWorks](https://www.rollworks.com/) dan kredensial administrator yang sesuai.
- [ID Pengiklan RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Segmen yang](segments.md) dikonfigurasi di Customer Insights.
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Tautan pribadi yang dikombinasikan dengan Bring your own storage (BYOS) tidak didukung.
- Hingga 250.000 profil pelanggan per ekspor ke RollWorks, yang dapat memakan waktu hingga 10 menit untuk diselesaikan. Jumlah profil pelanggan yang dapat Anda ekspor ke RollWorks tergantung pada kontrak Anda dengan RollWorks.
- Segmen saja.

## <a name="set-up-connection-to-rollworks"></a>Konfigurasikan koneksi ke RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **RollWorks**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini.  Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **Autentikasi dengan RollWorks** dan berikan kredensial admin Anda untuk RollWorks.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian RollWorks. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Masukkan ID **Pengiklan RollWorks Anda**.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
