---
title: Segmen dalam Customer Insights
description: Ikhtisar tentang segmen dan cara membuat dan mengelolanya.
ms.date: 05/20/2022
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
ms.openlocfilehash: d616ec8273115203dddb59334a348c66e72fa678
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800746"
---
# <a name="segments-overview"></a>Sekilas tentang segmen

Segmen memungkinkan Anda mengelompokkan pelanggan berdasarkan atribut demografi, transaksional, atau perilaku. Anda dapat menggunakan segmen untuk menargetkan kampanye promosi, aktivitas penjualan, dan tindakan dukungan pelanggan untuk mencapai sasaran bisnis Anda.

Profil pelanggan yang cocok dengan filter definisi segmen disebut sebagai *anggota* segmen. Beberapa [batas Layanan](/dynamics365/customer-insights/service-limits) berlaku.

## <a name="create-a-new-segment"></a>Buat segmen baru

Tersedia beberapa cara untuk membuat segmen baru: 

# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

- Segmen yang kompleks dengan pembuat segmen: [Buat milik kita sendiri](segment-builder.md#create-a-new-segment) 
- Segmen sederhana dengan satu operator: [Segmen cepat](segment-builder.md#quick-segments) 
- Cara yang didukung AI untuk menemukan pelanggan serupa: [Pelanggan Serupa](find-similar-customer-segments.md) 
- Saran yang didukung AI berdasarkan tindakan atau atribut: [Segmen yang disarankan untuk meningkatkan ukuran](suggested-segments.md) 
- Saran berdasarkan aktivitas: [Segmen yang disarankan berdasarkan aktivitas pelanggan](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

- Segmen yang kompleks dengan pembuat segmen: [Buat milik kita sendiri](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Mengelola segmen yang ada

Buka **halaman Segmen** untuk melihat semua segmen yang Anda simpan dan mengelolanya.

Setiap segmen diwakili oleh baris yang berisi informasi tambahan tentang segmen.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmen yang dipilih dengan daftar dropdown pilihan dan pilihan yang tersedia." lightbox="media/segments-selected-segment.png":::

Tindakan berikut tersedia saat Anda memilih segmen:

- **Lihat** rincian segmen, termasuk tren jumlah anggota yang menampilkan pratinjau anggota segmen.
- **Unduh** Daftar anggota sebagai File .CSV.
- **Edit** segmen untuk mengubah properti.
- **Membuat duplikat** segmen. Anda dapat memilih untuk segera mengedit propertinya atau menyimpan duplikatnya.
- **Refresh** segmen untuk menyertakan data terbaru.
- **Aktifkan** atau **Nonaktifkan** segmen. Untuk segmen yang tidak aktif, definisi segmen ada, namun tidak berisi pelanggan. Segmen aktif mencari pelanggan yang cocok dengan definisi segmen. Jika [penyegaran terjadwal](system.md#schedule-tab) dikonfigurasi, segmen yang tidak aktif memiliki **status** yang didaftarkan sebagai **dilewati**, yang menunjukkan bahwa penyegaran bahkan tidak dicoba. Bila segmen aktif diaktifkan, segmen akan diperbarui dan akan disertakan dalam penyegaran terjadwal.
  Atau, Anda dapat menggunakan fungsi **jadwalkan nanti** dalam menu menurun **Aktifkan/Nonaktifkan** untuk menentukan tanggal dan waktu di masa mendatang untuk pengaktifan dan penonaktifan segmen tertentu.
- **[Temukan pelanggan](find-similar-customer-segments.md)** serupa dari segmen tersebut.
- **Ganti nama** segmen.
- **Tag** untuk [mengelola tag](work-with-tags-columns.md#manage-tags) untuk segmen tersebut.
- **Unduh** Daftar anggota sebagai File .CSV.
- **Kelola ekspor** untuk melihat segmen terkait ekspor dan mengelolanya. [Pelajari lebih lanjut tentang ekspor.](export-destinations.md)
- **Hapus** segmen.
- **Kolom** untuk [mengkustomisasi kolom](work-with-tags-columns.md#customize-columns) yang ditampilkan.
- **Filter** untuk [memfilter tag](work-with-tags-columns.md#filter-on-tags).
- **Cari nama** untuk mencari berdasarkan nama segmen.

## <a name="refresh-segments"></a>Refresh Segmen

Anda dapat menyegarkan semua segmen sekaligus dengan memilih **Segarkan semua** pada halaman **segmen** atau Anda dapat menyegarkan satu atau beberapa segmen saat memilih dan memilih **Segarkan** dari pilihan. Atau, Anda dapat mengkonfigurasi refresh berulang pada **Admin** > **sistem** > **jadwal**. Saat refresh berulang dikonfigurasi, aturan berikut berlaku:

- Semua segmen dengan tipe **Dinamis** atau **Ekspansi** akan secara otomatis disegarkan pada irama yang ditetapkan. Setelah refresh selesai, **Status** menunjukkan apakah ada masalah dalam menyegarkan segmen. Yang **Terakhir disegarkan** menunjukkan stempel waktu dari penyegaran terakhir yang berhasil. Jika terjadi kesalahan, pilih kesalahan untuk melihat detail tentang apa yang terjadi.
- Segmen dengan tipe **Statis** *tidak* akan disegarkan secara otomatis. Yang **Terakhir disegarkan** menunjukkan stempel waktu terakhir kali segmen statis dijalankan atau disegarkan secara manual.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Ekspor segmen

Anda bisa mengekspor segmen dari halaman segmen atau [halaman ekspor](export-destinations.md). 

1. Buka halaman **Segmen**.

1. Pilih elipsis vertikal (&vellip;) untuk segmen yang ingin Anda ekspor.

1. Pilih **Kelola ekspor** dari daftar menurun tindakan.

1. Halaman **Ekspor (pratinjau) untuk segmen** terbuka. Anda dapat melihat semua ekspor terkonfigurasi yang dikelompokkan berdasarkan segmen saat ini atau tidak.

   1. Untuk menambahkan segmen yang dipilih ke ekspor, **Edit** ekspor masing-masing untuk memilih segmen terkait, lalu simpan. Di lingkungan untuk masing-masing pelanggan, Anda dapat memilih ekspor dalam daftar dan memilih **Tambahkan segmen** untuk mencapai hasil yang sama.

   1. Untuk membuat ekspor baru dengan segmen yang dipilih, pilih **Tambahkan ekspor**. Untuk informasi selengkapnya tentang membuat ekspor, lihat [Menyiapkan ekspor baru](export-destinations.md#set-up-a-new-export).

1. Pilih **Kembali** untuk kembali ke halaman utama untuk segmen.

## <a name="track-usage-of-a-segment"></a>Melacak penggunaan segmen

Jika Anda menggunakan segmen dalam aplikasi, yang didasarkan pada organisasi yang sama Microsoft Dataverse yang terhubung dengan Customer Insights, Anda dapat melacak penggunaan segmen. Untuk [segmen Customer Insights yang digunakan dalam perjalanan pelanggan Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), sistem memberi tahu Anda tentang penggunaan segmen tersebut.

Saat mengedit segmen yang sedang digunakan dalam lingkungan Customer Insights, atau dalam perjalanan pelanggan di Pemasaran, banner di [pembuat](segment-builder.md) segmen memberi tahu Anda tentang dependensi tersebut. Anda dapat memeriksa detail dependensi langsung dari banner atau dengan **memilih Penggunaan** di pembuat segmen.

Panel **Penggunaan** segmen menampilkan detail tentang penggunaan segmen ini di Dataverse aplikasi berbasis-berbasis. Untuk segmen yang digunakan dalam perjalanan pelanggan, Anda akan menemukan tautan untuk memeriksa perjalanan di Pemasaran tempat segmen ini digunakan. Jika anda memiliki izin untuk mengakses aplikasi Marketing, anda dapat mengakses detail selengkapnya di sana.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Panel samping dengan detail penggunaan segmen di pembuat segmen.":::

Sistem memberi tahu Anda tentang penggunaan segmen yang dilacak saat Anda mencoba menghapusnya. Jika segmen yang akan Anda hapus digunakan dalam perjalanan pelanggan di Pemasaran, perjalanan tersebut akan berhenti untuk semua pengguna di segmen tersebut. Jika perjalanan adalah bagian dari kampanye pemasaran, penghapusan akan memengaruhi kampanye itu sendiri. Namun, Anda masih dapat menghapus segmen meskipun ada peringatan.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Kotak dialog untuk mengonfirmasi penghapusan segmen saat segmen digunakan dalam Dataverse aplikasi.":::

### <a name="supported-apps"></a>Aplikasi yang didukung

Penggunaan saat ini dilacak di aplikasi berbasis berikut Dataverse:

- [Perjalanan pelanggan di Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="view-processing-history-and-segment-members"></a>Melihat riwayat pemrosesan dan anggota segmen

Anda dapat melihat data gabungan tentang segmen dengan meninjau detailnya.

Pada halaman **segmen**, pilih segmen yang ingin Anda tinjau.

Bagian atas halaman mencakup diagram tren yang memvisualkan perubahan dalam jumlah anggota. Arahkan kursor ke poin data untuk melihat jumlah anggota pada tanggal tertentu.

Anda dapat memperbarui jangka waktu visualisasi.

> [!div class="mx-imgBorder"]
> ![Rentang Waktu segmen.](media/segment-time-range.png "Rentang Waktu segmen")

Bagian bawah berisi daftar anggota segmen.

> [!NOTE]
> Bidang yang muncul di daftar ini didasarkan pada atribut entitas segmen.
>
>Daftar ini adalah pratinjau anggota segmen yang cocok dan menampilkan rekaman 100 pertama segmen Anda sehingga Anda dapat dengan cepat mengevaluasinya dan meninjau definisinya jika diperlukan. Untuk melihat semua rekaman yang cocok, Anda harus [mengekspor segmen](export-destinations.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
