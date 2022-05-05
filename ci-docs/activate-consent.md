---
title: Mengaktifkan aturan persetujuan untuk segmen
description: Ikuti langkah-langkah ini untuk menautkan data persetujuan dan mengaktifkan pemeriksaan persetujuan di Dynamics 365 Customer Insights. Admin juga dapat menonaktifkan pemeriksaan persetujuan.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bfa03f4b7b56b300a74ebd04721cd64b893879f1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642529"
---
# <a name="activate-consent-rules"></a>Mengaktifkan aturan persetujuan

[Pusat Persetujuan (pratinjau)](consent-management/overview.md) membantu Anda menyelaraskan data persetujuan dari berbagai sumber. Gunakan entitas Persetujuan *terpadu* untuk menerapkan pemeriksaan persetujuan default. Setelah mengimpor data persetujuan ke Pusat Persetujuan dan mengonfigurasi aturan untuk data, *entitas Persetujuan* secara otomatis disinkronkan ke Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Aktifkan pemeriksaan persetujuan

Dengan data persetujuan yang diimpor ke Pusat Persetujuan (pratinjau) dan aturan yang disiapkan, Anda dapat mengaktifkan pemeriksaan persetujuan. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Tab Persetujuan di pengaturan Wawasan Pelanggan dengan data persetujuan yang diaktifkan.":::

1. Di Customer Insights, buka **Admin** > **Sistem**.

1. **Pilih tab Persetujuan (pratinjau**).

1. **Di bagian Aktifkan pemeriksaan** persetujuan, atur sakelar ke **Aktif** untuk semua area yang ingin Anda aktifkan.

1. Pilih kotak centang **Izinkan penggantian aturan** persetujuan default untuk menghapus pemeriksaan persetujuan default yang diberlakukan pada segmen tertentu. 

1. Di menu tarik-turun, pilih di mana Anda ingin mengizinkan penimpaan.     

1. **Di bagian Tautkan persetujuan ke profil** pelanggan, pilih atribut yang digunakan sebagai pengenal untuk menautkan data persetujuan ke data pelanggan. Kemungkinan akan menjadi nomor telepon atau alamat email. 

1. Pilih **Simpan** untuk menerapkan pengaturan Anda.

## <a name="disable-consent-checks"></a>Menonaktifkan pemeriksaan persetujuan

Untuk berhenti menggunakan data persetujuan di Customer Insights, admin harus memperbarui pengaturan sistem yang sesuai.

1. Di Customer Insights, buka **Admin** > **Sistem**.

1. **Pilih tab Persetujuan (pratinjau**).

1. Di **bagian Aktifkan pemeriksaan** persetujuan, atur sakelar ke **Nonaktif**.

> [!TIP]
> Untuk berhenti menggunakan kemampuan manajemen persetujuan, lihat [Pengaturan sistem di Pusat Persetujuan (pratinjau)](consent-management/system-settings.md).
