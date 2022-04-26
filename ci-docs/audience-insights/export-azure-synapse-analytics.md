---
title: Mengekspor data Customer Insights ke Azure Synapse Analytics
description: Pelajari cara mengonfigurasi koneksi ke Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 8ace9fbee4fbd8822629a39d5902e176f8511cb5
ms.sourcegitcommit: 9f6733b2f2c273748c1e7b77f871e9b4e5a8666e
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/11/2022
ms.locfileid: "8560391"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Mengekspor data ke Azure Synapse Analytics (Pratinjau)

Azure Synapse adalah layanan analitik yang mempercepat waktu untuk wawasan di seluruh gudang data dan sistem data besar. Anda data menyerap dan menggunakan data Customer Insights dalam [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prasyarat

Prasyarat berikut harus dipenuhi untuk mengkonfigurasi sambungan dari Customer Insights ke Azure Synapse.

> [!NOTE]
> Pastikan untuk menetapkan semua **penugasan peran** seperti dijelaskan.  

## <a name="prerequisites-in-customer-insights"></a>Prasyarat di Customer Insights

* Akun pengguna (AD) Anda Azure Active Directory memiliki **peran Administrator** di Wawasan Pelanggan. Selengkapnya tentang [menetapkan izin pengguna di audiens wawasan](permissions.md#assign-roles-and-permissions)

Di Azure: 

- Langganan Azure aktif.

- Jika menggunakan akun Gen2 baru Azure Data Lake Storage, *perwakilan layanan untuk Wawasan* Pelanggan memerlukan **izin kontributor** Data Blob Penyimpanan. Selengkapnya tentang [menyambung ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure untuk wawasan audiens](connect-service-principal.md). Data Lake Storage Gen2 **harus mengaktifkan** [ruang nama hierarkis](/azure/storage/blobs/data-lake-storage-namespace).

- Pada grup sumber daya tempat Azure Synapse ruang kerja berada, *perwakilan* layanan dan *Azure AD pengguna dengan izin admin di Customer Insights* perlu ditetapkan setidaknya **Pembaca** izin. Untuk informasi lebih lanjut, lihat [Menetapkan peran Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

- Pengguna *Azure AD dengan izin admin di Customer Insights* memerlukan **izin Data Blob Penyimpanan kontributor** di Azure Data Lake Storage akun Gen2 tempat data berada dan ditautkan Azure Synapse ke ruang kerja. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identitas yang dikelola Ruang kerja Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* memerlukan memerlukan izin **kontributor Data Blob Penyimpanan** di akun Azure Data Lake Storage Gen2 dengan data berada dan ditautkan ke ruang kerja Azure Synapse. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse Di ruang kerja, *perwakilan layanan untuk Wawasan* Pelanggan memerlukan **peran Administrator** Synapse yang ditetapkan. Untuk informasi lebih lanjut, lihat [Cara mengkonfigurasi kontrol akses untuk ruang kerja Synapse Anda](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Siapkan sambungan ke dan ekspor ke Azure Synapse

### <a name="configure-a-connection"></a>Mengonfigurasi koneksi

Untuk membuat koneksi, perwakilan layanan dan akun pengguna di Customer Insights memerlukan **izin Pembaca** pada *grup* sumber daya tempat ruang kerja Synapse Analytics berada. Selain itu, perwakilan layanan dan pengguna di ruang kerja Synapse Analytics memerlukan **izin Administrator** Synapse. 

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Azure Synapse Analytics** atau pilih **Set up** pada **Azure Synapse Analytics** petak untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang nama tampilan. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih atau cari langganan yang akan digunakan untuk data Customer Insights. Segera setelah langganan dipilih, Anda juga dapat memilih **Ruang Kerja**, **Akun Penyimpanan**, dan **Wadah**.

1. Pilih **Simpan** untuk menyimpan koneksi.

### <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk mengonfigurasi ekspor dengan koneksi bersama, Anda memerlukan setidaknya **kontributor** izin di Customer Insights. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Di bidang **Koneksi untuk ekspor**, pilih koneksi dari **Azure Synapse Analytics** bagian. Jika Anda tidak melihat nama bagian ini, tidak ada [koneksi](connections.md) tipe ini yang tersedia untuk Anda.

1. Berikan daftar **nama tampilan** yang dapat dikenali untuk ekspor Anda dan **nama Database**.

1. Pilih entitas mana yang ingin Anda ekspor Azure Synapse Analytics.
   > [!NOTE]
   > Sumber data berdasarkan [folder Common Data Model](connect-common-data-model.md) tidak didukung.

2. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).

Untuk mengkueri data yang diekspor ke Synapse Analytics, Anda memerlukan **Data Blob Penyimpanan Pembaca** akses ke penyimpanan tujuan di ruang kerja ekspor. 

### <a name="update-an-export"></a>Memperbarui ekspor

1. Buka **Data** > **Ekspor**.

1. Pilih **Edit** di ekspor yang ingin Anda perbarui.

   - **Tambah** atau **Hilangkan** entitas dari pilihan. Jika entitas dihapus dari pilihan, entitas tersebut tidak akan dihapus dari database Synapse Analytics. Namun, pembaruan data mendatang tidak akan memperbarui entitas yang dihapus di database tersebut.

   - **Mengubah Nama Database** akan membuat database Synapse Analytics baru. Database dengan nama yang dikonfigurasi sebelum tidak akan menerima pembaruan apa pun di pembaruan mendatang.
