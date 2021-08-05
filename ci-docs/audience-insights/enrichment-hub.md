---
title: Perkaya profil pelanggan terpadu
description: Gunakan kemampuan untuk memperkaya data pelanggan Anda.
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: d12c0a9dd65d31f9ae8a9cafeafab2767d57893e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555265"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Pengayaan untuk profil pelanggan (pratinjau)

Gunakan data dari sumber seperti Microsoft dan mitra lainnya untuk memperkaya data pelanggan Anda.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Halaman hub pengayaan.":::

Di wawasan audiens, buka **Data** > **pengayaan** untuk menangani pilihan pengayaan.  

Anda harus memiliki izin kontributor atau Administrator untuk membuat atau mengedit pengayaan. Untuk informasi lebih lanjut, lihat [izin](permissions.md).

Pada tab **temukan**, Anda akan menemukan pengayaan berikut:

- [Merek](enrichment-microsoft.md) disediakan oleh Microsoft
- [Minat](enrichment-microsoft.md) disediakan oleh Microsoft
- [Alamat disempurnakan](enrichment-enhanced-addresses.md) yang disediakan oleh Microsoft
- [Data perusahaan](enrichment-leadspace.md) yang disediakan oleh Leadspace
- [Demografi](enrichment-experian.md) yang disediakan oleh Experian
- [data lokasi](enrichment-here.md) disediakan oleh HERE Technologies
- [Data Kustom](enrichment-SFTP-custom-import.md) melalui Secure File Transfer Protocol (SFTP)

Pada **tab pengayaan saya**, Anda dapat melihat pengayaan yang telah dikonfigurasi dan mengedit properti mereka.

## <a name="manage-existing-enrichments"></a>Mengelola pengayaan yang ada

Buka tab **Pengayaan saya** untuk melihat semua pengayaan terkonfigurasi. Setiap pengayaan ditunjukkan sebagai baris yang mencakup informasi tambahan tentang pengayaan.

Pilih pengayaan untuk melihat opsi yang tersedia. Anda juga dapat memilih elipsis (...) pada item daftar untuk melihat opsi. Jika Anda mengonfigurasi beberapa pengayaan, Anda bisa menggunakan kotak pencarian untuk menemukannya dengan cepat.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Pilihan untuk mengelola pengayaan dalam daftar pengayaan.":::

- **Lihat** rincian pengayaan dengan jumlah profil pelanggan yang diperkaya.
- **Edit** konfigurasi pengayaan.
- **Jalankan** pengayaan untuk memperbarui profil pelanggan dengan data terbaru.
- **Nonaktifkan** pengayaan yang ada untuk menghentikannya secara otomatis dengan setiap penyegaran terjadwal. Data dari penyegaran yang berhasil terakhir akan terus tersedia. **Aktifkan** pengayaan tidak aktif untuk me-restart penyegaran otomatis dengan setiap penyegaran terjadwal.
- **Hapus** pengayaan.

Jalankan atau nonaktifkan beberapa pengayaan sekaligus dengan memilihnya dalam daftar. Opsi tampilan dan pengeditan tidak tersedia sebagai tindakan massal. Mereka hanya bekerja untuk satu pengayaan pada satu waktu.

## <a name="enrichments-and-connections"></a>Koneksi dan pengayaan

Pengayaan pihak ketiga dikonfigurasi menggunakan [koneksi](connections.md), yang diatur administrator dengan kredensial dan memberikan persetujuan untuk transfer data. Koneksi dapat digunakan untuk mengonfigurasikan pengayaan oleh administrator dan kontributor.  

## <a name="multiple-enrichments-of-the-same-type"></a>Beberapa pengayaan dengan tipe yang sama

Entitas yang akan diperkaya ditentukan selama konfigurasi pengayaan, yang memungkinkan Anda hanya memperkaya subkumpulan profil Anda. Misalnya, perkaya data hanya untuk segmen tertentu. Anda dapat mengonfigurasi beberapa pengayaan dengan tipe yang sama dan menggunakan kembali koneksi yang sama. Beberapa pengayaan akan memiliki batasan jumlah pengayaan dengan jenis yang sama yang dapat dibuat. Batas dan penggunaan saat ini dapat dilihat pada halaman **Pengayaan**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
