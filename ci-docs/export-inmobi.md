---
title: Ekspor data Customer Insights ke InMobi
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059611"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Ekspor daftar segmen dan data lainnya ke InMobi (pratinjau)

Ekspor daftar segmen atau data lain dari instans Customer Insights Anda ke [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Prasyarat

1. Anda memiliki [akun](https://www.inmobi.com/) InMobi dan kredensial admin.
1. Anda memiliki nama akun penyimpanan Azure Blob dan kunci akun yang sesuai. Untuk informasi selengkapnya, lihat [Mengelola pengaturan akun penyimpanan di portal Microsoft Azure](/azure/storage/common/storage-account-manage). Ada kontainer di akun penyimpanan untuk mengekspor data inMobi. Untuk informasi selengkapnya, lihat [Membuat kontainer](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi akan membuat koneksi langsung ke Blob Storage Anda, dan mengonfigurasi impor otomatis data Anda ke InMobi. Hubungi perwakilan InMobi Anda untuk memulai prosesnya.

## <a name="known-limitations"></a>Pembatasan yang diketahui

1. Untuk Azure Blob Storage, Anda dapat memilih antara [Performa standar dan tingkat performa Premium](/azure/storage/blobs/storage-blob-performance-tiers). Jika Anda memilih tingkat performa Premium, pilih [blob blok premium sebagai jenis akun](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Menyiapkan koneksi ke Azure Blob Storage dan mengonfigurasi ekspor

1. Ikuti instruksi untuk [menyiapkan koneksi ke Azure Blob Storage](export-azure-blob-storage.md) Anda.
2. Ikuti petunjuk untuk [mengonfigurasi ekspor](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
