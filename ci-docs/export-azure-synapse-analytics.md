---
title: Mengekspor data ke Azure Synapse Analytics (pratinjau)
description: Pelajari cara mengonfigurasi koneksi ke Azure Synapse Analytics.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 60bacb313e0426564310f3c1339bf3b732e17489
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082870"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Mengekspor data ke Azure Synapse Analytics (pratinjau)

Azure Synapse adalah layanan analitik yang mempercepat waktu untuk wawasan di seluruh gudang data dan sistem data besar. Anda data menyerap dan menggunakan data Customer Insights dalam [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prasyarat

Prasyarat berikut harus dipenuhi untuk mengkonfigurasi sambungan dari Customer Insights ke Azure Synapse.

> [!NOTE]
> Pastikan untuk menetapkan semua **penugasan peran** seperti dijelaskan.  

## <a name="prerequisites-in-customer-insights"></a>Prasyarat di Customer Insights

* Akun pengguna (AD) Anda Azure Active Directory memiliki **peran Administrator** dalam Customer Insights. Pelajari selengkapnya tentang [cara mengatur izin pengguna](permissions.md#assign-roles-and-permissions).

Di Azure: 

- Langganan Azure aktif.

- Jika menggunakan akun Gen2 baru Azure Data Lake Storage, *perwakilan layanan untuk Customer Insights* memerlukan **data Blob Penyimpanan kontributor** izin. Pelajari selengkapnya tentang [menyambungkan ke Azure Data Lake Storage akun Gen2 dengan perwakilan layanan Azure untuk Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **harus mengaktifkan** [ruang nama hierarkis](/azure/storage/blobs/data-lake-storage-namespace).

- Pada grup sumber daya tempat Azure Synapse ruang kerja berada, *perwakilan* layanan dan *Azure AD pengguna dengan izin admin di Customer Insights* harus diberi setidaknya **Pembaca** izin. Untuk informasi lebih lanjut, lihat [Menetapkan peran Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

- Pengguna *Azure AD dengan izin admin di Customer Insights* memerlukan **izin kontributor** Data Blob Penyimpanan pada Azure Data Lake Storage akun Gen2 tempat data berada dan ditautkan ke Azure Synapse ruang kerja. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identitas yang dikelola Ruang kerja Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* memerlukan memerlukan izin **kontributor Data Blob Penyimpanan** di akun Azure Data Lake Storage Gen2 dengan data berada dan ditautkan ke ruang kerja Azure Synapse. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Di ruang Azure Synapse kerja, *perwakilan layanan untuk Customer Insights* memerlukan **peran Synapse Administrator** yang ditetapkan. Untuk informasi lebih lanjut, lihat [Cara mengkonfigurasi kontrol akses untuk ruang kerja Synapse Anda](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Siapkan sambungan ke dan ekspor ke Azure Synapse

### <a name="configure-a-connection"></a>Mengonfigurasi koneksi

Untuk membuat koneksi, perwakilan layanan dan akun pengguna di Customer Insights memerlukan **izin Pembaca** pada grup *sumber daya tempat* ruang kerja Synapse Analytics berada. Selain itu, perwakilan layanan dan pengguna di ruang kerja Synapse Analytics memerlukan **izin Synapse Administrator**. 

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Azure Synapse Analytics** atau pilih **petak Petakan** pada **Azure Synapse Analytics** petak peta untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang nama tampilan. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih atau cari langganan yang akan digunakan untuk data Customer Insights. Segera setelah langganan dipilih, Anda juga dapat memilih **Ruang Kerja**, **Akun Penyimpanan**, dan **Wadah**.

1. Pilih **Simpan** untuk menyimpan koneksi.

### <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk mengonfigurasi ekspor dengan koneksi bersama, Anda memerlukan setidaknya **izin kontributor** di Customer Insights. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Di **bidang Koneksi untuk ekspor**, pilih koneksi dari bagian tersebut **Azure Synapse Analytics**. Jika Anda tidak melihat nama bagian ini, tidak ada [koneksi](connections.md) tipe ini yang tersedia untuk Anda.

1. Berikan daftar **nama tampilan** yang dapat dikenali untuk ekspor Anda dan **nama Database**. Ekspor akan membuat database [Azure Synapse lake baru](/azure/synapse-analytics/database-designer/concepts-lake-database) di ruang kerja yang ditentukan dalam koneksi.

1. Pilih entitas mana yang ingin Anda ekspor ke Azure Synapse Analytics.
   > [!NOTE]
   > Sumber data berdasarkan [folder Common Data Model](connect-common-data-model.md) tidak didukung.

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).

Untuk mengkueri data yang diekspor ke Synapse Analytics, Anda memerlukan **Akses Pembaca** Data Blob Penyimpanan ke penyimpanan tujuan di ruang kerja ekspor. 

### <a name="update-an-export"></a>Memperbarui ekspor

1. Buka **Data** > **Ekspor**.

1. Pilih **Edit** di ekspor yang ingin Anda perbarui.

   - **Tambah** atau **Hilangkan** entitas dari pilihan. Jika entitas dihapus dari pilihan, entitas tersebut tidak akan dihapus dari database Synapse Analytics. Namun, pembaruan data mendatang tidak akan memperbarui entitas yang dihapus di database tersebut.

   - **Mengubah Nama Database** akan membuat database Synapse Analytics baru. Database dengan nama yang dikonfigurasi sebelum tidak akan menerima pembaruan apa pun di pembaruan mendatang.
