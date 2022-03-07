---
title: Tentang laporan Kustom
description: Pelajari cara membuat laporan kustom.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: e8cdfc07b67b78febc1d50b3b1fd44ab94448e64
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232152"
---
# <a name="create-and-edit-custom-reports"></a>Buat dan edit laporan kustom

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Selain laporan out-of-box (OOB), Anda dapat membuat laporan kustom dengan visualisasi diagram dan tabel untuk membantu Anda memahami perilaku pengguna. Artikel ini menjelaskan cara membuat laporan dengan data yang Anda perlukan menggunakan visualisasi tabel dan diagram. Untuk informasi tentang laporan OOB, lihat [Melihat laporan](view-reports.md).

## <a name="create-a-custom-report"></a>Buat laporan kustom

1. Buka **Analisis** > **Kustom** untuk mengakses daftar laporan kustom.

1. Pilih **Laporan baru** untuk mulai membuat laporan kustom.

   :::image type="content" source="media/new-custom-report.png" alt-text="Laporan Kustom baru.":::

1. Putuskan jenis laporan yang ingin Anda buat:

    - Pilih **Tambah visual** di bilah perintah untuk membuat visualisasi tabel default.
    - Atau, pilih kolom, bilah, baris, area, pai, donat, atau visualisasi tabel dari panel **editor Laporan**.

1. Di bagian **Data** pada panel **editor Visualisasi**, pilih salah satu pilihan yang tersedia (misalnya, tampilan halaman) dari dropdown **Metrik**. Anda juga dapat menambahkan **Dimensi** (contoh: negara) untuk ditampilkan pada visualisasi. Untuk informasi lebih lanjut, lihat [Melihat dan membuat metrik](metrics.md) serta [Melihat dan membuat dimensi](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Pilih metrik untuk laporan Anda.":::

1. Pilih bagian **Desain** pada panel **editor Visualisasi** untuk menambahkan **teks Judul** dan alihkan **Judul** ke aktif dan nonaktif.  Anda juga dapat mengubah jenis visualisasi dengan memilih diagram lain, misalnya **diagram pai**.

1. Untuk mengubah ukuran dan posisi visualisasi:
   - Pilih visualisasi, lalu tarik salah satu sudut atau batas untuk menyesuaikan ukurannya.
   - Pilih visualisasi, lalu pindahkan ke posisi baru. Anda juga dapat menggunakan tombol panah untuk mengubah posisi.
1. Klik **Tambah visual** di bilah perintah untuk menambahkan visualisasi lain.
1. Setelah menambahkan visualisasi yang diinginkan untuk laporan, pilih **Simpan** di bilah perintah.

1. Berikan nama untuk laporan kustom, lalu pilih **Simpan** untuk membuatnya.
 
## <a name="filter-a-custom-report"></a>Filter laporan kustom

Anda dapat memilih jangka waktu atau rentang tanggal dalam laporan kustom untuk fokus pada nilai atau periode waktu.

Untuk memilih jangka waktu, di sudut kanan atas tampilan laporan, pilih nilai dari daftar dropdown laporan. Anda juga dapat memilih **Rentang tanggal tetap*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filter berdasarkan waktu atau rentang tanggal.":::

Untuk sebagian besar laporan, pilih **+ Tambah kondisi**, untuk memilih dimensi atau segmen untuk memfilter laporan. Untuk informasi lebih lanjut, lihat [Melihat dan membuat segmen](segments.md).

## <a name="edit-a-custom-report"></a>Mengedit laporan kustom

1. Buka **Analisis** > **Kustom** untuk mengakses daftar laporan kustom.

1. Dalam daftar laporan kustom, pilih **Lainnya [...]** 

1. Pilih **Edit nama** untuk mengubah nama laporan.

1. Pilih nama laporan, lalu gunakan pilihan **+ Tambah visual** dan **Edit** untuk menambahkan, menghilangkan, memposisikan ulang, atau mengubah ukuran visualisasi.

1. Untuk mengubah properti visualisasi, pilih visual, pilih **...** dan kemudian **Edit visual**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Mengedit properti diagram untuk laporan kustom.":::

1. Setelah mengedit laporan, pilih **Simpan** untuk menerapkan perubahan Anda. 

## <a name="delete-a-custom-report"></a>Hapus laporan kustom

1. Buka **Analisis** > **Kustom** untuk mengakses daftar laporan kustom.

1. Dalam daftar laporan kustom, pilih **...**

1. Pilih **Hapus** untuk menghapus laporan.

1. Konfirmasikan penghapusan untuk menghapus laporan secara permanen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
