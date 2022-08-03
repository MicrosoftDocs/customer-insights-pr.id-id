---
title: Mengekspor segmen ke Marketo (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195248"
---
# <a name="export-segments-to-marketo-preview"></a>Mengekspor segmen ke Marketo (pratinjau)

Ekspor segmen profil pelanggan terpadu untuk membuat kampanye, menyediakan pemasaran melalui email, dan gunakan grup pelanggan tertentu dengan Marketo.

## <a name="prerequisites"></a>Prasyarat

- Akun [Marketo](https://login.marketo.com/) dan kredensial administrator yang sesuai.
- [ID klien Marketo, rahasia Klien, dan NAMA Host rest titik akhir](https://developers.marketo.com/rest-api/authentication/).
- [Daftar yang ada di Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) dan ID yang sesuai.
- [Segmen yang dikonfigurasi](segments.md).
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil pelanggan per ekspor ke Marketo, yang dapat memakan waktu hingga 3 jam. Jumlah profil pelanggan yang dapat Anda ekspor ke Marketo tergantung pada kontrak Anda dengan Marketo.
- Segmen saja.

## <a name="set-up-connection-to-marketo"></a>Konfigurasikan koneksi ke Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Marketo**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan ID klien Marketo Anda **, rahasia Klien, dan NAMA Host** REST titik akhir. Hostname titik akhir REST adalah hanya hostname, tanpa https://. Contoh: xyz-abc-123.mktorest.com.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Marketo. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Masukkan ID **daftar Marketo Anda**. ID daftar adalah nilai yang semata-mata numerik. Misalnya, jika ID daftar Marketo Anda adalah ST12345A7, hapus karakter sebelum dan sesudah angka dan masukkan *12345*.

1. Di bagian **Pencocokan** data, pilih setidaknya satu bidang yang mewakili alamat email pelanggan atau ID Marketo pelanggan.

1. Secara opsional, ekspor **nama depan**, **nama belakang**, Kota **,** **Negara Bagian**, dan **Negara/Wilayah** untuk membuat email yang lebih dipersonalisasi. Pilih **Tambah atribut** untuk memetakan bidang ini.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Di Marketo, temukan segmen Anda di bawah [daftar](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) Marketo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
