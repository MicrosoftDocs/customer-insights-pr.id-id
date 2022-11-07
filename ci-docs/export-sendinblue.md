---
title: Mengekspor segmen ke Sendinblue (pratinjau)
description: Pelajari lebih lanjut cara mengkonfigurasi sambungan dan mengekspor ke Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724898"
---
# <a name="export-segments-to-sendinblue-preview"></a>Mengekspor segmen ke Sendinblue (pratinjau)

Ekspor segmen profil pelanggan terpadu untuk membuat kampanye, menyediakan pemasaran melalui email, dan menggunakan grup pelanggan tertentu dengan Sendinblue.

## <a name="prerequisites"></a>Prasyarat

- Akun [Sendinblue](https://www.sendinblue.com/) dan kredensial administrator yang sesuai.
- Kunci [API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Daftar yang ada di Sendinblue dan ID yang sesuai.
- [Segmen yang dikonfigurasi](segments.md).
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Tautan pribadi yang dikombinasikan dengan Bring your own storage (BYOS) tidak didukung.
- Hingga 1 juta profil pelanggan per ekspor ke Sendinblue, yang dapat memakan waktu hingga 90 menit untuk diselesaikan. Jumlah profil pelanggan yang dapat Anda ekspor ke Sendinblue tergantung pada kontrak Anda dengan Sendinblue.
- Segmen saja.

## <a name="set-up-connection-to-sendinblue"></a>Konfigurasikan sambungan ke Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Sendinblue**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan kunci **API SendinBlue Anda**.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Di bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Sendinblue. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Masukkan ID **daftar Sendinblue Anda**.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan.

1. Secara opsional, ekspor **nama depan**, nama belakang **,** dan **Telepon** untuk membuat email yang lebih dipersonalisasi. Pilih **Tambah atribut** untuk memetakan bidang ini.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
