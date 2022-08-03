---
title: Mengekspor segmen ke LiveRamp (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan ekspor ke LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196720"
---
# <a name="export-segments-to-liverampreg-preview"></a>Mengekspor segmen ke LiveRamp&reg; (pratinjau)

Aktifkan data Anda di LiveRamp untuk terhubung dengan lebih dari 500 platform di seluruh digital, sosial, dan TV. Bekerja dengan data Anda di LiveRamp untuk menargetkan, menekan, dan mempersonalisasi kampanye iklan.

## <a name="prerequisites"></a>Prasyarat

- Langganan LiveRamp untuk menggunakan konektor ini. Untuk mendapatkan langganan, [hubungi langsung LiveRamp](https://liveramp.com/contact/). [Pelajari lebih lanjut tentang LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Ekspor LiveRamp menggunakan ekspor SFTP. Tujuan SFTP di belakang firewall saat ini tidak didukung.
- Jika Anda menggunakan kunci SSH untuk autentikasi, pastikan Anda [membuat kunci](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) privat sebagai pem atau format SSH.COM. Jika Anda menggunakan Putty, konversi kunci pribadi Anda dengan mengekspor adalah sebagai Open SSH. Format kunci pribadi berikut didukung:
  - RSA dalam format OpenSSL PEM dan ssh.com
  - DSA dalam format OpenSSL PEM dan ssh.com
  - ECDSA 256/384/521 dalam format Pem OpenSSL
  - ED25519 dan RSA dalam format kunci OpenSSH
- Runtime ekspor tergantung pada kinerja sistem Anda. Sebaiknya dua inti CPU dan memori 1 Gb sebagai konfigurasi minimal server Anda.
- Mengekspor entitas dengan hingga 100 juta profil pelanggan dapat berlangsung selama 90 menit bila menggunakan konfigurasi minimal yang disarankan untuk dua inti CPU dan 1 Gb memori.
- Jumlah sebenarnya dari profil (atau data) yang dapat Anda ekspor ke LiveRamp tergantung pada langganan Anda dengan LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Konfigurasikan koneksi ke LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **LiveRamp**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih apakah Anda ingin mengautentikasi melalui SSH atau nama pengguna/kata sandi untuk koneksi Anda dan berikan detail yang diperlukan.

1. Pilih **Verifikasikan** untuk menguji sambungan ke LiveRamp.

1. Setelah verifikasi berhasil, tinjau [privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian LiveRamp. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. **Di bidang Sambungkan data**, pilih **Email**, **Nama dan alamat**, atau **Telepon** untuk dikirim ke LiveRamp untuk resolusi identitas.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Konektor LiveRamp dengan pemetaan atribut.":::

1. Petakan atribut yang sesuai dari entitas *Pelanggan* untuk pengidentifikasi utama yang dipilih.

1. Pilih **Tambahkan atribut** untuk memetakan lebih banyak atribut untuk dikirim ke LiveRamp.

   > [!TIP]
   > Mengirimkan lebih banyak atribut pengidentifikasi kunci ke LiveRamp kemungkinan akan memberi Anda tingkat kecocokan yang lebih tinggi.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
