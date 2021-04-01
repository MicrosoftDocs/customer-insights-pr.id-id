---
title: Ekspor data Customer Insights ke AdRoll
description: Pelajari cara mengkonfigurasi sambungan ke AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697078"
---
# <a name="connector-for-adroll-preview"></a>Konektor untuk AdRoll (pratinjau)

Mengekspor segmen profil pelanggan terpadu ke AdRoll dan menggunakannya untuk iklan. 

## <a name="prerequisites"></a>Prasyarat

-   Anda memiliki [akun AdRoll](https://www.adroll.com/) dan kredensial administrator yang sesuai.
-   Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="connect-to-adroll"></a>Sambungkan ke AdRoll

1. Buka **Admin** > **Tujuan ekspor**.

1. Dalam **AdRoll**, pilih **konfigurasi**.

1. Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Panel konfigurasi untuk sambungan AdRoll.":::

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Sambungkan** untuk menginisialisasi sambungan ke AdRoll.

1. Pilih **autentikasi dengan AdRoll** dan berikan kredensial admin Anda untuk AdRoll. 

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Masukkan **ID Pengiklan AdRoll** [AdRoll Dapat Beriklan](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Pilih **berikutnya** untuk mengkonfigurasi ekspor.

## <a name="configure-the-connector"></a>Konfigurasikan konektor

1. Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan. Ini harus diekspor ke AdRoll.

1. Pilih segmen yang ingin diekspor. Pilih segmen dengan minimal 100 anggota. Anda tidak dapat mengekspor segmen yang lebih kecil. Selain itu, ukuran maksimum segmen untuk diekspor adalah 250.000 anggota per ekspor. 

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengekspor data

Anda dapat [mengekspor data sesuai permintaan](export-destinations.md). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Anda dapat mengekspor hingga 250.000 profil per ekspor ke AdRoll.
- Anda tidak dapat mengekspor segmen dengan kurang dari 100 profil ke AdRoll. 
- Mengekspor ke AdRoll terbatas untuk segmen.
- Mengekspor hingga 250.000 profil ke AdRoll dapat berlangsung hingga 10 menit untuk menyelesaikannya. 
- Jumlah profil yang dapat Anda ekspor ke AdRoll tergantung dan terbatas pada kontrak Anda dengan AdRoll.

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke AdRoll, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa AdRoll memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.
