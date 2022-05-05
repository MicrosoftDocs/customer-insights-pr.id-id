---
title: Mengekspor data Wawasan Pelanggan ke host SFTP (berisi video)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke lokasi SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5170ec4ca35ad2a94f02e9d696c44a32da888120
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642590"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Mengekspor segmen dan data lainnya ke SFTP (pratinjau)

Gunakan data pelanggan Anda dalam aplikasi pihak ketiga dengan mengekspornya ke lokasi Secure File Transfer Protocol (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Prasyarat untuk koneksi

- Ketersediaan host SFTP dan kredensial yang sesuai.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Tujuan SFTP di belakang firewall saat ini tidak didukung. 
- Runtime ekspor tergantung pada kinerja sistem Anda. Sebaiknya dua inti CPU dan memori 1 Gb sebagai konfigurasi minimal server Anda. 
- Mengekspor entitas dengan hingga 100 juta profil pelanggan dapat berlangsung selama 90 menit bila menggunakan konfigurasi minimal yang disarankan untuk dua inti CPU dan 1 Gb memori. 

## <a name="set-up-connection-to-sftp"></a>Siapkan koneksi ke SFTP

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **SFTP** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan **nama pengguna**, **sandi**, **nama host**, dan **folder Ekspor** untuk akun SFTP Anda.

1. Pilih **Verifikasi** untuk menguji koneksi.

1. Pilih jika Anda ingin mengekspor data **dengan di-zip** atau **tidak di-zip** dan **pembatas bidang** untuk file yang diekspor.

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian SFTP. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Pilih entitas, misalnya segmen, yang akan diekspor.

   > [!NOTE]
   > Setiap entitas yang dipilih akan dibagi menjadi hingga lima file output saat diekspor. 

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan melalui SFTP, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa tujuan ekspor memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.

[!INCLUDE [footer-include](includes/footer-banner.md)]
