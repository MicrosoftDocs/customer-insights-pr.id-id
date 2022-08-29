---
title: Memperbarui pengaturan penyatuan pelanggan, akun, atau kontak
description: Perbarui aturan duplikat, aturan kecocokan, atau bidang terpadu di pengaturan penyatuan pelanggan atau akun.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: f2c14c169f5973b5f400989b9eeea593eba09182
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304339"
---
# <a name="update-unification-settings"></a>Memperbarui pengaturan penyatuan

Untuk meninjau atau mengubah pengaturan penyatuan apa pun setelah profil terpadu dibuat, lakukan langkah-langkah berikut.

1. **Buka Data** > **Unify**.

   Untuk pelanggan individu (B-to-C), **halaman Satukan menampilkan** jumlah profil dan ubin pelanggan terpadu untuk setiap langkah penyatuan.

   :::image type="content" source="media/m3_unified.png" alt-text="Cuplikan layar halaman Penyatuan Data setelah data disatukan." lightbox="media/m3_unified.png":::

   Untuk akun bisnis (B-to-B), **halaman Satukan menampilkan** jumlah profil dan ubin akun terpadu untuk setiap langkah penyatuan akun. Jika kontak disatukan, jumlah profil kontak dan ubin terpadu untuk setiap langkah penyatuan kontak ditampilkan. Pilih petak yang sesuai di bawah **Satukan Akun** atau **Satukan Kontak (pratinjau)** bergantung pada apa yang ingin Anda perbarui.

   :::image type="content" source="media/b2b_unified.png" alt-text="Cuplikan layar halaman Penyatuan Data setelah data akun dan kontak disatukan." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Petak **peta Kondisi** yang cocok hanya ditampilkan jika beberapa entitas dipilih.

1. Pilih apa yang ingin Anda perbarui:
   - [Bidang sumber](#edit-source-fields) untuk menambahkan entitas atau atribut atau mengubah jenis atribut.
   - [Duplikat rekaman](#manage-deduplication-rules) untuk mengelola aturan deduplikasi atau menggabungkan preferensi.
   - [Kondisi yang cocok](#manage-match-rules) untuk memperbarui aturan yang cocok di dua entitas atau lebih.
   - [Bidang](#manage-unified-fields) pelanggan terpadu untuk menggabungkan atau mengecualikan bidang. Anda juga dapat mengelompokkan profil terkait ke dalam kluster.
   - [Bidang semantik](#manage-semantic-fields-for-unified-contacts) untuk mengelola jenis semantik untuk bidang kontak terpadu.
   - [Relasi](#manage-contact-and-account-relationships) untuk mengelola hubungan kontak ke akun.

1. Setelah membuat perubahan, pilih opsi berikutnya:

   - [Jalankan kondisi](#run-matching-conditions) pencocokan untuk mengevaluasi kualitas kondisi pencocokan Anda dengan cepat (deduplikasi dan aturan pertandingan) tanpa memperbarui profil terpadu. Opsi **Jalankan kondisi yang cocok saja** tidak ditampilkan untuk satu entitas.
   - [Satukan profil](#run-updates-to-the-unified-profile) untuk menjalankan kondisi yang cocok dan memperbarui entitas profil terpadu tanpa memengaruhi dependensi (seperti pengayaan, segmen, atau pengukuran). Proses dependen tidak dijalankan, tetapi akan disegarkan seperti [yang ditentukan dalam jadwal](schedule-refresh.md) refresh.
   - [Satukan profil dan dependensi](#run-updates-to-the-unified-profile) untuk menjalankan kondisi yang cocok, memperbarui entitas profil terpadu, dan memperbarui semua dependensi (seperti pengayaan, segmen, atau pengukuran). Semua proses dijalankan kembali secara otomatis. Di B-to-B, penyatuan dijalankan pada akun dan entitas kontak yang memperbarui profil terpadu.

## <a name="edit-source-fields"></a>Mengedit bidang sumber

Anda tidak dapat menghapus atribut atau entitas jika sudah disatukan.

1. Pilih **Edit** pada petak **bidang** Sumber.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Cuplikan layar halaman Bidang sumber memperlihatkan jumlah kunci utama, bidang yang dipetakan dan tidak dipetakan":::

   Jumlah bidang yang dipetakan dan tidak dipetakan ditampilkan.

1. Untuk menambahkan atribut atau entitas lain, pilih **Pilih entitas dan bidang**.

1. Secara opsional, Anda dapat mengubah kunci utama untuk entitas, jenis atribut, dan mengaktifkan atau menonaktifkan **Pemetaan** cerdas. Untuk informasi selengkapnya, lihat [Memilih bidang](map-entities.md) sumber.

1. Pilih **Berikutnya** untuk membuat perubahan pada aturan deduplikasi, atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-unification-settings) penyatuan.

## <a name="manage-deduplication-rules"></a>Mengelola aturan deduplikasi

1. Pilih **Edit** pada petak **Rekaman** duplikat.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Cuplikan layar halaman Catatan duplikat memperlihatkan jumlah rekaman duplikat" lightbox="media/m3_duplicates_edit.png":::

   Jumlah rekaman duplikat yang ditemukan ditampilkan di bawah **Duplikat**. Kolom **Rekaman dideduplicated** memperlihatkan entitas mana yang memiliki rekaman duplikat dan persentase rekaman duplikat.

1. Untuk menggunakan entitas yang diperkaya, pilih **Gunakan entitas** yang diperkaya. Untuk informasi selengkapnya, lihat [Pengayaan untuk sumber](data-sources-enrichment.md) data.

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

   1. Pilih **Selesai**.

1. Pilih **Berikutnya** untuk membuat perubahan pada kondisi yang cocok, atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-unification-settings) penyatuan.

## <a name="manage-match-rules"></a>Kelola aturan kecocokan

Anda dapat mengkonfigurasi ulang dan menyempurnakan sebagian besar parameter kecocokan. Anda tidak dapat menambahkan atau menghapus entitas. Aturan kecocokan tidak berlaku untuk satu entitas.

1. Pilih **Edit** pada petak **peta Kondisi** yang cocok.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Cuplikan layar halaman Cocokkan aturan dan ketentuan dengan statistik." lightbox="media/m3_match_edit.png":::

   Halaman ini menampilkan urutan kecocokan dan aturan yang ditentukan serta statistik berikut:
   - **Catatan** sumber unik menunjukkan jumlah rekaman sumber individual yang diproses dalam eksekusi pertandingan terakhir.
   - **Catatan yang cocok dan tidak** cocok menyoroti berapa banyak catatan unik yang tersisa setelah memproses aturan pencocokan.
   - **Catatan yang cocok hanya** menampilkan jumlah pertandingan di semua pasangan pertandingan Anda.

1. Untuk melihat hasil semua aturan dan skornya, pilih **Tampilkan eksekusi** terakhir. Hasil ditampilkan, termasuk ID kontak alternatif. Anda dapat mengunduh hasilnya.

1. Untuk melihat hasil dan skor aturan tertentu, pilih aturan lalu **Pratinjau**. Hasil ditampilkan. Anda dapat mengunduh hasilnya.

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

1. Pilih **Berikutnya** untuk membuat perubahan pada bidang terpadu, atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-unification-settings) penyatuan.

## <a name="manage-unified-fields"></a>Mengelola bidang terpadu

1. Pilih **Edit** pada petak **peta bidang** Pelanggan terpadu.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Cuplikan layar bidang pelanggan Terpadu":::

1. Tinjau bidang gabungan dan dikecualikan, dan buat perubahan apa pun sesuai kebutuhan. Tambahkan atau edit kunci CustomerID atau profil grup ke dalam kluster. Untuk informasi selengkapnya, lihat [Menyatukan bidang](merge-entities.md) pelanggan.

1. Untuk pelanggan atau akun, pilih **Berikutnya** untuk meninjau dan [memperbarui profil dan dependensi](#run-updates-to-the-unified-profile) terpadu. Atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-unification-settings) penyatuan untuk membuat lebih banyak perubahan.

   Untuk kontak, pilih **Berikutnya** untuk mengelola bidang semantik. Atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-unification-settings) penyatuan untuk membuat lebih banyak perubahan.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Mengelola bidang semantik untuk kontak terpadu

1. Pilih **Edit** pada petak **bidang** Semantik.

1. Untuk mengubah tipe semantik untuk bidang terpadu, pilih tipe baru. Untuk informasi selengkapnya, lihat [Menentukan bidang semantik untuk kontak](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts) terpadu.

1. Pilih **Berikutnya** untuk mengelola akun dan hubungan kontak, atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-unification-settings) penyatuan untuk membuat lebih banyak perubahan.

## <a name="manage-contact-and-account-relationships"></a>Mengelola kontak dan Relasi akun

1. Pilih **Edit** pada petak **Relasi**.

1. Untuk mengubah hubungan kontak dan akun, ubah salah satu informasi berikut:

   - **Kunci asing dari entitas** kontak: Pilih atribut yang menghubungkan entitas kontak Anda ke akun.
   - **Untuk entitas** akun: Pilih entitas akun yang terkait dengan kontak.

1. Pilih **Berikutnya** untuk meninjau pengaturan penyatuan dan [memperbarui profil dan dependensi](#run-updates-to-the-unified-profile) terpadu, atau pilih **Simpan dan tutup** dan kembali ke [Perbarui pengaturan](#update-unification-settings) penyatuan untuk membuat lebih banyak perubahan.

## <a name="run-matching-conditions"></a>Menjalankan kondisi yang cocok

Jalankan kondisi pencocokan hanya menjalankan aturan deduplikasi dan kecocokan dan memperbarui *entitas Deduplication_** dan *ConflationMatchPair*.

1. Dari halaman **Satukan** > **Data**, pilih **Jalankan kondisi yang cocok saja**.

   Petak **Catatan** duplikat dan **Kondisi** pencocokan memperlihatkan **status Antri** atau **Refresh**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Saat proses pencocokan selesai, pilih **Edit** pada petak **peta Kondisi** yang cocok.

   :::image type="content" source="media/match-KPIs.png" alt-text="Tangkapan layar yang dipotong untuk metrik kunci pada halaman Cocokkan dengan angka dan rincian.":::

1. Untuk membuat perubahan, lihat [Mengelola aturan](#manage-deduplication-rules) deduplikasi atau [Mengelola aturan](#manage-match-rules) kecocokan.

1. Jalankan proses pencocokan lagi atau [jalankan pembaruan ke profil](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Menjalankan pembaruan ke profil terpadu

- Untuk menjalankan kondisi yang cocok dan memperbarui entitas *profil terpadu tanpa* memengaruhi dependensi (seperti kartu pelanggan, pengayaan, segmen, atau pengukuran), pilih **Satukan profil** pelanggan. Untuk akun, pilih **Satukan akun** > **Satukan akun Satukan profil**. Untuk kontak, pilih **Satukan kontak (pratinjau)** > **Satukan profil**. Proses dependen tidak dijalankan, tetapi akan disegarkan seperti [yang ditentukan dalam jadwal](schedule-refresh.md) refresh.
- Untuk menjalankan kondisi yang cocok, perbarui profil terpadu, dan jalankan semua dependensi, pilih **Satukan profil dan dependensi** pelanggan. Semua proses dijalankan kembali secara otomatis. Untuk akun dan kontak, pilih **Satukan akun** > **Satukan akun Satukan profil dan dependensi**. Kondisi yang cocok dijalankan untuk akun dan kontak yang memperbarui profil terpadu dan semua dependensi lainnya dijalankan.

Semua petak kecuali **bidang** Sumber memperlihatkan **Antrean** atau **Refresh**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Hasil tampilan eksekusi yang berhasil dijalankan pada **halaman Satukan Satukan** yang menunjukkan jumlah profil terpadu.
