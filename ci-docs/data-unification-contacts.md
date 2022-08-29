---
title: Membuat profil kontak terpadu (pratinjau)
description: Lakukan proses penyatuan data untuk membuat satu himpunan data master kontak.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305080"
---
# <a name="create-a-unified-contact-profile-preview"></a>Membuat profil kontak terpadu (pratinjau)

Setelah [menyatukan akun](map-entities.md) bisnis, Anda dapat secara opsional menyatukan kontak untuk akun tersebut dan menautkan kontak terpadu ke akun terpadu. Proses penyatuan kontak memetakan data kontak dari beberapa sumber data, menghapus duplikat, mencocokkan data di seluruh entitas, menyiapkan pemetaan semantik, membuat Relasi antara kontak dan akun, lalu membuat profil kontak terpadu.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Beberapa langkah pertama identik dengan langkah-langkah akun pemersatu.

## <a name="prerequisites"></a>Prasyarat

Catatan akun dan kontak harus memiliki kunci unik (disebut kunci asing) yang menghubungkannya. Misalnya, ID akun yang ada di catatan akun dan catatan kontak yang mengikat akun dan kontak bersama-sama.

## <a name="preview-limitations"></a>Batasan pratinjau

- Kontak tanpa tautan ke akun akan dibatalkan.
- Jika akun dideduplicated, catatan pemenang diidentifikasi berdasarkan preferensi penggabungan. Catatan pecundang tidak dipilih dan oleh karena itu dijatuhkan. Kontak yang terkait dengan catatan yang kalah akan dihapus.
- Akun dapat memiliki beberapa kontak, tetapi kontak ditautkan ke satu akun.
- Atribut kontak yang dipetakan dalam langkah pemetaan semantik adalah satu-satunya atribut yang dapat ditampilkan pada kartu Pelanggan. Namun, 17 atribut tersedia.

## <a name="select-source-fields"></a>Pilih bidang sumber

1. Di bawah **Satukan kontak (pratinjau)**, pilih **Mulai**.

1. [Pilih entitas dan bidang](map-entities.md) untuk sumber data kontak Anda, termasuk kunci utama dan jenis atribut.

1. Pilih **Selanjutnya**.

## <a name="remove-duplicate-records"></a>Menghapus rekaman duplikat

1. Secara opsional, [tentukan aturan](remove-duplicates.md) deduplikasi untuk entitas yang Anda pilih.

1. Pilih **Selanjutnya**.

## <a name="match-conditions"></a>Kondisi pertandingan

1. [Tentukan urutan kecocokan dan aturan](match-entities.md) untuk pencocokan lintas entitas.

1. Pilih **Selanjutnya**.

## <a name="unify-contact-fields"></a>Menyatukan bidang kontak

1. [Gabungkan dan kecualikan bidang](merge-entities.md) kontak.

1. Pilih **Selanjutnya**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Tentukan bidang semantik untuk kontak terpadu

Langkah ini dalam proses penyatuan memetakan bidang kontak terpadu Anda ke jenis semantik. Di B-to-B, kartu pelanggan menunjukkan akun. Saat kartu dipilih, semua kontak yang terkait dengan akun ditampilkan. Bidang yang Anda petakan dalam langkah ini adalah bidang yang akan ditampilkan pada kartu.

1. Pilih jenis semantik yang memetakan ke setiap bidang terpadu. Pilih **Tidak Ada** jika jenis semantik tidak tersedia.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Cuplikan layar halaman bidang Semantik untuk menentukan tipe semantik." lightbox="media/semantic_mapping.png":::

1. Setelah memetakan semua bidang terpadu, pilih **Berikutnya**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Mengatur hubungan antara kontak dan akun

Langkah dalam proses penyatuan ini menghubungkan data kontak Anda ke data akun yang sesuai.

1. Untuk setiap entitas, masukkan informasi berikut:

   - **Kunci asing dari entitas** kontak: Pilih atribut yang menghubungkan entitas kontak Anda ke akun.
   - **Untuk entitas** akun: Pilih entitas akun yang terkait dengan kontak.

   :::image type="content" source="media/contact_relationship.png" alt-text="Cuplikan layar halaman Hubungan untuk menghubungkan entitas kontak dan akun.":::

1. Pilih **Selanjutnya**.

## <a name="review-contact-unification"></a>Meninjau penyatuan kontak

Tinjau ringkasan perubahan, buat profil terpadu, dan tinjau hasilnya.

### <a name="review-and-create-contact-profiles"></a>Tinjau dan buat profil kontak

Langkah terakhir dalam proses penyatuan ini menunjukkan ringkasan langkah-langkah dalam proses dan memberikan kesempatan untuk membuat perubahan sebelum Anda membuat profil kontak terpadu.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Cuplikan layar Tinjau dan buat profil kontak.":::

1. Pilih **Edit** pada salah satu langkah penyatuan kontak untuk meninjau dan membuat perubahan apa pun.

1. Jika Anda puas dengan pilihan Anda, pilih **Buat profil** kontak. Halaman **Satukan Unitkan** ditampilkan saat profil kontak terpadu sedang dibuat.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Cuplikan layar halaman Satukan Kontak dengan petak yang memperlihatkan Antrean atau Refresh.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Algoritma penyatuan membutuhkan waktu untuk diselesaikan dan Anda tidak dapat mengubah konfigurasi sampai selesai.

### <a name="view-the-results-of-contact-unification"></a>Melihat hasil penyatuan kontak

Setelah penyatuan selesai, **halaman Penyatuan** > **Data** menampilkan jumlah profil kontak terpadu. Hasil dari setiap langkah dalam proses penyatuan ditampilkan pada setiap ubin. Misalnya, **bidang** Sumber memperlihatkan jumlah atribut yang dipetakan (bidang) dan **Rekaman** duplikat memperlihatkan jumlah rekaman duplikat yang ditemukan.

:::image type="content" source="media/unified_contacts.png" alt-text="Cuplikan layar halaman Penyatuan Data setelah kontak disatukan.":::

> [!TIP]
> Petak **peta Kondisi** yang cocok hanya ditampilkan jika beberapa entitas dipilih.

Kami menyarankan Anda untuk meninjau hasilnya, terutama kualitas aturan [pertandingan Anda](data-unification-update.md#manage-match-rules) dan memperbaikinya jika perlu.

Bila diperlukan, [buat perubahan pada pengaturan](data-unification-update.md) penyatuan kontak dan jalankan kembali profil terpadu.

### <a name="verify-output-entities-from-data-unification"></a>Memverifikasi entitas output dari penyatuan data

Buka **Entitas** > **Data** untuk memverifikasi entitas output.

Entitas profil kontak terpadu, yang disebut *ContactProfile*, ditampilkan di **bagian entitas** Semantik. Eksekusi penyatuan pertama yang berhasil menciptakan entitas ContactProfile *terpadu*. Semua eksekusi berikutnya memperluas entitas tersebut.

Entitas *ContactsCustomer* (pratinjau) dibuat dan ditampilkan di **bagian Profil**. Entitas ini berisi data kontak tanpa tautan ke akun. Entitas ini digunakan sebagai input ke dalam pemetaan semantik dan langkah-langkah hubungan penyatuan kontak.

Entitas deduplikasi dan konflasi dibuat dan ditampilkan di **bagian Sistem**. Entitas yang dideduplicated untuk masing-masing entitas sumber dibuat dengan nama **Deduplication_DataSource_Entity**. Entitas **ContactsConflationMatchPairs** berisi informasi tentang kecocokan lintas entitas.

Entitas output deduplikasi berisi informasi berikut:
- ID/Kunci
  - Bidang Kunci utama dan ID Alternatif. Bidang ID alternatif terdiri dari semua ID alternatif yang diidentifikasi untuk rekaman.
  - Bidang Deduplication_GroupId menunjukkan grup atau kluster yang diidentifikasi dalam entitas yang mengelompokkan semua rekaman serupa berdasarkan bidang deduplikasi yang ditentukan. Ini digunakan untuk tujuan pemrosesan sistem. Jika tidak ada aturan deduplikasi manual yang ditentukan dan aturan deduplikasi yang didefinisikan sistem berlaku, Anda tidak dapat menemukan bidang ini dalam entitas output deduplikasi.
  - Deduplication_WinnerId: Bidang ini berisi ID pemenang dari grup atau kluster yang teridentifikasi. Jika Deduplication_WinnerId sama dengan nilai kunci Utama untuk rekaman, berarti rekaman adalah rekaman pemenang.
- Bidang yang digunakan untuk mendefinisikan aturan deduplikasi.
- Bidang Aturan dan Skor untuk menunjukkan aturan deduplikasi mana yang diterapkan dan skor yang dihasilkan oleh algoritme yang cocok.

## <a name="next-step"></a>Langkah Berikutnya

Konfigurasikan [aktivitas](activities.md), [pengayaan](enrichment-hub.md), atau [Relasi](relationships.md) untuk mendapatkan lebih banyak wawasan tentang kontak Anda.
