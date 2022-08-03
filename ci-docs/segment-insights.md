---
title: Wawasan segmen (Pratinjau)
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
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171007"
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

1. Setelah menyelesaikan analisis, temukan rincian tentang wawasan ini di **segmen** > **wawasan (pratinjau)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Rincian wawasan tumpang tindih segmen.":::

1. Pilih wawasan untuk melihat hasil analisis:

   - Jumlah anggota yang tumpang tindih di segmen yang dipilih untuk analisis.
   - Jumlah anggota yang tercakup dalam salah satu segmen namun tidak di segmen lainnya.
   - Jika Anda memilih bidang saat mengkonfigurasi analisis tumpang tindih, Anda akan menemukannya di tab yang sesuai. Anda dapat menggunakan dropdown filter untuk memilih tingkat atribut yang menarik dan tabel di bagian bawah akan menampilkan data yang sesuai.

## <a name="segment-differentiators"></a>Pembeda segmen

Pembeda segmen membantu Anda mengetahui apa yang membedakan segmen dari pelanggan atau segmen lain. Pilih segmen dan sistem mengidentifikasi atribut profil dan pengukuran yang membedakan segmen yang dipilih.

### <a name="run-a-differentiator-analysis"></a>Menjalankan analisis pembeda

1. Buka **segmen**, lalu pilih tab **wawasan (pratinjau)**.

1. Pilih **Baru** dan pilih **opsi Pembeda** di **panel Pilih Jenis** Wawasan.

1. Pilih segmen yang akan dianalisis sebagai **segmen utama,** lalu pilih **berikutnya**.

1. Pilih **semua pelanggan** atau **segmen sekunder** untuk membandingkan segmen utama dengan dan pilih **berikutnya**.

1. Atau, pilih satu atau beberapa bidang menarik untuk memfokuskan analisis pada atribut tertentu dan pilih **berikutnya**.

1. Berikan nama untuk Anda analisis pembeda, nama tampilan opsional, dan deskripsi.

1. Untuk mulai menganalisis, pilih **Simpan**. Analisis pembeda siap ketika status berubah dari Menyegarkan menjadi Berhasil.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Melihat dan mengoptimalkan analisis pembeda

1. Setelah menyelesaikan analisis, buka **Segments** > **Insights (pratinjau)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Rincian wawasan pembeda segmen.":::

1. Pilih wawasan untuk melihat hasil analisis. Analisis pembeda mencakup dua tab. Tab **atribut** berisi daftar atribut profil yang dianggap sebagai pembeda. Tab **Ukuran** mencantumkan pembeda. Setiap tab mencakup rincian berikut:

   - Daftar pembeda peringkat, diurutkan berdasarkan Skor perbedaan.
   - **Skor perbedaan** untuk setiap pembeda. Skor perbedaan menunjukkan tingkat perbedaan atribut antara dua segmen. Semakin tinggi Skor perbedaannya, semakin banyak atribut yang berbeda di antara kedua segmen. Pilih Skor untuk membuka panel **Skor perbedaan** dengan distribusi nilai untuk atribut tersebut.

## <a name="manage-segment-insights"></a>Mengelola wawasan segmen

Buka **Wawasan Segmen** > **(pratinjau)** untuk melihat wawasan segmen Anda dan mengelolanya. Pilih wawasan segmen untuk melihat tindakan yang tersedia.

- **Lihat** analisis wawasan
- **Mengedit** wawasan untuk mengubah propertinya
- **Segarkan** wawasan untuk menjalankan analisis lagi
- **Ganti nama** wawasan
- **Menghapus** wawasan

[!INCLUDE [footer-include](includes/footer-banner.md)]
