---
title: Menelan data dari Azure Synapse Analytics
description: Gunakan database sebagai Azure Synapse sumber data di Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642650"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse Menyambungkan sumber data (pratinjau)

Azure Synapse Analytics adalah layanan analitik perusahaan yang mempercepat waktu untuk wawasan di seluruh gudang data dan sistem data besar. Azure Synapse Analytics menyatukan yang terbaik dari teknologi SQL yang digunakan dalam pergudangan data perusahaan, teknologi Spark yang digunakan untuk data besar, Data Explorer untuk analitik log dan deret waktu, Pipelines untuk integrasi data dan ETL/ELT, dan integrasi mendalam dengan layanan Azure lainnya seperti Power BI,, Cosmos DB dan AzureML.

Untuk informasi selengkapnya, lihat [Azure Synapse gambaran umum](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prasyarat

Prasyarat berikut harus dipenuhi untuk mengonfigurasi koneksi dari Dynamics 365 Customer Insights ke Azure Synapse.

> [!IMPORTANT]
> Pastikan untuk menetapkan semua **penugasan peran** seperti dijelaskan.  

## <a name="prerequisites-in-customer-insights"></a>Prasyarat di Customer Insights

* Anda memiliki **peran Administrator** dalam Wawasan Pelanggan. Pelajari izin pengguna lebih [lanjut di Customer Insights](permissions.md#assign-roles-and-permissions).

Di Azure: 

- Langganan Azure aktif.

- Jika menggunakan akun Gen2 baru Azure Data Lake Storage, *perwakilan layanan untuk Customer Insights* memerlukan **izin kontributor** Storage Blob Data. Pelajari lebih lanjut cara [menyambungkan ke perwakilan Azure Data Lake Storage layanan untuk Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **harus mengaktifkan** [ruang nama hierarkis](/azure/storage/blobs/data-lake-storage-namespace).

- Pada grup Azure Synapse sumber daya ruang kerja berada, *perwakilan* layanan dan *pengguna untuk Wawasan* Pelanggan perlu ditetapkan setidaknya **Pembaca** izin. Untuk informasi lebih lanjut, lihat [Menetapkan peran Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

- *Pengguna* memerlukan izin **kontributor Data Blob Penyimpanan** di akun Azure Data Lake Storage Gen2 dengan data berada dan ditautkan ke ruang kerja Azure Synapse. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identitas yang dikelola Ruang kerja Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* memerlukan memerlukan izin **kontributor Data Blob Penyimpanan** di akun Azure Data Lake Storage Gen2 dengan data berada dan ditautkan ke ruang kerja Azure Synapse. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Di ruang kerja, perwakilan *layanan untuk Customer Insights* membutuhkan **peran Administrator** Synapse yang ditetapkan. Untuk informasi lebih lanjut, lihat [Cara mengkonfigurasi kontrol akses untuk ruang kerja Synapse Anda](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Menyambungkan ke database danau data di Azure Synapse Analytics

1. Buka **Data** > **Sumber data**.

1. Pilih **Tambahkan sumber data**.

1. **Azure Synapse Analytics Pilih metode (Pratinjau**).

1. Berikan **nama** untuk sumber data, lalu pilih **berikutnya** untuk membuat sumber data. 

1. Pilih koneksi [yang](connections.md) tersedia atau Azure Synapse Analytics buat yang baru.

1. **Pilih Database** Danau dari ruang kerja yang terhubung dalam koneksi yang Azure Synapse Analytics dipilih dan pilih **Berikutnya**.

1. Pilih entitas yang akan diserap dari database yang terhubung. 

1. Secara opsional, pilih entitas data untuk mengizinkan pembuatan profil data. 

1. Pilih **Simpan** untuk menerapkan pilihan Anda dan mulai konsumsi data dari sumber data yang baru Anda buat yang ditautkan ke tabel database Lake di Azure Synapse Analytics.
