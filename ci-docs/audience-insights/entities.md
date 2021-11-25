---
title: Entitas dan himpunan data
description: Lihat data pada halaman entitas.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 2a207a3dcad4bf192efb6ee1554195f10b19670b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732084"
---
# <a name="entities-in-audience-insights"></a>Entitas dalam wawasan audiens

Setelah [mengkonfigurasi sumber data](data-sources.md), buka halaman **entitas** untuk mengevaluasi kualitas data yang terserap. Entitas dianggap sebagai himpunan data. Beberapa kemampuan Dynamics 365 Customer Insights dibangun di sekitar entitas ini. Meninjau mereka secara dekat dapat membantu Anda memvalidasi output dari kemampuan tersebut.

Halaman **entitas** mencantumkan entitas dan mencakup beberapa kolom:

- **Nama**: nama entitas data Anda. Jika Anda melihat simbol peringatan di samping nama entitas, berarti bahwa data untuk entitas tersebut tidak berhasil dimuat.
- **Sumber**: jenis sumber data yang menyerap entitas
- **Dibuat oleh**: Nama orang yang membuat entitas
- **Dibuat**: tanggal dan waktu pembuatan entitas
- **Diperbarui:** Nama orang yang memperbarui entitas
- **Status:** Detail tentang pembaruan terakhir entitas

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Jelajahi data entitas tertentu

Pilih entitas untuk menjelajahi bidang dan rekaman yang berbeda yang tercakup dalam entitas tersebut.

> [!div class="mx-imgBorder"]
> ![Pilih entitas.](media/data-manager-entities-data.png "Pilih satu entitas")

- Tab **Data** menampilkan rincian daftar tabel tentang rekaman individual entitas.

> [!div class="mx-imgBorder"]
> ![Tabel bidang.](media/data-manager-entities-fields.PNG "Tabel bidang")

- Tab **Atribut** dipilih secara default dan menampilkan tabel untuk meninjau rincian entitas yang dipilih, seperti nama bidang, jenis data, dan jenis. Kolom **jenis** menunjukkan jenis terkait Common Data Model, yang baik yang diidentifikasi secara otomatis oleh sistem, atau yang [dipetakan secara manual](map-entities.md) oleh pengguna. Jenis ini adalah jenis semantik yang dapat berbeda dari jenis data atribut. Misalnya, bidang *email* di bawah ini memiliki jenis data *teks* namun jenis Common Data Model (semantik)-nya mungkin *email* atau *EmailAddress*.

> [!NOTE]
> Kedua tabel hanya menampilkan sampel data entitas. Untuk melihat himpunan data lengkap, buka halaman **sumber data**, pilih entitas, pilih **Edit**, lalu lihat data entitas ini dengan editor Power Query seperti dijelaskan dalam [sumber data](data-sources.md).

Untuk mempelajari lebih lanjut tentang data yang terserap di entitas, kolom **ringkasan** memberi Anda beberapa karakteristik penting data, seperti null, nilai yang tidak ada, nilai unik, jumlah, dan distribusi, sebagaimana berlaku untuk data Anda.

Pilih ikon diagram untuk melihat ringkasan data.

> [!div class="mx-imgBorder"]
> ![Simbol ringkasan.](media/data-manager-entities-summary.png "Tabel Ringkasan Data")

## <a name="entity-specific-information"></a>Informasi spesifik Entitas

Bagian berikut ini menyediakan informasi tentang beberapa entitas yang dibuat sistem.

### <a name="corrupted-data-sources"></a>Sumber data yang rusak

Bidang dari sumber data yang diserap dapat berisi data yang rusak. Rekaman dengan bidang yang rusak diekspos dalam entitas yang dibuat sistem. Mengetahui tentang rekaman yang rusak membantu Anda mengidentifikasi data mana yang akan ditinjau dan diperbarui pada sistem sumber. Setelah penyegaran berikutnya dari sumber data, rekaman yang dikoreksi diserap ke Customer Insights dan diteruskan ke proses hilir. 

Misalnya, kolom 'ulang tahun' memiliki himpunan tipe data sebagai 'tanggal'. Rekaman pelanggan memasukkan ulang tahun mereka sebagai '01/01/19777'. Sistem akan menandai rekaman ini sebagai rusak. Seseorang sekarang dapat mengubah ulang tahun dalam sistem sumber menjadi '1977'. Setelah refresh otomatis sumber data, bidang sekarang memiliki format yang valid dan rekaman akan dihapus dari entitas yang rusak. 

Buka **Data** > **Entitas** dan cari entitas yang rusak di bagian **Sistem**. Penamaan skema entitas yang rusak: 'DataSourceName_EntityName_corrupt'.

Customer Insights masih memproses rekaman yang rusak. Namun, mereka dapat menyebabkan masalah saat bekerja dengan data terpadu.

Pemeriksaan berikut ini berjalan pada data yang diserap untuk mengekspos rekaman yang rusak: 

- Nilai bidang tidak cocok dengan tipe data kolomnya.
- Bidang berisi karakter yang menyebabkan kolom tidak cocok dengan skema yang diharapkan. Misalnya: kutipan yang salah diformat, tanda kutip yang tidak di-escape, atau karakter baris baru.
- Jika ada kolom datetime/date/datetimeoffset, formatnya perlu ditentukan dalam model jika tidak mengikuti format ISO standar.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
