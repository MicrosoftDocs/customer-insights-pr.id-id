---
title: Buat ruang kerja baru
description: Tujuan ruang kerja dan cara membuat yang baru.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f8922703af506974c8b5b24086b61f05a83609d
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673447"
---
# <a name="create-a-new-workspace-and-add-members"></a>Membuat ruang kerja baru dan menambahkan anggota

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ruang kerja adalah bagaimana Anda dapat melihat aktivitas pengguna secara real time untuk lebih memahami data audiens. Di sini Anda dapat menyimpan dan mengelola aktivitas dan laporan.

Saat membuat ruang kerja, Anda dapat memilih jenis data yang akan difokuskan. Anda dapat menambahkan pengguna, atau anggota lain, ke ruang kerja yang ada kapan pun. 

## <a name="create-a-new-workspace"></a>Buat ruang kerja baru

Proses pembuatan ruang kerja mencakup pengaturan *lingkungan* untuk mengatur ruang kerja Anda. Lingkungan adalah ruang yang dapat berisi satu atau beberapa ruang kerja. Anda dapat menggunakan lingkungan untuk mengelola ruang kerja dan koneksi Anda ke kemampuan wawasan audiens.

1. Pilih **+Baru** dari pengalih ruang kerja.

   :::image type="content" source="media/new-workspace.png" alt-text="Halaman Wawasan Pelanggan dengan callout di panel navigasi dan deskripsi.":::

1. Di panel **Ruang Kerja**, masukkan **nama Ruang Kerja**.

   :::image type="content" source="media/workspace-name.png" alt-text="Ketikkan Nama ruang kerja.":::

1. Pilih jenis platform (web atau seluler) yang ingin Anda ukur.

1. Pilih **Tampilkan pengaturan lanjutan** untuk mengaktifkan atau menonaktifkan pengaturan opsional ini:

   - Alihkan **Tidak Dikenal ke dikenal** ke "diaktifkan" untuk mengaitkan aktivitas web dengan pengguna yang sebelumnya diautentikasi. Untuk informasi lebih lanjut, lihat [Mengenali aktivitas web dari pengunjung yang diautentikasi sebelumnya](unknown-to-known.md)
   - Alihkan **Filter lalu lintas bot** ke "diaktifkan" untuk menghilangkan lalu lintas web oleh bot untuk ruang kerja ini. 

1. Pilih **Selesai** setelah selesai. 

1. Instal cuplikan kode untuk mulai menerima data, lalu pilih **Selesai** untuk membuat ruang kerja. Untuk informasi lebih lanjut, lihat [Ikhtisar sumber daya Pengembang](developer-resources.md).

> [!NOTE]
> Anda sekarang dapat menambahkan anggota dan menetapkan tingkat izin mereka dari daftar **Peran**. Untuk Informasi lebih lanjut: lihat [peran dan izin](user-roles.md). 

Untuk informasi lebih lanjut, [lihat Mengelola lingkungan dan ruang kerja](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
