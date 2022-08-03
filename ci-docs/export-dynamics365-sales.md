---
title: Ekspor segmen ke Dynamics 365 Sales (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195985"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Ekspor segmen ke Dynamics 365 Sales (pratinjau)

Gunakan data pelanggan Anda untuk membuat daftar pemasaran, alur kerja tindak lanjut, dan mengirim promosi dengan Dynamics 365 Sales.

## <a name="prerequisites"></a>Prasyarat

Rekaman kontak harus ada di Dynamics 365 Sales agar Anda dapat mengekspor segmen dari Customer Insights ke Sales. Baca lebih lanjut tentang cara menyerap kontak dari [Dynamics 365 Sales menggunakan Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Mengekspor segmen dari Customer Insights ke Sales tidak akan membuat catatan kontak baru dalam instans Sales. Catatan kontak dari Penjualan harus diserap dalam Customer Insights dan digunakan sebagai sumber data. Id pelanggan juga harus disertakan dalam entitas Pelanggan terpadu untuk memetakan ID pelanggan agar ID dapat dihubungi sebelum segmen dapat diekspor.

## <a name="known-limitations"></a>Pembatasan yang diketahui

Ekspor ke Dynamics 365 Sales dibatasi hingga 100.000 per segmen, yang dapat memakan waktu hingga 3 jam untuk diselesaikan.

## <a name="set-up-connection-to-sales"></a>Menyiapkan koneksi ke Penjualan

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Dynamics 365 Sales**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan URL Sales organisasi di **bidang alamat server**.

1. Di Bagian **akun admin server**, pilih **masuk** dan pilih akun Dynamics 365 Sales.

1. Petakan bidang ID pelanggan ke ID kontak Dynamics 365.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Dynamics 365 Sales. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Pilih bidang ID Kontak di entitas Pelanggan yang cocok dengan ID Kontak Dynamics 365.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
