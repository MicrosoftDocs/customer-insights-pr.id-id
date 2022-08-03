---
title: Mengekspor data ke Azure Synapse Analytics (pratinjau)
description: Pelajari cara mengonfigurasi koneksi ke Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196398"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Mengekspor data ke Azure Synapse Analytics (pratinjau)

Azure Synapse adalah layanan analitik yang mempercepat waktu untuk wawasan di seluruh gudang data dan sistem data besar. Anda data menyerap dan menggunakan data Customer Insights dalam [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prasyarat

> [!NOTE]
> Pastikan untuk menetapkan semua **penugasan peran** seperti dijelaskan.

- Di Customer Insights, akun pengguna (AD) Anda Azure Active Directory harus memiliki [peran Administrator](permissions.md#assign-roles-and-permissions).

Di Azure:

- Langganan Azure aktif.

- Jika menggunakan akun Gen2 baru Azure Data Lake Storage, [perwakilan layanan untuk Customer Insights](connect-service-principal.md) memiliki **izin kontributor** Storage Blob Data. Data Lake Storage Gen2 **harus mengaktifkan** [ruang nama hierarkis](/azure/storage/blobs/data-lake-storage-namespace).

- Pada grup sumber daya tempat Azure Synapse ruang kerja berada, *perwakilan* layanan dan *Azure AD pengguna dengan izin admin di Customer Insights* harus diberi setidaknya **izin Pembaca**[...](/azure/role-based-access-control/role-assignments-portal).

- Pengguna *Azure AD dengan izin admin di Customer Insights* memiliki **izin kontributor** Data Blob Penyimpanan di Azure Data Lake Storage akun Gen2 tempat data berada dan ditautkan ke Azure Synapse ruang kerja. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Identitas *[Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* terkelola ruang kerja memiliki **izin kontributor** Data Blob Penyimpanan pada Azure Data Lake Storage akun Gen2 tempat data berada dan ditautkan ke Azure Synapse ruang kerja. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Di ruang Azure Synapse kerja, *perwakilan layanan untuk Customer Insights* memiliki **peran Administrator**[Synapse yang](/azure/synapse-analytics/security/how-to-set-up-access-control) ditetapkan.

## <a name="set-up-connection-to-azure-synapse"></a>Menyiapkan koneksi ke Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Azure Synapse Analytics**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih atau cari langganan yang akan digunakan untuk data Customer Insights. Segera setelah langganan dipilih, Anda juga dapat memilih **Ruang Kerja**, **Akun Penyimpanan**, dan **Wadah**.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)] Untuk mengonfigurasi ekspor dengan koneksi bersama, Anda memerlukan setidaknya **izin kontributor** di Customer Insights.

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Di **bidang Koneksi untuk ekspor**, pilih koneksi dari bagian tersebut Azure Synapse Analytics. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Berikan daftar **nama tampilan** yang dapat dikenali untuk ekspor Anda dan **nama Database**. Ekspor akan membuat database [Azure Synapse lake baru](/azure/synapse-analytics/database-designer/concepts-lake-database) di ruang kerja yang ditentukan dalam koneksi.

1. Pilih entitas mana yang ingin Anda ekspor ke Azure Synapse Analytics.
   > [!NOTE]
   > Sumber data berdasarkan [folder Common Data Model](connect-common-data-model.md) tidak didukung.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Untuk mengkueri data yang diekspor ke Synapse Analytics, Anda memerlukan **Akses Pembaca** Data Blob Penyimpanan ke penyimpanan tujuan di ruang kerja ekspor.

## <a name="update-an-export"></a>Memperbarui ekspor

1. Buka **Data** > **Ekspor**.

1. Pilih **Edit** di ekspor yang ingin Anda perbarui.

   - **Tambah** atau **Hilangkan** entitas dari pilihan. Jika entitas dihapus dari pilihan, entitas tersebut tidak akan dihapus dari database Synapse Analytics. Namun, pembaruan data mendatang tidak akan memperbarui entitas yang dihapus di database tersebut.

   - **Mengubah Nama Database** akan membuat database Synapse Analytics baru. Database dengan nama yang dikonfigurasi sebelum tidak akan menerima pembaruan apa pun di pembaruan mendatang.

[!INCLUDE [footer-include](includes/footer-banner.md)]
