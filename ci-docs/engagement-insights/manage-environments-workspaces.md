---
title: Mengelola ruang kerja dan lingkungan
description: Cara membuat, mengganti nama, dan menghapus ruang kerja dan lingkungan.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 279af24358a1d6ea2b4cc75d5496042af73a7cae
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645450"
---
# <a name="manage-environments-and-workspaces"></a>Mengelola lingkungan dan ruang kerja

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Gambaran Umum

Topik ini akan membahas cara mengelola ruang kerja dan lingkungan setelah dibuat. 

- *Ruang kerja* adalah ruang menyimpan dan mengelola aktivitas dan laporan. Di sini Anda dapat melihat aktivitas pengguna secara real time. Saat membuat ruang kerja, Anda dapat memilih jenis data untuk dikirimkan ke ruang kerja. Saat ini, data web dan aplikasi perangkat bergerak didukung. Untuk informasi lebih lanjut, lihat [Membuat ruang kerja dan menambahkan anggota](create-workspace.md).

- *Lingkungan* adalah ruang yang memungkinkan Anda mengelola ruang kerja dan sambungan. Untuk informasi lebih lanjut, lihat [Membuat lingkungan baru](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Kelola ruang kerja yang ada

Anda dapat mengelola beberapa ruang kerja secara bersamaan di lingkungan. [Peran](user-roles.md) Anda menentukan cara kerja Anda di dalamnya. 

 - Anda harus menjadi admin Lingkungan atau admin Ruang Kerja untuk mengelola ruang kerja.
 - Sebagai admin Ruang Kerja, Anda dapat mengganti nama ruang kerja yang ada atau menghapusnya. 

:::image type="content" source="media/workspace-edit.png" alt-text="Pusat Admin ruang kerja.":::

### <a name="edit-a-workspace-name"></a>Edit nama ruang kerja

1. Buka **Admin** > **Ruang kerja** dan pilih **Pengaturan**.

1. Masukkan nama baru di kotak **nama ruang kerja**.

1. Pilih **Simpan** untuk menerapkan perubahan.

### <a name="delete-a-workspace"></a>Hapus ruang kerja

Menghapus ruang kerja akan menghapus semua konten, data, pengaturan, dan izinnya secara permanen. Ini tidak dapat dibatalkan.

1. Buka **Admin** > **Ruang kerja** dan pilih **Pengaturan**.

1. Pilih **Hapus ruang kerja**. 

1. Dalam dialog **Hapus ruang kerja**, masukkan **KONFIRMASIKAN HAPUS** dengan huruf besar semua. 

1. Pilih **Hapus** untuk menghapus ruang kerja secara permanen.

### <a name="manage-workspace-members"></a>Mengelola anggota ruang kerja

1. Buka **Admin** > **Ruang kerja** dan pilih **Anggota**.

1. Pilih **Tambah anggota** untuk memberikan akses dan [menetapkan peran](user-roles.md). Saat ini, hanya **admin Ruang Kerja** yang tersedia.

1. Pilih **Tambah anggota** untuk menambahkannya ke ruang kerja Anda.

## <a name="manage-an-existing-environment"></a>Kelola lingkungan yang ada

Sebagai admin Lingkungan, Anda dapat mengakses lingkungan dari panel navigasi kiri. Anda dapat mengkonfigurasi pengaturan lingkungan, admin lingkungan lainnya, dan ruang kerja. Pilih tab untuk berpindah antar area berbeda di pusat admin.

:::image type="content" source="media/environment-edit.png" alt-text="Pusat admin lingkungan.":::

### <a name="rename-an-environment"></a>Ubah nama lingkungan

1. Buka **Admin** > **Lingkungan** dan pilih **Pengaturan**.

1. Perbarui **nama lingkungan**, lalu pilih **Simpan** untuk menerapkan perubahan Anda.

### <a name="manage-environment-members"></a>Kelola anggota lingkungan

1. Buka **Admin** > **Lingkungan** dan pilih **anggota**.

1. Pilih **Tambah anggota** untuk memperbarui anggota dan [menetapkan peran](user-roles.md). Saat ini, hanya **admin Lingkungan** yang tersedia.

1. Pilih **Tambah anggota** untuk menambahkannya ke lingkungan Anda.

### <a name="delete-an-environment"></a>Hapus lingkungan

Admin lingkungan dapat menghapus lingkungan. Sebelum dapat menghapus lingkungan, Anda harus menghapus semua ruang kerja di bawahnya.

1. Buka **Admin** > **Lingkungan** dan pilih **Pengaturan**.

1. Pilih **hapus lingkungan**. 

1. Dalam dialog **Hapus ruang kerja**, masukkan **KONFIRMASIKAN HAPUS** dengan huruf besar semua. 

1. Pilih **Hapus** untuk menghapus lingkungan secara permanen.

## <a name="manage-connections"></a>Kelola koneksi

Menetapkan sambungan ke wawasan audiens memungkinkan Anda melihat laporan dalam wawasan keterlibatan berdasarkan profil pelanggan terpadu. 

Untuk informasi lebih lanjut, lihat [Membuat tautan antara wawasan audiens dan wawasan keterlibatan](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Mengelola data pribadi

Untuk melindungi data pribadi pelanggan, Anda dapat menghapus atau mengekspor data identifikasi pengguna akhir.

Untuk informasi lebih lanjut, lihat [Menghapus dan mengekspor data aktivitas yang berisi informasi pribadi](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
