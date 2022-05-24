---
title: Meninjau penyatuan data
description: Tinjau langkah-langkah penyatuan data, buat profil pelanggan terpadu, dan tinjau hasilnya
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742969"
---
# <a name="review-data-unification"></a>Meninjau penyatuan data

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Langkah terakhir dalam proses penyatuan ini menunjukkan ringkasan langkah-langkah dalam proses dan memberikan kesempatan untuk membuat perubahan sebelum Anda membuat profil terpadu.

:::image type="content" source="media/m3_review.png" alt-text="Cuplikan layar Tinjau dan Buat profil pelanggan.":::

## <a name="review-the-data-unification-steps"></a>Meninjau langkah-langkah penyatuan data

1. Pilih **Edit** pada salah satu langkah penyatuan data untuk meninjau dan membuat perubahan apa pun.

1. Jika Anda puas dengan pilihan Anda, pilih **Buat profil pelanggan**. Halaman **Unify** ditampilkan saat profil pelanggan terpadu sedang dibuat. Algoritma penyatuan membutuhkan waktu untuk menyelesaikan dan Anda tidak dapat mengubah konfigurasi sampai selesai.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Ketika proses penyatuan selesai, entitas profil pelanggan terpadu, yang disebut *Pelanggan*, tercantum di **halaman Entitas** di **bagian Profil**. Unifikasi pertama yang berhasil menciptakan entitas Pelanggan *terpadu*. Semua run berikutnya memperluas entitas tersebut.

## <a name="review-the-results-of-data-unification"></a>Meninjau hasil penyatuan data

Setelah penyatuan, **halaman Pemersatu** > **Data** menunjukkan jumlah profil pelanggan terpadu. Hasil dari setiap langkah dalam proses penyatuan ditampilkan pada setiap ubin. Misalnya, **bidang** Sumber menunjukkan jumlah atribut yang dipetakan (bidang) dan **catatan** Duplikat menunjukkan jumlah rekaman duplikat yang ditemukan.

:::image type="content" source="media/m3_unified.png" alt-text="Cuplikan layar halaman Pemersatu Data setelah data disatukan.":::

> [!TIP]
> Petak **Kondisi pencocokan** hanya ditampilkan jika beberapa entitas dipilih.

Kami menyarankan Anda meninjau hasilnya, terutama kualitas aturan [pertandingan Anda](data-unification-update.md#manage-match-rules) dan memperbaikinya jika perlu.

Bila diperlukan, [buat perubahan pada pengaturan](data-unification-update.md) penyatuan dan jalankan kembali profil terpadu.

## <a name="next-step"></a>Langkah Berikutnya

Konfigurasikan [aktivitas](activities.md), [pengayaan](enrichment-hub.md), [Relasi](relationships.md), atau [langkah-langkah](measures.md) untuk mendapatkan lebih banyak wawasan tentang pelanggan Anda.

[!INCLUDE[footer-include](includes/footer-banner.md)]
