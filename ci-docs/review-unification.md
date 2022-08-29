---
title: Meninjau penyatuan data
description: Tinjau langkah-langkah penyatuan data, buat profil pelanggan terpadu, dan tinjau hasilnya
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303971"
---
# <a name="review-data-unification"></a>Meninjau penyatuan data

Tinjau ringkasan perubahan, buat profil terpadu, dan tinjau hasilnya.

## <a name="review-and-create-customer-profiles"></a>Tinjau dan buat profil pelanggan

Langkah terakhir dalam proses penyatuan ini menunjukkan ringkasan langkah-langkah dalam proses dan memberikan kesempatan untuk membuat perubahan sebelum Anda membuat profil terpadu.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Cuplikan layar Tinjau dan buat profil pelanggan.":::

1. Pilih **Edit** pada salah satu langkah penyatuan data untuk meninjau dan membuat perubahan apa pun.

1. Jika Anda puas dengan pilihan Anda, pilih **Buat profil** pelanggan (atau **Buat profil** akun untuk B-to-B). Halaman **Satukan Unitkan** ditampilkan saat profil pelanggan terpadu sedang dibuat.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Cuplikan layar halaman Satukan dengan petak yang memperlihatkan Antrean atau Refresh.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritma penyatuan membutuhkan waktu untuk diselesaikan dan Anda tidak dapat mengubah konfigurasi sampai selesai.

## <a name="view-the-results-of-data-unification"></a>Melihat hasil penyatuan data

Setelah penyatuan, halaman **Penyatuan** > **Data** menampilkan jumlah profil pelanggan terpadu (atau profil akun untuk B-to-B). Hasil dari setiap langkah dalam tampilan proses penyatuan pada setiap ubin. Misalnya, **bidang** Sumber memperlihatkan jumlah atribut yang dipetakan (bidang) dan **Rekaman** duplikat memperlihatkan jumlah rekaman duplikat yang ditemukan.

:::image type="content" source="media/m3_unified.png" alt-text="Cuplikan layar halaman Penyatuan Data setelah data disatukan.":::

> [!TIP]
> Petak **peta Kondisi** yang cocok hanya ditampilkan jika beberapa entitas dipilih.

Kami menyarankan Anda untuk meninjau hasilnya, terutama kualitas aturan [pertandingan Anda](data-unification-update.md#manage-match-rules) dan memperbaikinya jika perlu.

Bila diperlukan, [buat perubahan pada pengaturan](data-unification-update.md) penyatuan dan jalankan kembali profil terpadu.

### <a name="verify-output-entities-from-data-unification"></a>Memverifikasi entitas output dari penyatuan data

Buka **Entitas** > **Data** untuk memverifikasi entitas output.

Entitas profil pelanggan terpadu, yang disebut *Pelanggan*, ditampilkan di **bagian Profil**. Eksekusi penyatuan pertama yang berhasil menciptakan entitas Klien *terpadu*. Semua eksekusi berikutnya memperluas entitas tersebut.

Entitas deduplikasi dan konflasi dibuat dan ditampilkan di **bagian Sistem**. Entitas yang dideduplicated untuk masing-masing entitas sumber dibuat dengan nama **Deduplication_DataSource_Entity**. Entitas **ConflationMatchPairs** berisi informasi tentang kecocokan lintas entitas.

Entitas output deduplikasi berisi informasi berikut:
- ID/Kunci
  - Bidang Kunci utama dan ID Alternatif. Bidang ID alternatif terdiri dari semua ID alternatif yang diidentifikasi untuk rekaman.
  - Bidang Deduplication_GroupId menunjukkan grup atau kluster yang diidentifikasi dalam entitas yang mengelompokkan semua rekaman serupa berdasarkan bidang deduplikasi yang ditentukan. Ini digunakan untuk tujuan pemrosesan sistem. Jika tidak ada aturan deduplikasi manual yang ditentukan dan aturan deduplikasi yang didefinisikan sistem berlaku, Anda tidak dapat menemukan bidang ini dalam entitas output deduplikasi.
  - Deduplication_WinnerId: Bidang ini berisi ID pemenang dari grup atau kluster yang teridentifikasi. Jika Deduplication_WinnerId sama dengan nilai kunci Utama untuk rekaman, berarti rekaman adalah rekaman pemenang.
- Bidang yang digunakan untuk mendefinisikan aturan deduplikasi.
- Bidang Aturan dan Skor untuk menunjukkan aturan deduplikasi mana yang diterapkan dan skor yang dihasilkan oleh algoritme yang cocok.

## <a name="next-step"></a>Langkah Berikutnya

- Untuk B-to-B, secara opsional lakukan [penyatuan](data-unification-contacts.md) kontak.

- Untuk B-to-C, konfigurasikan [aktivitas](activities.md), [pengayaan](enrichment-hub.md), [Relasi](relationships.md), atau [tindakan](measures.md) untuk mendapatkan lebih banyak wawasan tentang pelanggan Anda.

[!INCLUDE[footer-include](includes/footer-banner.md)]
