---
title: Lihat Profil pelanggan
description: Melihat data pelanggan terpadu Anda termasuk menggunakan pencarian dan filter
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 0c8edfd8f45ce7770d568811df2b38be1b04e73a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303787"
---
# <a name="view-customer-profiles"></a>Lihat Profil pelanggan

Profil pelanggan tersedia setelah Anda [membuat entitas Pelanggan *terpadu*](data-unification.md). Tampilan gabungan profil pelanggan terpadu Anda ditampilkan di **halaman Pelanggan**. Pelanggan dapat perorangan atau organisasi.

Buka **halaman Pelanggan** untuk melihat pelanggan Anda dan profil mereka. Setiap profil pelanggan ditunjukkan dengan petak. Gunakan kontrol paginasi untuk mendapatkan rekaman lainnya. Kartu akan menampilkan bidang dari entitas *Pelanggan* sebagaimana ditentukan dalam **indeks Pencarian & filter**. Urutan bidang dalam setiap kartu dipilih oleh sistem.

> [!NOTE]
> Jika Anda tidak dapat melihat petak peta saat memilih **Pelanggan**, administrator Anda perlu [menentukan setidaknya satu atribut](search-filter-index.md) yang dapat dicari dalam **indeks** Pencarian &filter.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Halaman pelanggan memperlihatkan petak hasil.":::

Pilih salah satu tindakan berikut:
- [Lihat detail pelanggan](#view-customer-details)
- [Mengelola indeks](search-filter-index.md) pencarian &filter (khusus admin)
- [Filter pelanggan](#filter-customers)
- **Memperluas kartu** atau Menciutkan **kartu** untuk memperluas atau menciutkan informasi yang ditampilkan pada petak pelanggan
- **Mengurutkan berdasarkan** atribut tertentu
- [Cari pelanggan](#search-for-customers)

  > [!NOTE]
  > Untuk menggunakan pencarian dan filter, admin harus mengonfigurasi atribut yang dapat dicari dan menentukan bidang yang dapat difilter menggunakan indeks pencarian &filter.

## <a name="search-for-customers"></a>Cari pelanggan

Telusuri pelanggan dengan memasukkan nama atau atribut lain di **Pelanggan penelusuran**. Atribut yang dapat dicari ditentukan oleh admin dan berasal dari entitas Klien *terpadu*.

> [!NOTE]
> **String** adalah satu-satunya tipe data yang disertakan dalam pencarian. Gunakan di **bidang Cari pelanggan** di halaman Pelanggan untuk mencari pelanggan.

## <a name="filter-customers"></a>Filter pelanggan

Filter pelanggan berdasarkan *bidang entitas Pelanggan*. Bidang yang dapat difilter ditentukan oleh admin.

1. Pada halaman **Pelanggan**, pilih **Tampilkan filter**. Panel Filter ditampilkan.

1. Centang kotak di samping atribut untuk memfilter pelanggan.

1. Hapus semua filter dengan **memilih Hapus filter** atau kosongkan kotak centang di samping atribut yang dipilih.

1. Pilih **Sembunyikan filter** untuk menutup panel filter.

1. Untuk menyimpan hasil filter sebagai [segmen, pilih](segments.md) Simpan filter sebagai **segmen**.
   1. Masukkan nama untuk segmen tersebut.
   1. Pilih **Simpan** untuk menyimpan segmen.
   1. Pilih apakah akan menjalankan segmen sekarang dengan **memilih Aktifkan** atau jalankan **Nanti**.

## <a name="view-customer-details"></a>Lihat detail pelanggan

Pada halaman **Pelanggan**, pilih petak petak pelanggan untuk melihat detail bagi pelanggan yang dipilih.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Halaman detail pelanggan.":::

Rincian pelanggan mencakup:

**Petak** profil pelanggan memperlihatkan nilai yang berbeda dari entitas Klien *terpadu*. Jika bidang tidak memiliki nilai untuk profil pelanggan yang dipilih, bidang tersebut tidak akan ditampilkan kecuali untuk bidang alamat. petak terstruktur ke dalam bagian:

- Bagian pertama menampilkan rangkaian bidang yang ditetapkan sebelumnya diikuti oleh semua bidang yang merupakan bagian dari indeks pencarian &filter. Semua bidang terkait alamat digabungkan menjadi satu baris, yang menunjukkan meskipun profil tidak berisi informasi alamat.
- **Kontak untuk pelanggan** ini ditampilkan di lingkungan untuk akun bisnis (B-to-B). Setiap kontak ditampilkan dengan bidangnya. Bidang kosong disembunyikan.
- **Bidang** tambahan menunjukkan bidang yang tersisa dari pelanggan yang dipilih, kecuali ID.
- **ID mencantumkan** semua ID di bawah nama entitas yang sesuai. Bidang diidentifikasi sebagai ID oleh semantiknya.

**Linimasa** aktivitas menampilkan data jika Anda telah mengonfigurasi [aktivitas](activities.md). Tampilan timeline berisi aktivitas yang diurutkan secara kronologis dari pelanggan yang dipilih, yang diawali dengan aktivitas terbaru.

**wawasan**:

- **Pengukuran** menunjukkan apakah Anda telah mengonfigurasi [pengukuran](measures.md) atribut pelanggan. Mereka mencakup KPI yang dihitung di sekitar pelanggan Anda di tingkat pelanggan individual.

- **Minat potensial, merek** potensial menunjukkan jika Anda mengonfigurasi [pengayaan](enrichment-microsoft.md) afinitas merek atau minat. Profil ini menunjukkan minat dan afiliasi potensial untuk merek berdasarkan pelanggan lain yang profilnya mirip dengan profil pelanggan yang dipilih.

Untuk kembali ke **halaman Pelanggan**, pilih **Kembali ke Pelanggan**.

## <a name="next-steps"></a>Langkah berikutnya

[Tambahkan sumber data lainnya](data-sources.md), [perkaya profil terpadu](enrichment-hub.md), atau [buat segmen](segments.md) untuk bekerja dengan profil pelanggan terpadu di aplikasi lain.

[!INCLUDE [footer-include](includes/footer-banner.md)]
