---
title: Ekspor segmen ke Iterable (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ccf10b6e3a28a75f9d1bd3d8da3bf870ebc2b1b2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195433"
---
# <a name="export-segments-to-iterable-preview"></a>Ekspor segmen ke Iterable (pratinjau)

Ekspor segmen profil pelanggan terpadu ke Iterable dan gunakan untuk kegiatan pemasaran.

## <a name="prerequisites"></a>Prasyarat

- Akun [iterable](https://iterable.com/) dan kredensial administrator yang sesuai.
- Kunci [API yang Dapat Diulang](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Segmen yang](segments.md) dikonfigurasi di Customer Insights.
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil pelanggan ke Iterable, yang dapat memakan waktu hingga 30 menit untuk diselesaikan. Jumlah profil pelanggan yang dapat Anda ekspor ke Iterable tergantung pada kontrak Anda dengan Iterable.
- Segmen saja.

## <a name="set-up-connection-to-iterable"></a>Menyiapkan koneksi ke Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Dapat Diulang**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan kunci API Iterable Anda untuk terus masuk.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Di **bidang Koneksi untuk ekspor**, pilih koneksi dari bagian Iterable. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan. Daftar yang dibuat di Iterable akan menerima nama yang sama persis dengan nama segmen Anda di Dynamics 365 Customer Insights.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
