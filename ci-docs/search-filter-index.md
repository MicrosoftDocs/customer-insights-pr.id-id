---
title: Mengelola indeks pencarian &filter untuk profil pelanggan
description: Temukan informasi tentang profil pelanggan terpadu dan filter untuk atribut tertentu dengan cepat.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187913"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Mengelola indeks pencarian &filter untuk profil pelanggan

Hasil dari penyatuan data pelanggan Anda adalah entitas Pelanggan *yang* memberikan pandangan terpadu ke dalam total basis pelanggan Anda. Agar pengguna dapat dengan cepat [menemukan informasi tentang pelanggan atau grup pelanggan](customer-profiles.md) tertentu, admin harus mengonfigurasi **kemampuan Pencarian** dan **Filter** untuk **halaman Pelanggan**.

   :::image type="content" source="media/search-filter.png" alt-text="Cari filter":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Menentukan atribut yang dapat dicari dan bidang yang diindeks

Jika ini adalah pertama kalinya Anda menentukan atribut yang dapat dicari sebagai administrator, tentukan bidang yang diindeks terlebih dahulu. Sebaiknya Anda memilih semua atribut yang bisa digunakan pengguna untuk mencari dan memfilter pelanggan pada halaman **pelanggan**. Hanya atribut yang ada di entitas Pelanggan *yang* dibuat selama proses penyatuan data yang dapat ditentukan.

1. Buka **Pelanggan dan pilih** Cari &filter **indeks**.

1. Pilih **+ Tambahkan**.

1. Pilih atribut dalam daftar yang ingin Anda tambahkan sebagai bidang terindeks dan klik **Terapkan**.

1. Untuk menambahkan atribut lainnya, pilih **Tambahkan**. Untuk menghapus atribut yang dipilih, pilih atribut lalu **Hapus**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Cari & filter halaman indeks.":::

1. Pilih **Jalankan** setelah Anda siap untuk menerapkan pengaturan pencarian dan filter Anda. Setelah perubahan diproses, lihat di [kartu pelanggan di halaman](customer-profiles.md) Pelanggan.

## <a name="define-filtering-options-for-a-given-attribute"></a>Menentukan opsi pemfilteran untuk atribut tertentu

Siapkan bidang yang dapat digunakan untuk memfilter pelanggan di **halaman Pelanggan**.

1. Buka **Pelanggan dan pilih** Cari &filter **indeks**.

1. Pilih atribut dan **Tambahkan Filter**. Tentukan jumlah hasil dan urutan di mana mereka akan diatur. Bergantung pada tipe data atribut, salah satu panel berikut muncul.

   - Atribut tipe string: Tentukan jumlah hasil yang diinginkan pada **panel Filter** string dan kebijakan urutan yang dengannya mereka akan diatur.

   - Atribut tipe numerik: Tentukan interval yang disertakan pada **panel Filter** angka dan kebijakan urutan yang dengannya mereka akan diatur.

   - Atribut tipe tanggal: Tentukan interval yang disertakan pada **panel Filter** tanggal dan kebijakan pesanan yang dengannya mereka akan diatur.

1. Pilih **OK**. Ulangi untuk semua atribut yang ingin Anda filter.

1. Pilih **Jalankan** setelah Anda siap untuk menerapkan pengaturan pencarian dan filter Anda. Setelah perubahan diproses, lihat di [kartu pelanggan di halaman](customer-profiles.md) Pelanggan.

## <a name="view-indexed-customer-fields"></a>Melihat bidang pelanggan yang diindeks

Halaman **Indeks** pencarian &filter menampilkan informasi berikut:

- **Nama**: Mewakili nama atribut seperti yang muncul di *entitas Pelanggan*.
- **Jenis data**: menentukan apakah jenis data adalah string, angka, atau tanggal.
- **Tercakup dalam pencarian**: menentukan apakah atribut ini dapat digunakan untuk mencari pelanggan pada halaman **pelanggan** menggunakan bidang **pencarian**.
- **Tambahkan filter**: Kontrol untuk menentukan bagaimana atribut ini dapat digunakan untuk pemfilteran pada halaman **pelanggan**.

## <a name="next-steps"></a>Langkah berikutnya

Tinjau [halaman profil terpadu](customer-profiles.md) untuk mencari profil atau gunakan bidang yang diindeks untuk melihat subset semua profil terpadu.

[!INCLUDE [footer-include](includes/footer-banner.md)]
