---
title: Lihat Profil pelanggan
description: Dapatkan gabungan tampilan data pelanggan terpadu Anda.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: d6a9e7872a488b6d68afce35b547f93cc4a7c652
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596871"
---
# <a name="customer-profiles"></a>Profil pelanggan

Halaman **pelanggan** menampilkan tampilan gabungan pelanggan Anda, berdasarkan data profil yang Anda kumpulkan dari [semua sumber data](data-sources.md). Profil pelanggan tersedia setelah Anda [membuat entitas pelanggan terpadu](data-unification.md). Pastikan Anda menyelesaikan proses penyatuan data untuk mendapatkan tampilan Pelanggan yang lebih kaya. Halaman ini juga memungkinkan Anda mencari pelanggan.

Pelanggan dapat berupa individu atau organisasi (pratinjau). Setiap profil pelanggan atau organisasi diwakili oleh ubin. Pilih ubin untuk melihat informasi tambahan tentang pelanggan atau organisasi tertentu. Gunakan kontrol paginasi di bagian bawah halaman untuk melihat rekaman tambahan.

> [!div class="mx-imgBorder"] 
> ![Profil pelanggan B2C](media/profiles-customers.png "Profil pelanggan B2C")

Organisasi (Pratinjau)
> [!div class="mx-imgBorder"] 
> ![Profil pelanggan B2B](media/profile-customers-b2b.png "Profil pelanggan B2B")

> [!NOTE]
> Jika Anda tidak dapat melihat ubin ketika Anda memilih **pelanggan** di navigasi, administrator harus [menentukan sekurangnya satu atribut](search-filter-index.md) yang dapat dicari di layar **indeks Pencarian & Filter**.

## <a name="search-for-customers"></a>Cari pelanggan

Cari pelanggan dengan memasukkan nama atau suatu atribut lain di kotak pencarian. Pencarian hanya berfungsi dalam entitas profil pelanggan yang dibuat selama proses penyatuan data.

Sebagai admin, Anda dapat mengkonfigurasi atribut yang dapat dicari menggunakan halaman **indeks pencarian & filter**. Untuk informasi lebih lanjut, Lihat [mengelola indeks pencarian & Filter](search-filter-index.md).

## <a name="filter-customers"></a>Filter pelanggan

Anda dapat memfilter pelanggan berdasarkan bidang entitas profil pelanggan. Mirip dengan pencarian, admin harus terlebih dulu menentukan bidang tersebut sebagai dapat disaring menggunakan halaman **indeks pencarian & filter**.

1. Pilih **filter** pada halaman **pelanggan**.

2. Centang kotak di samping atribut untuk memfilter pelanggan.

   > [!div class="mx-imgBorder"] 
   > ![Profil pelanggan](media/profiles-customers3.png "Profil pelanggan")

3. Hapus Filter dengan memilih **Hapus Filter** pada halaman **pelanggan**.

##  <a name="customer-details-page"></a>Halaman Rincian pelanggan

Pilih salah satu ubin pelanggan untuk membuka **halaman rincian pelanggan**. Tampilan ini berisi informasi terpadu untuk pelanggan yang dipilih.

Rincian pelanggan mencakup:

-   **Ubin profil pelanggan:** ubin ini menampilkan nilai yang berbeda dari entitas profil pelanggan terpadu. Rincian ini dapat mencakup alamat email, nama, kota, dan sebagainya. 

-   **Minat potensial, merek potensial:** ditampilkan jika Anda mengonfigurasi pengayaan pihak pertama. Ini menunjukkan potensi minat dan afinitas untuk merek yang memiliki profil pelanggan yang serupa dengan yang mungkin dimiliki pelanggan ini. Untuk informasi lebih lanjut, lihat [memperkaya profil pelanggan dengan afinitas merek dan minat](enrichment-microsoft-graph.md).

-   **Tindakan:** menunjukkan jika Anda mengonfigurasi satu atau beberapa ukuran dari jenis tertentu: ukuran atribut pelanggan. Mereka mencakup KPI yang dihitung di sekitar pelanggan Anda di tingkat pelanggan individual. Untuk informasi lebih lanjut, lihat [menentukan dan mengelola langkah](measures.md).

-   **Timeline aktivitas:** menunjukkan apakah Anda telah mengonfigurasi aktivitas. Tampilan Timeline berisi aktivitas yang diurutkan secara kronologis dari pelanggan ini, dimulai dengan aktivitas terbaru. Untuk informasi lebih lanjut, lihat [Aktivitas pelanggan](activities.md).

pilih **kembali ke pelanggan** untuk kembali ke halaman pencarian pelanggan.

## <a name="next-steps"></a>Langkah berikutnya

[Tambahkan sumber data lainnya](data-sources.md) atau [Buat segmen pelanggan](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]