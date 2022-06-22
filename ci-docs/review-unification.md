---
title: Meninjau penyatuan data
description: Tinjau langkah-langkah penyatuan data, buat profil pelanggan terpadu, dan tinjau hasilnya
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844090"
---
# <a name="review-data-unification"></a>Meninjau penyatuan data

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Langkah terakhir dalam proses penyatuan ini menunjukkan ringkasan langkah-langkah dalam proses dan memberikan kesempatan untuk membuat perubahan sebelum Anda membuat profil terpadu.

:::image type="content" source="media/m3_review.png" alt-text="Cuplikan layar Tinjau dan Buat profil pelanggan.":::

## <a name="review-the-data-unification-steps"></a>Meninjau langkah-langkah penyatuan data

1. Pilih **Edit** pada salah satu langkah penyatuan data untuk meninjau dan membuat perubahan apa pun.

1. Jika Anda puas dengan pilihan Anda, pilih **Buat profil pelanggan**. Halaman **Satukan Unitkan** ditampilkan saat profil pelanggan terpadu sedang dibuat. Semua petak kecuali **bidang** Sumber memperlihatkan **status Antrekan** atau **Refresh**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Cuplikan layar halaman Satukan dengan petak yang memperlihatkan Antrean atau Refresh.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritma penyatuan membutuhkan waktu untuk diselesaikan dan Anda tidak dapat mengubah konfigurasi sampai selesai. Ketika proses penyatuan selesai, entitas profil pelanggan terpadu, yang disebut *Pelanggan*, tercantum di **halaman Entitas** di **bagian Profil**. Eksekusi penyatuan pertama yang berhasil menciptakan entitas Klien *terpadu*. Semua eksekusi berikutnya memperluas entitas tersebut.

## <a name="review-the-results-of-data-unification"></a>Meninjau hasil penyatuan data

Setelah penyatuan **, halaman Penyatuan** > **Data** menampilkan jumlah profil pelanggan terpadu. Hasil dari setiap langkah dalam tampilan proses penyatuan pada setiap ubin. Misalnya, **bidang** Sumber memperlihatkan jumlah atribut yang dipetakan (bidang) dan **Rekaman** duplikat memperlihatkan jumlah rekaman duplikat yang ditemukan.

:::image type="content" source="media/m3_unified.png" alt-text="Cuplikan layar halaman Penyatuan Data setelah data disatukan.":::

> [!TIP]
> Petak **peta Kondisi** yang cocok hanya ditampilkan jika beberapa entitas dipilih.

Kami menyarankan Anda untuk meninjau hasilnya, terutama kualitas aturan [pertandingan Anda](data-unification-update.md#manage-match-rules) dan memperbaikinya jika perlu.

Bila diperlukan, [buat perubahan pada pengaturan](data-unification-update.md) penyatuan dan jalankan kembali profil terpadu.

## <a name="next-step"></a>Langkah Berikutnya

Konfigurasikan [aktivitas](activities.md), [pengayaan](enrichment-hub.md), [Relasi](relationships.md), atau [tindakan](measures.md) untuk mendapatkan lebih banyak wawasan tentang pelanggan Anda.

[!INCLUDE[footer-include](includes/footer-banner.md)]
