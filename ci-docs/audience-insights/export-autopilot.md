---
title: Ekspor data Customer Insights ke Autopilot
description: Pelajari cara mengkonfigurasi sambungan ke Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269242"
---
# <a name="connector-for-autopilot-preview"></a>Konektor untuk Autopilot (pratinjau)

Ekspor segmen profil pelanggan terpadu ke Autopilot dan gunakan untuk pemasaran email di Autopilot. 

## <a name="prerequisites"></a>Prasyarat

-   Anda memiliki [akun Autopilot](https://www.autopilothq.com/) dan kredensial administrator yang sesuai.
-   Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="connect-to-autopilot"></a>Sambungkan ke Autopilot

1. Buka **Admin** > **Tujuan ekspor**.

1. Dalam **Autopilot**, pilih **konfigurasi**.

1. Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Panel konfigurasi untuk sambungan Autopilot.":::

1. Masukkan **kunci API Autopilot** [kunci API Autopilot](https://autopilot.docs.apiary.io/#).

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Sambungkan** untuk menginisialisasi sambungan ke Autopilot.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **berikutnya** untuk mengkonfigurasi ekspor.

## <a name="configure-the-connector"></a>Konfigurasikan konektor

1. Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan. Ulangi langkah yang sama untuk bidang opsional lainnya seperti **nama depan**, **nama belakang**.

1. Pilih segmen yang ingin diekspor. Kami sangat **menyarankan untuk tidak mengekspor lebih dari 100'000 profil pelanggan secara total** ke Autopilot. 

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengekspor data

Anda dapat [mengekspor data sesuai permintaan](export-destinations.md). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Anda dapat mengekspor hingga 100.000 profil pelanggan secara total ke Autopilot.
- Mengekspor ke Autopilot terbatas untuk segmen.
- Mengekspor hingga 100.000 profil ke Autopilot dapat memakan waktu hingga beberapa jam untuk menyelesaikannya. 
- Jumlah profil yang dapat Anda ekspor ke Autopilot tergantung dan terbatas pada kontrak Anda dengan Autopilot.

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Autopilot, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Autopilot memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]