---
title: Profil pelanggan
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
ms.openlocfilehash: 279c8e1291c6449005d593244f1979e871610a77
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052193"
---
# <a name="customer-profiles"></a>Profil pelanggan

Halaman **Pelanggan** menampilkan tampilan gabungan profil pelanggan terpadu Anda. Profil pelanggan tersedia setelah Anda [membuat entitas pelanggan terpadu](data-unification.md). Halaman tersebut memungkinkan Anda mencari pelanggan dan menentukan indeks untuk pencarian tersebut.

Pelanggan dapat perorangan atau organisasi. Setiap profil pelanggan ditunjukkan dengan petak. Gunakan kontrol paginasi untuk mendapatkan rekaman lainnya. Kartu akan menampilkan bidang dari entitas *Pelanggan* sebagaimana ditentukan dalam **indeks Pencarian & filter**. Urutan bidang dalam setiap kartu dipilih oleh sistem.

Pilih petak untuk melihat data untuk pelanggan yang dipilih di halaman khusus yang disebut [halaman Rincian pelanggan](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"]
> ![Halaman pelanggan yang menampilkan petak hasil](media/customers-page-result-tiles-B2C.png "Halaman pelanggan yang menampilkan petak hasil")

> [!NOTE]
> Jika Anda tidak dapat melihat petak saat Anda memilih **pelanggan** dalam navigasi, administrator harus [menentukan sekurangnya satu atribut yang dapat dicari](search-filter-index.md) di layar **indeks Pencarian & Filter**.

## <a name="search-for-customers"></a>Cari pelanggan

Cari pelanggan dengan memasukkan nama atau suatu atribut lain di kotak pencarian. Pencarian hanya berfungsi dalam entitas *Pelanggan* yang dibuat selama proses penyatuan data.

Sebagai admin, Anda dapat mengkonfigurasi atribut yang dapat dicari menggunakan halaman **indeks pencarian & filter**. Untuk informasi lebih lanjut, buka [Mengelola indeks pencarian dan filter](search-filter-index.md).

## <a name="filter-customers"></a>Filter pelanggan

Anda dapat memfilter pelanggan berdasarkan bidang entitas *Pelanggan*. Mirip dengan pencarian, admin harus terlebih dulu menentukan bidang tersebut sebagai dapat disaring menggunakan halaman **indeks pencarian & filter**.

1. Pilih **Tampilkan filter** pada halaman **Pelanggan**.

1. Centang kotak di samping atribut untuk memfilter pelanggan.

1. Hapus Filter dengan memilih **Hapus Filter** pada halaman **pelanggan**.

## <a name="customer-details-page"></a>Halaman Rincian pelanggan

Pilih salah satu ubin pelanggan untuk membuka **halaman rincian pelanggan**. Tampilan ini berisi informasi terpadu untuk pelanggan yang dipilih. Rincian pelanggan mencakup konten berikut:

**petak profil pelanggan**: petak ini menampilkan nilai yang berbeda dari entitas *Pelanggan* terpadu. Jika bidang tidak memiliki nilai untuk profil pelanggan yang dipilih, bidang tersebut tidak akan ditampilkan kecuali untuk bidang alamat. petak terstruktur ke dalam bagian:

- Bagian pertama menampilkan rangkaian bidang yang ditetapkan sebelumnya diikuti oleh semua bidang yang merupakan bagian dari indeks pencarian &filter. Semua bidang terkait alamat digabungkan menjadi satu baris, yang menunjukkan meskipun profil tidak berisi informasi alamat.
- **Kontak untuk pelanggan ini**: Di lingkungan untuk akun bisnis, Anda akan melihat semua kontak terkait untuk pelanggan ini sebagai bagian kedua. Setiap kontak ditampilkan dengan bidangnya. Bidang kosong disembunyikan.
- **Bidang tambahan**: Menampilkan bidang lainnya dari pelanggan yang dipilih, kecuali ID.
- **ID**: Daftarkan semua ID di dalam nama entitas terkait. Bidang diidentifikasi sebagai ID berdasarkan semantisnya, yang mengkategorikannya.

**Timeline aktivitas**: Menampilkan data jika Anda telah mengkonfigurasi aktivitas. Tampilan timeline berisi aktivitas yang diurutkan secara kronologis dari pelanggan yang dipilih, yang diawali dengan aktivitas terbaru. Untuk informasi lebih lanjut, buka [Aktivitas pelanggan](activities.md).

**wawasan**:

- **Ukuran**: Menunjukkan jika Anda mengkonfigurasi satu atau beberapa ukuran atribut pelanggan lainnya. Mereka mencakup KPI yang dihitung di sekitar pelanggan Anda di tingkat pelanggan individual. Untuk informasi lebih lanjut, buka [Menentukan dan mengelola ukuran](measures.md).

- **Minat potensial, calon merek**: Menunjukkan jika Anda mengonfigurasikan pengayaan afinitas minat atau merek. Profil ini menunjukkan minat dan afiliasi potensial untuk merek berdasarkan pelanggan lain yang profilnya mirip dengan profil pelanggan yang dipilih. Untuk informasi lebih lanjut, buka [Perkaya profil pelanggan dengan afinitas merek dan minat](enrichment-microsoft.md).

Untuk kembali ke halaman pencarian pelanggan, pilih **Kembali ke Pelanggan**.

## <a name="next-steps"></a>Langkah berikutnya

[Tambahkan sumber data lainnya](data-sources.md), [perkaya profil terpadu](enrichment-hub.md), atau [buat segmen](segments.md) untuk bekerja dengan profil pelanggan terpadu di aplikasi lain.

[!INCLUDE [footer-include](includes/footer-banner.md)]