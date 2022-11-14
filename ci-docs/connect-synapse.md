---
title: Menyambungkan Azure Synapse sumber data (pratinjau)
description: Gunakan database sebagai Azure Synapse sumber data di Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738160"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Menyambungkan Azure Synapse Analytics sumber data (pratinjau)

Azure Synapse Analytics adalah layanan analitik perusahaan yang mempercepat waktu untuk wawasan di seluruh gudang data dan sistem data besar. Azure Synapse Analytics menyatukan teknologi SQL terbaik yang digunakan dalam pergudangan data perusahaan, teknologi Spark yang digunakan untuk big data, Data Explorer untuk analitik log dan deret waktu, Pipelines untuk integrasi data dan ETL/ELT, dan integrasi mendalam dengan layanan Azure lainnya seperti Power BI,, Cosmos DB dan AzureML.

Untuk informasi selengkapnya, lihat [Azure Synapse gambaran umum](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prasyarat

> [!NOTE]
> Ruang Kerja Synapse yang mengaktifkan [firewall](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) saat ini tidak didukung.
> [!IMPORTANT]
> Pastikan untuk menetapkan semua **penugasan peran** seperti dijelaskan.  

**Dalam Customer Insights**:

* Anda memiliki **peran Administrator** di Customer Insights. Pelajari lebih lanjut [izin pengguna di Customer Insights](permissions.md#add-users).

**Di Azure**:

- Langganan Azure aktif.

- Jika menggunakan akun Gen2 baru Azure Data Lake Storage, *perwakilan layanan untuk Customer Insights yaitu "Dynamics 365 AI for Customer Insights*" memerlukan **izin kontributor** Data Blob Penyimpanan. Pelajari selengkapnya tentang [menyambungkan ke perwakilan Azure Data Lake Storage layanan dengan Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **harus mengaktifkan** [ruang nama hierarkis](/azure/storage/blobs/data-lake-storage-namespace).

- Pada grup sumber daya tempat Azure Synapse ruang kerja berada, *perwakilan* layanan yaitu "Dynamics 365 AI for Customer Insights" dan *pengguna untuk Customer Insights* harus diberi setidaknya **Pembaca** izin. Untuk informasi lebih lanjut, lihat [Menetapkan peran Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

- *Pengguna* memerlukan izin **kontributor Data Blob Penyimpanan** di akun Azure Data Lake Storage Gen2 dengan data berada dan ditautkan ke ruang kerja Azure Synapse. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identitas yang dikelola Ruang kerja Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* memerlukan memerlukan izin **kontributor Data Blob Penyimpanan** di akun Azure Data Lake Storage Gen2 dengan data berada dan ditautkan ke ruang kerja Azure Synapse. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Di ruang kerja, *perwakilan layanan untuk Customer Insights yaitu "Dynamics 365 AI for Customer Insights*" memerlukan **peran Administrator** Synapse yang ditetapkan. Pengguna **memerlukan** setidaknya **peran Synapse kontributor** yang ditetapkan untuk ruang kerja. Untuk informasi lebih lanjut, lihat [Cara mengkonfigurasi kontrol akses untuk ruang kerja Synapse Anda](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Jika lingkungan Customer Insights Anda menyimpan data sendiri [Azure Data Lake Storage](own-data-lake-storage.md), pengguna yang menyiapkan koneksi membutuhkan Azure Synapse Analytics setidaknya peran Pembaca **bawaan** di akun Data Lake Storage. Untuk informasi lebih lanjut, lihat [Menetapkan peran Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Menyambungkan ke database data lake di Azure Synapse Analytics

1. Buka **Data** > **Sumber data**.

1. Pilih **Tambahkan sumber data**.

1. **Azure Synapse Analytics Pilih metode (Pratinjau).**

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Kotak dialog untuk menyambungkan ke data Synapse Analytics":::
  
1. **Masukkan Nama** untuk sumber data dan Deskripsi **opsional**.

1. Pilih koneksi yang [tersedia untuk](connections.md) atau Azure Synapse Analytics buat yang [baru](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. **Pilih Database** dari ruang kerja yang tersambung dalam koneksi yang dipilih Azure Synapse Analytics dan pilih **Berikutnya**. Saat ini, kami hanya mendukung database jenis *database* Lake.

1. Pilih entitas yang akan diserap dari database yang tersambung dan pilih **Berikutnya**.

1. Secara opsional, pilih entitas data untuk mengizinkan pembuatan profil data.

1. Pilih **Simpan** untuk menerapkan pilihan Anda dan memulai penyerapan data dari sumber data yang baru Anda buat yang ditautkan ke tabel database Lake di Azure Synapse Analytics. Halaman **Sumber** data terbuka memperlihatkan sumber data baru dalam **status Refreshing**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuat data dapat memakan waktu. Setelah refresh berhasil, data yang diserap dapat ditinjau dari [**halaman Entitas**](entities.md) .

[!INCLUDE [footer-include](includes/footer-banner.md)]
