---
title: Wawasan segmen untuk segmen yang ada
description: Dapatkan wawasan tentang segmen yang ada untuk melihat perbedaan dan kesamaan.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 526b593ba9b038de3d3c27f6a7683ca76b3f2319
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642580"
---
# <a name="segment-insights-preview"></a>Wawasan segmen (Pratinjau)

Temukan informasi dan wawasan tambahan seputar segmen yang ada. Cari tahu apa yang membedakan dua segmen atau kesamaan.

## <a name="segment-overlap"></a>Tumpang Tindih Segmen

Analisis tumpang tindih segmen menunjukkan berapa banyak dan pelanggan mana yang memiliki kesamaan untuk dua atau beberapa segmen. Misalnya, cara segmen pelanggan sering tumpang tindih dengan segmen yang berisi Pelanggan yang puas dengan layanan atau produk Anda.
Anda juga dapat menganalisis bagaimana perubahan tumpang tindih untuk atribut tertentu.

### <a name="run-an-overlap-analysis"></a>Menjalankan analisis tumpang tindih

1. Buka **segmen**, lalu pilih tab **wawasan (pratinjau)**.

1. Pilih **baru**, lalu pilih pilihan **tumpang tindih** di panel **Pilih jenis wawasan**.

1. Pilih segmen minat dan pilih **berikutnya**.

1. Atau, pilih satu atau beberapa bidang yang diinginkan untuk menganalisis tumpang tindih untuk setiap nilai bidang yang mungkin dan pilih **berikutnya**.

1. Berikan nama untuk analisis tumpang tindih, nama tampilan opsional, dan deskripsi.

1. Untuk mulai menganalisis, pilih **Simpan**. Analisis tumpang tindih siap saat status berubah dari penyegaran menjadi berhasil.

### <a name="view-and-optimize-an-overlap-analysis"></a>Melihat dan mengoptimalkan analisis tumpang tindih

Setelah menyelesaikan analisis, temukan rincian tentang wawasan ini di **segmen** > **wawasan (pratinjau)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Rincian wawasan tumpang tindih segmen.":::

Pilih wawasan untuk melihat hasil analisis:

- Jumlah anggota yang tumpang tindih di segmen yang dipilih untuk analisis.
- Jumlah anggota yang tercakup dalam salah satu segmen namun tidak di segmen lainnya.
- Jika Anda memilih bidang saat mengkonfigurasi analisis tumpang tindih, Anda akan menemukannya di tab yang sesuai. Anda dapat menggunakan dropdown filter untuk memilih tingkat atribut yang menarik dan tabel di bagian bawah akan menampilkan data yang sesuai.

## <a name="segment-differentiators"></a>Pembeda segmen

Pembeda segmen membantu Anda mengetahui apa yang membedakan segmen dari pelanggan atau segmen lain. Anda hanya perlu memilih segmen dan sistem akan mengidentifikasi atribut dan ukuran profil yang membedakan segmen yang dipilih.

### <a name="run-a-differentiator-analysis"></a>Menjalankan analisis pembeda

1. Buka **segmen**, lalu pilih tab **wawasan (pratinjau)**.

1. Pilih **baru**, lalu pilih pilihan **tumpang tindih** di panel **Pilih jenis wawasan**.

1. Pilih segmen yang akan dianalisis sebagai **segmen utama,** lalu pilih **berikutnya**.

1. Pilih **semua pelanggan** atau **segmen sekunder** untuk membandingkan segmen utama dengan dan pilih **berikutnya**.

1. Atau, pilih satu atau beberapa bidang menarik untuk memfokuskan analisis pada atribut tertentu dan pilih **berikutnya**.

1. Berikan nama untuk analisis tumpang tindih, nama tampilan opsional, dan deskripsi.

1. Untuk mulai menganalisis, pilih **Simpan**. Analisis tumpang tindih siap saat status berubah dari penyegaran menjadi berhasil.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Melihat dan mengoptimalkan analisis pembeda

Setelah menyelesaikan analisis, temukan rincian tentang wawasan ini di **segmen** > **wawasan (pratinjau)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Rincian wawasan pembeda segmen.":::

Pilih wawasan untuk melihat hasil analisis. Analisis pembeda mencakup dua tab. Tab **atribut** berisi daftar atribut profil yang dianggap sebagai pembeda. Tab **Ukuran** mencantumkan pembeda. Setiap tab mencakup rincian berikut:

- Daftar pembeda peringkat, diurutkan berdasarkan Skor perbedaan.
- **Skor perbedaan** untuk setiap pembeda. Skor perbedaan menunjukkan tingkat perbedaan atribut antara dua segmen. Semakin tinggi Skor perbedaannya, semakin banyak atribut yang berbeda di antara kedua segmen. Pilih Skor untuk membuka panel **Skor perbedaan** dengan distribusi nilai untuk atribut tersebut.

## <a name="manage-segment-insights"></a>Mengelola wawasan segmen

Anda dapat menggunakan pilihan berikut pada wawasan Anda dari bilah perintah:

- **Kembali** untuk mengembalikan daftar wawasan
- **Segarkan** untuk menjalankan analisis lagi
- **Hapus** untuk menghapus wawasan ini


[!INCLUDE [footer-include](includes/footer-banner.md)]
