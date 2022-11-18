---
title: Mengekspor segmen ke Criteo (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 811752da943cd5e40608d48644a1744c7971d3c8
ms.sourcegitcommit: 40ae3322ac95913e485607494754dd03814e42bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760030"
---
# <a name="export-segments-to-criteo-preview"></a>Mengekspor segmen ke Criteo (pratinjau)

Ekspor segmen profil pelanggan terpadu untuk menghasilkan kampanye, menyediakan pemasaran email, dan menggunakan grup pelanggan tertentu dengan Criteo.

## <a name="prerequisites"></a>Prasyarat

- Akun [Penargetan](https://www.criteo.com/login/) Ulang Criteo Dynamics dan kredensial administrator yang sesuai.
- [Segmen yang dikonfigurasi](segments.md).
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil pelanggan per ekspor ke Criteo, yang dapat memakan waktu hingga 30 menit untuk diselesaikan. Jumlah profil pelanggan yang dapat Anda ekspor ke Criteo bergantung pada kontrak Anda dengan Criteo.
- Segmen saja.

## <a name="set-up-connection-to-criteo"></a>Menyiapkan koneksi ke Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Criteo**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **Autentikasi dengan Criteo dan berikan nama pengguna dan kredensial Admin Anda untuk Criteo** .

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Di **bidang Koneksi untuk ekspor**, pilih koneksi dari bagian Criteo. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
