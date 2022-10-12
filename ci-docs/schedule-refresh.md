---
title: Jadwalkan penyegaran sistem
description: Jadwalkan waktu ketika sistem harus disegarkan
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610332"
---
# <a name="schedule-system-refresh"></a>Jadwalkan penyegaran sistem

Jadwalkan refresh otomatis dari semua sumber data yang Anda [konsumsi](data-sources.md). Penyegaran otomatis membantu memastikan bahwa pembaruan dari sumber data Anda tercermin dalam profil pelanggan terpadu Anda.

> [!NOTE]
> Power Query sumber data yang dikelola oleh Anda refresh pada jadwal mereka sendiri. Untuk menjadwalkan refresh sumber data ini Power Query, konfigurasikan pengaturan refresh pada sumber data tertentu dari **halaman Sumber** data. Sejajarkan waktu dengan jadwal refresh data hulu sehingga refresh tidak semuanya terjadi sekaligus.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Pengaturan refresh aliran data.":::

## <a name="set-system-refresh-schedule"></a>Mengatur jadwal penyegaran sistem

1. Buka **Sistem** > **Admin** dan pilih tab **Jadwal**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Jadwalkan tab refresh dari halaman Sistem.":::

1. Status default untuk refresh terjadwal adalah **tidak aktif**. Untuk mengaktifkan penyegaran terjadwal, Ubah pengalih di bagian atas layar ke **aktif**.

1. Pilih antara penyegaran **mingguan** (default) dan **harian**. Jika Anda ingin menjadwalkan penyegaran mingguan, pilih satu atau beberapa hari untuk menjalankan refresh.

1. Atur **zona waktu**, lalu gunakan dropdown **waktu** untuk mengatur waktu penyegaran. Jika Anda ingin menjadwalkan beberapa penyegaran dalam satu hari, pilih **Tambah waktu lain**. Anda dapat menambahkan hingga empat penyegaran.

1. Pilih **Simpan** untuk menerapkan perubahan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
