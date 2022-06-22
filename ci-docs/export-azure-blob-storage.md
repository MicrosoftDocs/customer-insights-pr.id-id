---
title: Mengekspor data Customer Insights ke Penyimpanan Azure Blob
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke penyimpanan Blob.
ms.date: 06/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 623926bf520b19ee4156b7a05e953241cd819e9e
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947142"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Mengekspor daftar segmen dan data lainnya ke Penyimpanan Blob Azure (pratinjau)

Simpan data Customer Insights Anda di penyimpanan Blob atau gunakan untuk mentransfer data ke aplikasi lainnya.

## <a name="known-limitations"></a>Pembatasan yang diketahui

1. Untuk Azure Blob Storage, Anda dapat memilih antara [tingkat performa Standar dan performa Premium](/azure/storage/blobs/storage-blob-performance-tiers). Jika Anda memilih tingkat performa Premium, pilih [blob blok premium sebagai jenis akun](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Siapkan sambungan ke penyimpanan Blob

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **penyimpanan Blob Azure** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **Nama akun**, **Kunci akun**, dan **Wadah** untuk akun penyimpanan Blob Anda.
    - Untuk mempelajari selengkapnya tentang cara menemukan nama akun penyimpanan Blob dan kunci akun, lihat [Mengelola pengaturan akun penyimpanan di portal Azure](/azure/storage/common/storage-account-manage).
    - Untuk mempelajari cara membuat penampung, lihat [membuat penampung](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pilih **Simpan** untuk menyelesaikan koneksi. 

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Jika Anda mengaktifkan pengaturan penghapusan lunak untuk akun Azure Blob Storage, ekspor akan gagal. Nonaktifkan penghapusan lunak untuk mengekspor data ke blob. Untuk informasi selengkapnya, lihat [Mengaktifkan penghapusan lunak blob](/azure/storage/blobs/soft-delete-blob-enable)

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Penyimpanan Blob Azure. Jika Anda tidak melihat nama bagian ini, maka tidak ada sambungan dari jenis ini yang tersedia untuk Anda.

1. Centang kotak di samping masing-masing entitas yang akan diekspor ke tujuan ini.

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).

Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).

Data yang diekspor disimpan dalam wadah Blob Storage yang dikonfigurasi. Jalur folder berikut dibuat secara otomatis dalam penampung:

- Untuk entitas sumber dan entitas yang dihasilkan oleh sistem:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Contoh: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
  
  > [!TIP]
  > Ekspor entitas yang berisi sejumlah besar data dapat menyebabkan beberapa file CSV di folder yang sama untuk setiap ekspor. Pemisahan ekspor terjadi karena alasan kinerja untuk meminimalkan waktu yang diperlukan untuk menyelesaikan ekspor.

- Model.json untuk entitas yang diekspor akan berada di tingkat %ExportDestinationName%.  
  - Contoh: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
