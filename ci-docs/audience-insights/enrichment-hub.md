---
title: Perkaya profil pelanggan terpadu
description: Gunakan kemampuan untuk memperkaya data pelanggan Anda.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667098"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Pengayaan untuk profil pelanggan (pratinjau)

Gunakan data dari sumber seperti Microsoft dan mitra lainnya untuk memperkaya data pelanggan Anda.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Halaman hub pengayaan":::

Di wawasan audiens, buka **Data** > **pengayaan** untuk menangani pilihan pengayaan.    
Anda harus memiliki izin kontributor atau Administrator untuk membuat atau mengedit pengayaan. Untuk informasi lebih lanjut, lihat [izin](permissions.md).

Pada tab **temukan**, Anda akan menemukan pengayaan berikut:

- [Merek](enrichment-microsoft-graph.md) yang disediakan oleh Microsoft Graph
- [Minat](enrichment-microsoft-graph.md) Data disediakan oleh Microsoft Graph
- [Data perusahaan](enrichment-leadspace.md) yang disediakan oleh Leadspace
- [Demografi](enrichment-experian.md) Disediakan oleh Experian
- [data lokasi](enrichment-here.md) disediakan oleh HERE Technologies
- [Data Kustom](enrichment-SFTP-custom-import.md) melalui Secure File Transfer Protocol (SFTP)

Pada **tab pengayaan saya**, Anda dapat melihat pengayaan yang telah dikonfigurasi dan mengedit properti mereka.

## <a name="manage-existing-enrichments"></a>Mengelola pengayaan yang ada

Buka **pengayaan saya** untuk melihat semua pengayaan yang dikonfigurasi. Setiap pengayaan ditunjukkan sebagai baris yang mencakup informasi tambahan tentang pengayaan.

Pilih pengayaan untuk melihat pilihan yang tersedia. Atau, Anda dapat memilih elipsis (...) pada item daftar untuk melihat pilihan.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Pilihan untuk mengelola pengayaan dalam daftar pengayaan":::

- **Lihat** rincian pengayaan dengan jumlah profil pelanggan yang diperkaya.
- **Edit** konfigurasi pengayaan.
- **Jalankan** pengayaan untuk memperbarui profil pelanggan dengan data terbaru.
- **Nonaktifkan** pengayaan yang ada untuk menghentikannya secara otomatis dengan setiap penyegaran terjadwal. Data dari penyegaran yang berhasil terakhir akan terus tersedia. **Aktifkan** pengayaan tidak aktif untuk me-restart penyegaran otomatis dengan setiap penyegaran terjadwal.
- **Hapus** pengayaan.

Anda dapat menjalankan atau menonaktifkan beberapa pengayaan sekaligus dengan memilihnya dalam daftar. Pilihan Lihat dan Edit tidak tersedia sebagai tindakan massal dan hanya berfungsi untuk satu pengayaan setiap kalinya.
