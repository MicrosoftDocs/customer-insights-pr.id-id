---
title: Ekspor data Customer Insights ke Azure Data Lake Storage Gen2
description: Pelajari cara mengkonfigurasi sambungan ke Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22eee11666752459a1750d728c4e254ab0c59e58
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947234"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Mengekspor daftar segmen dan data lainnya ke Azure Data Lake Storage Gen2 (pratinjau)

Simpan data Customer Insights Anda di akun Data Lake Storage Gen2 atau gunakan untuk mentransfer data Anda ke aplikasi lain.

## <a name="known-limitations"></a>Pembatasan yang diketahui

1. Untuk Azure Data Lake Storage Gen2, Anda dapat memilih antara [tingkat performa Standar dan tingkat performa Premium](/azure/storage/blobs/create-data-lake-storage-account) saat membuat akun penyimpanan untuk data lake. Jika Anda memilih tingkat performa Premium, pilih blob blok premium sebagai jenis akun.

## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Siapkan sambungan ke Azure Data Lake Storage Gen2

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Azure Data Lake Gen 2** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **Nama akun**, **Kunci akun**, dan **Wadah** untuk Azure Data Lake Storage Gen2 Anda.
    - Untuk mempelajari cara membuat akun penyimpanan yang akan digunakan dengan Azure Data Lake Storage Gen2, lihat [Membuat akun penyimpanan](/azure/storage/blobs/create-data-lake-storage-account). 
    - Untuk mempelajari selengkapnya tentang nama akun Azure Data Lake Gen 2 dan kunci akun, lihat [Mengelola pengaturan akun penyimpanan di portal Azure](/azure/storage/common/storage-account-manage).

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian **Azure Data Lake**. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Centang kotak di samping masing-masing entitas yang akan diekspor ke tujuan ini.

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).
Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).

Data yang diekspor disimpan dalam wadah penyimpanan Azure Data Lake Gen 2 yang dikonfigurasi.

> [!TIP]
> Ekspor entitas yang berisi sejumlah besar data dapat menyebabkan beberapa file CSV di folder yang sama untuk setiap ekspor. Pemisahan ekspor terjadi karena alasan kinerja untuk meminimalkan waktu yang diperlukan untuk menyelesaikan ekspor.

[!INCLUDE [footer-include](includes/footer-banner.md)]
