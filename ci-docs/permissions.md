---
title: Menetapkan izin pengguna
description: Pelajari tentang izin dan peran pengguna.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245423"
---
# <a name="assign-user-permissions"></a>Menetapkan izin pengguna

Akses ke Customer Insights dibatasi untuk pengguna di organisasi Anda yang ditambahkan ke aplikasi oleh admin. Admin dapat menambahkan, mengedit, atau menghapus pengguna. Pengguna dapat berupa satu pengguna, grup, atau aplikasi. Ada tiga jenis peran yang dapat dimiliki pengguna:

## <a name="viewer"></a>Penampil

- Jelajahi wawasan dan segmen di halaman **Beranda** dan **segmen**.
- Cari dan filter profil pelanggan menggunakan halaman **pelanggan**. Bidang harus dapat dicari.
- Lihat dan Jelajahi halaman **pengayaan**.
- Jelajahi serta ekspor entitas menggunakan halaman **entitas**.
- Lihat status proses sistem menggunakan halaman **sistem**.
- Lihat ekspor dalam halaman **Ekspor**.
- Menginstal dan menggunakan dasbor **Power BI Customer Insights**.

## <a name="contributor"></a>Kontributor

- Semua izin yang tersedia untuk pemirsa.
- Muat dan Ubah data menggunakan halaman **sumber data**.
- Penyatuan **Data Lengkap** yang menghasilkan entitas profil pelanggan terpadu.
- Tentukan **Relasi** dan **aktivitas**.
- Buat segmen menggunakan halaman **segmen**.
- Buat ukuran menggunakan halaman **ukuran**.
- Kelola konfigurasi dan Perkaya profil pelanggan dari halaman **pengayaan** (hanya untuk pengayaan pihak pertama).
- Kelola dan buat ekspor berdasarkan [koneksi yang dibagikan dengan kontributor](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Admin

- Semua izin yang tersedia untuk Kontributor.
- Ubah pengaturan pada **halaman Sistem**, termasuk bahasa kerja, refresh jadwal untuk proses sistem Anda, dan ekspor log diagnostik.
- Ubah pengaturan di **halaman Keamanan**, termasuk pengguna, kunci API, tautan privat, dan brankas kunci.
- Atur definisi pencarian dan filter untuk halaman pelanggan menggunakan halaman **indeks pencarian & Filter** (dapat diakses melalui halaman **pelanggan**).
- Kelola koneksi dan izinkan mereka untuk peran pengguna lain di halaman **Koneksi**.
- Kelola konfigurasi dan Perkaya profil pelanggan dari halaman **pengayaan** (untuk semua pengayaan).
- Mengelola dan membuat ekspor di halaman **Ekspor**.
- Instal dan gunakan **Add -in kartu pelanggan**.
- Tambahkan dan gunakan **Power Apps connector**.
- Aktifkan penggunaan [API Customer Insights](apis.md).
- [Tetapkan kepemilikan](manage-environments.md#change-the-owner-of-an-environment) lingkungan ke admin lain.

## <a name="admin-owner"></a>Admin (pemilik)

- Semua izin tersedia untuk Admin.
- [Atur ulang dan hapus](manage-environments.md#reset-an-existing-environment-preview) lingkungan.

## <a name="add-users"></a>Tambah pengguna

1. Buka **Keamanan** > **Admin** dan pilih tab **Pengguna**.

1. Pilih **Tambah Pengguna** untuk membuka panel **Tambah/Edit izin**.

1. Gunakan bidang **Pencarian** untuk menemukan pengguna atau grup yang Azure Active Directory ingin Anda tambahkan. Pilih **peran** yang akan ditetapkan ke pengguna atau grup tersebut.

1. Pilih **Simpan**. Lingkungan saat ini secara otomatis dibagikan dengan pengguna atau anggota grup. Pengguna dapat mengakses aplikasi customer Insights dan bekerja sesuai dengan peran mereka.

## <a name="view-current-permissions"></a>Lihat izin saat ini

Buka **Keamanan** > **Admin** dan pilih tab **Pengguna** untuk melihat daftar pengguna aktif dan penetapan peran mereka. Anda dapat mengurutkan daftar pengguna berdasarkan kolom mana pun atau menggunakan kotak pencarian untuk menemukan pengguna tertentu.

## <a name="manage-current-users"></a>Mengelola pengguna saat ini

Buka **Keamanan** > **Admin** dan pilih tab **Pengguna**. Anda dapat mengurutkan daftar pengguna berdasarkan kolom mana pun atau menggunakan kotak pencarian untuk menemukan pengguna yang ingin Anda kelola.

Pilih pengguna untuk melihat tindakan yang tersedia.

- **Edit** untuk mengedit peran pengguna di Customer Insights. Pilih **Simpan** untuk mengonfirmasi perubahan.
- **Hapus** untuk menghapus pengguna agar tidak memiliki akses ke Customer Insights. Klik **Hapus**, untuk mengonfirmasi penghapusan tersebut.

[!INCLUDE [footer-include](includes/footer-banner.md)]
