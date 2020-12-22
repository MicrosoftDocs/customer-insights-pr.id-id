---
title: Kelola izin pengguna
description: Pelajari tentang izin dan peran pengguna.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7de78c0ef71ec5b83870d396de36a7dcabbd14e5
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689224"
---
# <a name="user-permissions"></a>Izin pengguna

Halaman **izin** adalah tempat Anda akan mengkonfigurasi peran dan izin untuk menggunakan wawasan audiens.

Anda harus memiliki izin administrator untuk melihat halaman. Untuk mengakses halaman izin di wawasan audiens, buka **Admin** > **izin**.

Ada tiga jenis peran:

## <a name="viewer"></a>Penampil

- Jelajahi wawasan dan segmen di halaman **Beranda** dan **segmen**.
- Cari dan filter profil pelanggan menggunakan halaman **pelanggan**. Bidang harus dapat dicari.
- Lihat dan Jelajahi halaman **pengayaan**.
- Jelajahi serta ekspor entitas menggunakan halaman **entitas**.
- Lihat status proses sistem menggunakan halaman **sistem**.
- Ekspor segmen dari halaman **segmen**.
- Menginstal dan menggunakan dasbor **Power BI Customer Insights**.

## <a name="contributor"></a>Kontributor

- Semua izin yang tersedia untuk pemirsa.
- Muat dan Ubah data menggunakan halaman **sumber data**.
- Lengkapi bagian *penyatuan data* (**memetakan**, **mencocokkan**, dan **menggabungkan**) yang menghasilkan entitas profil pelanggan terpadu.
- Tentukan **Relasi** dan **aktivitas**.
- Buat segmen menggunakan halaman **segmen**.
- Buat ukuran menggunakan halaman **ukuran**.
- Kelola konfigurasi dan Perkaya profil pelanggan dari halaman **pengayaan** (hanya untuk pengayaan pihak pertama).

## <a name="administrator"></a>Administrator

- Semua izin yang tersedia untuk Kontributor.
- Ubah pengaturan pada halaman **sistem**, termasuk bahasa kerja dan refresh jadwal untuk proses sistem Anda.
- Lihat dan tambahkan izin menggunakan halaman **izin**.
- Atur definisi pencarian dan filter untuk halaman pelanggan menggunakan halaman **indeks pencarian & Filter** (dapat diakses melalui halaman **pelanggan**).
- Tentukan tujuan segmen Dynamics 365 Sales menggunakan halaman **Tujuan ekspor**.
- Kelola konfigurasi dan Perkaya profil pelanggan dari halaman **pengayaan** (untuk semua pengayaan).
- Instal dan gunakan **Add -in kartu pelanggan**.
- Tambahkan dan gunakan **Power Apps connector**.
- Aktifkan penggunaan [API Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Menetapkan izin dan peran

1. Di wawasan audiens, buka **Admin** > **Izin**.

1. Pilih **Tambah Pengguna** untuk membuka panel **Tambah/Edit izin**.

1. Gunakan bidang **pencarian** untuk menemukan pengguna Azure Active Directory atau grup yang izinnya ingin Anda Sesuaikan. Pilih **peran** yang akan ditetapkan ke pengguna atau grup tersebut.

1. Pilih **Simpan**. Lingkungan saat ini akan secara otomatis dibagikan dengan pengguna atau anggota grup yang izinnya telah Anda ubah. Pengguna dapat mengakses aplikasi customer Insights dan bekerja sesuai dengan peran mereka.

## <a name="view-current-permissions"></a>Lihat izin saat ini

Di audiens wawasan, buka **Admin** > **izin** untuk melihat tugas peran apa yang saat ini aktif.

- Kolom **jenis** menentukan pengguna, grup, atau aplikasi tunggal. Sistem ini mendukung setiap pengguna dan grup.
- Peran ditentukan dalam kolom **peran**.
- Pilih judul kolom untuk mengurutkan hasil berdasarkan nilai kolom tersebut.
- Gunakan bidang **pencarian** di bagian atas halaman untuk mencari pengguna tertentu.
