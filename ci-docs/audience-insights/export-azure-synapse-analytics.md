---
title: Mengekspor data Customer Insights ke Azure Synapse Analytics
description: Pelajari lebih lanjut cara mengkonfigurasi sambungan ke Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7ee57aa9e86ebf9bd1989d88750642f0b01bd4bf
ms.sourcegitcommit: f18635c29bb25d9e424a3f5825dc2696278450cf
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/30/2021
ms.locfileid: "6327368"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Ekspor data ke Azure Synapse Analytics (pratinjau)

Azure Synapse adalah layanan analitik yang mempercepat waktu untuk wawasan di seluruh gudang data dan sistem data besar. Anda data menyerap dan menggunakan data Customer Insights dalam [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Prasyarat

Prasyarat berikut harus dipenuhi untuk mengkonfigurasi sambungan dari Customer Insights ke Azure Synapse.

> [!NOTE]
> Pastikan untuk menetapkan semua **penugasan peran** seperti dijelaskan.  

## <a name="prerequisites-in-customer-insights"></a>Prasyarat di Customer Insights

* Anda memiliki peran **Administrator** di wawasan audiens. Selengkapnya tentang [menetapkan izin pengguna di audiens wawasan](permissions.md#assign-roles-and-permissions)

Di Azure: 

- Langganan Azure aktif.

- Jika menggunakan akun Azure Data Lake Storage Gen2 baru, *prinsipal layanan untuk wawasan audiens* memerlukan izin **kontributor Data Blob penyimpanan**. Selengkapnya tentang [menyambung ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure untuk wawasan audiens](connect-service-principal.md). Data Lake Storage Gen2 **harus mengaktifkan** [ruang nama hierarkis](/azure/storage/blobs/data-lake-storage-namespace).

- Pada grup sumber daya, tempat ruang kerja Azure Synapse terletak, *prinsipal layanan* dan *pengguna wawasan audiens* harus ditetapkan sekurangnya izin **Pembaca**. Untuk informasi lebih lanjut, lihat [Menetapkan peran Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).

- *Pengguna* memerlukan izin **kontributor Data Blob Penyimpanan** di akun Azure Data Lake Storage Gen2 dengan data berada dan ditautkan ke ruang kerja Azure Synapse. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Identitas yang dikelola Ruang kerja Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* memerlukan memerlukan izin **kontributor Data Blob Penyimpanan** di akun Azure Data Lake Storage Gen2 dengan data berada dan ditautkan ke ruang kerja Azure Synapse. Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Di ruang kerja Azure Synapse, *prinsipal layanan untuk wawasan audiens* memerlukan **penetapan peran Administrator Synapse**. Untuk informasi lebih lanjut, lihat [Cara mengkonfigurasi kontrol akses untuk ruang kerja Synapse Anda](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Siapkan sambungan ke dan ekspor ke Azure Synapse

### <a name="configure-a-connection"></a>Mengonfigurasi koneksi

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambah koneksi** dan pilih **Azure Synapse Analytics** atau pilih **Konfigurasi** dalam petak **Azure Synapse Analytics** untuk mengonfigurasikan koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang nama tampilan. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Pilih atau cari langganan yang akan digunakan untuk data Customer Insights. Segera setelah langganan dipilih, Anda juga dapat memilih **Ruang Kerja**, **Akun Penyimpanan**, dan **Wadah**.

1. Pilih **Simpan** untuk menyimpan koneksi.

### <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian **Azure Synapse Analytics**. Jika Anda tidak melihat nama bagian ini, tidak ada [koneksi](connections.md) tipe ini yang tersedia untuk Anda.

1. Berikan daftar **nama tampilan** yang dapat dikenali untuk ekspor Anda dan **nama Database**.

1. Pilih entitas yang akan diekspor ke Azure Synapse Analytics.
   > [!NOTE]
   > Sumber data berdasarkan [folder Common Data Model](connect-common-data-model.md) tidak didukung.

2. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>Memperbarui ekspor

1. Buka **Data** > **Ekspor**.

1. Pilih **Edit** di ekspor yang ingin Anda perbarui.

   - **Tambah** atau **Hilangkan** entitas dari pilihan. Jika entitas dihapus dari pilihan, entitas tersebut tidak akan dihapus dari database Synapse Analytics. Namun, pembaruan data mendatang tidak akan memperbarui entitas yang dihapus di database tersebut.

   - **Mengubah Nama Database** akan membuat database Synapse Analytics baru. Database dengan nama yang dikonfigurasi sebelum tidak akan menerima pembaruan apa pun di pembaruan mendatang.
