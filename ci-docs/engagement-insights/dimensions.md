---
title: Melihat dan membuat dimensi
description: Bagaimana membuat, mengedit, dan menghapus dimensi.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: d35c72f73d2f3e202ae3c5a5ef26e9db89360084
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226310"
---
# <a name="view-and-create-dimensions"></a>Melihat dan membuat dimensi

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dimensi adalah atribut aktivitas yang dapat mendeskripsikan, memfilter, atau mengelompokkan data. Jika Anda menjalankan promosi pemasaran di situs web, Anda dapat menggunakan dimensi untuk mengurutkan pengunjung berdasarkan pengguna baru dan yang kembali.  

Wawasan keterlibatan mencakup dimensi standar (OOB) untuk properti aktivitas. Contoh termasuk:

- Nama browser
- Nama halaman
- Model perangkat
- Sistem operasi
- Negara

## <a name="view-dimensions"></a>Lihat dimensi

Dimensi didasarkan pada properti aktivitas yang ada. Bila Anda menggunakan kode pelacakan untuk wawasan keterlibatan, dimensi sistem secara otomatis dibuat.

1. Di panel navigasi kiri, buka **Data**. 
1. Pilih **Dimensi** untuk melihat daftar semua dimensi di ruang kerja. 
   > [!NOTE]
   > Dimensi yang dihasilkan sistem hanya dapat baca. Anda tidak dapat mengeditnya. Anda hanya dapat membuat dan mengedit dimensi kustom.

## <a name="create-a-dimension"></a>Buat dimensi

Selain dimensi yang dihasilkan sistem, admin lingkungan dan ruang kerja dapat membuat dimensi kustom. Dimensi kustom didasarkan pada properti default aktivitas dasar atau mereka dapat menggunakan [properti kustom aktivitas](advanced-SDK-implementation.md).

1. Buka **Data** > **Dimensi**.
1. Pilih **Dimensi baru**.

   :::image type="content" source="media/add-dimension.png" alt-text="Menambahkan dimensi ke aktivitas.":::

1. Di panel **Buat dimensi**, pilih properti untuk dasar dimensi. Daftar properti akan menampilkan semua properti di ruang kerja yang tidak ditetapkan ke dimensi.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Buat dimensi baru.":::
      
3. Masukkan nama dalam kotak **nama tampilan**. Atau, Anda dapat menambahkan **deskripsi**.
4. Pilih **Buat** untuk menyimpan dimensi. Diperlukan waktu hingga satu menit sebelum Anda dapat menggunakan dimensi dalam [laporan kustom](custom-reports.md) atau [segmen](segments.md). 

## <a name="edit-a-dimension"></a>Edit dimensi

Anda dapat mengubah nama dan deskripsi dimensi. Anda hanya dapat mengedit dimensi yang dibuat pengguna, namun Anda tidak dapat mengedit dimensi sistem.


1. Buka **Data** > **Dimensi**.
1. Pilih dimensi yang akan dihapus.
1. Di panel **Edit dimensi**, perbarui dimensi.
1. Pilih **Terapkan** untuk menyimpan perubahan.

## <a name="delete-a-dimension"></a>Hapus dimensi

Anda hanya dapat menghapus dimensi yang dibuat pengguna, namun Anda tidak dapat menghilangkan dimensi sistem.

Menghapus dimensi bersifat permanen. Laporan dan segmen yang menggunakan dimensi yang dihapus tidak akan lagi berfungsi. 

1. Buka **Data** > **Dimensi**.
1. Pilih dimensi yang akan dihapus.
1. Di panel **Edit dimensi**, pilih **Hapus dimensi**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Menghapus dimensi pada aktivitas.":::

1. Masukkan **KONFIRMASIKAN HAPUS** (semua dengan huruf kapital) untuk mengkonfirmasi penghapusan. 
1. Pilih **Hapus**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
