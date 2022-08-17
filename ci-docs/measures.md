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
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245377"
---
# <a name="measures-overview"></a>Gambaran umum pengukuran

Ukuran membantu Anda untuk lebih memahami perilaku pelanggan dan kinerja bisnis. Mereka melihat nilai-nilai yang relevan dari [profil terpadu](data-unification.md). Misalnya, bisnis ingin melihat *total pengeluaran per pelanggan* untuk memahami riwayat pembelian pelanggan individual atau mengukur *total penjualan perusahaan* untuk memahami pendapatan tingkat agregat dalam seluruh bisnis.

Buat langkah-langkah untuk merencanakan aktivitas bisnis dengan mengkueri data pelanggan dan mengekstrak wawasan. Misalnya, buat ukuran total pembelanjaan *per pelanggan* dan *total pengembalian per pelanggan* untuk membantu mengidentifikasi sekelompok pelanggan dengan pengeluaran tinggi namun pengembalian tinggi. Kemudian, [buat segmen berdasarkan langkah-langkah](segments.md) ini untuk mendorong tindakan terbaik berikutnya.

## <a name="create-a-measure"></a>Membuat ukuran

Pilih cara membuat pengukuran berdasarkan audiens target Anda.

# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

- Dari awal dengan pembuat ukuran: [Bangun sendiri](measure-builder.md).
- Dari tindakan yang umum digunakan: [Gunakan templat](measure-templates.md) yang telah ditentukan sebelumnya.

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

Dari awal dengan pembuat ukuran: [Bangun sendiri](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Mengelola langkah-langkah yang ada

Buka **halaman Tindakan** untuk melihat pengukuran yang Anda buat, statusnya, jenis pengukurannya, dan terakhir kali data disegarkan. Anda bisa mengurutkan daftar pengukuran menurut kolom mana pun atau menggunakan kotak pencarian untuk menemukan pengukuran yang ingin Anda kelola.

Pilih di samping pengukuran untuk melihat tindakan yang tersedia. Pilih nama pengukuran untuk melihat pratinjau output dan mendownload file CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Tindakan untuk mengelola ukuran tunggal."lightbox="media/measures-actions.png":::

- **Edit** pengukuran untuk mengubah propertinya.
- **Refresh** pengukuran untuk menyertakan data terbaru.
- **Ubah nama** ukuran.
- **Mengaktifkan** atau **Menonaktifkan** pengukuran. Tindakan tidak aktif tidak akan disegarkan selama [refresh](schedule-refresh.md) terjadwal dan **statusnya** terdaftar sebagai **Dilewati**, yang menunjukkan bahwa refresh bahkan tidak dicoba.
- **Beri** tag untuk [mengelola tag](work-with-tags-columns.md#manage-tags) untuk pengukuran tersebut.
- **Hapus** ukuran.
- **Kolom** untuk [mengkustomisasi kolom](work-with-tags-columns.md#customize-columns) yang ditampilkan.
- **Filter** untuk [memfilter tag](work-with-tags-columns.md#filter-on-tags).
- **Cari nama** untuk dicari berdasarkan nama pengukuran.

## <a name="refresh-measures"></a>Langkah-langkah penyegaran

Langkah-langkah dapat disegarkan pada jadwal otomatis atau disegarkan secara manual sesuai permintaan. Untuk me-refresh satu atau beberapa pengukuran secara manual, pilih pengukuran tersebut dan pilih **Refresh**. Untuk [menjadwalkan refresh](schedule-refresh.md) otomatis, buka **Jadwal** > **Sistem** > **Admin**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
