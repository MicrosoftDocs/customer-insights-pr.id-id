---
title: Perkaya profil pelanggan terpadu
description: Gunakan kemampuan untuk memperkaya data pelanggan Anda.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 3bbe8b829a6698da55d84709dbab6c36aa76792a
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954045"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Pengayaan untuk profil pelanggan (pratinjau)

Gunakan data dari sumber seperti Microsoft dan mitra lainnya untuk memperkaya data pelanggan Anda.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Halaman hub pengayaan.":::

Buka **Pengayaan** > **Data** untuk bekerja dengan opsi pengayaan.  

Anda harus memiliki izin kontributor atau Administrator untuk membuat atau mengedit pengayaan. Untuk informasi lebih lanjut, lihat [izin](permissions.md).

Pada tab **Temukan**, Anda akan menemukan semua pilihan pengayaan yang didukung.

# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

- [Identitas](enrichment-liveramp.md) AbiliTec disediakan oleh LiveRamp AbiliTec
- [Merek](enrichment-microsoft.md) disediakan oleh Microsoft
- [Demografi](enrichment-experian.md) yang disediakan oleh Experian
- [Alamat disempurnakan](enrichment-enhanced-addresses.md) yang disediakan oleh Microsoft
- [Minat](enrichment-microsoft.md) disediakan oleh Microsoft
- [data](enrichment-azure-maps.md) lokasi disediakan oleh Microsoft Azure Maps
- [data lokasi](enrichment-here.md) disediakan oleh HERE Technologies
- [Data](enrichment-SFTP-custom-import.md) kustom SFTP melalui Secure File Transfer Protocol (SFTP)

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

- [Data keterlibatan akun](enrichment-office.md) yang disediakan oleh Microsoft
- [Data perusahaan](enrichment-dnb.md) disediakan oleh Dun & Bradstreet
- [Data perusahaan](enrichment-leadspace.md) yang disediakan oleh Leadspace
- [Alamat disempurnakan](enrichment-enhanced-addresses.md) yang disediakan oleh Microsoft
- [Data](enrichment-enhanced-company-data.md) perusahaan yang disempurnakan yang disediakan oleh Microsoft
- [data](enrichment-azure-maps.md) lokasi disediakan oleh Microsoft Azure Maps
- [data lokasi](enrichment-here.md) disediakan oleh HERE Technologies
- [Data](enrichment-SFTP-custom-import.md) kustom SFTP melalui Secure File Transfer Protocol (SFTP)

---

Pada **tab pengayaan saya**, Anda dapat melihat pengayaan yang telah dikonfigurasi dan mengedit properti mereka. Anda juga dapat membuat [segmen](segments.md) atau [ukuran](measures.md) dari pengayaan.

## <a name="manage-existing-enrichments"></a>Mengelola pengayaan yang ada

Buka tab **Pengayaan saya** untuk melihat semua pengayaan terkonfigurasi. Setiap pengayaan ditunjukkan sebagai baris yang mencakup informasi tambahan tentang pengayaan.

Pilih pengayaan untuk melihat opsi yang tersedia. Anda juga dapat memilih elipsis vertikal (&vellip;) pada item daftar untuk melihat opsi. Jika Anda mengonfigurasi beberapa pengayaan, Anda bisa menggunakan kotak pencarian untuk menemukannya dengan cepat.

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

Entitas yang akan diperkaya ditentukan selama konfigurasi pengayaan, yang memungkinkan Anda hanya memperkaya subkumpulan profil Anda. Misalnya, perkaya data hanya untuk segmen tertentu. Anda dapat mengonfigurasi beberapa pengayaan dengan tipe yang sama dan menggunakan kembali koneksi yang sama. Beberapa pengayaan akan memiliki batasan jumlah pengayaan dengan jenis yang sama yang dapat dibuat. Batas dan penggunaan saat ini dapat dilihat pada setiap ubin pada tab **Temukan** di **halaman Pengayaan**.

## <a name="enrich-data-sources-before-unification"></a>Perkaya sumber data sebelum penyatuan

Anda dapat memperkaya data pelanggan Anda sebelum penyatuan data untuk membantu meningkatkan kualitas kecocokan data. Untuk informasi selengkapnya, lihat [pengayaan](data-sources-enrichment.md) sumber data.

## <a name="run-or-refresh-enrichments"></a>Menjalankan atau menyegarkan pengayaan

1. Untuk memulai proses pengayaan, pilih **Jalankan**. Atau, biarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari penyegaran [terjadwal](system.md#schedule-tab). Waktu pemrosesan tergantung pada ukuran data pelanggan Anda.

1. Secara opsional, [lihat kemajuan proses](#see-the-progress-of-the-enrichment-process) pengayaan.

1. Setelah proses pengayaan selesai, buka **Pengayaan** saya untuk meninjau data profil pelanggan yang baru diperkaya, waktu pembaruan terakhir, dan jumlah profil yang diperkaya.

1. Pilih pengayaan untuk melihat [hasil](#enrichment-results) pengayaan.

### <a name="see-the-progress-of-the-enrichment-process"></a>Lihat kemajuan proses pengayaan

Anda dapat menemukan rincian tentang pemrosesan pengayaan, termasuk statusnya dan kemungkinan masalah saat sedang menyegarkan atau setelah penyegaran selesai. Pahami proses yang terlibat untuk me-refresh pengayaan dan berapa lama waktu yang digunakan untuk menjalankan proses. Status pengayaan didukung untuk Experian, Leadspace, HERE Technologies, Impor SFTP, dan Azure Maps.

1. Buka **Data** > **Pengayaan**.
1. Di tab **Pengayaan** saya, pilih status pengayaan untuk membuka panel samping.
1. Di panel **Rincian progres**, perluas bagian **Pengayaan**.
1. Dalam pengayaan yang ingin Anda lihat kemajuannya, pilih **Lihat rincian**.
1. Di panel **Rincian tugas**, pilih **Tampilkan rincian** untuk melihat proses yang terlibat dalam memperbarui pengayaan dan statusnya.

## <a name="enrichment-results"></a>Hasil pengayaan

Setelah pengayaan selesai dijalankan, tinjau hasil pengayaan.

1. Buka **Data** > **Pengayaan**.
1. Di tab **Pengayaan** saya, pilih pengayaan yang Anda inginkan informasinya.

Semua pengayaan menunjukkan informasi dasar seperti jumlah profil yang diperkaya dan jumlah profil yang diperkaya dari waktu ke waktu. Petak **pratinjau** Pelanggan yang diperkaya menunjukkan sampel entitas pengayaan yang dihasilkan. Untuk melihat tampilan mendetail, pilih **Lihat lainnya** dan pilih tab **Data**.

:::image type="content" source="media/enrichments-results.png" alt-text="Halaman hasil pengayaan.":::

Jika tersedia, **Jumlah pelanggan yang diperkaya oleh lapangan** memberikan penelusuran ke dalam cakupan setiap bidang yang diperkaya.

Beberapa pengayaan juga menunjukkan informasi khusus untuk jenis pengayaan. Untuk informasi selengkapnya, lihat dokumentasi terkait.

[!INCLUDE [footer-include](includes/footer-banner.md)]
