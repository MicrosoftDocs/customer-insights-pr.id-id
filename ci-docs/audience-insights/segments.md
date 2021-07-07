---
title: Segmen di wawasan audiens
description: Ikhtisar tentang segmen dan cara membuat dan mengelolanya.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306261"
---
# <a name="segments-overview"></a>Sekilas tentang segmen

Segmen memungkinkan Anda mengelompokkan pelanggan berdasarkan atribut demografi, transaksional, atau perilaku. Anda dapat menggunakan segmen untuk menargetkan kampanye promosi, aktivitas penjualan, dan tindakan dukungan pelanggan untuk mencapai sasaran bisnis Anda.

Profil pelanggan yang cocok dengan filter definisi segmen disebut sebagai *anggota* segmen. Beberapa [batas Layanan](service-limits.md) berlaku.

## <a name="create-a-new-segment"></a>Buat segmen baru

Tersedia beberapa cara untuk membuat segmen baru: 

- Segmen kompleks dengan pembuat segmen: [Segmen kosong](segment-builder.md#create-a-new-segment)
- Segmen sederhana dengan satu operator: [Segmen cepat](segment-builder.md#quick-segments)
- Cara yang didukung AI untuk menemukan pelanggan serupa: [Pelanggan Serupa](find-similar-customer-segments.md)
- Saran yang didukung AI berdasarkan tindakan atau atribut: [Segmen yang disarankan untuk meningkatkan ukuran](suggested-segments.md)
- Saran berdasarkan aktivitas: [Segmen yang disarankan berdasarkan aktivitas pelanggan](suggested-segments-activity.md)

## <a name="manage-existing-segments"></a>Mengelola segmen yang ada

Buka halaman **Segmen**, untuk melihat semua segmen tersimpan dan mengelolanya.

Setiap segmen diwakili oleh baris yang berisi informasi tambahan tentang segmen.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmen yang dipilih dengan daftar dropdown pilihan dan pilihan yang tersedia.":::

Tindakan berikut tersedia bila Anda memilih segmen:

- **Lihat** rincian segmen, termasuk tren jumlah anggota yang menampilkan pratinjau anggota segmen.
- **Edit** segmen untuk mengubah properti.
- **Membuat duplikat** segmen. Anda dapat langsung memilih untuk mengedit propertinya atau cukup menyimpan duplikat.
- **Refresh** segmen untuk menyertakan data terbaru.
- **Aktifkan** atau **Nonaktifkan** segmen. Segmen memiliki dua kemungkinan status - aktif atau tidak aktif. Status ini berguna saat mengedit segmen. Untuk segmen yang tidak aktif, definisi segmen ada, namun tidak berisi pelanggan. Bila Anda mengaktifkan segmen, status akan berubah dari ' tidak aktif ' menjadi ' aktif ' dan mulai mencari Pelanggan yang cocok dengan definisi segmen. Jika [penyegaran terjadwal](system.md#schedule-tab) dikonfigurasi, segmen yang tidak aktif memiliki **status** yang didaftarkan sebagai **dilewati**, yang menunjukkan bahwa penyegaran bahkan tidak dicoba. Bila segmen aktif diaktifkan, segmen akan diperbarui dan akan disertakan dalam penyegaran terjadwal.
  Atau, Anda dapat menggunakan fungsi **jadwalkan nanti** dalam menu menurun **Aktifkan/Nonaktifkan** untuk menentukan tanggal dan waktu di masa mendatang untuk pengaktifan dan penonaktifan segmen tertentu.
- **Ganti nama** segmen.
- **Unduh** Daftar anggota sebagai File .CSV.
- **Kelola ekspor** untuk melihat segmen terkait ekspor dan mengelolanya. [Pelajari lebih lanjut tentang ekspor.](export-destinations.md)
- **Hapus** segmen.

## <a name="refresh-segments"></a>Refresh Segmen

Anda dapat menyegarkan semua segmen sekaligus dengan memilih **Segarkan semua** pada halaman **segmen** atau Anda dapat menyegarkan satu atau beberapa segmen saat memilih dan memilih **Segarkan** dari pilihan. Atau, Anda dapat mengkonfigurasi refresh berulang pada **Admin** > **sistem** > **jadwal**.

> [!TIP]
> Ada [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies). Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan. Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.

## <a name="export-segments"></a>Ekspor segmen

Anda bisa mengekspor segmen dari halaman segmen atau [halaman ekspor](export-destinations.md). 

1. Buka halaman **Segmen**.

1. Pilih **Tampilkan lainnya [...]** untuk segmen yang ingin diekspor.

1. Pilih **Kelola ekspor** dari daftar menurun tindakan.

1. Halaman **Ekspor (pratinjau) untuk segmen** terbuka. Anda dapat melihat semua ekspor yang dikonfigurasi yang dikelompokkan menurut ekspor yang berisi segmen saat ini atau tidak berisi ekspor tersebut.

   1. Untuk menambahkan segmen yang dipilih ke ekspor, pilih ekspor dalam daftar dan pilih **Tambahkan segmen**.

   1. Untuk membuat ekspor baru dengan segmen yang dipilih, pilih **Tambahkan ekspor**. Untuk informasi selengkapnya tentang membuat ekspor, lihat [Menyiapkan ekspor baru](export-destinations.md#set-up-a-new-export).

1. Pilih **Kembali** untuk kembali ke halaman utama untuk segmen.

## <a name="view-processing-history-and-segment-members"></a>Melihat riwayat pemrosesan dan anggota segmen

Anda dapat melihat data gabungan tentang segmen dengan meninjau detailnya.

Pada halaman **segmen**, pilih segmen yang ingin Anda tinjau.

Bagian atas halaman mencakup diagram tren yang memvisualkan perubahan dalam jumlah anggota. Arahkan kursor ke poin data untuk melihat jumlah anggota pada tanggal tertentu.

Anda dapat memperbarui jangka waktu visualisasi.

> [!div class="mx-imgBorder"]
> ![Rentang Waktu segmen](media/segment-time-range.png "Rentang Waktu segmen")

Bagian bawah berisi daftar anggota segmen.

> [!NOTE]
> Bidang yang muncul di daftar ini didasarkan pada atribut entitas segmen.
>
>Daftar ini adalah pratinjau anggota segmen yang cocok dan menampilkan rekaman 100 pertama segmen Anda sehingga Anda dapat dengan cepat mengevaluasinya dan meninjau definisinya jika diperlukan. Untuk melihat semua rekaman yang cocok, Anda harus [mengekspor segmen](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
