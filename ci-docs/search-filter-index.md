---
title: 'Profil pelanggan: Indeks Cari & Filter'
description: Temukan informasi tentang profil pelanggan terpadu dan filter untuk atribut tertentu dengan cepat.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: fc076e341f744ac2922dcacdf5f20ae8ecbdbaa0
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050813"
---
# <a name="customer-profiles-search--filter-index"></a>Profil pelanggan: Indeks Cari & Filter

Hasil mempersatukan data pelanggan adalah entitas profil pelanggan yang memberikan tampilan terpadu ke basis pelanggan Total Anda. Untuk dengan cepat [mencari informasi tentang pelanggan atau grup pelanggan tertentu](customer-profiles.md), Anda dapat mengkonfigurasi kemampuan **pencarian** dan **filter** pada halaman **pelanggan**. Baca terus untuk mempelajari cara admin dapat mengedit atribut pada halaman **indeks pencarian & Filter**, yang tersedia bagi pengguna untuk mencari dan memfilter.

   :::image type="content" source="media/search-filter.png" alt-text="Cari filter":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

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

3. Pilih **Jalankan** setelah Anda siap menerapkan pengaturan Anda. Setelah perubahan diproses, Anda akan menemukannya di [kartu pelanggan pada halaman Pelanggan](customer-profiles.md). 

## <a name="next-steps"></a>Langkah berikutnya

Tinjau [halaman profil terpadu](customer-profiles.md) untuk mencari profil atau gunakan bidang yang diindeks untuk melihat subset semua profil terpadu.


[!INCLUDE [footer-include](includes/footer-banner.md)]
