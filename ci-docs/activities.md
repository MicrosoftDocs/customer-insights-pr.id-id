---
title: Aktivitas kontak pelanggan atau bisnis
description: Tentukan aktivitas kontak pelanggan atau bisnis dan lihat dalam garis waktu di profil pelanggan.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
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
- customerInsights
ms.openlocfilehash: bbb8bc30d079273bc935181c628915bb3c02d982
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304109"
---
# <a name="customer-or-business-contact-activities"></a>Aktivitas kontak pelanggan atau bisnis

Aktivitas pelanggan adalah tindakan atau peristiwa yang dilakukan oleh pelanggan atau kontak bisnis. Misalnya, transaksi, durasi panggilan dukungan, ulasan situs web, pembelian, atau pengembalian. Kegiatan ini terdapat dalam satu atau beberapa sumber data. Dengan Customers Insights, gabungkan aktivitas pelanggan Anda dari sumber [data ini](data-sources.md) dan kaitkan dengan profil pelanggan. Aktivitas ini muncul secara kronologis dalam garis waktu di profil pelanggan. Sertakan garis waktu di aplikasi Dynamics 365 dengan [solusi add-in](customer-card-add-in.md) Kartu Pelanggan.

## <a name="define-a-customer-activity"></a>Menentukan aktivitas pelanggan

Entitas harus memiliki setidaknya satu atribut jenis **Tanggal** untuk disertakan dalam linimasa pelanggan. Kontrol **Tambah aktivitas** dinonaktifkan jika tidak ada entitas yang ditemukan.

1. **Buka Aktivitas Data** > **·**.

1. Pilih **Tambahkan aktivitas** untuk memulai pengalaman terpandu.

1. **Dalam langkah Data** aktivitas, masukkan informasi berikut:

   - **Nama aktivitas**: Pilih nama untuk aktivitas Anda.
   - **Entitas aktivitas**: Pilih entitas yang menyertakan data transaksional atau aktivitas.
   - **Kunci utama**: Pilih bidang yang secara unik mengidentifikasi rekaman. Ini tidak boleh berisi nilai duplikat, nilai kosong, atau nilai yang tidak ada.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Siapkan data aktivitas dengan nama, entitas, dan kunci utama.":::

1. Pilih **Selanjutnya**.

1. **Di langkah Hubungan**, pilih **Tambahkan hubungan** untuk menyambungkan data aktivitas Anda ke catatan pelanggan yang sesuai. Langkah ini memvisualisasikan hubungan antar entitas.  

   - **Kunci** asing: Bidang asing di entitas aktivitas Anda yang akan digunakan untuk menjalin hubungan dengan entitas lain.
   - **Untuk nama** entitas: Entitas pelanggan sumber yang sesuai dengan mana entitas aktivitas Anda akan berada dalam hubungannya. Anda hanya dapat berhubungan dengan entitas pelanggan sumber yang digunakan dalam proses penyatuan data.
   - **Nama hubungan**: Jika hubungan antara entitas aktivitas ini dan entitas pelanggan sumber yang dipilih sudah ada, nama hubungan akan berada dalam mode baca-saja. Jika tidak ada relasi tersebut, relasi baru akan dibuat dengan nama yang Anda berikan di kotak ini.

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

## <a name="manage-existing-customer-activities"></a>Mengelola aktivitas pelanggan yang sudah ada

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

> [!NOTE]
> Filter aktivitas akan dihapus bila Anda meninggalkan profil pelanggan. Anda harus menerapkannya setiap kali Anda membuka profil pelanggan.

## <a name="define-a-contact-activity"></a>Menentukan aktivitas kontak

Untuk akun bisnis (B-to-B), gunakan *entitas ContactProfile* untuk menangkap aktivitas kontak. Anda dapat melihat di linimasa aktivitas untuk akun mana yang bertanggung jawab atas setiap aktivitas. Sebagian besar langkah mengikuti konfigurasi pemetaan aktivitas pelanggan.

   > [!NOTE]
   > Untuk menentukan aktivitas tingkat kontak, *entitas ContactProfile* harus dibuat, baik sebagai [profil](data-unification-contacts.md) kontak terpadu atau melalui [pemetaan](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) semantik.
   >
   > Anda harus memiliki atribut **AccountID** dan **ContactID** untuk setiap rekaman dalam data aktivitas Anda.
  
1. **Buka Aktivitas Data** > **·**.

1. Pilih **Tambahkan Aktivitas**.

1. Beri nama aktivitas, pilih entitas aktivitas sumber, dan pilih kunci utama entitas aktivitas.

1. **Pada langkah Relasi**, buat hubungan tidak langsung antara data sumber aktivitas Anda ke akun, menggunakan data kontak Anda sebagai entitas perantara. Untuk informasi selengkapnya, lihat [jalur hubungan langsung dan tidak langsung](relationships.md#relationship-paths).
   - Contoh hubungan untuk aktivitas yang disebut *Pembelian*:
      - **Membeli Data** > **Kontak Data** Aktivitas Sumber pada atribut **ContactID**
      - **Data** > **Akun Data** Kontak pada atribut **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Contoh pengaturan hubungan.":::

1. Setelah menyiapkan Relasi, pilih **Berikutnya** dan selesaikan konfigurasi pemetaan aktivitas Anda. Untuk langkah-langkah terperinci tentang pembuatan aktivitas, lihat [menentukan aktivitas](#define-a-customer-activity) pelanggan.

1. Jalankan pemetaan aktivitas Anda.

1. Aktivitas tingkat kontak Anda sekarang akan terlihat di linimasa pelanggan Anda.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Hasil akhir setelah mengonfigurasi aktivitas kontak":::

## <a name="contact-level-activity-timeline-filtering"></a>Pemfilteran garis waktu aktivitas tingkat kontak

Setelah mengonfigurasi pemetaan aktivitas tingkat kontak dan menjalankannya, linimasa aktivitas untuk pelanggan Anda akan diperbarui. Ini termasuk ID atau nama mereka, tergantung pada konfigurasi ContactProfile *Anda*, untuk aktivitas yang mereka tindak lanjuti. Anda dapat memfilter aktivitas berdasarkan kontak di garis waktu untuk melihat kontak tertentu yang Anda minati. Selain itu, Anda dapat melihat semua aktivitas yang tidak ditetapkan ke kontak tertentu dengan **memilih Aktivitas yang tidak dipetakan ke Kontak**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opsi pemfilteran tersedia untuk aktivitas tingkat Kontak.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
