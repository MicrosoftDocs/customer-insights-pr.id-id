---
title: Ekspor segmen ke MoEngage
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: df38e9e88a9c116252fba26983b5f3711b46f051
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725270"
---
# <a name="export-segments-to-moengage-preview"></a>Mengekspor segmen ke MoEngage (pratinjau)

Ekspor segmen profil pelanggan terpadu ke MoEngage dan gunakan untuk pemasaran email di MoEngage.

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk koneksi

- [Akun](https://www.moengage.com/) MoEngage dan kredensial administrator yang sesuai.
- Kunci API MoEngage dari Pengaturan > API di MoEngage.
- [Segmen yang](segments.md) dikonfigurasi di Customer Insights.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Tautan pribadi yang dikombinasikan dengan Bring your own storage (BYOS) tidak didukung.
- Hingga 100.000 profil pelanggan per ekspor ke MoEngage, yang dapat memakan waktu hingga 15 menit. Jumlah profil pelanggan yang dapat Anda ekspor ke MoEngage bergantung pada kontrak Anda dengan MoEngage.
- Segmen saja.

## <a name="set-up-connection-to-moengage"></a>Menyiapkan koneksi ke MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi dan pilih** MoEngage **untuk mengonfigurasi koneksi**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan ID API Data MoEngage dan kunci API [Anda](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi ke MoEngage.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Di **bidang Koneksi untuk ekspor**, pilih koneksi dari bagian MoEngage. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan. Ulangi langkah yang sama untuk bidang opsional lainnya.

1. Pilih segmen yang ingin diekspor. Kami akan membuat satu atau beberapa segmen dengan nama yang sama dengan segmen yang dipilih di MoEngage di bawah **Segmen** > **Kustom Segmen**.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
