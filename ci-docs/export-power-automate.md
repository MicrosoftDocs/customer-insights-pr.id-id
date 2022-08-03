---
title: Power Automate| konektor (pratinjau) Dokumen Microsoft
description: Buat alur di Microsoft Power Automate dari Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196122"
---
# <a name="power-automate-connector-preview"></a>Power Automate connector (pratinjau)

Picu aktivitas tertentu agar terjadi secara otomatis jika data Anda berubah dan kelola aliran yang lebih kompleks secara langsung di [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Maksimal 100 panggilan per 60 detik. [Gunakan parameter](/connectors/customerinsights/#get-items-from-an-entity) $skip untuk memanggil API titik akhir beberapa kali.

## <a name="power-automate-triggers"></a>Pemicu Power Automate

Gunakan memicu untuk membuat alur cloud dan mengotomatisasi tugas berulang, seperti pemberitahuan atau tindakan yang lebih lanjut. Gunakan pemicu saat:

- Penyegaran sumber data gagal.
- Penyegaran sumber data berhasil.
- Ambang batas dilintasi pada segmen. Pemicu terbatas untuk melebihi atas ambang batas.
- Ambang batas dilintasi pada ukuran bisnis. Hanya ukuran bisnis tanpa dimensi yang didukung. Pemicu terbatas untuk melebihi atas ambang batas.
- Penyegaran terjadwal penuh selesai. Pemicu ini tidak berfungsi untuk refresh yang dimulai secara manual.
- Penyegaran proses penyatuan selesai.

[Konfigurasikan pemicu di Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Tindakan Power Automate

Konektor Power Automate menyediakan tindakan lain selain pemicu yang tersedia. Untuk informasi lebih lanjut, lihat [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Buat Alur Power Automate

1. Buka **Admin** > **Koneksi**.

1. Di petak **Power Automate**, pilih **konfigurasi**.

1. Customer Insights Connector (pratinjau) dalam Power Automate terbuka. **Masuk** ke Power Automate.

1. Pilih salah satu pemicu yang tersedia dan tambahkan langkah lainnya ke alur baru Anda. Untuk informasi lebih lanjut, lihat [Membuat alur cloud dalam Power Automate](/power-automate/get-started-logic-flow).

Contoh cara menggunakan alur: 
- Posting pesan ke saluran Microsoft Teams jika penyegaran sumber data gagal. 
- Kirim email ke pemilik data saat ambang batas pada segmen terlewati.

[!INCLUDE [footer-include](includes/footer-banner.md)]
