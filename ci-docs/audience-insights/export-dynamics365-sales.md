---
title: Ekspor data Customer Insights ke Dynamics 365 Sales
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f11ab189117da5bcc1aee843b73962ec6615e82
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692347"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Gunakan segmen di Dynamics 365 Sales (pratinjau)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Gunakan data pelanggan Anda untuk membuat daftar pemasaran, alur kerja tindak lanjut, dan mengirim promosi dengan Dynamics 365 Sales.

## <a name="prerequisite-for-connection"></a>Prasyarat untuk koneksi

1. Rekaman kontak harus ada di Dynamics 365 Sales agar Anda dapat mengekspor segmen dari Customer Insights ke Sales. Baca selengkapnya tentang cara menyerap kontak di [Dynamics 365 Sales menggunakan Microsoft Dataverse](connect-power-query.md).

   > [!NOTE]
   > Mengekspor segmen dari wawasan audiens ke Sales tidak akan membuat rekaman kontak baru di instans Sales. Rekaman kontak dari Sales harus digunakan dalam audiens wawasan dan digunakan sebagai sumber data. Id pelanggan juga harus disertakan dalam entitas Pelanggan terpadu untuk memetakan ID pelanggan agar ID dapat dihubungi sebelum segmen dapat diekspor.

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

[!INCLUDE[footer-include](../includes/footer-banner.md)]
