---
title: Kelola izin pengguna
description: Pelajari tentang izin dan peran pengguna.
ms.date: 02/09/2022
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
ms.openlocfilehash: 8022563f8994400b88389c20d7d661d9ea82bab1
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833726"
---
# <a name="user-permissions"></a>Izin pengguna

Halaman **Izin** adalah tempat Anda akan menyiapkan peran dan izin untuk menggunakan Customer Insights.

Anda harus memiliki izin administrator untuk melihat halaman. Untuk mengakses halaman izin, buka **Pengguna Keamanan** > **Admin** > **·**.

Ada tiga jenis peran:

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
- Lengkap ***Penyatuan** Data yang menghasilkan entitas profil pelanggan terpadu.
- Tentukan **Relasi** dan **aktivitas**.
- Buat segmen menggunakan halaman **segmen**.
- Buat ukuran menggunakan halaman **ukuran**.
- Kelola konfigurasi dan Perkaya profil pelanggan dari halaman **pengayaan** (hanya untuk pengayaan pihak pertama).
- Kelola dan buat ekspor berdasarkan koneksi yang dibagikan dengan kontributor. [Selengkapnya tentang cara administrator mengizinkan kontributor menggunakan sambungan untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Admin

- Semua izin yang tersedia untuk Kontributor.
- Ubah pengaturan pada halaman **sistem**, termasuk bahasa kerja dan refresh jadwal untuk proses sistem Anda.
- Lihat dan tambahkan izin menggunakan halaman **izin**.
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

## <a name="assign-roles-and-permissions"></a>Menetapkan izin dan peran

1. Buka **> Keamanan** > **Admin****Pengguna***.

1. Pilih **Tambah Pengguna** untuk membuka panel **Tambah/Edit izin**.

1. Gunakan bidang **pencarian** untuk menemukan pengguna Azure Active Directory atau grup yang izinnya ingin Anda Sesuaikan. Pilih **peran** yang akan ditetapkan ke pengguna atau grup tersebut.

1. Pilih **Simpan**. Lingkungan saat ini akan secara otomatis dibagikan dengan pengguna atau anggota grup yang izinnya telah Anda ubah. Pengguna dapat mengakses aplikasi customer Insights dan bekerja sesuai dengan peran mereka.

## <a name="view-current-permissions"></a>Lihat izin saat ini

Buka **Pengguna** > **Keamanan** > **Admin** untuk melihat penetapan peran apa yang saat ini aktif.

- Kolom **jenis** menentukan pengguna, grup, atau aplikasi tunggal. Sistem ini mendukung setiap pengguna dan grup.
- Peran ditentukan dalam kolom **peran**.
- Pilih judul kolom untuk mengurutkan hasil berdasarkan nilai kolom tersebut.
- Gunakan bidang **pencarian** di bagian atas halaman untuk mencari pengguna tertentu.


[!INCLUDE [footer-include](includes/footer-banner.md)]
