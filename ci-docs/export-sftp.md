---
title: Mengekspor data ke host SFTP (pratinjau) (berisi video)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke lokasi SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207233"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Mengekspor data ke host SFTP (pratinjau)

Gunakan data pelanggan Anda dalam aplikasi pihak ketiga dengan mengekspornya ke lokasi Secure File Transfer Protocol (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Prasyarat

- Ketersediaan host SFTP dan kredensial yang sesuai.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Tujuan SFTP di belakang firewall saat ini tidak didukung.
- Runtime ekspor tergantung pada kinerja sistem Anda. Sebaiknya dua inti CPU dan memori 1 Gb sebagai konfigurasi minimal server Anda.
- Hingga 100 juta profil pelanggan, yang dapat memakan waktu 90 menit saat menggunakan konfigurasi minimal yang disarankan dari dua inti CPU dan memori 1 Gb.
- Jika Anda menggunakan kunci SSH untuk autentikasi, pastikan Anda [membuat kunci](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) privat sebagai pem atau format SSH.COM. Jika Anda menggunakan Putty, konversi kunci pribadi Anda dengan mengekspor adalah sebagai Open SSH. Format kunci pribadi berikut didukung:
  - RSA dalam format OpenSSL PEM dan ssh.com
  - DSA dalam format OpenSSL PEM dan ssh.com
  - ECDSA 256/384/521 dalam format Pem OpenSSL
  - ED25519 dan RSA dalam format kunci OpenSSH

## <a name="set-up-connection-to-sftp"></a>Siapkan koneksi ke SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **SFTP**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih apakah Anda ingin mengautentikasi melalui SSH atau nama pengguna/kata sandi untuk koneksi Anda dan berikan detail yang diperlukan. Jika Anda menggunakan kunci SSH untuk autentikasi, pastikan Anda [membuat kunci](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) privat sebagai pem atau format SSH.COM. Jika Anda menggunakan Putty, konversi kunci pribadi Anda dengan mengekspor adalah sebagai Open SSH. Format kunci pribadi berikut didukung:
   - RSA dalam format OpenSSL PEM dan ssh.com
   - DSA dalam format OpenSSL PEM dan ssh.com
   - ECDSA 256/384/521 dalam format Pem OpenSSL
   - ED25519 dan RSA dalam format kunci OpenSSH

1. Pilih **Verifikasi** untuk menguji koneksi.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian SFTP. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Pilih jika Anda ingin mengekspor data **dengan di-zip** atau **tidak di-zip** dan **pembatas bidang** untuk file yang diekspor.

1. Pilih entitas, misalnya segmen, yang ingin Anda ekspor.

   > [!NOTE]
   > Setiap entitas yang dipilih akan dibagi menjadi maksimal lima file output saat diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> Ekspor entitas yang berisi sejumlah besar data dapat menyebabkan beberapa file CSV di folder yang sama untuk setiap ekspor. Pemisahan ekspor terjadi karena alasan kinerja untuk meminimalkan waktu yang diperlukan untuk menyelesaikan ekspor.

[!INCLUDE [footer-include](includes/footer-banner.md)]
