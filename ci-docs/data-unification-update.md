---
title: Memperbarui pengaturan penyatuan
description: Perbarui aturan duplikat, aturan pencocokan, atau bidang terpadu dalam pengaturan penyatuan.
ms.date: 06/01/2022
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
ms.openlocfilehash: a7cf06c07e4b95b848a55dfe5fe0b09397fe744e
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245598"
---
# <a name="update-the-unification-settings"></a>Memperbarui pengaturan penyatuan

Untuk meninjau atau mengubah pengaturan penyatuan apa pun setelah profil terpadu dibuat, lakukan langkah-langkah berikut.

1. **Buka Data** > **Unify**.

   :::image type="content" source="media/m3_unified.png" alt-text="Cuplikan layar halaman Penyatuan Data setelah data disatukan.":::

   > [!TIP]
   > Petak **peta Kondisi** yang cocok hanya ditampilkan jika beberapa entitas dipilih.

1. Pilih apa yang ingin Anda perbarui:
   - [Bidang sumber](#edit-source-fields) untuk menambahkan entitas atau atribut atau mengubah jenis atribut.
   - [Duplikat rekaman](#manage-deduplication-rules) untuk mengelola aturan deduplikasi atau menggabungkan preferensi.
   - [Kondisi yang cocok](#manage-match-rules) untuk memperbarui aturan yang cocok di dua entitas atau lebih.
   - [Bidang](#manage-unified-fields) pelanggan terpadu untuk menggabungkan atau mengecualikan bidang. Anda juga dapat mengelompokkan profil terkait ke dalam kluster.

1. Setelah membuat perubahan, pilih opsi berikutnya:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Cuplikan layar halaman Penyatuan Data dengan opsi Satukan yang disorot.":::

   - [Jalankan kondisi](#run-matching-conditions) pencocokan untuk mengevaluasi kualitas kondisi pencocokan Anda dengan cepat (deduplikasi dan aturan pertandingan) tanpa memperbarui profil terpadu. Opsi **Jalankan kondisi yang cocok saja** tidak ditampilkan untuk satu entitas.
   - [Satukan profil](#run-updates-to-the-unified-customer-profile) pelanggan untuk menjalankan kondisi yang cocok dan memperbarui entitas profil pelanggan terpadu tanpa memengaruhi dependensi (seperti pengayaan, segmen, atau tindakan). Proses dependen tidak dijalankan, tetapi akan disegarkan seperti [yang ditentukan dalam jadwal](schedule-refresh.md) refresh.
   - [Satukan profil dan dependensi](#run-updates-to-the-unified-customer-profile) pelanggan untuk menjalankan kondisi yang cocok dan memperbarui entitas profil pelanggan terpadu dan semua dependensi (seperti pengayaan, segmen, atau tindakan). Semua proses dijalankan kembali secara otomatis.

## <a name="edit-source-fields"></a>Mengedit bidang sumber

Anda tidak dapat menghapus atribut atau entitas jika sudah disatukan.

1. Pilih **Edit** pada petak **bidang** Sumber.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Cuplikan layar halaman Bidang sumber memperlihatkan jumlah kunci utama, bidang yang dipetakan dan tidak dipetakan":::

   Jumlah bidang yang dipetakan dan tidak dipetakan ditampilkan.

1. Pilih **Pilih entitas dan bidang** untuk menambahkan atribut atau entitas lain. Gunakan pencarian atau gulir untuk mencari dan memilih atribut dan entitas yang diinginkan. Pilih **Terapkan**.

1. Secara opsional, Anda dapat mengubah kunci utama untuk entitas, jenis atribut, dan mengaktifkan atau menonaktifkan **Pemetaan** cerdas. Untuk informasi selengkapnya, lihat [Memilih kunci utama dan tipe semantik untuk atribut](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Pilih **Berikutnya** untuk membuat perubahan pada aturan deduplikasi, atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-the-unification-settings) penyatuan.

## <a name="manage-deduplication-rules"></a>Mengelola aturan deduplikasi

1. Pilih **Edit** pada petak **Rekaman** duplikat.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Cuplikan layar halaman Catatan duplikat memperlihatkan jumlah rekaman duplikat" lightbox="media/m3_duplicates_edit.png":::

   Jumlah rekaman duplikat yang ditemukan ditampilkan di bawah **Duplikat**. Kolom **Rekaman dideduplicated** memperlihatkan entitas mana yang memiliki rekaman duplikat dan persentase rekaman duplikat.

1. Jika Anda menambahkan entitas yang diperkaya, pilih **Gunakan entitas** yang diperkaya. Untuk informasi selengkapnya, lihat [Pengayaan untuk sumber](data-sources-enrichment.md) data.

1. Untuk mengelola aturan deduplikasi, pilih salah satu opsi berikut:
   - **Membuat aturan** baru: Pilih **Tambahkan aturan** di bawah entitas yang sesuai. Untuk informasi selengkapnya, lihat [Menentukan aturan](remove-duplicates.md#define-deduplication-rules) deduplikasi.
   - **Mengubah kondisi** aturan: Pilih aturan lalu **Edit**. Ubah bidang, tambahkan atau hapus kondisi, atau tambahkan atau hapus pengecualian.
   - **Pratinjau**: Pilih aturan lalu **Pratinjau** untuk melihat hasil eksekusi terakhir untuk aturan ini.
   - **Menonaktifkan aturan**: Pilih aturan lalu **Nonaktifkan** untuk mempertahankan aturan deduplikasi sambil mengecualikannya dari proses pencocokan.
   - **Menduplikasi aturan**: Pilih aturan lalu **Duplikat** untuk membuat aturan serupa dengan modifikasi.
   - **Menghapus aturan**: Pilih aturan lalu **Hapus**.

1. Untuk mengubah preferensi gabungan, pilih entitas. Anda hanya dapat mengubah preferensi jika aturan dibuat.
   1. Pilih **Edit preferensi** gabungan dan ubah **opsi Rekam untuk disimpan**.
   1. Untuk mengubah preferensi gabungan pada atribut individual entitas, pilih **Tingkat Lanjut** dan buat perubahan yang diperlukan.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Cuplikan layar preferensi gabungan tingkat lanjut memperlihatkan email terbaru dan alamat terlengkap":::

   1. Pilih **Selesai**.

1. Pilih **Berikutnya** untuk membuat perubahan pada kondisi yang cocok, atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-the-unification-settings) penyatuan.

## <a name="manage-match-rules"></a>Kelola aturan kecocokan

Anda dapat mengkonfigurasi ulang dan menyempurnakan sebagian besar parameter kecocokan. Anda tidak dapat menambahkan atau menghapus entitas. Aturan kecocokan tidak berlaku untuk satu entitas.

1. Pilih **Edit** pada petak **peta Kondisi** yang cocok.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Cuplikan layar halaman Cocokkan aturan dan ketentuan dengan statistik." lightbox="media/m3_match_edit.png":::

   Halaman ini menampilkan urutan kecocokan dan aturan yang ditentukan serta statistik berikut:
   - **Rekaman sumber unik** menampilkan jumlah rekaman sumber individual yang diproses dalam penjalanan kecocokan terakhir.
   - **Rekaman yang cocok dan tidak cocok** akan menyorot jumlah rekaman unik yang tersisa setelah memproses aturan kecocokan.
   - **Hanya Rekaman yang cocok** menampilkan jumlah kecocokan di semua pasangan kecocokan.

1. Untuk melihat hasil semua aturan dan skornya, pilih **Tampilkan eksekusi** terakhir. Hasilnya ditampilkan, termasuk ID kontak alternatif. Anda dapat mengunduh hasilnya.

1. Untuk melihat hasil dan skor aturan tertentu, pilih aturan lalu **Pratinjau**. Hasilnya ditampilkan. Anda dapat mengunduh hasilnya.

1. Untuk melihat hasil kondisi tertentu pada aturan, pilih aturan lalu **Edit**. Pada panel Edit, pilih **Pratinjau** di bawah kondisi. Anda dapat mengunduh hasilnya.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Representasi grafis dari rekaman yang tidak cocok dan cocok termasuk daftar data.":::

1. Jika Anda menambahkan entitas yang diperkaya, pilih **Gunakan entitas** yang diperkaya. Untuk informasi selengkapnya, lihat [Pengayaan untuk sumber](data-sources-enrichment.md) data.

1. Untuk mengelola aturan, pilih salah satu opsi berikut:
   - **Membuat aturan** baru: Pilih **Tambahkan aturan** di bawah entitas yang sesuai. Untuk informasi selengkapnya, lihat [Menentukan aturan untuk pasangan kecocokan](match-entities.md#define-rules-for-match-pairs).
   - **Mengubah urutan aturan** Anda jika Anda menentukan beberapa aturan: Seret dan lepas aturan ke dalam urutan yang Anda inginkan. Untuk informasi selengkapnya, lihat [Menentukan urutan](match-entities.md#specify-the-match-order) kecocokan.
   - **Mengubah kondisi** aturan: Pilih aturan lalu **Edit**. Ubah bidang, tambahkan atau hapus kondisi, atau tambahkan atau hapus pengecualian.
   - **Menonaktifkan aturan**: Pilih aturan lalu **Nonaktifkan** untuk mempertahankan aturan pencocokan sambil mengecualikannya dari proses pencocokan.
   - **Menduplikasi aturan**: Pilih aturan lalu **Duplikat** untuk membuat aturan serupa dengan modifikasi.
   - **Menghapus aturan**: Pilih aturan lalu **Hapus**.

1. Pilih **Berikutnya** untuk membuat perubahan pada bidang terpadu, atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-the-unification-settings) penyatuan.

## <a name="manage-unified-fields"></a>Mengelola bidang terpadu

1. Pilih **Edit** pada petak **peta bidang** Pelanggan terpadu.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Cuplikan layar bidang pelanggan Terpadu":::

1. Tinjau bidang gabungan dan dikecualikan, dan buat perubahan apa pun sesuai kebutuhan. Tambahkan atau edit kunci CustomerID atau profil grup ke dalam kluster. Untuk informasi selengkapnya, lihat [Menyatukan bidang](merge-entities.md) pelanggan.

1. Pilih **Berikutnya** untuk meninjau pengaturan penyatuan dan [memperbarui profil dan dependensi](#run-updates-to-the-unified-customer-profile) terpadu, atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-the-unification-settings) penyatuan untuk membuat lebih banyak perubahan.

## <a name="run-matching-conditions"></a>Menjalankan kondisi yang cocok

Jalankan kondisi pencocokan hanya menjalankan aturan deduplikasi dan kecocokan dan memperbarui *entitas Deduplication_** dan *ConflationMatchPair*.

1. Dari halaman **Satukan** > **Data**, pilih **Jalankan kondisi yang cocok saja**.

   Petak **Catatan** duplikat dan **Kondisi** pencocokan memperlihatkan **status Antri** atau **Refresh**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Saat proses pencocokan selesai, pilih **Edit** pada petak **peta Kondisi** yang cocok.

   :::image type="content" source="media/match-KPIs.png" alt-text="Tangkapan layar yang dipotong untuk metrik kunci pada halaman Cocokkan dengan angka dan rincian.":::

1. Untuk membuat perubahan, lihat [Mengelola aturan](#manage-deduplication-rules) deduplikasi atau [Mengelola aturan](#manage-match-rules) kecocokan.

1. Jalankan proses pencocokan lagi atau [jalankan pembaruan ke profil](#run-updates-to-the-unified-customer-profile) pelanggan.

## <a name="run-updates-to-the-unified-customer-profile"></a>Menjalankan pembaruan ke profil pelanggan terpadu

1. Dari halaman **Penyatuan** > **Data**, pilih:

   - **Satukan profil** pelanggan: Menjalankan kondisi yang cocok dan memperbarui entitas profil pelanggan terpadu tanpa memengaruhi dependensi (seperti pengayaan, segmen, atau pengukuran). Proses dependen tidak dijalankan, tetapi akan disegarkan seperti [yang ditentukan dalam jadwal](schedule-refresh.md) refresh.

   - **Satukan profil dan dependensi** pelanggan: Menjalankan kondisi yang cocok dan memperbarui profil terpadu dan semua dependensi. Semua proses dijalankan kembali secara otomatis. Setelah semua proses hilir selesai, profil pelanggan mencerminkan data yang diperbarui.

   Petak **bidang Rekaman** duplikat, **Kondisi** pencocokan, dan **Bidang** pelanggan terpadu memperlihatkan **status Antri** atau **Refresh**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Hasil tampilan eksekusi yang berhasil dijalankan pada **halaman Satukan Satukan** yang menunjukkan jumlah profil pelanggan terpadu.
