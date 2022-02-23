---
title: Buat lingkungan baru
description: Tujuan lingkungan dan cara membuat yang baru.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 8ff04a6b2ffbd513a77f7f8a33358f3d8f559c7e
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673646"
---
# <a name="create-a-new-environment"></a>Buat lingkungan baru 

## <a name="overview"></a>Gambaran Umum

Lingkungan adalah ruang yang memungkinkan Anda mengelola ruang kerja dan sambungan. Cara menggunakan lingkungan tergantung pada organisasi dan kasus penggunaan Anda. Misalnya, Anda dapat membuat:

- Satu lingkungan.
- Lingkungan terpisah untuk pengujian dan produksi.
- Lingkungan terpisah untuk tim atau departemen tertentu di organisasi Anda yang berisi aktivitas relevan untuk setiap audiens.
- Lingkungan terpisah untuk berbagai cabang global perusahaan Anda.
- Koneksi ke kemampuan wawasan audiens Customer Insights.

## <a name="create-a-new-environment"></a>Buat lingkungan baru

1. Di sisi kanan banner utama, pilih pemilih lingkungan, lalu **+Baru**.

   :::image type="content" source="media/environment-picker.png" alt-text="Pilih pemilih Lingkungan.":::

1. Di panel **Konfigurasi**, ketik **nama Lingkungan**.

1. Pilih **Jenis** akun, tergantung pada jenis paket.

1. Pilih **Kawasan** dan pilih **Berikutnya**. 

1. Ketik **nama** Workspace, yang memungkinkan Anda mengumpulkan data untuk situs web atau aplikasi tertentu. Untuk informasi lebih lanjut lihat [Buat ruang kerja](create-workspace.md).

1. Pilih **tipe Workspace** (web atau seluler) yang ingin Anda buat. 

1. Pilih **Tampilkan pengaturan lanjutan** untuk mengaktifkan atau menonaktifkan pengaturan opsional ini:

   - Alihkan **Tidak Dikenal ke dikenal** ke "diaktifkan" untuk mengaitkan aktivitas web dengan pengguna yang sebelumnya diautentikasi. Untuk informasi selengkapnya, lihat [Mengenali acara web dari pengunjung yang diautentikasi sebelumnya](unknown-to-known.md).
   - Alihkan **Filter lalu lintas bot** ke "diaktifkan" untuk menghilangkan lalu lintas web oleh bot untuk ruang kerja ini. 

1. Pilih **Selesai** setelah selesai. 

1. Instal cuplikan kode untuk mulai menerima data, lalu pilih **Selesai** untuk membuat ruang kerja. Untuk informasi lebih lanjut, lihat [Ikhtisar sumber daya Pengembang](developer-resources.md).

> [!NOTE]
> Anda sekarang dapat menambahkan anggota dan menetapkan tingkat izin mereka dari daftar **Peran**. Untuk Informasi lebih lanjut: lihat [peran dan izin](user-roles.md). 

Untuk informasi lebih lanjut, [lihat Mengelola lingkungan dan ruang kerja](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Bekerja dengan lingkungan baru Anda

- [Buat ruang kerja](../engagement-insights/create-workspace.md) dan tambahkan anggota.
- [Tambahkan kode ke situs web](../engagement-insights/instrument-website.md) atau [aplikasi seluler](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps) Anda.
- Melihat [laporan real-time](../engagement-insights/view-reports.md) atau buat [laporan kustom](../engagement-insights/custom-reports.md).
- [Buat aktivitas disempurnakan](../engagement-insights/refined-events.md) untuk ekspor.
- [Ekspor data](../engagement-insights/export-events.md) ke Data Lake Store.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
