---
title: Ekspor data Customer Insights ke Dynamics 365 Sales
description: Pelajari cara mengkonfigurasi sambungan ke Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598113"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Konektor untuk Dynamics 365 Sales (pratinjau)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Gunakan data pelanggan Anda untuk membuat daftar pemasaran, alur kerja tindak lanjut, dan mengirim promosi dengan Dynamics 365 Sales.

## <a name="prerequisite"></a>Prasyarat

1. Rekaman kontak harus ada di Dynamics 365 Sales agar Anda dapat mengekspor segmen dari Customer Insights ke Sales. Baca selengkapnya tentang cara menyerap kontak di [Dynamics 365 Sales menggunakan Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Mengekspor segmen dari wawasan audiens ke Sales tidak akan membuat rekaman kontak baru di instans Sales. Rekaman kontak dari Sales harus digunakan dalam audiens wawasan dan digunakan sebagai sumber data. Id pelanggan juga harus disertakan dalam entitas Pelanggan terpadu untuk memetakan ID pelanggan agar ID dapat dihubungi sebelum segmen dapat diekspor.

## <a name="configure-the-connector-for-sales"></a>Konfigurasikan konektor untuk Sales

1. Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.

1. Di dalam **Dynamics 365 Sales**, pilih **konfigurasi**.

1. Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.

1. Masukkan URL Sales organisasi di **bidang alamat server**.

1. Di Bagian **akun admin server**, pilih **masuk** dan pilih akun Dynamics 365 Sales.

1. Petakan bidang ID pelanggan ke ID kontak Dynamics 365.

1. Pilih **Selanjutnya**.

1. Pilih satu atau beberapa segmen.

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengekspor data

Anda dapat [mengekspor data sesuai permintaan](export-destinations.md). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]