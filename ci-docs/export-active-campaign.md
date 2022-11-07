---
title: Mengekspor segmen ke ActiveCampaign
description: Pelajari lebih lanjut cara mengkonfigurasi sambungan dan mengekspor ke ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725404"
---
# <a name="export-segments-to-activecampaign-preview"></a>Mengekspor segmen ke ActiveCampaign (pratinjau)

Mengekspor segmen profil pelanggan terpadu ke ActiveCampaign dan menggunakannya untuk aktivitas pemasaran.

## <a name="prerequisites"></a>Prasyarat

- Akun [ActiveCampaign](https://www.activecampaign.com/) dan kredensial administrator yang sesuai.
- [ID Daftar ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- [Kunci](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) API ActiveCampaign dan Nama Host REST titik akhir.
- [Segmen yang](segments.md) dikonfigurasi di Customer Insights.
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Tautan pribadi yang dikombinasikan dengan Bring your own storage (BYOS) tidak didukung.
- Hingga 1 juta profil pelanggan per ekspor ke ActiveCampaign, yang dapat memakan waktu hingga 90 menit untuk diselesaikan. Jumlah profil pelanggan yang dapat Anda ekspor ke ActiveCampaign tergantung pada kontrak Anda dengan ActiveCampaign.
- Segmen saja.

## <a name="set-up-connection-to-activecampaign"></a>Siapkan sambungan ke ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **ActiveCampaign**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan Hostname titik akhir REST dan Kunci API ActiveCampaign. Hostname titik akhir REST adalah hanya hostname, tanpa https://.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Di bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian ActiveCampaign. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Masukkan ID **Daftar ActiveCampaign Anda**.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan.

1. Secara opsional, ekspor **nama depan**, nama belakang **,** dan **Telepon** untuk membuat email yang lebih dipersonalisasi. Pilih **Tambah atribut** untuk memetakan bidang ini.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
