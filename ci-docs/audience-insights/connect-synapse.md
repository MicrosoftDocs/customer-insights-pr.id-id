---
title: Menelan data dari Azure Synapse Analytics
description: Gunakan database Azure Synapse sebagai sumber data di Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356047"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse Menyambungkan sumber data (pratinjau)

Azure Synapse Analytics adalah layanan analisis perusahaan yang mempercepat waktu untuk wawasan di seluruh gudang data dan sistem data besar. Azure Synapse Analytics menyatukan yang terbaik dari teknologi SQL yang digunakan dalam pergudangan data perusahaan, teknologi Spark yang digunakan untuk data besar, Data Explorer untuk analitik log dan deret waktu, Pipelines untuk integrasi data dan ETL / ELT, dan integrasi mendalam dengan layanan Azure lainnya seperti Power BI, Cosmos DB, dan AzureML.

Untuk informasi selengkapnya, lihat [Azure Synapse gambaran umum](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prasyarat

Prasyarat berikut harus dipenuhi untuk mengkonfigurasi sambungan dari Customer Insights ke Azure Synapse.

> [!IMPORTANT]
> Pastikan untuk menetapkan semua **penugasan peran** seperti dijelaskan.  

## <a name="prerequisites-in-customer-insights"></a>Prasyarat di Customer Insights

* Anda memiliki **peran Administrator** dalam Wawasan Pelanggan. Pelajari lebih lanjut tentang [izin pengguna di wawasan audiens](permissions.md#assign-roles-and-permissions).

Di Azure: 

- Langganan Azure aktif.

- Jika menggunakan akun Azure Data Lake Storage Gen2 baru, *prinsipal layanan untuk wawasan audiens* memerlukan izin **kontributor Data Blob penyimpanan**. Pelajari lebih lanjut cara [menyambungkan ke Azure Data Lake Storage prinsipal layanan untuk audiens wawasan](connect-service-principal.md). Data Lake Storage Gen2 **harus mengaktifkan** [ruang nama hierarkis](/azure/storage/blobs/data-lake-storage-namespace).

- Pada grup sumber daya, tempat ruang kerja Azure Synapse terletak, *prinsipal layanan* dan *pengguna wawasan audiens* harus ditetapkan sekurangnya izin **Pembaca**. Untuk informasi lebih lanjut, lihat [Menetapkan peran Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

- *Pengguna* memerlukan izin **kontributor Data Blob Penyimpanan** di akun Azure Data Lake Storage Gen2 dengan data berada dan ditautkan ke ruang kerja Azure Synapse. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identitas yang dikelola Ruang kerja Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* memerlukan memerlukan izin **kontributor Data Blob Penyimpanan** di akun Azure Data Lake Storage Gen2 dengan data berada dan ditautkan ke ruang kerja Azure Synapse. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Di ruang kerja Azure Synapse, *prinsipal layanan untuk wawasan audiens* memerlukan **penetapan peran Administrator Synapse**. Untuk informasi lebih lanjut, lihat [Cara mengkonfigurasi kontrol akses untuk ruang kerja Synapse Anda](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Menyambungkan ke database data lake di Azure Synapse Analytics

1. Buka **Data** > **Sumber data**.

1. Pilih **Tambahkan sumber data**.

1. **Azure Synapse Analytics Pilih metode (Pratinjau**).

1. Berikan **nama** untuk sumber data, lalu pilih **berikutnya** untuk membuat sumber data. 

1. Pilih koneksi [yang](connections.md) tersedia atau Azure Synapse Analytics buat yang baru.

1. **Pilih Database** Danau dari ruang kerja yang terhubung di koneksi yang Azure Synapse Analytics dipilih dan pilih **Berikutnya**.

1. Pilih entitas untuk dicerna dari database yang terhubung. 

1. Secara opsional, pilih entitas data untuk mengaktifkan pembuatan profil data. 

1. Pilih **Simpan** untuk menerapkan pilihan Anda dan mulai konsumsi data dari sumber data yang baru Anda buat yang ditautkan ke tabel database Lake di Azure Synapse Analytics.
