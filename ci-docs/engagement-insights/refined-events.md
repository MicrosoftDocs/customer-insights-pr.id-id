---
title: Membuat dan memodifikasi aktivitas
description: Cara membuat dan memodifikasi aktivitas.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 935dc4cd41218842e8406b747daef47de04e337a
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606223"
---
# <a name="create-and-modify-events"></a>Membuat dan memodifikasi aktivitas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Aktivitas adalah data yang menunjukkan perilaku pengguna, seperti aktivitas di situs web.

- Rekaman aktivitas *dasar* ketika pengguna melihat halaman (aktivitas melihat) atau berinteraksi dengan konten (aktivitas tindakan).
- Aktivitas *yang disempurnakan* adalah tampilan virtual aktivitas dasar. Anda mendefinisikan aktivitas yang disempurnakan dengan menghapus dan menambahkan properti atau dengan memfilter aktivitas berdasarkan nilai properti.

## <a name="prerequisites"></a>Prasyarat

Untuk mendapatkan aktivitas, data situs web Anda pertama harus dihubungkan ke wawasan keterlibatan dengan cuplikan kode. Untuk informasi lebih lanjut, lihat [Menginstal SDK web di situs web](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Sambungkan data Anda terlebih dulu.":::

## <a name="create-refined-events"></a>Buat aktivitas yang disempurnakan

Gunakan aktivitas disempurnakan untuk mengurangi cakupan aktivitas dasar untuk [ekspor](export-events.md) atau menghilangkan properti yang tidak diperlukan untuk paparan ata.

> [!NOTE]
> Setelah menambahkan SDK web ke situs web, Anda dapat melihat aktivitas dasar dan membuat aktivitas disempurnakan. 

Untuk melihat aktivitas dasar Anda:

1. Di panel navigasi kiri, buka **Data**.

1. Pilih **Aktivitas** untuk melihat daftar semua aktivitas di ruang kerja.

    :::image type="content" source="media/data-events.png" alt-text="Lihat aktivitas.":::

Untuk membuat aktivitas disempurnakan dari aktivitas dasar: 

1. Buka **Data** > **Aktivitas**, lalu pilih **+ Aktivitas baru** di bagian atas layar.

1. Dalam dialog **Aktivitas baru**, pilih **Buat aktivitas disempurnakan**, lalu pilih **Berikutnya**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Wizard aktivitas baru.":::
     
1. Dalam dialog **Aktivitas baru**, masukkan informasi berikut:

   - Pilih aktivitas dari dropdown **Aktivitas dasar**.
   - Masukkan nama dalam kotak **nama tampilan aktivitas yang disempurnakan**.
   - Atau, perbarui **nama Aktual** yang disarankan tanpa menggunakan spasi.

1. Pilih **Buat** untuk menerapkan pengaturan.

Aktivitas yang disempurnakan sekarang akan ditampilkan dalam daftar **Aktivitas**.

### <a name="edit-event-name"></a>Mengedit Nama aktivitas

Anda dapat mengubah nama dan properti aktivitas dasar atau disempurnakan.

1. Buka **data** > **aktivitas**. 

1. Pilih **Lainnya [...]** untuk aktivitas, lalu pilih **Edit nama**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Pilihan untuk membuat aktivitas disempurnakan.":::

3. Perbarui nama aktivitas, lalu pilih **Ganti nama**.

### <a name="view-the-details-of-a-refined-event"></a>Melihat rincian aktivitas disempurnakan:

1. Dalam daftar **Aktivitas**, pilih aktivitas dasar atau yang disempurnakan. 

1. Pilih **Tambah dan hilangkan properti** di bagian atas layar untuk membuka panel **Edit properti**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Menambahkan dan menghapus properti.":::

1. Gunakan kotak centang untuk memilih properti yang ingin Anda tampilkan dan properti yang akan disembunyikan. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Mengedit properti untuk aktivitas disempurnakan.":::

1. Pilih **Konfirmasi** untuk menerapkan pilihan, lalu pilih **Simpan**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Mengedit properti yang dipilih untuk aktivitas disempurnakan

1. Buka **Data** > **Aktivitas**, lalu pilih aktivitas disempurnakan untuk membuka tampilan rinci.
1. Pilih **Tambah dan hilangkan properti**. 
1. Edit pilihan kotak centang.
1. Pilih **Konfirmasi**, lalu **Simpan** untuk menerapkan perubahan.

Untuk informasi tentang cara mengekspor aktivitas, lihat [Aktivitas ekspor](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
