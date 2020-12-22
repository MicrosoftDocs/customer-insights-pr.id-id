---
title: Ekspor data Customer Insights ke host SFTP
description: Pelajari cara mengkonfigurasi sambungan ke host SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643507"
---
# <a name="connector-for-sftp-preview"></a>Konektor untuk SFTP (pratinjau)

Gunakan data pelanggan di aplikasi pihak ketiga dengan mengekspornya ke host Secure File Transfer Protocol(SFTP).

## <a name="prerequisites"></a>Prasyarat

- Ketersediaan host SFTP dan kredensial terkait.

## <a name="connect-to-sftp"></a>Sambungkan ke SFTP

1. Buka **Admin** > **Tujuan ekspor**.

1. Di dalam **SFTP**, pilih **konfigurasi**.

1. Beri nama yang dikenali di bidang **nama tampilan** tujuan anda.

1. Berikan **nama pengguna**, **sandi**, dan **nama host** untuk akun SFTP Anda. Contoh: Jika folder root server SFTP Anda adalah/root/folder, dan Anda ingin data diekspor ke /root/folder/ci_export_destination_folder, host harus sftp://<server_address>/ci_export_destination_folder".

1. Pilih **Verifikasi** untuk menguji koneksi.

1. Setelah berhasil melakukan verifikasi, pilih jika Anda ingin mengekspor data Anda **di-zip** atau **tidak di-zip**, dan pilih **pembatas bidang** untuk file yang diekspor.

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **berikutnya** untuk mulai mengkonfigurasi ekspor.

## <a name="configure-the-connection"></a>Mengonfigurasi koneksi

1. Pilih **atribut pelanggan** untuk diekspor. Anda dapat mengekspor satu atau beberapa atribut.

1. Pilih **Selanjutnya**.

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengekspor data

Anda dapat [mengekspor data sesuai permintaan](export-destinations.md). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan melalui SFTP, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa tujuan ekspor memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.
