---
title: Perkaya profil pelanggan terpadu
description: Gunakan kemampuan untuk memperkaya data pelanggan Anda.
ms.date: 11/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: e44e973bf7713ed5c31dfb9849419decd4ad1c78
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884220"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Pengayaan untuk profil pelanggan (pratinjau)

Gunakan data dari sumber seperti Microsoft dan mitra lainnya untuk memperkaya data pelanggan Anda.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Halaman hub pengayaan.":::

Di wawasan audiens, buka **Data** > **pengayaan** untuk menangani pilihan pengayaan.  

Anda harus memiliki izin kontributor atau Administrator untuk membuat atau mengedit pengayaan. Untuk informasi lebih lanjut, lihat [izin](permissions.md).

Pada tab **Temukan**, Anda akan menemukan semua pilihan pengayaan yang didukung.

# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

- [Merek](enrichment-microsoft.md) disediakan oleh Microsoft
- [Minat](enrichment-microsoft.md) disediakan oleh Microsoft
- [Alamat disempurnakan](enrichment-enhanced-addresses.md) yang disediakan oleh Microsoft 
- [Demografi](enrichment-experian.md) yang disediakan oleh Experian
- [Data Kustom](enrichment-SFTP-custom-import.md) melalui Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) disediakan oleh Microsoft

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

- [Data perusahaan](enrichment-leadspace.md) yang disediakan oleh Leadspace
- [Alamat disempurnakan](enrichment-enhanced-addresses.md) yang disediakan oleh Microsoft 
- [Data perusahaan yang](enrichment-enhanced-company-data.md) disempurnakan yang disediakan oleh Microsoft
- [data lokasi](enrichment-here.md) disediakan oleh HERE Technologies 
- [Data Kustom](enrichment-SFTP-custom-import.md) melalui Secure File Transfer Protocol (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) disediakan oleh Microsoft
- [Data keterlibatan akun](enrichment-office.md) yang disediakan oleh Microsoft

---

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

Pengayaan pihak ketiga dikonfigurasi menggunakan [koneksi](connections.md), yang diatur administrator dengan kredensial dan memberikan persetujuan untuk transfer data. Sambungan dapat digunakan oleh administrator dan kontributor untuk mengonfigurasikan pengayaan.  

## <a name="multiple-enrichments-of-the-same-type"></a>Beberapa pengayaan dengan tipe yang sama

Entitas yang akan diperkaya ditentukan selama konfigurasi pengayaan, yang memungkinkan Anda hanya memperkaya subkumpulan profil Anda. Misalnya, perkaya data hanya untuk segmen tertentu. Anda dapat mengonfigurasi beberapa pengayaan dengan tipe yang sama dan menggunakan kembali koneksi yang sama. Beberapa pengayaan akan memiliki batasan jumlah pengayaan dengan jenis yang sama yang dapat dibuat. Batas dan penggunaan saat ini dapat dilihat pada halaman **Pengayaan**.

## <a name="see-the-progress-of-the-enrichment-process"></a>Lihat kemajuan proses pengayaan

Anda dapat menemukan rincian tentang pemrosesan pengayaan, termasuk statusnya dan kemungkinan masalah saat sedang menyegarkan atau setelah penyegaran selesai. Pahami proses yang terlibat untuk me-refresh pengayaan dan berapa lama waktu yang digunakan untuk menjalankan proses. Status pengayaan didukung untuk Experian, Leadspace, HERE Technologies, Impor SFTP, dan Azure Maps.

Untuk melihat status pengayaan

1. Buka **Data** > **Pengayaan**. 
1. Pada tab **Pengayaan saya**, pilih status pengayaan untuk membuka panel sisi. 
1. Di panel **Rincian progres**, perluas bagian **Pengayaan**. 
1. Dalam pengayaan yang ingin Anda lihat kemajuannya, pilih **Lihat rincian**. 
1. Di panel **Rincian tugas**, pilih **Tampilkan rincian** untuk melihat proses yang terlibat dalam memperbarui pengayaan dan statusnya. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
