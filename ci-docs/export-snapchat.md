---
title: Mengekspor segmen ke Snapchat (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195386"
---
# <a name="export-segments-to-snapchat-preview"></a>Mengekspor segmen ke Snapchat (pratinjau)

Ekspor segmen profil pelanggan terpadu ke Snapchat dan gunakan untuk periklanan.

## <a name="prerequisites"></a>Prasyarat

- Akun [Snapchat Business,](https://business.snapchat.com/) akun [Iklan](https://ads.snapchat.com/) Snapchat, dan kredensial administrator terkait. Anda setidaknya harus menjadi anggota Akun Organisasi dan Manajer Data dari Akun Iklan tertentu.
- Setidaknya satu audiens di Snapchat audiens manajer jenis SAM (Snap audiens Match).
- [Id Segmen/audiens Snapchat](https://businesshelp.snapchat.com/s/article/custom-audiences). ID audiens dapat ditemukan di URL setelah memilih audiens di Audiens Manager Snapchat.
- [Segmen yang](segments.md) dikonfigurasi di Customer Insights.
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil pelanggan, yang dapat memakan waktu hingga 15 menit untuk diselesaikan.
- Segmen saja.

## <a name="set-up-connection-to-snapchat"></a>Konfigurasikan koneksi ke Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Snapchat**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **Autentikasi dengan Snapchat** dan berikan kredensial admin Anda untuk Snapchat.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Snapchat. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. **Masukkan ID** Segmen/audiens Snapchat.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
