---
title: Melihat dan membuat segmen
description: Cara membuat, mengedit, dan menghapus segmen serta lokasi penggunaannya.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: e99c04e6c92d8ca16c2d69957e0f5b7dba0ac757
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225380"
---
# <a name="view-and-create-segments"></a>Melihat dan membuat segmen

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmen memungkinkan Anda mengidentifikasi subset pengunjung berdasarkan karakteristik atau interaksi situs web. Segmen memungkinkan Anda menerapkan filter dan menganalisis subset tersebut. Analisis dapat membantu memeriksa dan merespons tren dalam bisnis Anda. 

:::image type="content" source="media/segments-page.png" alt-text="Cuplikan layar aplikasi wawasan keterlibatan yang menampilkan daftar segmen yang ada di ruang kerja.":::

## <a name="view-segments"></a>Lihat segmen

1. Di panel navigasi kiri, buka **Data**. 

1. Pilih tab **Segmen** untuk melihat daftar semua segmen dalam ruang kerja. 

## <a name="create-a-segment"></a>Buat segmen

Segmen terdiri dari aturan dan kondisi yang tersambung dengan operator logika. Kondisi menerapkan filter ke dimensi yang dipilih. Setiap segmen dapat menggunakan hingga lima dimensi.

Contoh berikut menampilkan segmen dengan dua kondisi pada satu aturan. Ini memfilter semua aktivitas situs web dengan browser adalah Chrome dan sistem operasinya adalah iOS atau Android.

:::image type="content" source="media/segment-sample.png" alt-text="Segmen contoh dengan dua kondisi dalam aturan untuk memfilter aktivitas situs web.":::

Bagian ini menjelaskan cara membuat *segmen kosong* dari awal.

1. Buka **Data** > **Segmen**.

1. pilih **Segmen baru**.

1. Di **Pustaka Sumber Daya**, pilih (+) di sebelah atribut yang akan difilter. Saat ini, Anda hanya dapat membuat segmen berdasarkan dimensi.

   :::image type="content" source="media/create-new-segment.png" alt-text="Buat segmen baru.":::

1. Di bagian **Aturan**, pilih operator dan nilai untuk atribut yang dipilih. Operasi berikut didukung.

   :::image type="content" source="media/choose-operator-segment.png" alt-text="Pilih operator untuk segmen baru Anda.":::

   - **is**: memerlukan pencocokan sama persis untuk mencakup nilai. Menggunakan **equal to** untuk satu nilai atau **any of** untuk mencakup beberapa nilai.
   - **is not**: memerlukan pencocokan sama persis untuk memisahkan nilai. Menggunakan **equal to** untuk satu nilai atau **any of** untuk mencakup beberapa nilai.
   - **starts with**: string yang mengawali nilai yang cocok.
   - **ends with**: string yang mengakhiri nilai yang cocok.
   - **contains**: string yang terdapat dalam nilai yang cocok.

1. Untuk menambahkan kondisi lainnya ke grup, Anda dapat menggunakan operator logika. Atribut yang diproyeksikan digunakan saat menggunakan operator yang ditentukan.
   - Operator **AND**: kedua kondisi harus dipenuhi sebagai bagian dari proses segmentasi. Pilihan ini paling berguna saat Anda menentukan kondisi di seluruh entitas yang berbeda.
   - Operator **OR**: Salah satu dari kondisi harus dipenuhi sebagai bagian dari proses segmentasi. Pilihan ini paling berguna saat Anda menentukan beberapa kondisi untuk entitas yang sama.

1. Pilih **Simpan** dan nama segmen. 

Segmen akan didaftarkan pada halaman **Segmen** dan Anda dapat menerapkannya ke semua laporan dan corong di ruang kerja.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Menggunakan segmen dalam laporan atau corong

Anda dapat menerapkan segmen ke laporan atau corong untuk memfilternya berdasarkan kondisi di segmen. Namun, Anda tidak dapat menerapkan segmen pada laporan penggunaan real-time.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Laporan tampilan halaman dengan daftar dropdown diperluas untuk memilih segmen yang akan diterapkan.":::

Untuk menerapkan segmen, buka laporan atau corong. Pilih **+ Tambah kondisi**, lalu pilih **Filter berdasarkan segmen**. Pilih segmen dari daftar yang ingin Anda terapkan. Segmen diterapkan ke laporan. Jika diagram tidak mendukung segmen, diagram akan menampilkan kesalahan. Untuk informasi lebih lanjut, lihat [Membuat dan mengelola laporan corong](funnel-reports.md).
 
Anda dapat menerapkan *hingga tiga segmen* ke laporan atau corong.

## <a name="edit-a-segment"></a>Edit segmen

1. Buka **Data** > **Segmen**.
1. Pilih segmen dalam daftar untuk membukanya. 
1. Ubah atau tambah nilai jika diperlukan.
1. Pilih **Simpan** untuk menerapkan perubahan.

## <a name="change-the-name-of-a-segment"></a>Ubah nama segmen

1. Buka **Data** > **Segmen**.
1. Dalam daftar segmen, pilih **Lainnya [...]**. 
1. Pilih **Edit nama** dari daftar dropdown.
1. Masukkan nama baru lalu pilih **Ganti nama**.

## <a name="delete-a-segment"></a>Hapus segmen

1. Buka **Data** > **Segmen**.
1. Dalam daftar segmen, pilih **Lainnya [...]**. 
1. Pilih **Hapus** dari daftar dropdown.
1. Untuk mengonfirmasikan, pilih **Hapus**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
