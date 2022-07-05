---
title: Ekspor segmen ke Dynamics 365 Sales (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: b8e756313ca037dca41cb25587229808f0c584c9
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082387"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Ekspor segmen ke Dynamics 365 Sales (pratinjau)

Gunakan data pelanggan Anda untuk membuat daftar pemasaran, alur kerja tindak lanjut, dan mengirim promosi dengan Dynamics 365 Sales.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Ekspor ke Dynamics 365 Sales dibatasi hingga 100.000 anggota per segmen.
- Ekspor segmen ke Dynamics 365 Sales dapat memakan waktu hingga 3 jam untuk diselesaikan. 

## <a name="prerequisite-for-connection"></a>Prasyarat untuk koneksi

1. Rekaman kontak harus ada di Dynamics 365 Sales agar Anda dapat mengekspor segmen dari Customer Insights ke Sales. Baca lebih lanjut tentang cara menyerap kontak dari [Dynamics 365 Sales menggunakan Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Mengekspor segmen dari Customer Insights ke Sales tidak akan membuat catatan kontak baru dalam instans Sales. Catatan kontak dari Penjualan harus diserap dalam Customer Insights dan digunakan sebagai sumber data. Id pelanggan juga harus disertakan dalam entitas Pelanggan terpadu untuk memetakan ID pelanggan agar ID dapat dihubungi sebelum segmen dapat diekspor.

## <a name="set-up-the-connection-to-sales"></a>Konfigurasikan koneksi ke Sales

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Dynamics 365 Sales** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan URL Sales organisasi di **bidang alamat server**.

1. Di Bagian **akun admin server**, pilih **masuk** dan pilih akun Dynamics 365 Sales.

1. Petakan bidang ID pelanggan ke ID kontak Dynamics 365.

1. Pilih **Simpan** untuk menyelesaikan koneksi. 

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Dynamics 365 Sales. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Pilih satu atau beberapa segmen.

1. Pilih **Simpan**

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]