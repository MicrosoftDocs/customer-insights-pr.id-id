---
title: Mengekspor segmen ke AdRoll (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke AdRoll.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8110eab199920ab8fc2ea15678139faf264a242a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195754"
---
# <a name="export-segments-to-adroll-preview"></a>Mengekspor segmen ke AdRoll (pratinjau)

Mengekspor segmen profil pelanggan terpadu ke AdRoll dan menggunakannya untuk iklan.

## <a name="prerequisites"></a>Prasyarat

- Akun [AdRoll](https://www.adroll.com/) dan kredensial administrator yang sesuai.
- [ID Pengiklan AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Segmen yang](segments.md) dikonfigurasi di Customer Insights.
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 250.000 profil pelanggan per ekspor ke AdRoll, yang dapat memakan waktu hingga 10 menit untuk diselesaikan. Jumlah profil pelanggan yang dapat Anda ekspor ke AdRoll bergantung pada kontrak Anda dengan AdRoll.
- Segmen saja. Segmen harus berisi setidaknya 100 profil pelanggan.

## <a name="set-up-connection-to-adroll"></a>Konfigurasikan koneksi ke AdRoll

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **AdRoll**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **autentikasi dengan AdRoll** dan berikan kredensial admin Anda untuk AdRoll.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian AdRoll. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Masukkan **ID Pengiklan AdRoll** Anda.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
