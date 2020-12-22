---
title: Mengekspor data Customer Insights ke penyimpanan Azure Blob
description: Pelajari cara mengkonfigurasi sambungan ke Penyimpanan Blob Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667143"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Konektor untuk Penyimpanan Blob Azure (pratinjau)

Simpan data Customer Insights Anda di Azure Data Lake storage atau gunakan untuk mentransfer data Anda ke aplikasi lain.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Konfigurasikan konektor untuk Penyimpanan Blob Azure

1. Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.

1. Di **Penyimpanan Blob Azure**, pilih **konfigurasi**.

1. Masukkan **nama akun**, **kunci akun**, dan **penampung** untuk akun penyimpanan Blob Azure Anda.
    - Untuk mempelajari lebih lanjut tentang cara menemukan kunci akun dan nama akun penyimpanan Azure Blob, lihat [mengelola pengaturan akun penyimpanan di portal Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Untuk mempelajari cara membuat penampung, lihat [membuat penampung](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Beri nama yang dikenali di bidang **nama tampilan** tujuan anda.

1. Pilih **Selanjutnya**.

1. Centang kotak di samping masing-masing entitas yang akan diekspor ke tujuan ini.

1. Pilih **Simpan**.

Data yang diekspor disimpan dalam wadah penyimpanan Azure Blob yang Anda konfigurasikan. Jalur folder berikut dibuat secara otomatis dalam penampung:

- Untuk entitas sumber dan entitas yang dihasilkan oleh sistem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Contoh: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model .JSON untuk entitas yang diekspor akan berada di tingkat %ExportDestinationName%
  - Contoh: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Mengekspor data

Anda dapat [mengekspor data sesuai permintaan](/export-destinations.md#export-data-on-demand). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).
