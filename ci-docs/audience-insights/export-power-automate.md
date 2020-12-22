---
title: Konektor Power Automate | Microsoft Docs
description: Buat alur di Microsoft Power Automate dari Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406035"
---
# <a name="power-automate-connector-preview"></a>Power Automate connector (pratinjau)

Picu aktivitas tertentu agar terjadi secara otomatis jika data Anda berubah dan kelola aliran yang lebih kompleks secara langsung di [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Pemicu Power Automate

Anda dapat menggunakan berbagai pemicu yang memungkinkan Anda membuat alur untuk mengotomatisasi tugas yang berulang-ulang, seperti pemberitahuan atau tindakan yang lebih canggih. 

- Memicu saat refresh sumber data gagal. 
- Memicu saat refresh sumber data berhasil.
- Memicu bila ambang terlewati pada segmen. Pemicu terbatas untuk melebihi atas ambang batas.
- Memicu bila ambang terlewati pada ukuran bisnis. Pemicu terbatas untuk melebihi atas ambang batas.
- Picu saat penyegaran penuh (sumber data, segmen, ukuran,...) selesai.
- Pemicu saat refresh proses penyatuan (peta, pencocokan, penggabungan) selesai.

[Konfigurasikan pemicu di Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Tindakan Power Automate
Konektor Power Automate menyediakan tindakan lain selain pemicu yang tersedia. Untuk informasi lebih lanjut, lihat [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Membuat alur Power Automate di wawasan audiens

1. Di wawasan audiens, buka **Admin** > **Sistem**.

1. Di halaman **Sistem**, pilih tab **Status**.

1. Di Bagian **sumber data**, pilih **alur**, lalu pilih **buat alur** dari daftar menurun.
   > [!div class="mx-imgBorder"]
   > ![Power Automate connector yang menampilkan tindakan membuat alur](media/power-automate-connector-create-flow.png "Power Automate connector yang menampilkan tindakan membuat alur")

1. Di Power Automate, pilih salah satu pemicu yang tersedia untuk membuat alur yang diinginkan. Jika Anda membuat alur pertama, Anda harus mengotentikasi dengan Power Automate connector terlebih dulu.
