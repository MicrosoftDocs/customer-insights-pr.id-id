---
title: Mencari dan memfilter Profil Pelanggan
description: Temukan informasi tentang profil pelanggan terpadu dan filter untuk atribut tertentu dengan cepat.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597147"
---
# <a name="customer-profiles-search--filter-index"></a>Profil pelanggan: Indeks Cari & Filter

Hasil mempersatukan data pelanggan adalah entitas profil pelanggan yang memberikan tampilan terpadu ke basis pelanggan Total Anda. Untuk dengan cepat [mencari informasi tentang pelanggan atau grup pelanggan tertentu](customer-profiles.md), Anda dapat mengkonfigurasi kemampuan **pencarian** dan **filter** pada halaman **pelanggan**. Baca terus untuk mempelajari cara admin dapat mengedit atribut pada halaman **indeks pencarian & Filter**, yang tersedia bagi pengguna untuk mencari dan memfilter.

> [!div class="mx-imgBorder"]
> ![Cari filter](media/search-filter.png "Cari filter")

## <a name="add-fields-and-specify-attributes"></a>Tambahkan bidang dan tentukan atribut

Jika ini adalah pertama kali Anda menentukan atribut yang dapat dicari sebagai administrator, Anda harus menentukan bidang terindeks terlebih dulu. Sebaiknya Anda memilih semua atribut yang bisa digunakan pengguna untuk mencari dan memfilter pelanggan pada halaman **pelanggan**. Anda hanya dapat menentukan atribut yang ada di entitas profil pelanggan yang Anda buat selama proses penyatuan data.

1. Buka halaman **pelanggan** dan pilih **index pencarian & filter**.

2. Pilih **+Tambah** untuk menentukan bidang yang diindeks.

3. Pilih atribut dalam daftar yang ingin ditambahkan sebagai bidang terindeks. Anda selalu dapat menambahkan atribut lainnya dengan memilih **Tambah**. Anda juga dapat menghapus setiap atribut yang dipilih dengan memilih simbol **Hapus**.

## <a name="explore-the-indexed-customer-fields-table"></a>Jelajahi tabel bidang pelanggan terindeks

Informasi berikut disajikan dalam tabel.

- **Nama**: Mewakili nama atribut sebagaimana ditampilkan di entitas profil pelanggan.
- **Jenis data**: menentukan apakah jenis data adalah string, angka, atau tanggal.
- **Tercakup dalam pencarian**: menentukan apakah atribut ini dapat digunakan untuk mencari pelanggan pada halaman **pelanggan** menggunakan bidang **pencarian**.
- **Tambahkan filter**: Kontrol untuk menentukan bagaimana atribut ini dapat digunakan untuk pemfilteran pada halaman **pelanggan**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Mengedit pilihan filter untuk atribut tertentu

Menu **filter** pada halaman **pelanggan** dapat mencakup berbagai tingkat atribut (misalnya, kelompok usia berbeda untuk memfilter pelanggan berdasarkannya).

1. Pilih **Tambah filter** untuk atribut tertentu pada halaman **indeks pencarian & filter**. Anda dapat menentukan jumlah hasil dan urutan pengaturannya. Tergantung pada jenis data atribut, salah satu panel berikut ditampilkan.

- Atribut jenis string: Tentukan jumlah hasil yang diinginkan pada panel **Opsi filter string**, serta kebijakan pesanan untuk mengaturnya.

- Atribut jenis numerik: Tentukan interval yang disertakan di panel **Opsi filter Angka**, serta kebijakan pesanan untuk mengaturnya.

- Atribut jenis tanggal: Tentukan interval yang disertakan di panel **Opsi filter Tanggal**, serta kebijakan pesanan untuk mengaturnya.

2. Pilih **Simpan** untuk menerapkan perubahan.

3. Pilih **Jalankan** setelah Anda siap menerapkan pengaturan Anda.

## <a name="next-steps"></a>Langkah berikutnya

Buka halaman **Pelanggan** untuk mencari profil pelanggan atau gunakan bidang yang diindeks untuk melihat subset semua profil pelanggan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]