---
title: Menyerap data dari Azure Synapse Analytics
description: Gunakan database sebagai Azure Synapse sumber data di Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6f94cdbcc203fc4518544f7a945bd80e871b36c1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011431"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Azure Synapse Analytics Menyambungkan sumber data (pratinjau)

Azure Synapse Analytics adalah layanan analitik perusahaan yang mempercepat waktu untuk wawasan di seluruh gudang data dan sistem big data. Azure Synapse Analytics menyatukan teknologi SQL terbaik yang digunakan dalam pergudangan data perusahaan, teknologi Spark yang digunakan untuk big data, Data Explorer untuk analitik log dan deret waktu, Pipeline untuk integrasi data dan ETL/ELT, dan integrasi mendalam dengan layanan Azure lainnya seperti Power BI, Cosmos DB, dan AzureML.

Untuk informasi selengkapnya, lihat [Azure Synapse gambaran umum](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prasyarat

> [!IMPORTANT]
> Pastikan untuk menetapkan semua **penugasan peran** seperti dijelaskan.  

**Dalam Wawasan** Pelanggan:

* Anda memiliki **peran Administrator** di Customer Insights. Pelajari selengkapnya tentang [izin pengguna di Customer Insights](permissions.md#assign-roles-and-permissions).

**Di Azure**:

- Langganan Azure aktif.

- Jika menggunakan akun Gen2 baru Azure Data Lake Storage, *perwakilan layanan untuk Customer Insights* memerlukan **data Blob Penyimpanan kontributor** izin. Pelajari selengkapnya tentang [terhubung ke perwakilan Azure Data Lake Storage layanan dengan perwakilan layanan untuk Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **harus mengaktifkan** [ruang nama hierarkis](/azure/storage/blobs/data-lake-storage-namespace).

- Pada grup sumber daya tempat Azure Synapse ruang kerja berada, *perwakilan* layanan dan *pengguna untuk Customer Insights* harus ditetapkan setidaknya **Pembaca** izin. Untuk informasi lebih lanjut, lihat [Menetapkan peran Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

- *Pengguna* memerlukan izin **kontributor Data Blob Penyimpanan** di akun Azure Data Lake Storage Gen2 dengan data berada dan ditautkan ke ruang kerja Azure Synapse. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identitas yang dikelola Ruang kerja Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* memerlukan memerlukan izin **kontributor Data Blob Penyimpanan** di akun Azure Data Lake Storage Gen2 dengan data berada dan ditautkan ke ruang kerja Azure Synapse. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Di ruang Azure Synapse kerja, *perwakilan layanan untuk Customer Insights* memerlukan **peran Synapse Administrator** yang ditetapkan. Untuk informasi lebih lanjut, lihat [Cara mengkonfigurasi kontrol akses untuk ruang kerja Synapse Anda](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Menyambungkan ke database data lake di Azure Synapse Analytics

1. Buka **Data** > **Sumber data**.

1. Pilih **Tambahkan sumber data**.

1. **Azure Synapse Analytics Pilih metode (Pratinjau**).

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Kotak dialog untuk menyambungkan ke data Synapse Analytics":::
  
1. **Masukkan Nama** untuk sumber data dan Deskripsi **opsional**.

1. Pilih koneksi [yang](connections.md) tersedia ke Azure Synapse Analytics atau buat yang baru.

1. **Pilih Database** dari ruang kerja yang tersambung dalam koneksi yang Azure Synapse Analytics dipilih dan pilih **Berikutnya**.

1. Pilih entitas yang akan diserap dari database yang terhubung dan pilih **Berikutnya**.

1. Secara opsional, pilih entitas data untuk mengizinkan pembuatan profil data.

1. Pilih **Simpan** untuk menerapkan pilihan Anda dan mulai penyerapan data dari sumber data yang baru Anda buat yang ditautkan ke tabel database Lake di Azure Synapse Analytics. Halaman **Sumber data** terbuka memperlihatkan sumber data baru dalam **status Refresh**.
