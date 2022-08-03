---
title: Mengekspor segmen ke SendGrid (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196996"
---
# <a name="export-segments-to-sendgrid-preview"></a>Mengekspor segmen ke SendGrid (pratinjau)

Ekspor segmen profil pelanggan terpadu ke daftar kontak SendGrid dan gunakan untuk kampanye dan pemasaran email di SendGrid.

## <a name="prerequisites"></a>Prasyarat

- Akun [SendGrid](https://sendgrid.com/) dan kredensial administrator yang sesuai.
- [Daftar kontak yang ada di SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) dan ID yang sesuai.
- Kunci [API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Segmen yang](segments.md) dikonfigurasi di Customer Insights.
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 100.000 profil pelanggan secara total ke SendGrid, yang dapat memakan waktu hingga beberapa jam untuk diselesaikan. Jumlah profil pelanggan yang dapat Anda ekspor ke SendGrid tergantung pada kontrak Anda dengan SendGrid.
- Segmen saja.

## <a name="set-up-connection-to-sendgrid"></a>Konfigurasikan koneksi ke SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **SendGrid**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan kunci **API SendGrid Anda**.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian SendGrid. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Masukkan ID **daftar SendGrid Anda**.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan.

1. Secara opsional, pilih bidang seperti nama depan, nama belakang, Negara/Wilayah **,** Negara Bagian **,** Kota **, dan** kode **Pos.** **·** **·**

1. Pilih segmen yang ingin Anda ekspor mengikuti batasan yang diketahui.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
