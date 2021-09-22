---
title: Tambahkan kode ke situs web Anda
description: Cara menambahkan cuplikan kode aktivitas di situs web Anda.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035098"
---
# <a name="install-the-code-snippet-on-a-website"></a>Instal cuplikan kode di situs web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Artikel ini menjelaskan cara administrator menginstal cuplikan kode di situs web. Anda akan mulai melihat aktivitas di ruang kerja setelah menambahkan skrip ke situs web Anda. Untuk informasi lebih lanjut, lihat [Mengelola lingkungan dan ruang kerja](manage-environments-workspaces.md). Untuk mengambil aktivitas dalam aplikasi perangkat bergerak, lihat [ikhtisar sumber daya pengembang](developer-resources.md).


### <a name="prerequisites"></a>Prasyarat

* Anda harus memiliki izin administrator untuk ruang kerja untuk menyimpan data.
* Situs web atau proyek Anda harus di-host secara online untuk mengirim data aktivitas. Data yang dikirim dari file lokal tidak akan diterima oleh server.


## <a name="add-code-to-your-website"></a>Tambahkan kode ke situs web Anda
1.  Buka **Admin** > **Ruang Kerja**  lalu pilih **Panduan penginstalan**.
1. Pilih **Salin kode** untuk menyalin cuplikan kode. Secara default, tombol serap untuk ruang kerja Anda disematkan dalam cuplikan kode.
:::image type="content" source="media/copy-code.png" alt-text="Cuplikan layar halaman cuplikan kode.":::
3. Tambahkan cuplikan kode yang disalin ke situs web Anda, di dekat <head> tag dan sebelum skrip atau tag CSS lain.
4.  Publikasikan situs web yang diperbarui, lalu tunggu beberapa menit untuk mendapatkan lalu lintas web masuk.
5.  Untuk melihat data, pilih ruang kerja dari pengalih ruang kerja di panel navigasi. Selanjutnya, pilih salah satu laporan di bagian **Temukan**.

## <a name="configuration-options"></a>Pilihan Konfigurasi

Anda dapat mengubah pilihan konfigurasi berikut di cuplikan kode:

- **ingestionKey**: Kunci serap yang digunakan untuk mengirim aktivitas ke ruang kerja Anda. Anda dapat mengubah kunci penyerapan untuk mengirim aktivitas ke ruang kerja yang berbeda. Kunci penyerapan bersifat unik untuk setiap ruang kerja. 
- **autoCapture**: Menentukan apakah tampilan dan interaksi halaman dengan situs web direkam. Ia memiliki dua pilihan:
    - **lihat**: Diatur ke *benar* untuk mengambil tampilan halaman. Tampilan halaman diambil sebagai [aktivitas](glossary.md#event) *melihat* suatu jenis [aktivitas dasar](glossary.md#base-event).
    - **klik**: Diatur ke *benar* untuk menangkap interaksi pengunjung di situs web. Interaksi ditangkap sebagai [aktivitas](glossary.md#event) *Tindakan* suatu jenis [aktivitas dasar](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
