---
title: Pemetaan semantik (pratinjau)
description: Ikhtisar pemetaan semantis dan cara menggunakannya.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183635"
---
# <a name="semantic-mappings-preview"></a>Pemetaan semantik (pratinjau)

Pemetaan semantis memungkinkan Anda memetakan data non-aktivitas ke skema yang telah ditentukan sebelumnya. Skema ini membantu Customer Insights lebih memahami atribut data Anda. Pemetaan semantik dan data yang disediakan memungkinkan wawasan dan fitur baru di Customer Insights. Untuk memetakan data aktivitas Anda ke skema, tinjau dokumentasi [aktivitas](activities.md).

**Pemetaan semantis saat ini diaktifkan untuk lingkungan berdasarkan akun bisnis**. *ContactProfile* adalah satu-satunya jenis pemetaan semantik yang saat ini tersedia di Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Mendefinisikan pemetaan entitas semantis ContactProfile

1. Buka **pemetaan Semantik Data** > **(pratinjau)**.

1. Pilih **Tambahkan pemetaan semantis** untuk memulai pengalaman terpandu.

1. Pada langkah **data Entitas**, atur nilai untuk bidang berikut:

   - **Nama** pemetaan entitas semantik: Nama untuk pemetaan entitas semantik Anda.
   - **Entitas** Sumber: Entitas yang mencakup data kontak.
   - **Kunci** utama: Bidang yang secara unik mengidentifikasi rekaman kontak. Ini tidak boleh berisi nilai duplikat, nilai kosong, atau nilai yang tidak ada.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Atur pemetaan entitas semantis dengan nama, entitas sumber, dan kunci utama.":::

1. Pilih **Selanjutnya**.

1. Pada langkah **Relasi**, konfigurasikan rincian untuk menghubungkan data kontak Anda dengan data akun terkait. Langkah ini memvisualisasikan hubungan antar entitas.  

   Ada dua jenis jalur relasi yang dapat diimplementasikan: **Relasi langsung** dan **Relasi tidak langsung**. Untuk informasi lebih lanjut, buka [jalur relasi langsung dan tidak langsung](relationships.md#relationship-paths).

   1. Pilih **Tambahkan Hubungan** untuk mengonfigurasi hubungan.
   1. Pilih atribut dari entitas sumber Anda yang menghubungkan entitas kontak Anda ke entitas lain.
   1. Pilih entitas untuk menghubungkan entitas kontak Anda. Pilih entitas dari **entitas** Akun atau **bagian Entitas** perantara. Jika Anda memilih entitas perantara, tentukan hubungan kedua untuk terhubung ke entitas akun target Anda.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Pilih entitas Akun atau entitas antara.":::

   1. Beri **Nama relasi**. Jika relasi antara entitas Anda sudah ada, nama relasi adalah hanya baca. Jika tidak ada relasi, relasi baru akan dibuat dengan nama yang Anda berikan.
   1. Pilih **Terapkan** untuk menyelesaikan konfigurasi relasi.

   > [!NOTE]
   > Anda dapat mengkonfigurasikan lebih banyak Relasi antara entitas kontak dan entitas akun lain dengan entitas antara.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisasi berbagai Relasi menghubungkan entitas kontak ke entitas akun.":::

1. Pilih **Selanjutnya**.

1. Di langkah **Atur jenis semantik**, pilih **jenis Semantik**. Saat ini, ada satu **Jenis Semantik** yang disebut *ContactProfile*.

1. Petakan id kontak Anda ke *contactprofile* tipe semantik **Contact ID**. Secara opsional, petakan bidang lain seperti nama depan, nama belakang, jenis kelamin, atau email.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Petakan atribut data kontak Anda ke bidang wajib dan opsional yang disediakan.":::

1. Pilih **Selanjutnya**.

1. **Dalam langkah Tinjau**, tinjau konfigurasi pemetaan semantik. Untuk membuat perubahan, pilih **Edit** untuk bagian terkait.

1. Pilih **Simpan**.

1. Untuk memproses pemetaan semantik, pilih **Jalankan**. Atau pilih **Tutup** untuk menyimpan pemetaan semantik Anda tanpa memprosesnya. Untuk menjalankannya nanti, pilih pemetaan semantik dan pilih **Refresh**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Mengelola pemetaan semantis yang ada

Buka **pemetaan Semantik Data** > **(pratinjau)** untuk melihat pemetaan semantik yang disimpan, entitas sumbernya, jenis semantik, jenis pemetaan, dan statusnya.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Pilihan untuk mengelola pemetaan semantis.":::

Pilih pemetaan semantik untuk melihat tindakan yang tersedia.
- **Edit** konfigurasi saat ini. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.
- **Refresh** pemetaan semantik untuk menyertakan data terbaru. Menyegarkan pemetaan semantis tertentu akan me-refresh semua pemetaan semantis dari jenis yang sama.
- **Ganti nama** pemetaan semantik. Pilih **Simpan**.
- **Hapus** pemetaan semantik. Untuk menghapus lebih dari satu pemetaan semantik sekaligus, pilih pemetaan semantik dan ikon hapus. Klik **Hapus**, untuk mengonfirmasi penghapusan tersebut.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Menggunakan pemetaan entitas semantik ContactProfile untuk membuat aktivitas tingkat kontak

Setelah membuat *pemetaan entitas semantik ContactProfile*, Anda dapat menangkap aktivitas kontak. Ini memungkinkan Anda untuk melihat di linimasa aktivitas untuk akun kontak mana yang bertanggung jawab atas setiap aktivitas. Sebagian besar langkah mengikuti konfigurasi pemetaan aktivitas yang khas.

   > [!NOTE]
   > Agar aktivitas tingkat kontak berfungsi, Anda harus memiliki **atribut AccountID** dan **ContactID** untuk setiap rekaman dalam data aktivitas Anda.

1. [*Tentukan pemetaan* entitas semantik ContactProfile](#define-a-contactprofile-semantic-entity-mapping) dan jalankan pemetaan semantik.

1. **Buka Aktivitas** > **Data**.

1. Pilih **Tambahkan Aktivitas** untuk membuat aktivitas baru.

1. Beri nama aktivitas, pilih entitas aktivitas sumber, dan pilih kunci utama entitas aktivitas.

1. **Pada langkah Relasi**, buat hubungan tidak langsung antara data sumber aktivitas Anda ke akun, menggunakan data kontak Anda sebagai entitas perantara. Untuk informasi selengkapnya, lihat [jalur](relationships.md#relationship-paths) hubungan langsung dan tidak langsung.
   - Contoh hubungan untuk aktivitas yang disebut *Pembelian*:
      - **Membeli Data** > **Kontak Data** Aktivitas Sumber pada atribut **ContactID**
      - **Data** > **Akun Data** Kontak pada atribut **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Contoh pengaturan hubungan.":::

1. Setelah menyiapkan Relasi, pilih **Berikutnya** dan selesaikan konfigurasi pemetaan aktivitas Anda. Untuk langkah-langkah terperinci tentang pembuatan aktivitas, lihat [menentukan aktivitas](activities.md).

1. Jalankan pemetaan aktivitas Anda.

1. Setelah pemetaan aktivitas tingkat kontak berjalan, pilih **Pelanggan**. Aktivitas tingkat kontak ditampilkan di linimasa pelanggan Anda.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Hasil akhir setelah mengonfigurasi aktivitas kontak":::

### <a name="contact-level-activity-timeline-filtering"></a>Pemfilteran garis waktu aktivitas tingkat kontak

Linimasa aktivitas untuk pelanggan Anda mencakup ID atau nama mereka, tergantung pada konfigurasi ContactProfile *Anda*, untuk aktivitas yang mereka tindak lanjuti. Filter aktivitas menurut kontak di garis waktu untuk melihat kontak tertentu yang Anda minati. Untuk menampilkan semua aktivitas yang tidak ditetapkan ke kontak tertentu, pilih **Aktivitas yang tidak dipetakan ke Kontak**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Opsi pemfilteran tersedia untuk aktivitas tingkat Kontak.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
