---
title: Mengaktifkan aturan persetujuan untuk segmen
description: Ikuti langkah-langkah ini untuk menautkan data persetujuan dan mengaktifkan pemeriksaan persetujuan di audiens wawasan. Admin juga dapat menonaktifkan pemeriksaan persetujuan.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4b55c82229b1a6189c0dd67d145386344286df8a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227497"
---
# <a name="activate-consent-rules"></a>Mengaktifkan aturan persetujuan

[Pusat Persetujuan (pratinjau)](../consent-management/overview.md) membantu Anda menyelaraskan data persetujuan dari berbagai sumber. Gunakan entitas Persetujuan *terpadu* untuk menerapkan pemeriksaan persetujuan default. Setelah mengimpor data persetujuan ke Pusat Persetujuan dan mengonfigurasi aturan untuk data, *entitas Persetujuan* secara otomatis disinkronkan ke wawasan audiens.

## <a name="enable-consent-checks"></a>Aktifkan pemeriksaan persetujuan

Dengan data persetujuan yang diimpor ke Pusat Persetujuan (pratinjau) dan aturan yang disiapkan, Anda dapat mengaktifkan pemeriksaan persetujuan. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Tab Persetujuan di setelan wawasan audiens dengan data persetujuan yang diaktifkan.":::

1. Di wawasan audiens, buka **Admin** > **Sistem**.

1. **Pilih tab Persetujuan (pratinjau**).

1. **Di bagian Aktifkan pemeriksaan** persetujuan, atur tombol ke **Aktif** untuk semua area yang ingin Anda aktifkan.

1. **Pilih kotak centang Izinkan penggantian aturan** persetujuan default untuk menghapus pemeriksaan persetujuan default yang diberlakukan pada segmen tertentu. 

1. Di menu tarik-turun, pilih di mana Anda ingin mengizinkan penggantian.     

1. **Di bagian Tautkan persetujuan ke profil** pelanggan, pilih atribut yang digunakan sebagai pengidentifikasi untuk menautkan data persetujuan ke data pelanggan. Ini mungkin akan menjadi nomor telepon atau alamat email. 

1. Pilih **Simpan** untuk menerapkan pengaturan Anda.

## <a name="disable-consent-checks"></a>Nonaktifkan pemeriksaan persetujuan

Untuk berhenti menggunakan data persetujuan dalam audiens insight, admin harus memperbarui pengaturan sistem yang sesuai.

1. Di wawasan audiens, buka **Admin** > **Sistem**.

1. **Pilih tab Persetujuan (pratinjau**).

1. **Di bagian Aktifkan pemeriksaan** persetujuan, atur alihkan ke **Mati**.

> [!TIP]
> Untuk berhenti menggunakan kemampuan manajemen persetujuan, lihat [Pengaturan sistem di Pusat Persetujuan (pratinjau)](../consent-management/system-settings.md).
