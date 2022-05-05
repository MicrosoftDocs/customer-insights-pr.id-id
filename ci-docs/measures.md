---
title: Memahami dan mengelola langkah-langkah
description: Pelajari bagaimana langkah-langkah membantu menganalisis dan mencerminkan kinerja bisnis Anda.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 84a3a10a2517258c1f895800882b9c67391ec3de
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642630"
---
# <a name="measures-overview"></a>Gambaran umum pengukuran

Ukuran membantu Anda untuk lebih memahami perilaku pelanggan dan kinerja bisnis. Mereka melihat nilai-nilai yang relevan dari [profil terpadu](data-unification.md). Misalnya, bisnis ingin melihat *total pengeluaran per pelanggan* untuk memahami riwayat pembelian pelanggan individual atau mengukur *total penjualan perusahaan* untuk memahami pendapatan tingkat agregat dalam seluruh bisnis.  

Langkah-langkah dibuat [menggunakan pembuat](measure-builder.md) ukuran, platform kueri data dengan berbagai operator dan opsi pemetaan sederhana. Alat ini memungkinkan Anda memfilter data, mengelompokkan hasil, mendeteksi [jalur relasi entitas](relationships.md), dan mempratinjau output. Anda dapat [menggunakan templat](measure-templates.md) yang telah ditentukan untuk mengonfigurasi tindakan yang umum digunakan secara efisien.

Gunakan pembuat ukuran untuk merencanakan aktivitas bisnis dengan mengkueri data pelanggan dan mengekstrak wawasan. Contohnya, membuat ukuran *total pengeluaran per pelanggan* dan *penghasilan total per pelanggan* membantu mengidentifikasi grup pelanggan dengan pengeluaran tinggi namun penghasilan yang tinggi. Anda dapat [membuat segmen](segments.md) berdasarkan langkah-langkah ini untuk mendorong tindakan terbaik berikutnya.

## <a name="manage-your-measures"></a>Kelola ukuran Anda

Anda dapat menemukan daftar ukuran di halaman **Ukuran**.

Anda akan menemukan informasi tentang jenis pengukuran, pembuat, tanggal pembuatan, status, dan status. Bila Anda memilih ukuran dari daftar, Anda dapat mempratinjau output dan mengunduh file CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Tindakan untuk mengelola ukuran tunggal."lightbox="media/measures-actions.png":::

Tindakan berikut tersedia saat Anda memilih ukuran:

- **Edit** konfigurasi ukuran.
- **Menduplikasi** ukuran. Anda dapat langsung memilih untuk mengedit propertinya atau cukup menyimpan duplikat.
- **segarkan** pengukuran berdasarkan data terbaru. Untuk menyegarkan semua tindakan Anda secara bersamaan, pilih semua tindakan lalu **Refresh**.
- **Ubah nama** ukuran.
- **Aktifkan** atau **Nonaktifkan**. Ukuran yang tidak aktif tidak akan di-refresh selama [refresh terjadwal](system.md#schedule-tab).
- **Tag** untuk [mengelola tag](work-with-tags-columns.md#manage-tags) untuk segmen.
- **Hapus** ukuran.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Langkah selanjutnya

Anda dapat menggunakan langkah-langkah yang ada untuk membuat [segmen pelanggan](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
