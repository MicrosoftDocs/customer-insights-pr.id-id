---
title: Ekspor data Customer Insights ke Azure Data Lake Storage Gen2
description: Pelajari cara mengkonfigurasi sambungan ke Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477183"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Konektor untuk Azure Data Lake Storage Gen2 (pratinjau)

Simpan data Customer Insights Anda di Azure Data Lake Storage Gen2 atau gunakan untuk mentransfer data ke aplikasi lainnya.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Mengkonfigurasi konektor untuk Azure Data Lake Storage Gen2

1. Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.

1. Dalam **Azure Data Lake Storage Gen2**, pilih **Konfigurasi**.

1. Beri nama yang dikenali di bidang **nama tampilan** tujuan anda.

1. Masukkan **Nama akun**, **Kunci akun**, dan **Wadah** untuk Azure Data Lake Storage Gen2 Anda.
    - Untuk mempelajari cara membuat akun penyimpanan yang akan digunakan dengan Azure Data Lake Storage Gen2, lihat [Membuat akun penyimpanan](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Untuk mempelajari lebih lanjut tentang cara menemukan nama akun dan kunci akun penyimpanan Azure Data Lake Gen2, lihat [Mengelola pengaturan akun penyimpanan di portal Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Pilih **Selanjutnya**.

1. Centang kotak di samping masing-masing entitas yang akan diekspor ke tujuan ini.

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengekspor data

Anda dapat [mengekspor data sesuai permintaan](export-destinations.md#export-data-on-demand). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).
