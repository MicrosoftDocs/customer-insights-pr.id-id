---
title: Ekspor segmen ke Dynamics 365 Marketing (pratinjau)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196628"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Ekspor segmen ke Dynamics 365 Marketing (pratinjau)

Gunakan [segmen](segments.md) untuk menghasilkan kampanye dan menghubungi grup pelanggan tertentu dengan [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Jika Anda menggunakan kemampuan baru Dynamics 365 Marketing untuk orkestrasi perjalanan pelanggan real-time di organisasi Dataverse, Anda tidak perlu membuat ekspor standar ke Dynamics 365 Marketing. Kontak dan segmen dari Customer Insights tersedia langsung di Dynamics 365 Marketing setelah menghubungkan Marketing dan Customer Insights. Sebelum Anda menghapus ekspor yang ada, tinjau dokumentasi tentang [cara menghubungkan Customer Insights dan orkestrasi dynamics 365 Marketing perjalanan pelanggan](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Prasyarat

Rekaman kontak harus ada di Dynamics 365 Marketing agar Anda dapat mengekspor segmen dari Customer Insights ke Marketing. Baca selengkapnya tentang cara menyerap kontak di [Dynamics 365 Marketing menggunakan Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> Mengekspor segmen dari Customer Insights ke Marketing tidak akan membuat catatan kontak baru dalam instans Marketing. Catatan kontak dari Pemasaran harus diserap dalam Customer Insights dan digunakan sebagai sumber data. Id pelanggan juga harus disertakan dalam entitas Pelanggan terpadu untuk memetakan ID pelanggan agar ID dapat dihubungi sebelum segmen dapat diekspor.

## <a name="set-up-connection-to-marketing"></a>Konfigurasikan koneksi ke Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Dynamics 365 Marketing**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan URL Marketing organisasi di **bidang alamat server**.

1. Di Bagian **akun admin server**, pilih **masuk** dan pilih akun Dynamics 365 Marketing.

1. Petakan bidang ID Kontak di entitas Pelanggan ke ID Kontak Dynamics 365.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Dynamics 365 Marketing. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Pilih bidang ID Kontak di entitas Pelanggan yang cocok dengan ID Kontak Dynamics 365.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
