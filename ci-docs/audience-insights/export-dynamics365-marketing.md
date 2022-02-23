---
title: Ekspor data Customer Insights ke Dynamics 365 Marketing
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e2ec9f1cc11fdab5ff313bb3041d2b158ed6ca67
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046700"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Gunakan segmen di Dynamics 365 Marketing (pratinjau)



Gunakan [segmen](segments.md) untuk membuat kampanye dan hubungi grup pelanggan tertentu dengan Dynamics 365 Marketing. Untuk informasi lebih lanjut, lihat [menggunakan segmen dari Dynamics 365 Customer Insights dengan Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Jika Anda menggunakan kemampuan baru Dynamics 365 Marketing untuk orkestrasi perjalanan pelanggan real-time di organisasi Dataverse, Anda tidak perlu membuat ekspor standar ke Dynamics 365 Marketing. Kontak dan segmen dari audiens tersedia langsung di Dynamics 365 Marketing setelah menghubungkan Marketing dan Customer Insights. Sebelum Anda menghapus ekspor yang ada, lihat dokumentasi cara [menyambungkan wawasan audiens dengan orkestrasi perjalanan pelanggan Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Prasyarat untuk koneksi

- Rekaman kontak harus ada di Dynamics 365 Marketing agar Anda dapat mengekspor segmen dari Customer Insights ke Marketing. Baca selengkapnya tentang cara menyerap kontak di [Dynamics 365 Marketing menggunakan Microsoft Dataverse](connect-power-query.md).

  > [!NOTE]
  > Mengekspor segmen dari wawasan audiens ke Marketing tidak akan membuat rekaman kontak baru di instans Marketing. Rekaman kontak dari Marketing harus digunakan dalam audiens wawasan dan digunakan sebagai sumber data. Id pelanggan juga harus disertakan dalam entitas Pelanggan terpadu untuk memetakan ID pelanggan agar ID dapat dihubungi sebelum segmen dapat diekspor.

## <a name="set-up-connection-to-marketing"></a>Konfigurasikan koneksi ke Marketing

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Dynamics 365 Marketing** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan URL Marketing organisasi di **bidang alamat server**.

1. Di Bagian **akun admin server**, pilih **masuk** dan pilih akun Dynamics 365 Marketing.

1. Peta bidang ID Kontak di entitas Pelanggan ke ID Kontak Dynamics 365.

1. Pilih **Simpan** untuk menyelesaikan koneksi. 

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Dynamics 365 Marketing. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Pilih satu atau beberapa segmen.

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
