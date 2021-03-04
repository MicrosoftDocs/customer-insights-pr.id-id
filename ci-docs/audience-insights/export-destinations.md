---
title: Destinasi ekspor
description: Ekspor data dan Kelola tujuan ekspor.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477137"
---
# <a name="export-destinations-preview-overview"></a>Ikhtisar destinasi ekspor (pratinjau)

Halaman **tujuan ekspor** menampilkan semua lokasi yang telah Anda konfigurasikan untuk mengekspor data. Anda juga dapat menambahkan tujuan baru untuk ekspor. Selain itu, ia menampilkan pilihan ekspor yang tersedia saat ini. Dapatkan ikhtisar ringkas, deskripsi, dan cari tahu apa yang dapat Anda lakukan dengan setiap pilihan Ekstensibilitas. Ekspor profil terpadu, langkah, dan segmen ke aplikasi yang didukung dan relevan untuk bisnis Anda.

Buka **Admin** > **tujuan ekspor** untuk menemukan pilihan Ekstensibilitas berikut:

- [Add-in Kartu Pelanggan Dynamics 365](customer-card-add-in.md)
- [Konektor manajer iklan Facebook](export-facebook.md)
- [Konektor Power Automate](export-power-automate.md)
- [Konektor Power Apps](export-power-apps.md)
- [Konektor Power BI](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Penyimpanan Blob Azure](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [Konektor LiveRamp&reg;](export-liveramp.md)
- [Bot untuk Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [API Customer Insights](apis.md)

## <a name="add-a-new-export-destination"></a>Menambahkan tujuan ekspor baru

Untuk menambahkan tujuan ekspor, Anda memiliki [izin administrator](permissions.md). Jika Anda mengekspor ke layanan Microsoft, kami menganggap kedua layanan tersebut berada di organisasi yang sama.

1. Buka **Admin** > **Tujuan ekspor**.

1. Beralih ke **tab tujuan ekspor saya**.

1. Pilih **Tambah tujuan** untuk membuat tujuan ekspor baru.

1. Di **panel Tambah tujuan**, pilih **jenis** tujuan ekspor di drop-down.

1. Berikan rincian yang diperlukan dan pilih **berikutnya** untuk membuat tujuan ekspor.

Anda juga dapat memilih **konfigurasi** di ubin pada tab **temukan**.

## <a name="view-export-destinations"></a>Lihat Tujuan Ekspor

Setelah membuat tujuan ekspor, Anda akan menemukannya dalam tabel di tab **tujuan ekspor saya**. Tabel ini memiliki tiga kolom:

- **Nama tampilan**: nama yang Anda masukkan ketika membuat tujuan.
- **Jenis**: jenis tujuan ekspor yang Anda tetapkan ketika membuat tujuan.
- **Dibuat**: tanggal Anda membuat tujuan.

## <a name="edit-an-export-destination"></a>Edit tujuan ekspor

1. Pilih elipsis vertikal untuk tujuan ekspor yang akan diedit.

   > [!div class="mx-imgBorder"]
   > ![Elipsis vertikal](media/export-destinations-page-ellipsis.png "Elipsis vertikal")

1. Pilih **Edit** dari menu menurun.

1. Ubah nilai yang memerlukan pembaruan dan pilih **Simpan**.

## <a name="export-data-on-demand"></a>Ekspor data sesuai permintaan

Setelah mengkonfigurasi konektor untuk tujuan ekspor, ekspor akan dijalankan dengan setiap [refresh terjadwal](system.md#schedule-tab).

Untuk mengekspor data tanpa menunggu refresh terjadwal, buka tab **tujuan ekspor saya** pada **admin** > **tujuan ekspor**.

> [!div class="mx-imgBorder"]
> ![Elipsis vertikal](media/export-destinations-page-ellipsis.png "Elipsis vertikal")

- Pilih **ekspor** di atas daftar untuk menjalankan ekspor ke semua tujuan ekspor secara bersamaan.
- Pilih elipsis (...) setelah item daftar, lalu pilih pilihan **ekspor** untuk menjalankan ekspor untuk satu tujuan ekspor.

## <a name="remove-an-export-destination"></a>Menghapus tujuan ekspor

Untuk menghapus tujuan ekspor, mulai dari halaman **tujuan ekspor** utama.

1. Pilih elipsis vertikal untuk tujuan ekspor yang akan dihilangkan.

   > [!div class="mx-imgBorder"]
   > ![Elipsis vertikal](media/export-destinations-page-ellipsis.png "Elipsis vertikal")

2. Dari menu dropdown, pilih **hilangkan**.

3. Konfirmasikan penghapusan dengan memilih **Hapus** di layar konfirmasi.


[!INCLUDE[footer-include](../includes/footer-banner.md)]