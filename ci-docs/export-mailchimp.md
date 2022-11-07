---
title: Mengekspor segmen ke Mailchimp (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Mailchimp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d74672768afec94e899ff0aec8c118c2afcde368
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725036"
---
# <a name="export-segments-to-mailchimp-preview"></a>Mengekspor segmen ke Mailchimp (pratinjau)

Ekspor segmen profil pelanggan terpadu ke MailChimp untuk membuat kampanye newsletter dan email.

## <a name="prerequisites"></a>Prasyarat

- Akun [Mailchimp](https://mailchimp.com/) dan kredensial administrator yang sesuai.
- [Audiens yang ada di Mailchimp](https://mailchimp.com/help/create-audience/) dan ID audiens yang [sesuai](https://mailchimp.com/help/find-audience-id/).
- [Segmen yang dikonfigurasi](segments.md).
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Tautan pribadi yang dikombinasikan dengan Bring your own storage (BYOS) tidak didukung.
- Hingga 1 juta profil pelanggan per ekspor ke Mailchimp, yang dapat memakan waktu hingga tiga jam. Jumlah profil pelanggan yang dapat Anda ekspor ke Mailchimp tergantung pada kontrak Anda dengan Mailchimp.
- Segmen saja.

## <a name="set-up-connection-to-mailchimp"></a>Konfigurasikan koneksi ke Mailchimp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Mailchimp**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **autentikasi dengan Mailchimp** dan berikan kredensial Mailchimp Anda.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Mailchimp. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Masukkan ID **audiens Mailchimp Anda**.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan.

1. Secara opsional, ekspor **nama depan** dan **nama belakang** untuk membuat email yang lebih dipersonalisasi. Pilih **Tambah atribut** untuk memetakan bidang ini.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
