---
title: Mengekspor segmen ke Omnisend (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Omnisend.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c23d6d3538c4df6006c14064f95379169af06622
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196168"
---
# <a name="export-segments-to-omnisend-preview"></a>Mengekspor segmen ke Omnisend (pratinjau)

Ekspor segmen profil pelanggan terpadu ke Omnisend dan gunakan untuk aktivitas pemasaran.

## <a name="prerequisites"></a>Prasyarat

- Akun [Omnisend](https://www.omnisend.com/) dan kredensial administrator yang sesuai.
- Kunci [API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).
- [Segmen yang](segments.md) dikonfigurasi di Customer Insights.
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil pelanggan per ekspor ke Omnisend, yang dapat memakan waktu hingga empat jam untuk diselesaikan. Jumlah profil pelanggan yang dapat Anda ekspor ke Omnisend tergantung pada kontrak Anda dengan Omnisend.
- Segmen saja.

## <a name="set-up-connection-to-omnisend"></a>Konfigurasikan koneksi ke Omnisend

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Akhirat**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan kunci API Omnisend Anda.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Omnisend. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan.

1. Secara opsional, ekspor **nama depan**, **nama belakang**, **Alamat**, **Negara/Wilayah**, **Negara Bagian**, **Kota**, dan **Kode** Pos untuk membuat email yang lebih dipersonalisasi. Pilih **Tambah atribut** untuk memetakan bidang ini.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
