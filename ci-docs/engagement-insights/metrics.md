---
title: Melihat dan membuat metrik
description: Bagaimana membuat, mengedit, dan menghapus metrik.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 79600a14bc7e98dfd066270f19c353fd007e1341
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623726"
---
# <a name="view-and-create-metrics"></a>Melihat dan membuat metrik

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Metrik membantu memahami perilaku pengunjung Anda. Mereka menggabungkan properti aktivitas dan mengukur statistik dan kinerja properti web Anda.  

Misalkan Anda menjalankan promosi pemasaran di situs web Anda. Anda dapat menggunakan metrik untuk melacak jumlah pengunjung unik atau pengguna yang datang ke situs web Anda selama promosi. Menganalisis metrik akan membantu Anda memahami dengan lebih baik audiens situs web Anda. Menggabungkan metrik dengan [dimensi](dimensions.md) pada [laporan kustom](custom-reports.md) memungkinkan Anda mengukur perilaku untuk memahami pengguna. Misalnya, Anda dapat memisahkan pengunjung ke kategori baru dan kembali untuk mengidentifikasi perbedaan dalam minat dan maksud di antara grup tersebut.

## <a name="view-metrics"></a>Lihat metrik

Wawasan keterlibatan mencakup agregasi properti aktivitas yang umum digunakan sebagai metrik sistem: 

- Pengunjung
- Kunjungan
- Tampilan halaman
- Klik

Metrik sistem ini didasarkan pada properti aktivitas yang ada di aktivitas dasar.

1. Di panel navigasi kiri, buka **Data**. 
1. Pilih tab **Metrik** untuk melihat daftar semua metrik di ruang kerja. 
   > [!NOTE]
   > Metrik yang dihasilkan sistem hanya dapat baca. Anda tidak dapat mengedit atau menghapusnya. Anda hanya dapat membuat dan mengedit metrik kustom.

## <a name="create-a-metric"></a>Buat metrik

Admin lingkungan dan ruang kerja dapat membuat metrik. Properti aktivitas harus dikirim ke ruang kerja sebelum Anda membuat metrik. Anda dapat membuat metrik berdasarkan properti aktivitas yang dikirim oleh aktivitas dasar atau menggunakan SDK web untuk [mengirim properti aktivitas kustom](advanced-SDK-implementation.md).

1. Buka **data** > **Metrik**.
1. Pilih **Metrik baru** untuk membuka **Pustaka Sumber Daya** dan dialog **metrik tanpa judul baru**.

   :::image type="content" source="media/new-metric.png" alt-text="Menambahkan metrik ke aktivitas.":::

1. Dalam dialog **metrik tanpa judul baru**, pilih daftar dropdown **Format**, dan pilih jenis data **bilangan bulat** atau **ganda**. Bilangan bulat di sini adalah bilangan cacah. Untuk Ganda, Anda dapat memilih satu dan tiga tempat desimal.

   :::image type="content" source="media/create-new-metric.png" alt-text="Membuat metrik baru.":::
   
5. Di panel **Pustaka sumber daya**, cari properti aktivitas sebagai dasar metrik.
6. Pilih **tanda plus (+)** di sebelah properti untuk menggunakannya dalam rumus. Anda hanya dapat membuat rumus berdasarkan satu properti. 
7. Pilih salah satu dari fungsi agregat berikut ini. 

   - Jumlah: total aritmetika dari semua nilai 
   - Rata-rata: rata-rata dari semua nilai
   - Hitung: jumlah total nilai
   - Hitungan jelas: jumlah total nilai yang berbeda

   Setelah menentukan metrik, Anda melihat pratinjau aktivitas metrik selama satu jam terakhir.

1. Pilih **Simpan**. 
1. Masukkan nama untuk metrik, dan kemudian pilih **Simpan**.

Diperlukan waktu hingga satu menit untuk metrik sebelum Anda dapat menggunakannya untuk [membuat laporan kustom](custom-reports.md).

## <a name="edit-a-metric"></a>Mengedit metrik

Anda hanya dapat mengedit metrik kustom.

1. Buka **data** > **Metrik**.
1. Pilih metrik dalam daftar.
1. Mengubah definisi metrik
1. Pilih **Simpan**.

## <a name="change-the-name-of-a-metric"></a>Ubah nama metrik

Anda hanya dapat mengubah nama metrik kustom.

1. Buka **data** > **Metrik**.
1. Pilih **Lainnya [...]** untuk metrik dan pilih **Edit nama**.
1. Ubah nama. 
1. Pilih **Ganti Nama**.

## <a name="delete-a-metric"></a>Hapus metrik

Anda hanya dapat menghapus metrik kustom.

1. Buka **data** > **Metrik**.
1. Pilih **Lainnya [...]** untuk metrik dan pilih **Hapus**.

   :::image type="content" source="media/delete-metric.png" alt-text="Hapus metrik pada aktivitas.":::

1. Klik **Hapus**, untuk mengonfirmasi penghapusan tersebut.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
