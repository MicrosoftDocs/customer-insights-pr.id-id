---
title: Konektor Power Automate | Microsoft Docs
description: Buat alur di Microsoft Power Automate dari Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 95e0fcbfb43f2b3e7e2d0e8a1690dc7ff5a44433402b7ef3d437710eb0efff15
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035603"
---
# <a name="power-automate-connector-preview"></a>Power Automate connector (pratinjau)

Picu aktivitas tertentu agar terjadi secara otomatis jika data Anda berubah dan kelola aliran yang lebih kompleks secara langsung di [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Pemicu Power Automate

Gunakan memicu untuk membuat alur cloud dan mengotomatisasi tugas berulang, seperti pemberitahuan atau tindakan yang lebih lanjut. 

- Memicu saat refresh sumber data gagal. 
- Memicu saat refresh sumber data berhasil.
- Memicu bila ambang terlewati pada segmen. Pemicu terbatas untuk melebihi atas ambang batas.
- Memicu bila ambang terlewati pada ukuran bisnis. Hanya ukuran bisnis tanpa dimensi yang didukung. Pemicu terbatas untuk melebihi atas ambang batas.
- Picu saat penyegaran penuh (sumber data, segmen, ukuran, ...) selesai.
- Pemicu saat refresh proses penyatuan (peta, pencocokan, penggabungan) selesai.

[Konfigurasikan pemicu di Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Tindakan Power Automate

Konektor Power Automate menyediakan tindakan lain selain pemicu yang tersedia. Untuk informasi lebih lanjut, lihat [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Buat Alur Power Automate

1. Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.

1. Di petak **Power Automate**, pilih **konfigurasi**.

1. Customer Insights Connector (pratinjau) dalam Power Automate terbuka. **Masuk** ke Power Automate.

1. Pilih salah satu pemicu yang tersedia dan tambahkan langkah lainnya ke alur baru Anda. Untuk informasi lebih lanjut, lihat [Membuat alur cloud dalam Power Automate](/power-automate/get-started-logic-flow).

Contoh cara menggunakan alur: 
- Posting pesan ke saluran Microsoft Teams jika penyegaran sumber data gagal. 
- Kirim email ke pemilik data saat ambang batas pada segmen terlewati.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
