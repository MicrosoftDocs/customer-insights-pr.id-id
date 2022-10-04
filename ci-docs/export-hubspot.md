---
title: Ekspor data Customer Insights ke HubSpot
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588930"
---
# <a name="export-segments-to-hubspot-preview"></a>Mengekspor segmen ke HubSpot (pratinjau)

Ekspor segmen profil pelanggan terpadu ke HubSpot dan gunakan untuk pemasaran email.

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk koneksi

- Akun [HubSpot](https://www.hubspot.com/) dan kredensial administrator yang sesuai.
- [Kunci](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) API dari HubSpot.
- [Segmen yang](segments.md) dikonfigurasi di Customer Insights.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 100.000 profil pelanggan per ekspor ke HubSpot, yang dapat memakan waktu hingga 15 menit untuk diselesaikan. Jumlah profil pelanggan yang dapat Anda ekspor ke HubSpot tergantung dan terbatas pada kontrak Anda dengan HubSpot.
- Segmen saja.

## <a name="set-up-connection-to-hubspot"></a>Menyiapkan koneksi ke HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **HubSpot** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan kredensial HubSpot Anda saat diminta.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi ke HubSpot.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Di **bidang Koneksi untuk ekspor**, pilih koneksi dari bagian HubSpot. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan. Ulangi langkah yang sama untuk bidang opsional lainnya.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
