---
title: Memahami dan mengelola langkah-langkah
description: Pelajari bagaimana langkah-langkah membantu menganalisis dan mencerminkan kinerja bisnis Anda.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359782"
---
# <a name="measures-overview"></a>Mengukur gambaran umum

Ukuran membantu Anda untuk lebih memahami perilaku pelanggan dan kinerja bisnis. Mereka melihat nilai-nilai yang relevan dari [profil terpadu](data-unification.md). Misalnya, bisnis ingin melihat *total pengeluaran per pelanggan* untuk memahami riwayat pembelian pelanggan individual atau mengukur *total penjualan perusahaan* untuk memahami pendapatan tingkat agregat dalam seluruh bisnis.  

Langkah-langkah dibuat [menggunakan pembangun](measure-builder.md) ukuran, platform kueri data dengan berbagai operator dan opsi pemetaan sederhana. Alat ini memungkinkan Anda memfilter data, mengelompokkan hasil, mendeteksi [jalur relasi entitas](relationships.md), dan mempratinjau output. Anda dapat [menggunakan templat](measure-templates.md) yang telah ditentukan untuk mengonfigurasi tindakan yang umum digunakan secara efisien.

Gunakan pembuat ukuran untuk merencanakan aktivitas bisnis dengan mengkueri data pelanggan dan mengekstrak wawasan. Contohnya, membuat ukuran *total pengeluaran per pelanggan* dan *penghasilan total per pelanggan* membantu mengidentifikasi grup pelanggan dengan pengeluaran tinggi namun penghasilan yang tinggi. Anda dapat [membuat segmen](segments.md) berdasarkan langkah-langkah ini untuk mendorong tindakan terbaik berikutnya. 

## <a name="manage-your-measures"></a>Kelola ukuran Anda

Anda dapat menemukan daftar ukuran di halaman **Ukuran**.

Anda akan menemukan informasi tentang jenis pengukuran, pembuat, tanggal pembuatan, status, dan status. Bila Anda memilih ukuran dari daftar, Anda dapat mempratinjau output dan mengunduh file CSV.

Untuk me-refresh semua ukuran Anda pada waktu yang sama, pilih **Segarkan semua** tanpa memilih ukuran tertentu.

:::image type="content" source="media/measure-actions.png" alt-text="Tindakan untuk mengelola ukuran tunggal.":::

Pilih ukuran dari daftar untuk pilihan berikut:

- Pilih nama ukuran untuk melihat rinciannya.
- **Edit** konfigurasi ukuran.
- **segarkan** pengukuran berdasarkan data terbaru.
- **Ubah nama** ukuran.
- **Hapus** ukuran.
- **Aktifkan** atau **Nonaktifkan**. Ukuran yang tidak aktif tidak akan di-refresh selama [refresh terjadwal](system.md#schedule-tab).

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Langkah selanjutnya

Anda dapat menggunakan langkah-langkah yang ada untuk membuat [segmen pelanggan](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
