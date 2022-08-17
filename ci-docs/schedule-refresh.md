---
title: Jadwalkan penyegaran sistem
description: Jadwalkan waktu ketika sistem harus disegarkan
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: ce10fcfe9906d33209270f8f6930a51b045b13e2
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246430"
---
# <a name="schedule-system-refresh"></a>Jadwalkan penyegaran sistem

Jadwalkan refresh otomatis dari semua sumber data yang Anda [konsumsi](data-sources.md). Penyegaran otomatis membantu memastikan bahwa pembaruan dari sumber data Anda tercermin dalam profil pelanggan terpadu Anda.

> [!NOTE]
> Power Query sumber data yang dikelola oleh Anda refresh pada jadwal mereka sendiri. Untuk menjadwalkan refresh sumber data ini Power Query, konfigurasikan pengaturan refresh pada sumber data tertentu dari **halaman Sumber** data.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Pengaturan refresh aliran data.":::

## <a name="set-system-refresh-schedule"></a>Mengatur jadwal penyegaran sistem

1. Buka **Sistem** > **Admin** dan pilih tab **Jadwal**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Jadwalkan tab refresh dari halaman Sistem.":::

1. Status default untuk refresh terjadwal adalah **tidak aktif**. Untuk mengaktifkan penyegaran terjadwal, Ubah pengalih di bagian atas layar ke **aktif**.

1. Pilih antara penyegaran **mingguan** (default) dan **harian**. Jika Anda ingin menjadwalkan penyegaran mingguan, pilih satu atau beberapa hari untuk menjalankan refresh.

1. Atur **zona waktu**, lalu gunakan dropdown **waktu** untuk mengatur waktu penyegaran. Jika Anda ingin menjadwalkan beberapa penyegaran dalam satu hari, pilih **Tambah waktu lain**.

1. Pilih **Simpan** untuk menerapkan perubahan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
