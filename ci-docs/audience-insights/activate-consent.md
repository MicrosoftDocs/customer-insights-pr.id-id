---
title: Mengaktifkan aturan persetujuan untuk segmen
description: Ikuti langkah-langkah ini untuk menautkan data persetujuan dan aktifkan pemeriksaan persetujuan dalam wawasan audiens. Admin juga dapat menonaktifkan pemeriksaan persetujuan.
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 552cb0739c4d17266dd028638df067f3384b738a
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884078"
---
# <a name="activate-consent-rules"></a>Mengaktifkan aturan persetujuan

[Pusat Persetujuan (pratinjau)](../consent-management/overview.md) membantu Anda menyelaraskan data persetujuan dari berbagai sumber. Gunakan entitas Persetujuan terpadu *untuk menerapkan pemeriksaan persetujuan* default. Setelah mengimpor data persetujuan ke Pusat Persetujuan dan mengonfigurasi aturan untuk data, *entitas Persetujuan secara otomatis* disinkronkan untuk audiens wawasan.

## <a name="enable-consent-checks"></a>Aktifkan pemeriksaan persetujuan

Dengan data persetujuan yang diimpor ke Pusat Persetujuan (pratinjau) dan aturan yang disiapkan, Anda dapat mengaktifkan pemeriksaan persetujuan. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Tab Persetujuan di audiens pengaturan wawasan dengan data persetujuan yang diaktifkan.":::

1. Di wawasan audiens, buka **Admin** > **Sistem**.

1. Pilih **tab Persetujuan** (pratinjau).

1. Di **bagian Aktifkan pemeriksaan** persetujuan, atur sakelar ke **On untuk semua area yang ingin Anda** aktifkan.

1. Pilih **kotak centang Izinkan penilang aturan persetujuan default** untuk menghapus pemeriksaan persetujuan default yang diberlakukan pada segmen tertentu. 

1. Di menu dropdown, pilih di mana Anda ingin mengizinkan peni1 atas.     

1. Di **bagian Persetujuan Tautan ke** profil pelanggan, pilih atribut yang digunakan sebagai pengenal untuk menautkan data persetujuan ke data pelanggan. Kemungkinan akan menjadi nomor telepon atau alamat email. 

1. Pilih **Simpan untuk menerapkan pengaturan** Anda.

## <a name="disable-consent-checks"></a>Nonaktifkan pemeriksaan persetujuan

Untuk berhenti menggunakan data persetujuan dalam wawasan audiens, admin harus memperbarui pengaturan sistem yang sesuai.

1. Di wawasan audiens, buka **Admin** > **Sistem**.

1. Pilih **tab Persetujuan** (pratinjau).

1. Di **bagian Aktifkan pemeriksaan** persetujuan, atur sakelar ke **Mati**.

> [!TIP]
> Untuk berhenti menggunakan kemampuan manajemen persetujuan, lihat [Pengaturan sistem di Pusat Persetujuan (pratinjau).](../consent-management/system-settings.md)
