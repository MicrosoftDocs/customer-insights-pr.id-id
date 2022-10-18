---
title: Mengekspor segmen ke Braze (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 2f52eb8196e057f934c8d2b5ac0518ce121606b6
ms.sourcegitcommit: 003c1929f730d7d505c108aba84f6269f4c98978
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/12/2022
ms.locfileid: "9655298"
---
# <a name="export-segments-to-braze-preview"></a>Mengekspor segmen ke Braze (pratinjau)

Ekspor segmen profil pelanggan terpadu ke Braze dan gunakan untuk kegiatan pemasaran.

## <a name="prerequisites"></a>Prasyarat

- Akun [Braze](https://www.braze.com/) dan kredensial administrator yang sesuai.
- Kunci [API Braze](https://www.braze.com/docs/api/basics/)
- Braze REST Anda [titik akhir](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Segmen yang](segments.md) dikonfigurasi di Customer Insights.
- Profil pelanggan terpadu dalam segmen yang diekspor berisi bidang yang mewakili alamat email dan ID pelanggan Braze.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil pelanggan ke Braze, yang dapat memakan waktu hingga 40 menit untuk diselesaikan. Jumlah profil pelanggan yang dapat Anda ekspor ke Braze tergantung pada kontrak Anda dengan Braze.
- Segmen saja.
- Azure Private Link tidak didukung untuk ekspor Braze.

## <a name="set-up-connection-to-braze"></a>Menyiapkan koneksi ke Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Braze**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan kunci API Braze Anda untuk terus masuk.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Sambungkan** untuk menginisialisasi koneksi.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Di **bidang Koneksi untuk ekspor**, pilih koneksi dari bagian Braze. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan titik akhir REST Anda ke **dalam bidang Nama** Host dalam format berikut:`rest.iad-03.braze.com`.

1. Masukkan nama untuk ekspor.

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan. **Di bidang ID Pelanggan, pilih bidang yang mewakili ID** Braze pelanggan. Segmen di Braze akan dibuat dengan nama segmen yang sama seperti di Dynamics 365 Customer Insights. Anda dapat memilih lebih banyak bidang opsional untuk mencocokkan data.

1. Pilih entitas atau segmen yang ingin Anda ekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
