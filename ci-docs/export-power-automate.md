---
title: Konektor Power Automate | Microsoft Docs
description: Buat alur di Microsoft Power Automate dari Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d22c4c785695b23a257a89f1ffa519fdc18b443e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741183"
---
# <a name="power-automate-connector-preview"></a>Power Automate connector (pratinjau)

Picu aktivitas tertentu agar terjadi secara otomatis jika data Anda berubah dan kelola aliran yang lebih kompleks secara langsung di [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Anda dapat melakukan maksimal 100 panggilan per 60 detik. Anda dapat memanggil API titik akhir beberapa kali dengan menggunakan parameter $skip. [Pelajari parameter $skip lebih lanjut](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Pemicu Power Automate

Gunakan memicu untuk membuat alur cloud dan mengotomatisasi tugas berulang, seperti pemberitahuan atau tindakan yang lebih lanjut.

- Memicu saat refresh sumber data gagal.
- Memicu saat refresh sumber data berhasil.
- Memicu bila ambang terlewati pada segmen. Pemicu terbatas untuk melebihi atas ambang batas.
- Memicu bila ambang terlewati pada ukuran bisnis. Hanya ukuran bisnis tanpa dimensi yang didukung. Pemicu terbatas untuk melebihi atas ambang batas.
- Picu saat penyegaran penuh (sumber data, segmen, ukuran, ...) selesai.
- Pemicu saat penyegaran proses penyatuan selesai.

[Konfigurasikan pemicu di Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Tindakan Power Automate

Konektor Power Automate menyediakan tindakan lain selain pemicu yang tersedia. Untuk informasi lebih lanjut, lihat [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Buat Alur Power Automate

1. Buka **Admin** > **Tujuan ekspor**.

1. Di petak **Power Automate**, pilih **konfigurasi**.

1. Customer Insights Connector (pratinjau) dalam Power Automate terbuka. **Masuk** ke Power Automate.

1. Pilih salah satu pemicu yang tersedia dan tambahkan langkah lainnya ke alur baru Anda. Untuk informasi lebih lanjut, lihat [Membuat alur cloud dalam Power Automate](/power-automate/get-started-logic-flow).

Contoh cara menggunakan alur: 
- Posting pesan ke saluran Microsoft Teams jika penyegaran sumber data gagal. 
- Kirim email ke pemilik data saat ambang batas pada segmen terlewati.



[!INCLUDE [footer-include](includes/footer-banner.md)]
