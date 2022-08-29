---
title: Sekilas tentang segmen
description: Ikhtisar tentang segmen dan cara membuat dan mengelolanya.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: d4de3a6af6bc7d54305a23e3fbd3cc95d464d352
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304799"
---
# <a name="segments-overview"></a>Sekilas tentang segmen

Segmen memungkinkan Anda mengelompokkan pelanggan berdasarkan atribut demografi, transaksional, atau perilaku. Anda dapat menggunakan segmen untuk menargetkan kampanye promosi, aktivitas penjualan, dan tindakan dukungan pelanggan untuk mencapai sasaran bisnis Anda.

Profil pelanggan atau kontak yang cocok dengan filter definisi segmen disebut sebagai *anggota* segmen. Beberapa [batas Layanan](/dynamics365/customer-insights/service-limits) berlaku.

## <a name="create-a-segment"></a>Buat segmen

Pilih cara membuat segmen berdasarkan target anda audiens.

# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

- Segmen kompleks dengan pembuat segmen: [Bangun segmen Anda sendiri](segment-builder.md)
- Segmen sederhana dengan satu operator: [Segmen cepat](segment-quick.md)
- Cara yang didukung AI untuk menemukan pelanggan serupa: [Pelanggan serupa](find-similar-customer-segments.md)
- Saran yang didukung AI berdasarkan pengukuran atau atribut: [Segmen yang disarankan berdasarkan pengukuran](suggested-segments.md)
- Saran berdasarkan aktivitas: [Segmen yang disarankan berdasarkan aktivitas pelanggan](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

Segmen akun atau segmen kontak (pratinjau) dengan pembuat segmen: [Buat akun Anda sendiri](segment-builder.md)

> [!NOTE]
> Sebagian besar tujuan ekspor memerlukan informasi kontak untuk tujuan Pemasaran. Oleh karena itu, buat segmen kontak untuk digunakan untuk ekspor tersebut.

---

## <a name="manage-existing-segments"></a>Mengelola segmen yang ada

Buka **halaman Segmen** untuk melihat segmen yang Anda buat, status dan statusnya, dan terakhir kali data di-refresh. Anda bisa mengurutkan daftar segmen menurut kolom mana pun atau menggunakan kotak pencarian untuk menemukan segmen yang ingin Anda kelola.

> [!TIP]
> Di lingkungan B-ke-B, **kolom Tipe** audiens mengidentifikasi apakah segmen didasarkan pada akun atau kontak.

Pilih segmen untuk melihat tindakan yang tersedia.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmen yang dipilih dengan daftar dropdown pilihan dan pilihan yang tersedia." lightbox="media/segments-selected-segment.png":::

- [**Lihat**](#view-segment-details) detail segmen, termasuk tren jumlah anggota dan pratinjau anggota segmen.
- **Unduh** Daftar anggota sebagai File .CSV.
- **Edit** segmen untuk mengubah properti.
- **Membuat duplikat** segmen. Anda dapat memilih untuk segera mengedit propertinya atau menyimpan duplikatnya.
- [**Refresh**](#refresh-segments) segmen untuk menyertakan data terbaru.
- **Aktifkan** atau **Nonaktifkan** segmen. Segmen yang tidak aktif tidak akan disegarkan selama [refresh](schedule-refresh.md) terjadwal dan statusnya **terdaftar** sebagai **Dilewati**, menunjukkan bahwa refresh bahkan tidak dicoba. Segmen aktif disegarkan berdasarkan jenisnya: statis atau dinamis.
- **Jadikan statis** atau **Jadikan dinamis** sebagai tipe segmen. Segmen statis harus disegarkan secara manual. Segmen dinamis secara otomatis disegarkan selama penyegaran sistem.
- [**Temukan pelanggan**](find-similar-customer-segments.md) serupa dari segmen tersebut.
- **Ganti nama** segmen.
- **Tag** untuk [mengelola tag](work-with-tags-columns.md#manage-tags) untuk segmen tersebut.
- [**Kelola ekspor**](#export-segments) untuk melihat segmen terkait ekspor dan mengelolanya. [Pelajari lebih lanjut tentang ekspor.](export-destinations.md)
- **Hapus** segmen.
- **Kolom** untuk [mengkustomisasi kolom](work-with-tags-columns.md#customize-columns) yang ditampilkan.
- **Filter** untuk [memfilter tag](work-with-tags-columns.md#filter-on-tags).
- **Cari nama** untuk mencari berdasarkan nama segmen.

## <a name="view-segment-details"></a>Lihat detail segmen

Pada halaman **Segmen**, pilih segmen untuk melihat riwayat pemrosesan dan anggota segmen.

Bagian atas halaman mencakup diagram tren yang memvisualkan perubahan dalam jumlah anggota. Arahkan kursor ke poin data untuk melihat jumlah anggota pada tanggal tertentu. Ubah jangka waktu visualisasi.

:::image type="content" source="media/segment-time-range.png" alt-text="Rentang Waktu segmen.":::

Bagian bawah berisi daftar anggota segmen.

> [!NOTE]
> Bidang yang muncul di daftar ini didasarkan pada atribut entitas segmen.
>
> Daftar ini adalah pratinjau anggota segmen yang cocok dan menampilkan rekaman 100 pertama segmen Anda sehingga Anda dapat dengan cepat mengevaluasinya dan meninjau definisinya jika diperlukan. Untuk melihat semua rekaman yang cocok, pilih **Lihat lainnya** yang membuka [**halaman Entitas**](entities.md) atau [mengekspor segmen](export-destinations.md).

## <a name="refresh-segments"></a>Refresh Segmen

Segmen dapat disegarkan pada jadwal otomatis atau disegarkan secara manual sesuai permintaan. Untuk me-refresh satu atau beberapa segmen secara manual, pilih segmen tersebut dan pilih **Refresh**.

Untuk [menjadwalkan refresh](schedule-refresh.md) otomatis, buka **Jadwal** > **Sistem** > **Admin**. Aturan berikut berlaku:

- Semua segmen dengan tipe **Dinamis** atau **Ekspansi** akan secara otomatis disegarkan pada irama yang ditetapkan. Setelah refresh selesai, **Status** menunjukkan apakah ada masalah dalam menyegarkan segmen. Yang **Terakhir disegarkan** menunjukkan stempel waktu dari penyegaran terakhir yang berhasil. Jika terjadi kesalahan, pilih kesalahan untuk melihat detail tentang apa yang terjadi.
- Segmen dengan tipe **Statis** *tidak* akan disegarkan secara otomatis. Yang **Terakhir disegarkan** menunjukkan stempel waktu terakhir kali segmen statis dijalankan atau disegarkan secara manual.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Ekspor segmen

Ekspor segmen ke aplikasi lain untuk menggunakan data lebih lanjut. Ekspor segmen dari halaman segmen atau [halaman](export-destinations.md) ekspor.

1. Buka halaman **Segmen** dan pilih segmen yang ingin Anda ekspor.

1. Pilih **Kelola ekspor**. Halaman **Ekspor (pratinjau) untuk segmen** terbuka. Lihat semua ekspor yang dikonfigurasi yang dikelompokkan berdasarkan apakah ekspor tersebut berisi segmen saat ini atau tidak.

   1. Untuk menambahkan segmen yang dipilih ke ekspor, **Edit** ekspor masing-masing untuk memilih segmen terkait, lalu simpan. Di lingkungan untuk masing-masing pelanggan, pilih ekspor dalam daftar dan pilih **Tambahkan segmen** untuk mencapai hasil yang sama.

   1. Untuk membuat ekspor baru dengan segmen yang dipilih, pilih **Tambahkan ekspor**. Untuk informasi selengkapnya tentang membuat ekspor, lihat [Menyiapkan ekspor baru](export-destinations.md#set-up-a-new-export).

1. Pilih **Kembali** untuk kembali ke halaman utama untuk segmen.

## <a name="track-usage-of-a-segment"></a>Melacak penggunaan segmen

Jika Anda menggunakan segmen dalam aplikasi yang didasarkan pada organisasi yang sama Microsoft Dataverse yang terhubung dengan Customer Insights, Anda dapat melacak penggunaan segmen. Untuk [segmen Customer Insights yang digunakan dalam perjalanan pelanggan Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), sistem memberi tahu Anda tentang penggunaan segmen tersebut.

Saat mengedit segmen yang sedang digunakan dalam lingkungan Customer Insights, atau dalam perjalanan pelanggan di Pemasaran, banner di [pembuat](segment-builder.md) segmen memberi tahu Anda tentang dependensi tersebut. Periksa detail dependensi langsung dari banner atau dengan **memilih Penggunaan** di pembuat segmen.

Panel **Penggunaan** segmen menampilkan detail tentang penggunaan segmen ini di Dataverse aplikasi berbasis-berbasis. Untuk segmen yang digunakan dalam perjalanan pelanggan, Anda akan menemukan tautan untuk memeriksa perjalanan di Pemasaran tempat segmen ini digunakan. Jika Anda memiliki izin untuk mengakses aplikasi Pemasaran, lihat detail selengkapnya di sana.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Panel samping dengan detail penggunaan segmen di pembuat segmen.":::

Sistem memberi tahu Anda tentang penggunaan segmen yang dilacak saat Anda mencoba menghapusnya. Jika segmen yang akan Anda hapus digunakan dalam perjalanan pelanggan di Pemasaran, perjalanan tersebut akan berhenti untuk semua pengguna di segmen tersebut. Jika perjalanan adalah bagian dari kampanye pemasaran, penghapusan akan memengaruhi kampanye itu sendiri. Namun, Anda masih dapat menghapus segmen meskipun ada peringatan.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Kotak dialog untuk mengonfirmasi penghapusan segmen saat segmen digunakan dalam Dataverse aplikasi.":::

### <a name="supported-apps"></a>Aplikasi yang didukung

Penggunaan saat ini dilacak di aplikasi berbasis berikut Dataverse:

- [Perjalanan pelanggan di Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
