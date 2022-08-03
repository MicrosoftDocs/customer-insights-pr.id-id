---
title: Mengekspor data ke Azure Blob Storage (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke penyimpanan Blob.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195708"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Mengekspor data ke Azure Blob Storage (pratinjau)

Simpan data Customer Insights Anda di penyimpanan Blob atau gunakan untuk mentransfer data ke aplikasi lainnya.

## <a name="prerequisites"></a>Prasyarat

- Nama [akun](/azure/storage/blobs/create-data-lake-storage-account) dan kunci akun Azure Blob Storage. Untuk menemukan nama dan kunci, lihat [Mengelola pengaturan akun penyimpanan di portal Microsoft Azure](/azure/storage/common/storage-account-manage).
- Kontainer [Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Untuk Azure Blob Storage, pilih antara [Performa standar dan tingkat performa Premium](/azure/storage/blobs/storage-blob-performance-tiers). Jika Anda memilih tingkat performa Premium, pilih [blob blok premium sebagai jenis akun](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Menyiapkan koneksi ke Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Azure Blob Storage**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **Nama akun**, **Kunci akun**, dan **Wadah** untuk akun penyimpanan Blob Anda.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Untuk mengonfigurasi ekspor ini, Anda harus memiliki [izin](export-destinations.md#set-up-a-new-export) untuk jenis koneksi ini.

> [!IMPORTANT]
> Jika Anda mengaktifkan [pengaturan penghapusan sementara](/azure/storage/blobs/soft-delete-blob-enable) untuk akun Azure Blob Storage, ekspor akan gagal. Nonaktifkan penghapusan lunak untuk mengekspor data ke blob.

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Penyimpanan Blob Azure. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Masukkan nama folder untuk penyimpanan Blob.

1. Centang kotak di samping masing-masing entitas yang akan diekspor ke tujuan ini.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Data yang diekspor disimpan dalam wadah Blob Storage yang dikonfigurasi. Jalur folder berikut dibuat secara otomatis dalam penampung:

- Untuk entitas sumber dan entitas yang dihasilkan oleh sistem:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Contoh: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Ekspor entitas yang berisi sejumlah besar data dapat menyebabkan beberapa file CSV di folder yang sama untuk setiap ekspor. Pemisahan ekspor terjadi karena alasan kinerja untuk meminimalkan waktu yang diperlukan untuk menyelesaikan ekspor.

- model.json untuk entitas yang diekspor berada di level tersebut *%ExportDestinationName%*.  
  
  Contoh: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
