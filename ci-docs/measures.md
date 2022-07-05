---
title: Gambaran umum pengukuran
description: Pelajari bagaimana ukuran membantu menganalisis dan mencerminkan kinerja bisnis Anda.
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
ms.openlocfilehash: 880c06bffcfa269151d96cb4c597eed4832fc61b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083122"
---
# <a name="measures-overview"></a>Gambaran umum pengukuran

Ukuran membantu Anda untuk lebih memahami perilaku pelanggan dan kinerja bisnis. Mereka melihat nilai-nilai yang relevan dari [profil terpadu](data-unification.md). Misalnya, bisnis ingin melihat *total pengeluaran per pelanggan* untuk memahami riwayat pembelian pelanggan individual atau mengukur *total penjualan perusahaan* untuk memahami pendapatan tingkat agregat dalam seluruh bisnis.  

Pengukuran dibuat [menggunakan pembuat](measure-builder.md) pengukuran, platform kueri data dengan berbagai operator, dan opsi pemetaan sederhana. Alat ini memungkinkan Anda memfilter data, mengelompokkan hasil, mendeteksi [jalur relasi entitas](relationships.md), dan mempratinjau output. Anda dapat [menggunakan templat](measure-templates.md) yang telah ditentukan sebelumnya untuk mengonfigurasi tindakan yang umum digunakan secara efisien.

Gunakan pembuat ukuran untuk merencanakan aktivitas bisnis dengan mengkueri data pelanggan dan mengekstrak wawasan. Contohnya, membuat ukuran *total pengeluaran per pelanggan* dan *penghasilan total per pelanggan* membantu mengidentifikasi grup pelanggan dengan pengeluaran tinggi namun penghasilan yang tinggi. Anda dapat [membuat segmen berdasarkan langkah-langkah](segments.md) ini untuk mendorong tindakan terbaik berikutnya.

## <a name="manage-your-measures"></a>Kelola ukuran Anda

Anda dapat menemukan daftar ukuran di halaman **Ukuran**.

Anda akan menemukan informasi tentang jenis pengukuran, pembuat, tanggal pembuatan, status, dan status. Bila Anda memilih ukuran dari daftar, Anda dapat mempratinjau output dan mengunduh file CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Tindakan untuk mengelola ukuran tunggal."lightbox="media/measures-actions.png":::

Tindakan berikut tersedia saat Anda memilih pengukuran:

- **Edit** konfigurasi ukuran.
- **Gandakan** ukuran. Anda dapat langsung memilih untuk mengedit propertinya atau cukup menyimpan duplikat.
- **segarkan** pengukuran berdasarkan data terbaru. Untuk menyegarkan semua tindakan Anda secara bersamaan, pilih semua tindakan, lalu **Refresh**.
- **Ubah nama** ukuran.
- **Aktifkan** atau **Nonaktifkan**. Ukuran yang tidak aktif tidak akan di-refresh selama [refresh terjadwal](system.md#schedule-tab).
- **Tag** untuk [mengelola tag](work-with-tags-columns.md#manage-tags) untuk segmen tersebut.
- **Hapus** ukuran.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Langkah selanjutnya

Anda dapat menggunakan langkah-langkah yang ada untuk membuat [segmen pelanggan](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
