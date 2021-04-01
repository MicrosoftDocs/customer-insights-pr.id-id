---
title: Ekspor data Customer Insights ke host SFTP
description: Pelajari cara mengkonfigurasi sambungan ke host SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598389"
---
# <a name="connector-for-sftp-preview"></a>Konektor untuk SFTP (pratinjau)

Gunakan data pelanggan di aplikasi pihak ketiga dengan mengekspornya ke host Secure File Transfer Protocol(SFTP).

## <a name="prerequisites"></a>Prasyarat

- Ketersediaan host SFTP dan kredensial yang sesuai.

## <a name="connect-to-sftp"></a>Sambungkan ke SFTP

1. Buka **Admin** > **Tujuan ekspor**.

1. Di dalam **SFTP**, pilih **konfigurasi**.

1. Beri nama yang dikenali di bidang **nama tampilan** tujuan anda.

1. Berikan **nama pengguna**, **sandi**, **nama host**, dan **folder Ekspor** untuk akun SFTP Anda.

1. Pilih **Verifikasi** untuk menguji koneksi.

1. Setelah verifikasi berhasil, pilih jika Anda ingin mengekspor data **Di-zip** atau **Tidak di-zip**, dan pilih **pembatas bidang** untuk file yang diekspor.

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **berikutnya** untuk mulai mengkonfigurasi ekspor.

## <a name="configure-the-export"></a>Mengonfigurasi ekspor

1. Pilih entitas, misalnya segmen, yang akan diekspor.

   > [!NOTE]
   > Setiap entitas yang dipilih adalah maksimal lima file output saat diekspor. 

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengekspor data

Anda dapat [mengekspor data sesuai permintaan](export-destinations.md). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Runtime ekspor tergantung pada kinerja sistem Anda. Sebaiknya dua inti CPU dan memori 1 Gb sebagai konfigurasi minimal server Anda. 
- Mengekspor entitas dengan hingga 100 juta profil pelanggan dapat berlangsung selama 90 menit bila menggunakan konfigurasi minimal yang disarankan untuk dua inti CPU dan 1 Gb memori. 

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan melalui SFTP, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa tujuan ekspor memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]