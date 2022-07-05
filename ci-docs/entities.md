---
title: Entitas di Customer Insights
description: Lihat data pada halaman entitas.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 4abb7704710ac269a4f3c9463fe905fa6eec3234
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082723"
---
# <a name="entities-in-customer-insights"></a>Entitas di Customer Insights

Setelah [mengkonfigurasi sumber data](data-sources.md), buka halaman **entitas** untuk mengevaluasi kualitas data yang terserap. Entitas dianggap sebagai himpunan data. Beberapa kemampuan Dynamics 365 Customer Insights dibangun di sekitar entitas ini. Meninjau mereka secara dekat dapat membantu Anda memvalidasi output dari kemampuan tersebut.

Halaman **Entitas** mencantumkan entitas dan menyertakan kolom ini:

- **Nama**: Nama entitas data. Jika Anda melihat simbol peringatan di samping nama entitas, berarti bahwa data untuk entitas tersebut tidak berhasil dimuat.
- **Sumber**: Jenis sumber data yang menelan entitas.
- **Diperbarui**: Waktu entitas terakhir diperbarui.
- **Status**: Detail tentang pembaruan terakhir entitas.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Jelajahi data entitas tertentu

1. Buka **Entitas Data** > **·**.
1. Dari halaman **Entitas**, pilih entitas untuk membuka halaman detail.  
1. Jelajahi berbagai bidang dan rekaman yang disertakan untuk entitas tersebut.

- Tab **Atribut** dipilih secara default dan menampilkan tabel untuk meninjau rincian entitas yang dipilih, seperti nama bidang, jenis data, dan jenis. Kolom **jenis** menunjukkan jenis terkait Common Data Model, yang baik yang diidentifikasi secara otomatis oleh sistem, atau yang [dipetakan secara manual](map-entities.md) oleh pengguna. Jenis ini adalah jenis semantik yang dapat berbeda dari jenis data atribut. Misalnya, bidang *email* di bawah ini memiliki jenis data *teks* namun jenis Common Data Model (semantik)-nya mungkin *email* atau *EmailAddress*.

> [!div class="mx-imgBorder"]
> ![Tabel bidang.](media/data-manager-entities-fields.PNG "Tabel bidang")

> [!NOTE]
> Halaman ini hanya menampilkan sampel data entitas Anda. Untuk melihat himpunan data lengkap, buka **halaman Sumber** data, pilih entitas, pilih **Edit**, lalu lihat data entitas ini dengan Power Query editor seperti yang dijelaskan di [Sumber data](data-sources.md).

Untuk mempelajari lebih lanjut tentang data yang terserap di entitas, kolom **ringkasan** memberi Anda beberapa karakteristik penting data, seperti null, nilai yang tidak ada, nilai unik, jumlah, dan distribusi, sebagaimana berlaku untuk data Anda. Pilih ikon diagram untuk melihat ringkasan data.

> [!div class="mx-imgBorder"]
> ![Simbol ringkasan.](media/data-manager-entities-summary.png "Tabel Ringkasan Data")

- Tab **Data** menampilkan rincian daftar tabel tentang rekaman individual entitas. Detail yang tercantum bergantung pada tipe data entitas.

> [!div class="mx-imgBorder"]
> ![Pilih entitas.](media/data-manager-entities-data.png "Pilih satu entitas")

- Tab **Laporan** (tersedia untuk beberapa entitas) memungkinkan Anda memvisualisasikan data dengan membuat laporan, dan menyertakan kolom berikut:

  - **Nama laporan**: Nama laporan.
  - **Dibuat oleh**: Nama orang yang membuat entitas.
  - **Dibuat**: Tanggal dan waktu pembuatan entitas.
  - **Diedit oleh**: Nama orang yang memodifikasi entitas.
  - **Diedit**: Tanggal dan waktu modifikasi entitas. 

## <a name="entity-specific-information"></a>Informasi spesifik Entitas

Bagian berikut ini menyediakan informasi tentang beberapa entitas yang dibuat sistem.

### <a name="corrupted-data-sources"></a>Sumber data yang rusak

Bidang dari sumber data yang diserap dapat berisi data yang rusak. Rekaman dengan bidang yang rusak diekspos dalam entitas yang dibuat sistem. Mengetahui tentang rekaman yang rusak membantu Anda mengidentifikasi data mana yang akan ditinjau dan diperbarui pada sistem sumber. Setelah penyegaran berikutnya dari sumber data, rekaman yang dikoreksi diserap ke Customer Insights dan diteruskan ke proses hilir. 

Misalnya, kolom 'ulang tahun' memiliki himpunan tipe data sebagai 'tanggal'. Rekaman pelanggan memasukkan ulang tahun mereka sebagai '01/01/19777'. Sistem akan menandai rekaman ini sebagai rusak. Seseorang sekarang dapat mengubah ulang tahun dalam sistem sumber menjadi '1977'. Setelah refresh otomatis sumber data, bidang sekarang memiliki format yang valid dan rekaman akan dihapus dari entitas yang rusak. 

Buka **Data** > **Entitas** dan cari entitas yang rusak di bagian **Sistem**. Penamaan skema entitas yang rusak: 'DataSourceName_EntityName_corrupt'. Pilih entitas yang rusak untuk mengidentifikasi semua bidang yang rusak dan alasannya di tingkat rekaman individu.
> [!div class="mx-imgBorder"]
> ![Alasan korupsi.](media/corruption-reason.png "Alasan Korupsi")

Customer Insights masih memproses rekaman yang rusak. Namun, mereka dapat menyebabkan masalah saat bekerja dengan data terpadu.

Pemeriksaan berikut ini berjalan pada data yang diserap untuk mengekspos rekaman yang rusak: 

- Nilai bidang tidak cocok dengan tipe data kolomnya.
- Bidang berisi karakter yang menyebabkan kolom tidak cocok dengan skema yang diharapkan. Misalnya: kutipan yang salah diformat, tanda kutip yang tidak di-escape, atau karakter baris baru.
- Jika ada kolom datetime/date/datetimeoffset, formatnya perlu ditentukan dalam model jika tidak mengikuti format ISO standar.


[!INCLUDE [footer-include](includes/footer-banner.md)]
