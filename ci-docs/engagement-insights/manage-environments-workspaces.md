---
title: Mengelola ruang kerja dan lingkungan
description: Cara membuat, mengganti nama, dan menghapus ruang kerja dan lingkungan.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 07/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: bf310b1a50ba7baac5d11d5f22ff42003fbba516efd7d165c00b59adc958da2e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034046"
---
# <a name="manage-environments-and-workspaces"></a>Mengelola lingkungan dan ruang kerja

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Gambaran Umum

Ruang kerja adalah ruang menyimpan dan mengelola aktivitas dan laporan. Di sini Anda dapat melihat aktivitas pengguna secara real time. Saat membuat ruang kerja, Anda dapat memilih jenis data untuk dikirimkan ke ruang kerja. Saat ini, data web dan aplikasi perangkat bergerak didukung.

Lingkungan adalah ruang yang memungkinkan Anda mengelola ruang kerja dan sambungan. Cara menggunakan lingkungan tergantung pada organisasi dan kasus penggunaan Anda. Misalnya, Anda dapat membuat:

-   Satu lingkungan.
-   Lingkungan terpisah untuk pengujian dan produksi.
-   Lingkungan terpisah untuk tim atau departemen tertentu di organisasi Anda yang berisi aktivitas relevan untuk setiap audiens.
-   Lingkungan terpisah untuk berbagai cabang global perusahaan Anda.
-   Koneksi ke kemampuan wawasan audiens Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Memilih lingkungan dan membuat ruang kerja 

Setiap ruang kerja harus berada dalam lingkungan. Anda dapat memilih lingkungan yang sudah ada sebelumnya atau membuat yang baru saat membuat ruang kerja. Selanjutnya, Anda dapat memilih untuk menambahkan anggota ruang kerja dan mulai mengumpulkan data.

**Untuk membuat ruang kerja pertama Anda**

1. Dalam wawasan keterlibatan, pilih **Baru** dari pengalih ruang kerja. 

   :::image type="content" source="media/New-workspace.png" alt-text="Pemilih ruang kerja halaman Customer Insights.":::

1. Pilih lingkungan dari daftar atau pilih **Buat lingkungan baru**.

1. Masukkan nama di **nama ruang kerja**. 

1. Pilih jenis lingkungan yang ingin Anda buat, tergantung pada apakah Anda ingin mengukur apa yang terjadi di situs web atau di aplikasi seluler. 

1. Anda dapat menambahkan anggota dan menetapkan tingkat izin mereka dari daftar **Peran**. Selanjutnya, pilih **Selesai** untuk membuat ruang kerja atau **Berikutnya** untuk menginstal kode. 

1. Instal cuplikan kode untuk mulai menerima data, lalu pilih **Selesai**. 

## <a name="manage-a-workspace"></a>Kelola ruang kerja

Anda dapat mengelola beberapa ruang kerja secara bersamaan di lingkungan. [Peran](user-roles.md) Anda menentukan cara kerja Anda di dalamnya. 

 - Anda harus menjadi admin Lingkungan atau admin Ruang Kerja untuk mengelola ruang kerja.
 - Sebagai admin Ruang Kerja, Anda dapat mengganti nama ruang kerja yang ada atau menghapusnya. 

### <a name="edit-a-workspace-name"></a>Edit nama ruang kerja

1. Buka **Admin** > **Ruang kerja** dan pilih **Pengaturan**.

1. Masukkan nama baru di kotak **nama ruang kerja**.

1. Pilih **Simpan** untuk menerapkan perubahan.

### <a name="delete-a-workspace"></a>Hapus ruang kerja

Menghapus ruang kerja akan menghapus semua konten, data, pengaturan, dan izinnya secara permanen. Ini tidak dapat dibatalkan.

1. Buka **Admin** > **Ruang kerja** dan pilih **Pengaturan**.

1. Pilih **Hapus ruang kerja**. 

1. Masukkan **KONFIRMASIKAN PENGHAPUSAN** di dialog **Hapus ruang kerja**. 

1. Pilih **Hapus** untuk menghapus ruang kerja secara permanen.

### <a name="manage-workspace-members"></a>Mengelola anggota ruang kerja

1. Buka **Admin** > **Ruang kerja** dan pilih **Anggota**.

1. Pilih **Tambah anggota** untuk memberikan akses dan [menetapkan peran](user-roles.md). Saat ini, hanya **admin Ruang Kerja** yang tersedia.

1. Jika mengkonfigurasi [sambungan ke audiens wawasan](configure-connections.md), Anda dapat memilih **Izinkan akses ke data profil** untuk memungkinkan anggota melihat laporan berdasarkan [profil pengguna](profile-reports.md).

1. Pilih **Tambah anggota** untuk menambahkannya ke ruang kerja Anda.

## <a name="manage-an-environment"></a>Kelola lingkungan

Sebagai admin Lingkungan, Anda dapat mengakses lingkungan dari panel navigasi kiri. Anda dapat mengkonfigurasi pengaturan lingkungan, admin Lingkungan, ruang kerja, dan [sambungan ke wawasan audiens](configure-connections.md). Pilih tab untuk berpindah antar area berbeda di pusat admin.

:::image type="content" source="media/New-environment.png" alt-text="Pusat admin lingkungan.":::

### <a name="create-an-environment"></a>Buat lingkungan

1. Di pemilih kerja, pilih **+Baru**.

1. Dalam pengalaman berpemandu, buka menu drop-down **Lingkungan** dan pilih **Buat lingkungan baru**. 

1. Berikan **nama Lingkungan**.

   :::image type="content" source="media/create-environment.png" alt-text="Langkah dalam pengalaman berpemandu untuk menentukan detail lingkungan.":::

1. Pilih **Kawasan** dan pilih **Berikutnya**. 

1. Sediakan nama Ruang Kerja dan pilih tipe ruang kerja yang ingin Anda buat. 

1.  Atau, tambahkan anggota dan salin cuplikan kode untuk menyelesaikan proses pembuatan.

### <a name="rename-an-environment"></a>Ubah nama lingkungan

1. Buka **Admin** > **Lingkungan** dan pilih **Pengaturan**.

1. Perbarui **nama lingkungan**, lalu pilih **Simpan** untuk menerapkan perubahan Anda.

### <a name="manage-environment-members"></a>Kelola anggota lingkungan

1. Buka **Admin** > **Lingkungan** dan pilih **anggota**.

1. Pilih **Tambah anggota** untuk memperbarui anggota dan [menetapkan peran](user-roles.md). Saat ini, hanya **admin Lingkungan** yang tersedia.

1. Jika mengkonfigurasi [sambungan ke audiens wawasan](configure-connections.md), Anda dapat memilih **Izinkan akses ke data profil** untuk memungkinkan anggota melihat laporan berdasarkan [profil pengguna](profile-reports.md).

1. Pilih **Tambah anggota** untuk menambahkannya ke lingkungan Anda.

### <a name="delete-an-environment"></a>Hapus lingkungan

Admin lingkungan dapat menghapus lingkungan. Sebelum dapat menghapus lingkungan, Anda harus menghapus semua ruang kerja di bawahnya.

1. Buka **Admin** > **Lingkungan** dan pilih **Pengaturan**.

1. Pilih **hapus lingkungan**. 

1. Masukkan **KONFIRMASIKAN PENGHAPUSAN** di dialog **Hapus ruang kerja**. 

1. Pilih **Hapus** untuk menghapus lingkungan secara permanen.

## <a name="manage-connections"></a>Kelola koneksi

Menetapkan sambungan ke wawasan audiens memungkinkan Anda melihat laporan dalam wawasan keterlibatan berdasarkan profil pelanggan terpadu. 

Untuk informasi lebih lanjut lihat [konfigurasikan koneksi](configure-connections.md).

## <a name="manage-personal-data"></a>Mengelola data pribadi

Untuk melindungi data pribadi pelanggan, Anda dapat menghapus atau mengekspor data identifikasi pengguna akhir.

Untuk informasi lebih lanjut, lihat [Menghapus dan mengekspor data aktivitas yang berisi informasi pribadi](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
