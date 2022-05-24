---
title: Memperbarui pengaturan penyatuan
description: Perbarui aturan duplikat, aturan kecocokan, atau bidang terpadu dalam pengaturan penyatuan.
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: be399da9b98d8803d7d1a90f44a40e0d638a8d47
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755594"
---
# <a name="update-the-unification-settings"></a>Memperbarui pengaturan penyatuan

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Untuk meninjau atau mengubah pengaturan penyatuan apa pun setelah profil terpadu dibuat, lakukan langkah-langkah berikut.

1. **Buka Data** > **Unify**.

   :::image type="content" source="media/m3_unified.png" alt-text="Cuplikan layar halaman Pemersatu Data setelah data disatukan.":::

   > [!TIP]
   > Petak **Kondisi pencocokan** hanya ditampilkan jika beberapa entitas dipilih.

1. Pilih apa yang ingin Anda perbarui:
   - [Bidang sumber](#edit-source-fields) untuk menambahkan entitas atau atribut atau mengubah jenis atribut.
   - [Duplikat catatan](#manage-deduplication-rules) untuk mengelola aturan deduplikasi atau menggabungkan preferensi.
   - [Mencocokkan kondisi untuk memperbarui aturan yang](#manage-match-rules) cocok di dua entitas atau lebih.
   - [Bidang pelanggan terpadu](#manage-unified-fields) untuk menggabungkan atau mengecualikan bidang. Anda juga dapat mengelompokkan profil terkait ke dalam grup.

1. Setelah membuat perubahan, pilih opsi berikutnya:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Cuplikan layar halaman Pemersatu Data dengan opsi Unify disorot.":::

   - Untuk memperbarui profil pelanggan terpadu (dengan atau tanpa dependensi), lihat [Menjalankan pembaruan ke profil](#run-updates-to-the-unified-customer-profile) pelanggan.
   - Untuk mengevaluasi kualitas kondisi pencocokan Anda tanpa memperbarui profil terpadu, lihat [Menjalankan kondisi yang](#run-matching-conditions) cocok. Opsi **Jalankan kondisi pencocokan saja** tidak ditampilkan untuk satu entitas.

## <a name="edit-source-fields"></a>Mengedit bidang sumber

Anda tidak dapat menghapus atribut atau entitas jika atribut tersebut telah disatukan.

1. Pilih **Edit** pada petak **Bidang** sumber.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Cuplikan layar halaman Bidang sumber memperlihatkan jumlah kunci utama, bidang yang dipetakan dan dipetakan":::

   Jumlah bidang yang dipetakan dan tidak dipetakan ditampilkan.

1. Pilih **Pilih entitas dan bidang** untuk menambahkan atribut atau entitas lain. Gunakan pencarian atau gulir untuk mencari dan memilih atribut dan entitas yang diinginkan. Pilih **Terapkan**.

1. Secara opsional, Anda dapat mengubah kunci utama untuk entitas, jenis atribut, dan mengaktifkan **atau menonaktifkan Pemetaan** cerdas. Untuk informasi selengkapnya, lihat [Memilih kunci utama dan tipe semantik untuk atribut](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Pilih **Berikutnya** untuk membuat perubahan pada aturan deduplikasi, atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-the-unification-settings) penyatuan.

## <a name="manage-deduplication-rules"></a>Mengelola aturan deduplikasi

1. Pilih **Edit** pada petak **Duplikat catatan**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Cuplikan layar halaman Catatan duplikat memperlihatkan jumlah rekaman duplikat" lightbox="media/m3_duplicates_edit.png":::

   Jumlah catatan duplikat yang ditemukan ditampilkan di bawah **Duplikat**. Kolom **deduplicated** Records menunjukkan entitas mana yang memiliki catatan duplikat dan persentase rekaman duplikat.

1. Jika Anda menambahkan entitas yang diperkaya, pilih **Gunakan entitas** yang diperkaya. Untuk informasi selengkapnya, lihat [Pengayaan untuk sumber data](data-sources-enrichment.md).

1. Untuk mengelola aturan deduplikasi, pilih salah satu opsi berikut:
   - **Membuat aturan** baru: Pilih Tambahkan **aturan** di bawah entitas yang sesuai. Untuk informasi selengkapnya, lihat [Menentukan aturan](remove-duplicates.md#define-deduplication-rules) deduplikasi.
   - **Mengubah kondisi** aturan: Pilih aturan lalu **Edit**. Mengubah bidang, menambah atau menghapus kondisi, atau menambahkan atau menghapus pengecualian.
   - **Pratinjau**: Pilih aturan lalu **Pratinjau** untuk melihat hasil eksekusi terakhir untuk aturan ini.
   - **Menonaktifkan aturan**: Pilih aturan lalu **Nonaktifkan** untuk mempertahankan aturan deduplikasi sambil mengecualikannya dari proses pencocokan.
   - **Duplikat aturan**: Pilih aturan lalu **Duplikat** untuk membuat aturan serupa dengan modifikasi.
   - **Menghapus aturan**: Pilih aturan lalu **Hapus**.

1. Untuk mengubah preferensi gabungan, pilih entitas. Anda hanya dapat mengubah preferensi jika aturan dibuat.
   1. Pilih **Edit preferensi** gabungan dan ubah **opsi Rekam untuk disimpan**.
   1. Untuk mengubah preferensi gabungan pada atribut individual entitas, pilih **Tingkat Lanjut** dan buat perubahan yang diperlukan.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Cuplikan layar preferensi penggabungan lanjutan yang menampilkan email terbaru dan alamat terlengkap":::

   1. Pilih **Selesai**.

1. Pilih **Berikutnya** untuk membuat perubahan pada kondisi yang cocok, atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-the-unification-settings) penyatuan.

## <a name="manage-match-rules"></a>Kelola aturan kecocokan

Anda dapat mengkonfigurasi ulang dan menyempurnakan sebagian besar parameter kecocokan. Anda tidak dapat menambahkan atau menghapus entitas. Aturan pencocokan tidak berlaku untuk satu entitas.

1. Pilih **Edit** pada petak **Kondisi** pencocokan.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Cuplikan layar halaman Aturan dan kondisi kecocokan dengan statistik." lightbox="media/m3_match_edit.png":::

   Halaman menampilkan urutan kecocokan dan aturan yang ditentukan serta statistik berikut:
   - **Rekaman sumber unik** menampilkan jumlah rekaman sumber individual yang diproses dalam penjalanan kecocokan terakhir.
   - **Rekaman yang cocok dan tidak cocok** akan menyorot jumlah rekaman unik yang tersisa setelah memproses aturan kecocokan.
   - **Hanya Rekaman yang cocok** menampilkan jumlah kecocokan di semua pasangan kecocokan.

1. Untuk melihat hasil semua aturan dan skornya, pilih **Lihat eksekusi terakhir**. Hasilnya ditampilkan, termasuk ID kontak alternatif. Anda dapat mengunduh hasilnya.

1. Untuk melihat hasil dan skor aturan tertentu, pilih aturan **lalu Pratinjau**. Hasilnya ditampilkan. Anda dapat mengunduh hasilnya.

1. Untuk melihat hasil kondisi tertentu pada aturan, pilih aturan lalu **Edit**. Pada panel Edit, pilih **Pratinjau** dalam kondisi tersebut. Anda dapat mengunduh hasilnya.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Representasi grafis dari catatan yang tak tertandingi dan cocok termasuk daftar data.":::

1. Jika Anda menambahkan entitas yang diperkaya, pilih **Gunakan entitas** yang diperkaya. Untuk informasi selengkapnya, lihat [Pengayaan untuk sumber data](data-sources-enrichment.md).

1. Untuk mengelola aturan, pilih salah satu opsi berikut:
   - **Membuat aturan** baru: Pilih Tambahkan **aturan** di bawah entitas yang sesuai. Untuk informasi selengkapnya, lihat [Menentukan aturan untuk pasangan pasangan.](match-entities.md#define-rules-for-match-pairs)
   - **Mengubah urutan aturan** Anda jika Anda menentukan beberapa aturan: Seret dan lepas aturan ke dalam urutan yang Anda inginkan. Untuk informasi selengkapnya, lihat [Menentukan urutan](match-entities.md#specify-the-match-order) kecocokan.
   - **Mengubah kondisi** aturan: Pilih aturan lalu **Edit**. Mengubah bidang, menambah atau menghapus kondisi, atau menambahkan atau menghapus pengecualian.
   - **Menonaktifkan aturan**: Pilih aturan lalu **Nonaktifkan** untuk mempertahankan aturan pencocokan sambil mengecualikannya dari proses pencocokan.
   - **Duplikat aturan**: Pilih aturan lalu **Duplikat** untuk membuat aturan serupa dengan modifikasi.
   - **Menghapus aturan**: Pilih aturan lalu **Hapus**.

1. Pilih **Berikutnya** untuk membuat perubahan pada bidang terpadu, atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-the-unification-settings) penyatuan.

## <a name="manage-unified-fields"></a>Mengelola bidang terpadu

1. Pilih **Edit** pada petak **Bidang** pelanggan terpadu.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Cuplikan layar bidang Pelanggan terpadu":::

1. Tinjau bidang gabungan dan dikecualikan, dan buat perubahan apa pun sesuai kebutuhan. Menambahkan atau mengedit kunci CustomerID atau profil grup ke dalam kluster. Untuk informasi selengkapnya, lihat [Menyatukan bidang](merge-entities.md) pelanggan.

1. Pilih **Berikutnya** untuk meninjau pengaturan penyatuan dan [memperbarui profil dan dependensi](#run-updates-to-the-unified-customer-profile) terpadu, atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-the-unification-settings) penyatuan untuk membuat lebih banyak perubahan.

## <a name="run-matching-conditions"></a>Menjalankan kondisi yang cocok

1. **Dari halaman Pemersatu** > **Data**, pilih **Jalankan kondisi pencocokan saja**.

   Ubin **Catatan** duplikat dan **Kondisi pencocokan** menunjukkan **Antrean** atau **Penyegaran**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

1. Saat proses pencocokan selesai, pilih **Edit** pada petak **Kondisi** pencocokan.

   :::image type="content" source="media/match-KPIs.png" alt-text="Tangkapan layar yang dipotong untuk metrik kunci pada halaman Cocokkan dengan angka dan rincian.":::

1. Untuk membuat perubahan, lihat [Mengelola aturan](#manage-deduplication-rules) deduplikasi atau [Mengelola aturan](#manage-match-rules) kecocokan.

1. Jalankan proses pencocokan lagi atau [jalankan pembaruan ke profil](#run-updates-to-the-unified-customer-profile) pelanggan.

## <a name="run-updates-to-the-unified-customer-profile"></a>Menjalankan pembaruan ke profil pelanggan terpadu

1. Dari **halaman Pemersatu** > **Data**, pilih:

   - **Menyatukan profil** pelanggan: Memperbarui entitas profil pelanggan terpadu tanpa memengaruhi dependensi (seperti pengayaan, segmen, atau tindakan). Proses dependen tidak dijalankan, tetapi akan disegarkan seperti [yang didefinisikan dalam jadwal](system.md#schedule-tab) refresh.

   - **Menyatukan profil dan dependensi** pelanggan: Memperbarui profil terpadu dan semua dependensi. Semua proses dijalankan kembali secara otomatis. Setelah semua proses hilir selesai, profil pelanggan mencerminkan data yang diperbarui.

   Catatan **duplikat**, **Kondisi** pencocokan, dan **ubin bidang** pelanggan terpadu menunjukkan **Mengantri** atau **Menyegarkan**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]
