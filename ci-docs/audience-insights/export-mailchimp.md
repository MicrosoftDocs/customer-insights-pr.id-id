---
title: Ekspor data Customer Insights ke Mailchimp
description: Pelajari cara mengkonfigurasi sambungan ke Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406041"
---
# <a name="connector-for-mailchimp-preview"></a>Konektor untuk Mailchimp (pratinjau)

Ekspor segmen profil pelanggan terpadu ke MailChimp untuk membuat kampanye newsletter dan email.

## <a name="prerequisites"></a>Prasyarat

-   Anda memiliki [akun Mailchimp](https://mailchimp.com/) dan kredensial administrator yang sesuai.
-   Audiens sudah ada di Mailchimp dan id yang sesuai. Untuk informasi lebih lanjut, lihat [audiens Mailchimp](https://mailchimp.com/help/create-audience/).
-   Anda telah [mengonfigurasi segmen](segments.md)
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.

## <a name="connect-to-mailchimp"></a>Hubungkan ke Mailchimp

1. Buka **Admin** > **Tujuan ekspor**.

1. Dalam **Mailchimp**, pilih **konfigurasi**.

1. Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Masukkan **[ID audiens Mailchimp](https://mailchimp.com/help/find-audience-id/)**, lalu pilih **sambungkan** untuk menginisialisasi sambungan ke Mailchimp.

1. Pilih **autentikasi dengan Mailchimp** dan berikan kredensial Mailchimp Anda.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Mengekspor tangkapan layar untuk sambungan Mailchimp":::

1. Pilih **berikutnya** untuk mengkonfigurasi ekspor.

## <a name="configure-the-connector"></a>Konfigurasikan konektor

1. Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan. 

1. Atau, anda dapat mengekspor **nama depan** dan **nama belakang** sebagai bidang tambahan untuk membuat email yang lebih disesuaikan. Pilih **Tambah atribut** untuk memetakan bidang ini.

1. Pilih segmen yang ingin diekspor. Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Pilih bidang dan segmen untuk diekspor ke MailChimp":::

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengekspor data

Anda dapat [mengekspor data sesuai permintaan](export-destinations.md). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Di Mailchimp, Anda sekarang dapat menemukan segmen Anda dalam [audiens Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 1 juta profil per ekspor ke Mailchimp.
- Mengekspor ke Mailchimp terbatas untuk segmen.
- Mengekspor segmen dengan total 1 juta profil dapat memakan waktu hingga tiga jam karena keterbatasan pada sisi Provider. 
- Jumlah profil yang dapat Anda ekspor ke Mailchimp tergantung dan terbatas pada kontrak Anda dengan Mailchimp.

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Mailchimp, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Mailchimp memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.
