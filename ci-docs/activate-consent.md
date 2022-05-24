---
title: Mengaktifkan aturan persetujuan untuk segmen
description: Ikuti langkah-langkah ini untuk menautkan data persetujuan dan mengaktifkan pemeriksaan persetujuan di Dynamics 365 Customer Insights. Admin juga dapat menonaktifkan pemeriksaan persetujuan.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755174"
---
# <a name="activate-consent-rules"></a>Mengaktifkan aturan persetujuan

[Pusat Persetujuan (pratinjau)](consent-management/overview.md) membantu Anda menyelaraskan data persetujuan dari berbagai sumber. Gunakan entitas Persetujuan *terpadu* untuk menerapkan pemeriksaan persetujuan default. Setelah mengimpor data persetujuan dan mengonfigurasi aturan peta, *entitas Persetujuan* secara otomatis disinkronkan ke Dynamics 365 Customer Insights.

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
