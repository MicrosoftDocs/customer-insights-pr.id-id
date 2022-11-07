---
title: Mengekspor segmen ke Campaign Monitor (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 82303c7bcb269ee68419c9639ee743e13451f273
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724688"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Mengekspor segmen ke Campaign Monitor (pratinjau)

Ekspor segmen profil pelanggan terpadu ke Campaign Monitor dan gunakan untuk aktivitas pemasaran.

## <a name="prerequisites"></a>Prasyarat

- Akun [Monitor](https://www.campaignmonitor.com/) Kampanye dan kredensial administrator yang sesuai.
- [ID Daftar Monitor Kampanye](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Kunci [API](https://www.campaignmonitor.com/api/getting-started/) yang Dihasilkan dari **Pengaturan** Akun di Monitor Kampanye untuk mendapatkan ID daftar API.
- [Segmen yang](segments.md) dikonfigurasi di Customer Insights.
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Tautan pribadi yang dikombinasikan dengan Bring your own storage (BYOS) tidak didukung.
- Hingga 1 juta profil pelanggan per ekspor ke Campaign Monitor, yang dapat memakan waktu hingga 20 menit untuk diselesaikan. Jumlah profil pelanggan yang dapat Anda ekspor ke Campaign Monitor bergantung pada kontrak Anda dengan Campaign Monitor.
- Segmen saja.

## <a name="set-up-connection-to-campaign-monitor"></a>Konfigurasikan koneksi ke Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Pemantau Kampanye**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi ke Campaign Monitor.

1. Pilih **Autentikasi dengan Campaign Monitor** dan berikan kredensial admin Anda untuk Campaign Monitor.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Campaign Monitor. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Masukkan ID **Daftar Monitor Kampanye Anda**.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan. Segmen harus diekspor ke Campaign Monitor.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
