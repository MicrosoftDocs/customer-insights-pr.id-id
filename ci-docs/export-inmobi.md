---
title: Ekspor data Customer Insights ke InMobi
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195892"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Ekspor data Customer Insights ke InMobi (pratinjau)

Ekspor daftar segmen atau data lain dari instans Customer Insights Anda ke [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Prasyarat

- Akun [InMobi](https://www.inmobi.com/) dan kredensial admin.
- Nama [akun](/azure/storage/blobs/create-data-lake-storage-account) dan kunci akun Azure Blob Storage. Untuk menemukan nama dan kunci, lihat [Mengelola pengaturan akun penyimpanan di portal Microsoft Azure](/azure/storage/common/storage-account-manage).
- Kontainer [Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) untuk mengekspor data InMobi.
- InMobi akan membuat koneksi langsung ke Blob Storage Anda, dan mengonfigurasi impor otomatis data Anda ke InMobi. Hubungi perwakilan InMobi Anda untuk memulai prosesnya.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Untuk Azure Blob Storage, pilih antara [Performa standar dan tingkat performa Premium](/azure/storage/blobs/storage-blob-performance-tiers). Jika Anda memilih tingkat performa Premium, pilih [blob blok premium sebagai jenis akun](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Menyiapkan koneksi ke Azure Blob Storage

[Siapkan koneksi ke Azure Blob Storage](export-azure-blob-storage.md) Anda.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[Mengonfigurasi ekspor](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
