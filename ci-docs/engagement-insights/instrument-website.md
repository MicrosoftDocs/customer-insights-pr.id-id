---
title: Tambahkan kode ke situs web Anda
description: Cara menambahkan cuplikan kode untuk menangkap aktivitas Dynamics 365 Customer Insights di situs web Anda.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 99e1c04877993a9cd81912e3d400402aab06a7de
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231026"
---
# <a name="install-the-web-sdk-on-a-website"></a>Menginstal SDK web di situs web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Artikel ini menjelaskan cara administrator menginstal SDK (toolkit pengembangan perangkat lunak web) di situs web. Anda akan mulai melihat aktivitas di ruang kerja segera setelah instrumentasi situs web Anda. Untuk informasi lebih lanjut, lihat [Mengelola lingkungan dan ruang kerja](manage-environments-workspaces.md). Untuk mengambil aktivitas dalam aplikasi perangkat bergerak, lihat [ikhtisar sumber daya pengembang](developer-resources.md).


### <a name="prerequisites"></a>Prasyarat

* Anda harus memiliki izin administrator untuk ruang kerja untuk menyimpan data.
* Situs web atau proyek Anda harus di-host secara online untuk mengirim data aktivitas. Data yang dikirim dari file lokal tidak akan diterima oleh server.


## <a name="add-web-sdk-to-your-website"></a>Tambahkan SDK web ke situs web Anda

Buka **Admin** > **Ruang Kerja**  lalu pilih **Panduan penginstalan**. Ada dua pilihan untuk menginstal SDK web. Yang pertama adalah menggunakan tautan unduhan, dan yang kedua adalah menginstal paket NPM (manajer paket node).

### <a name="option-1-using-the-download-link"></a>Pilihan 1: Menggunakan tautan unduhan

1. Pilih **Salin kode** untuk menyalin cuplikan kode. Secara default, tombol serap untuk ruang kerja Anda disematkan dalam cuplikan kode.
  :::image type="content" source="media/copy-code.png" alt-text="Cuplikan layar halaman cuplikan kode.":::

1. Tambahkan kode yang disalin ke situs web Anda, di dekat <head> tag dan sebelum skrip atau tag CSS lain.
1. Publikasikan situs web yang diperbarui, lalu tunggu beberapa menit untuk mendapatkan lalu lintas web masuk.
1. Untuk melihat data, pilih ruang kerja dari pengalih ruang kerja di panel navigasi. Selanjutnya, pilih salah satu laporan di bagian **Temukan**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Pilihan 2: Menggunakan paket NPM (disarankan untuk Aplikasi web berbasis JavaScript)

1. Buka [halaman web NPM](https://www.npmjs.com/package/engagementinsights-web), lalu ikuti petunjuk untuk menginstal dan mengkonfigurasi paket NPM SDK web.
1. Publikasikan situs web yang diperbarui, lalu tunggu beberapa menit untuk mendapatkan lalu lintas web masuk.
1. Untuk melihat data, pilih ruang kerja dari pengalih ruang kerja di panel navigasi. Selanjutnya, pilih salah satu laporan di bagian **Temukan**.

## <a name="configuration-options"></a>Pilihan Konfigurasi

Anda dapat mengubah pilihan konfigurasi berikut di cuplikan kode:

- **ingestionKey**: Kunci serap yang digunakan untuk mengirim aktivitas ke ruang kerja Anda. Anda dapat mengubah kunci penyerapan untuk mengirim aktivitas ke ruang kerja yang berbeda. Kunci penyerapan bersifat unik untuk setiap ruang kerja.
- **autoCapture**: Menentukan apakah tampilan dan interaksi halaman dengan situs web direkam. Ia memiliki dua pilihan:
    - **lihat**: Diatur ke *benar* untuk mengambil tampilan halaman. Tampilan halaman diambil sebagai [aktivitas](glossary.md#event) *melihat* suatu jenis [aktivitas dasar](glossary.md#base-event).
    - **klik**: Diatur ke *benar* untuk menangkap interaksi pengunjung di situs web. Interaksi ditangkap sebagai [aktivitas](glossary.md#event) *Tindakan* suatu jenis [aktivitas dasar](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
