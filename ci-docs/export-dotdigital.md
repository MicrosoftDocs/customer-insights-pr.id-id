---
title: Mengekspor segmen ke DotDigital (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724990"
---
# <a name="export-segments-to-dotdigital-preview"></a>Mengekspor segmen ke DotDigital (pratinjau)

Ekspor segmen profil pelanggan terpadu ke buku alamat DotDigital dan gunakan untuk kampanye, pemasaran email, dan untuk membangun segmen pelanggan dengan DotDigital.

## <a name="prerequisites"></a>Prasyarat

- Akun [DotDigital](https://dotdigital.com/) dan [pengguna API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- ID DotDigital dari [buku alamat baru](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) atau yang sudah ada di DotDigital. ID dapat ditemukan di URL saat Anda memilih dan membuka buku alamat.
- [Segmen yang](segments.md) dikonfigurasi di Customer Insights.
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Tautan pribadi yang dikombinasikan dengan Bring your own storage (BYOS) tidak didukung.
- Hingga 1 juta profil pelanggan per ekspor ke DotDigital, yang dapat memakan waktu hingga tiga jam untuk diselesaikan karena keterbatasan di sisi penyedia. Jumlah profil pelanggan yang dapat Anda ekspor ke DotDigital tergantung pada kontrak Anda dengan DotDigital.
- Segmen saja.

## <a name="set-up-connection-to-dotdigital"></a>Konfigurasikan koneksi ke DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **DotDigital**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **nama pengguna dan sandi API DotDigital** Anda.

1. Masukkan ID **buku alamat DotDigital Anda**.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian DotDigital. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan.

1. Secara opsional, ekspor **nama depan, nama belakang**, Nama **lengkap, Jenis Kelamin**, **·** **dan** Kode **pos.**

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Di DotDigital, temukan segmen Anda di [buku](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) alamat DotDigital.

[!INCLUDE [footer-include](includes/footer-banner.md)]
