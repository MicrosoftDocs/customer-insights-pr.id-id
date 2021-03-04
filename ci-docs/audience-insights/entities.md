---
title: Entitas dan himpunan data
description: Lihat data pada halaman entitas.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269380"
---
# <a name="entities-in-audience-insights"></a>Entitas dalam wawasan audiens

Setelah [mengkonfigurasi sumber data](data-sources.md), buka halaman **entitas** untuk mengevaluasi kualitas data yang terserap. Entitas dianggap sebagai himpunan data. Beberapa kemampuan Dynamics 365 Customer Insights dibangun di sekitar entitas ini. Meninjau mereka secara dekat dapat membantu Anda memvalidasi output dari kemampuan tersebut.

Halaman **entitas** mencantumkan entitas dan mencakup beberapa kolom:

- **Nama**: nama entitas data Anda. Jika Anda melihat simbol peringatan di samping nama entitas, berarti bahwa data untuk entitas tersebut tidak berhasil dimuat.
- **Sumber**: jenis sumber data yang menyerap entitas
- **Dibuat oleh**: Nama orang yang membuat entitas
- **Dibuat**: tanggal dan waktu pembuatan entitas
- **Diperbarui oleh**: Nama orang yang memperbarui entitas
- **Terakhir Diperbarui**: tanggal dan waktu pembaruan terakhir entitas
- **Refresh terakhir**: tanggal dan waktu penyegaran data terakhir

## <a name="exploring-a-specific-entitys-data"></a>Menjelajahi data entitas tertentu

Pilih entitas untuk menjelajahi bidang dan rekaman yang berbeda yang tercakup dalam entitas tersebut.

> [!div class="mx-imgBorder"]
> ![Pilih entitas](media/data-manager-entities-data.png "Pilih entitas")

- Tab **data** dipilih secara default dan menampilkan rincian daftar tabel tentang rekaman individual entitas.

> [!div class="mx-imgBorder"]
> ![Tabel bidang](media/data-manager-entities-fields.PNG "Tabel bidang")

- Tab **Bidang** menampilkan tabel untuk meninjau rincian untuk entitas yang dipilih, seperti nama bidang, jenis data, dan jenis. Kolom **jenis** menunjukkan jenis terkait Common Data Model, yang baik yang diidentifikasi secara otomatis oleh sistem, atau yang [dipetakan secara manual](map-entities.md) oleh pengguna. Jenis semantik ini dapat berbeda dari jenis data atribut misalnya, bidang *email* di bawah ini memiliki jenis data *teks* namun jenis Common Data Model (semantik)-nya mungkin *email* atau *EmailAddress*.

> [!NOTE]
> Kedua tabel hanya menampilkan sampel data entitas. Untuk melihat himpunan data lengkap, buka halaman **sumber data**, pilih entitas, pilih **Edit**, lalu lihat data entitas ini dengan editor Power Query seperti dijelaskan dalam [sumber data](data-sources.md).

Untuk mempelajari lebih lanjut tentang data yang terserap di entitas, kolom **ringkasan** memberi Anda beberapa karakteristik penting data, seperti null, nilai yang tidak ada, nilai unik, jumlah, dan distribusi, sebagaimana berlaku untuk data Anda.

Pilih ikon diagram untuk melihat ringkasan data.

> [!div class="mx-imgBorder"]
> ![Simbol ringkasan](media/data-manager-entities-summary.png "Tabel Ringkasan Data")

### <a name="next-step"></a>Langkah berikutnya

Lihat topik [Satukan](data-unification.md) untuk mempelajari cara *memetakan*, *mencocokkan*, dan *menggabungkan* data yang terserap.


[!INCLUDE[footer-include](../includes/footer-banner.md)]