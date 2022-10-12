---
title: Entitas di Customer Insights
description: Lihat data pada halaman entitas.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610102"
---
# <a name="entities-in-customer-insights"></a>Entitas di Customer Insights

Setelah [mengkonfigurasi sumber data](data-sources.md), buka halaman **entitas** untuk mengevaluasi kualitas data yang terserap. Entitas dianggap sebagai himpunan data. Beberapa kemampuan Dynamics 365 Customer Insights dibangun di sekitar entitas ini. Meninjau mereka secara dekat dapat membantu Anda memvalidasi output dari kemampuan tersebut.

Saat Anda bekerja di Customer Insights yang memperkaya data Anda atau membuat segmen, ukuran, dan aktivitas, entitas yang dibuat dari tindakan tersebut ditampilkan di **halaman Entitas**.

## <a name="view-a-list-of-entities"></a>Menampilkan daftar entitas

Buka **Entitas** > **Data** untuk melihat daftar entitas. Informasi berikut ditampilkan untuk setiap entitas.

- **Nama**: Nama entitas data. Jika Anda melihat simbol peringatan di samping nama entitas, berarti bahwa data untuk entitas tersebut tidak berhasil dimuat.
- **Sumber**: Jenis sumber data yang menelan entitas.
- **Diperbarui**: Waktu entitas terakhir diperbarui.
- **Status**: Detail tentang pembaruan terakhir entitas.

## <a name="explore-a-specific-entitys-data"></a>Jelajahi data entitas tertentu

1. Buka **Entitas** > **Data**.
1. Pilih entitas untuk membuka halaman detail.  
1. Jelajahi berbagai bidang dan rekaman yang disertakan untuk entitas tersebut.

- Tab **Atribut** dipilih secara default dan menampilkan detail untuk entitas yang dipilih, seperti nama bidang, tipe data, dan jenis. Kolom **jenis** menunjukkan jenis terkait Common Data Model, yang baik yang diidentifikasi secara otomatis oleh sistem, atau yang [dipetakan secara manual](map-entities.md) oleh pengguna. Jenis ini adalah jenis semantik yang dapat berbeda dari jenis data atribut. Misalnya, bidang *Email* di bawah ini memiliki string tipe *data* tetapi jenis Common Data Model (semantik) mungkin *Email*, *EmailAddress*, atau *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabel bidang.":::

   > [!NOTE]
   > Halaman ini hanya menampilkan sampel data entitas Anda. Untuk melihat himpunan data lengkap, buka **halaman Sumber** data, pilih entitas, pilih **Edit**, lalu lihat data entitas ini dengan Power Query editor seperti yang dijelaskan di [Sumber data](data-sources.md).

   Untuk mempelajari selengkapnya tentang data yang diserap dalam entitas, **kolom Ringkasan** menyediakan beberapa karakteristik data penting, seperti nulls, missing values, unique values, counts, and distributions, apa pun yang berlaku untuk data Anda. Pilih ikon diagram untuk melihat ringkasan data.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Tabel ringkasan data.":::

- Tab **Data** menampilkan detail tentang rekaman individual entitas. Detail yang tercantum bergantung pada tipe data entitas.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Pilih entitas.":::

- Tab **Laporan** (tersedia untuk beberapa entitas) memungkinkan Anda memvisualisasikan data dengan membuat laporan, yang mencakup kolom berikut:

  - **Nama laporan**: Nama laporan.
  - **Dibuat oleh**: Nama orang yang membuat entitas.
  - **Dibuat**: Tanggal dan waktu pembuatan entitas.
  - **Diedit oleh**: Nama orang yang memodifikasi entitas.
  - **Diedit**: Tanggal dan waktu modifikasi entitas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
