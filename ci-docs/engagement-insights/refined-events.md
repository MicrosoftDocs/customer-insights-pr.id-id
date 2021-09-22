---
title: Buat dan modifikasi aktivitas yang disempurnakan
description: Cara membuat dan memodifikasi aktivitas yang disempurnakan.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034778"
---
# <a name="create-and-modify-refined-events"></a>Buat dan modifikasi aktivitas yang disempurnakan

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Aktivitas adalah data yang menunjukkan perilaku pengguna, seperti aktivitas di situs web.

- Rekaman aktivitas *dasar* ketika pengguna melihat halaman (aktivitas melihat) atau berinteraksi dengan konten (aktivitas tindakan).
- Aktivitas *yang disempurnakan* adalah tampilan virtual aktivitas dasar. Anda mendefinisikan aktivitas yang disempurnakan dengan menghapus dan menambahkan properti atau dengan memfilter aktivitas berdasarkan nilai properti.

Gunakan aktivitas disempurnakan untuk mengurangi cakupan aktivitas dasar untuk [ekspor](export-events.md) atau menghilangkan properti yang tidak diperlukan untuk paparan ata.

## <a name="create-refined-events"></a>Buat aktivitas yang disempurnakan

Tersedia tiga cara untuk membuat aktivitas disempurnakan dari aktivitas dasar. 

1. Buka **Data**> **Aktivitas**, lalu tentukan salah satu pilihan berikut:
    - Pilih **Aktivitas baru**, lalu pilih **Buat aktivitas disempurnakan**.
    - Pilih aktivitas dasar untuk membuka tampilan rinci, lalu pilih **Buat aktivitas disempurnakan** dari menu atas.
    - Pilih **Lainnya [...]** untuk membuka menu pintasan untuk aktivitas dasar. Kemudian pilih **Buat aktivitas disempurnakan**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Pilihan untuk membuat aktivitas disempurnakan.":::

1. Dalam dialog **Buat aktivitas yang disempurnakan**, masukkan informasi berikut:

- Pilih aktivitas dari dropdown **Aktivitas dasar** jika Anda membuat aktivitas baru.
- Masukkan nama dalam kotak **nama tampilan aktivitas yang disempurnakan**.
- Atau, perbarui **nama Aktual** yang disarankan tanpa menggunakan spasi.

3. Pilih **Buat** untuk menerapkan pengaturan.

1. Di tampilan rinci aktivitas disempurnakan Anda, pilih **Tambah dan hilangkan properti** untuk membuka panel **Edit properti**. 

1. Gunakan kotak centang untuk memilih properti yang ingin Anda tampilkan dan properti yang akan disembunyikan. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Mengedit properti untuk aktivitas disempurnakan.":::

1. Pilih **Konfirmasi** untuk menerapkan pilihan Anda.

1. Pilih **Simpan** untuk menyimpan konfigurasi.

## <a name="edit-refined-events"></a>Mengedit aktivitas disempurnakan

Anda dapat mengubah nama dan properti aktivitas disempurnakan.

### <a name="edit-event-name"></a>Mengedit Nama aktivitas

1. Buka **data** > **aktivitas**. 
1. Pilih **Lainnya [...]** untuk aktivitas, lalu pilih **Edit nama**.
1. Perbarui nama aktivitas, lalu pilih **Ganti nama**.

### <a name="edit-selected-properties"></a>Edit Properti yang dipilih

1. Buka **Data** > **Aktivitas**, lalu pilih aktivitas disempurnakan untuk membuka tampilan rinci.
1. Pilih **Tambah dan hilangkan properti**. 
1. Edit pilihan kotak centang.
1. Pilih **Konfirmasi**, lalu **Simpan** untuk menerapkan perubahan.

Untuk informasi tentang cara mengekspor aktivitas, lihat [Aktivitas ekspor](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
