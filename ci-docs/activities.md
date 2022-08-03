---
title: Aktivitas pelanggan
description: Tentukan aktivitas pelanggan dan lihat di timeline pada profil pelanggan.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188143"
---
# <a name="customer-activities"></a>Aktivitas pelanggan

Aktivitas pelanggan adalah tindakan atau peristiwa yang dilakukan oleh pelanggan. Misalnya, transaksi, durasi panggilan dukungan, ulasan situs web, pembelian, atau pengembalian. Kegiatan ini terdapat dalam satu atau beberapa sumber data. Dengan Customers Insights, gabungkan aktivitas pelanggan Anda dari sumber [data ini](data-sources.md) dan kaitkan dengan profil pelanggan. Aktivitas ini muncul secara kronologis dalam garis waktu di profil pelanggan. Sertakan garis waktu di aplikasi Dynamics 365 dengan [solusi add-in](customer-card-add-in.md) Kartu Pelanggan.

## <a name="define-an-activity"></a>Menentukan Aktivitas

Entitas harus memiliki setidaknya satu atribut jenis **Tanggal** untuk disertakan dalam linimasa pelanggan. Kontrol **Tambah aktivitas** dinonaktifkan jika tidak ada entitas yang ditemukan.

1. **Buka Aktivitas** > **Data**.

1. Pilih **Tambahkan aktivitas** untuk memulai pengalaman terpandu.

1. **Dalam langkah Data** aktivitas, masukkan informasi berikut:

   - **Nama aktivitas**: Nama untuk aktivitas Anda.
   - **Entitas aktivitas**: Entitas yang mencakup data transaksional atau aktivitas.
   - **Kunci** utama: Bidang yang secara unik mengidentifikasi rekaman. Ini tidak boleh berisi nilai duplikat, nilai kosong, atau nilai yang tidak ada.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Siapkan data aktivitas dengan nama, entitas, dan kunci utama.":::

1. Pilih **Selanjutnya**.

1. **Di langkah Hubungan**, pilih **Tambahkan hubungan** untuk menyambungkan data aktivitas Anda ke catatan pelanggan yang sesuai. Langkah ini memvisualisasikan hubungan antar entitas.  

   - **Kunci asing dari entitas**: Bidang di entitas aktivitas Anda yang akan digunakan untuk membangun hubungan dengan entitas lain.
   - **Untuk nama** entitas: Entitas pelanggan sumber yang sesuai dengan mana entitas aktivitas Anda akan berada dalam hubungannya. Anda hanya dapat berhubungan dengan entitas pelanggan sumber yang digunakan dalam proses penyatuan data.
   - **Nama hubungan**: Nama yang mengidentifikasi hubungan antar entitas. Jika hubungan antara entitas aktivitas ini dan entitas pelanggan sumber yang dipilih sudah ada, nama hubungannya adalah baca-saja.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Tentukan relasi entitas.":::

   > [!TIP]
   > Di lingkungan B to B, Anda dapat memilih antara entitas akun dan entitas lain. Jika Anda memilih entitas akun, jalur relasi akan secara otomatis diatur. Untuk entitas lain, Anda harus menentukan jalur relasi pada satu atau beberapa entitas menengah hingga mencapai entitas akun.

1. Pilih **Terapkan** untuk membuat hubungan.

1. Pilih **Selanjutnya**.

1. Dalam langkah **Penyatuan aktivitas**, pilih peristiwa aktivitas dan waktu mulai aktivitas Anda.
   - **Bidang yang diperlukan**
      - **Aktivitas peristiwa**: Bidang yang menjadi ajang aktivitas ini.
      - **Cap waktu**: Bidang yang mewakili waktu mulai aktivitas Anda.

   - **Bidang Opsional**
      - **Detail tambahan**: Bidang dengan informasi yang relevan untuk kegiatan ini.
      - **Ikon**: Ikon yang paling mewakili jenis aktivitas ini.
      - **Alamat web**: Bidang yang berisi URL dengan informasi tentang aktivitas ini. Misalnya, sistem transaksional yang menjadi sumber aktivitas ini. URL ini dapat berupa bidang apa pun dari sumber data, atau dapat dibangun sebagai bidang baru menggunakan Power Query transformasi. Data URL akan disimpan di entitas *Aktivitas Terpadu*, yang dapat dikonsumsi di hilir menggunakan [API](apis.md).

   - **Tampilkan di kronologi**
      - Pilih apakah Anda ingin menampilkan aktivitas ini di tampilan timeline pada profil pelanggan Anda. Pilih **Ya** untuk menampilkan aktivitas di timeline atau **Tidak** untuk menyembunyikannya.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Tentukan data aktivitas pelanggan dalam entitas Aktivitas Terpadu.":::

1. Pilih **Berikutnya** untuk memilih jenis aktivitas, atau pilih **Selesai dan tinjau** untuk menyimpan aktivitas dengan jenis aktivitas yang diatur ke **Lainnya**.

1. Dalam langkah **Jenis Aktivitas**, pilih jenis aktivitas dan pilih secara opsional jika Anda ingin memetakan beberapa jenis aktivitas untuk digunakan di area lain dari Customer Insights. Saat ini, *jenis aktivitas Umpan Balik* *,* Loyalitas *, SalesOrder*, *SalesOrderLine*, dan *Langganan* mendukung semantik setelah setuju untuk memetakan bidang. Jika jenis aktivitas tidak relevan untuk aktivitas baru, Anda dapat memilih *Lainnya* atau *buat yang baru* untuk jenis aktivitas kustom.

1. Pilih **Selanjutnya**.

1. Di langkah **Tinjau**, verifikasi pilihan Anda. Kembali ke langkah-langkah sebelumnya dan perbarui informasi jika perlu.

1. Pilih **Simpan aktivitas** untuk menerapkan perubahan Anda dan pilih **Selesai** untuk kembali ke **Data** > **Aktivitas**. Aktivitas yang dibuat ditampilkan.

1. Setelah membuat semua aktivitas Anda, pilih **Jalankan** untuk memprosesnya.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Mengelola aktivitas yang ada

Buka **Aktivitas** > **Data** untuk melihat aktivitas tersimpan Anda, entitas sumbernya, jenis aktivitas, dan jika aktivitas tersebut disertakan dalam linimasa pelanggan. Anda bisa mengurutkan daftar aktivitas menurut kolom mana pun atau menggunakan kotak pencarian untuk menemukan aktivitas yang ingin Anda kelola.

Pilih aktivitas untuk melihat tindakan yang tersedia.

- **Edit** aktivitas untuk mengubah konfigurasinya. Konfigurasi terbuka pada langkah peninjauan. Setelah mengubah konfigurasi, pilih **Simpan aktivitas** lalu pilih **Jalankan** untuk memproses perubahan.
- **Ganti nama** aktivitas. Pilih **Simpan** untuk menerapkan perubahan.
- **Hapus** aktivitas. Untuk menghapus lebih dari satu aktivitas sekaligus, pilih aktivitas lalu **Hapus**. Konfirmasikan Penghapusan.

## <a name="view-activity-timelines-on-customer-profiles"></a>Melihat timeline aktivitas di profil pelanggan

1. Jika Anda memilih **Tampilkan di linimasa** aktivitas dalam konfigurasi aktivitas, buka **Pelanggan** dan pilih profil pelanggan untuk melihat aktivitas pelanggan di **bagian Linimasa** aktivitas.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Melihat aktivitas terkonfigurasi di Profil Pelanggan.":::

1. Untuk memfilter aktivitas di linimasa aktivitas:

   - Pilih satu atau beberapa ikon aktivitas untuk mempersempit hasil Anda untuk menyertakan jenis yang dipilih saja.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Memfilter aktivitas berdasarkan jenis menggunakan ikon.":::

   - Pilih **Filter** untuk membuka panel filter untuk mengonfigurasi filter garis waktu Anda. Filter menurut *ActivityType* dan/atau *Date*. Pilih **Terapkan**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Gunakan panel filter untuk mengkonfigurasi kondisi filter.":::

1. Untuk menghapus filter, pilih **Hapus filter** atau pilih **Filter** dan kosongkan kotak centang filter.

> [!NOTE]
> Filter aktivitas akan dihapus bila Anda meninggalkan profil pelanggan. Anda harus menerapkannya setiap kali Anda membuka profil pelanggan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
