---
title: Ekspor data Customer Insights ke Dynamics 365 Marketing
description: Pelajari cara mengkonfigurasi sambungan ke Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643777"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Konektor untuk Dynamics 365 Marketing (pratinjau)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Gunakan [segmen](segments.md) untuk membuat kampanye dan hubungi grup pelanggan tertentu dengan Dynamics 365 Marketing. Untuk informasi lebih lanjut, lihat [menggunakan segmen dari Dynamics 365 Customer Insights dengan Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Prasyarat

Kontak rekaman dari [Common Data Service yang diserap Dynamics 365 Marketing](connect-power-query.md).

## <a name="configure-the-connector-for-marketing"></a>Konfigurasikan konektor untuk Marketing

1. Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.

1. Di dalam **Dynamics 365 Marketing**, pilih **konfigurasi**.

1. Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.

1. Masukkan URL Marketing organisasi di **bidang alamat server**.

1. Di Bagian **akun admin server**, pilih **masuk** dan pilih akun Dynamics 365 Marketing.

1. Petakan bidang ID pelanggan ke ID kontak Dynamics 365.

1. Pilih **Selanjutnya**.

1. Pilih satu atau beberapa segmen.

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengekspor data

Anda dapat [mengekspor data sesuai permintaan](export-destinations.md). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).
