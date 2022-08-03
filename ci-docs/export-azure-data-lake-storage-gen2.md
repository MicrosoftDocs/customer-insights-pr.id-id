---
title: Mengekspor data ke Azure Data Lake Storage Gen2 (pratinjau)
description: Pelajari cara mengkonfigurasi sambungan ke Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196444"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Mengekspor data ke Azure Data Lake Storage Gen2 (pratinjau)

Simpan data Customer Insights Anda di akun Data Lake Storage Gen2 atau gunakan untuk mentransfer data Anda ke aplikasi lain.

## <a name="prerequisites"></a>Prasyarat

- Akun [penyimpanan untuk digunakan dengan Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Untuk menemukan nama dan kunci akun penyimpanan, lihat [Mengelola pengaturan akun penyimpanan di portal Microsoft Azure](/azure/storage/common/storage-account-manage).
- Kontainer [Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Untuk Azure Data Lake Storage Gen2, pilih antara [performa Standar dan tingkat performa Premium](/azure/storage/blobs/create-data-lake-storage-account). Jika Anda memilih tingkat performa Premium, pilih [blob blok premium sebagai jenis akun](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Menyiapkan koneksi ke Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Azure Data Lake Gen 2**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **Nama akun**, **Kunci akun**, dan **Wadah** untuk Azure Data Lake Storage Gen2 Anda.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Di **bidang Koneksi untuk ekspor**, pilih koneksi dari bagian Azure Data Lake. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Masukkan nama folder untuk Azure Data Lake Storage penyimpanan Gen2.

1. Centang kotak di samping masing-masing entitas yang akan diekspor ke tujuan ini.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Data yang diekspor disimpan dalam wadah penyimpanan Azure Data Lake Gen 2 yang dikonfigurasi.

> [!TIP]
> Ekspor entitas yang berisi sejumlah besar data dapat menyebabkan beberapa file CSV di folder yang sama untuk setiap ekspor. Pemisahan ekspor terjadi karena alasan kinerja untuk meminimalkan waktu yang diperlukan untuk menyelesaikan ekspor.

[!INCLUDE [footer-include](includes/footer-banner.md)]
