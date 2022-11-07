---
title: Mengekspor segmen ke Google Ads (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725082"
---
# <a name="export-segments-to-google-ads-preview"></a>Mengekspor segmen ke Google Ads (pratinjau)

Ekspor segmen profil pelanggan terpadu ke daftar audiens Google Ads dan gunakan untuk mengiklankan di Google Penelusuran, Gmail, YouTube, dan Google Display Network.

## <a name="prerequisites"></a>Prasyarat

- Akun [Google](https://ads.google.com/) Ads dan kredensial administrator yang sesuai.
- ID [pelanggan Google Ads](https://support.google.com/google-ads/answer/1704344).
- Persyaratan [Kebijakan](https://support.google.com/adspolicy/answer/6299717) Customer Match terpenuhi.
- Persyaratan [ukuran](https://support.google.com/google-ads/answer/7558048) daftar pemasaran ulang terpenuhi.
- [Segmen yang](segments.md) dikonfigurasi.
- Profil pelanggan terpadu dalam segmen yang diekspor berisi bidang yang mewakili alamat email, telepon, ID pengiklan seluler, ID pengguna pihak ketiga, atau alamat.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Tautan pribadi yang dikombinasikan dengan Bring your own storage (BYOS) tidak didukung.
- Ekspor hingga 1 juta profil pelanggan per ekspor ke Google Ads, yang dapat memakan waktu hingga 30 menit untuk diselesaikan karena keterbatasan di sisi penyedia.
- Segmen saja.
- Pencocokan di Google Ads dapat memakan waktu hingga 48 jam.

## <a name="set-up-connection-to-google-ads"></a>Konfigurasikan koneksi ke Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Google Ads**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan ID pelanggan Google Ads Anda.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **autentikasi dengan Google Ads** dan berikan kredensial Google Ads Anda.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Google Ads. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Pilih apakah akan menggunakan audiens yang sudah ada atau membuat yang baru:
   - Untuk memperbarui audiens Google Ads yang ada, masukkan ID [audiens Google Ads Anda](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Untuk membuat audiens baru, biarkan bidang ID audiens Google kosong. Customer Insights akan secara otomatis membuat audiens baru di akun Google Ads Anda dan menggunakan nama segmen yang diekspor.

1. **Di bagian Pencocokan** data, pilih satu atau beberapa bidang data untuk diekspor, dan pilih bidang yang mewakili bidang data terkait di Customer Insights.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
