---
title: Pemetaan semantik (pratinjau)
description: Ikhtisar pemetaan semantis dan cara menggunakannya.
ms.date: 12/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: 08b257b97704b219bb3277042516e00deb886a49
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881834"
---
# <a name="semantic-mappings-preview"></a>Pemetaan semantik (pratinjau)

Pemetaan semantis memungkinkan Anda memetakan data non-aktivitas ke skema yang telah ditentukan sebelumnya. Skema ini membantu wawasan audiens untuk lebih memahami atribut data Anda. Pemetaan semantis dan data yang diberikan memungkinkan wawasan dan fitur baru di wawasan audiens. Untuk memetakan data aktivitas Anda ke skema, tinjau dokumentasi [aktivitas](activities.md).

**Pemetaan semantis saat ini diaktifkan untuk lingkungan berdasarkan akun bisnis**. *ContactProfile* adalah satu-satunya jenis pemetaan semantis yang saat ini tersedia wawasan audiens.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Mendefinisikan pemetaan entitas semantis ContactProfile

1. Dalam wawasan audiens, buka **Data** > **pemetaan semantis (pratinjau)**.

1. Pilih **Tambahkan pemetaan semantis** untuk memulai pengalaman terpandu.

1. Pada langkah **data Entitas**, atur nilai untuk bidang berikut:

   - **Nama pemetaan entitas semantis**: Berikan nama untuk pemetaan entitas semantis Anda.
   - **Entitas Sumber**: Pilih entitas yang mencakup data kontak.
   - **Kunci utama**; Pilih bidang yang secara unik mengidentifikasi rekaman kontak. Ini tidak boleh berisi nilai duplikat, nilai kosong, atau nilai yang tidak ada.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Atur pemetaan entitas semantis dengan nama, entitas sumber, dan kunci utama.":::

1. Untuk melanjutkan, klik **Berikutnya**.

1. Pada langkah **Relasi**, konfigurasikan rincian untuk menghubungkan data kontak Anda dengan data akun terkait. Langkah ini memvisualisasikan hubungan antar entitas.  

   Ada dua jenis jalur relasi yang dapat diimplementasikan: **Relasi langsung** dan **Relasi tidak langsung**. Untuk informasi lebih lanjut, buka [jalur relasi langsung dan tidak langsung](relationships.md#relationship-paths).

   1. Pilih **Tambah Relasi** untuk mengkonfigurasi relasi.
   1. Pilih atribut dari entitas sumber Anda yang menghubungkan entitas kontak Anda ke entitas lain.
   1. Pilih entitas untuk menghubungkan entitas kontak Anda. Anda dapat memilih entitas dari **entitas Akun** atau bagian **entitas Antara**. Jika memilih entitas tingkat dua, Anda harus menentukan relasi kedua untuk terhubung ke entitas akun target.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Pilih entitas Akun atau entitas antara.":::

   1. Beri **Nama relasi**. Jika relasi antara entitas Anda sudah ada, nama relasi adalah hanya baca. Jika tidak ada relasi, relasi baru akan dibuat dengan nama yang Anda berikan.
   1. Pilih **Terapkan** untuk menyelesaikan konfigurasi relasi.

   > [!NOTE]
   > Anda dapat mengkonfigurasikan lebih banyak Relasi antara entitas kontak dan entitas akun lain dengan entitas antara.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisasi berbagai Relasi menghubungkan entitas kontak ke entitas akun.":::

1. Pilih **Berikutnya** setelah selesai dengan konfigurasi relasi.

1. Di langkah **Atur jenis semantik**, pilih **jenis Semantik**. Saat ini, ada satu **Jenis Semantik** yang disebut *ContactProfile*.

1. Petakan data Anda ke **jenis sinematik** *ContactProfile* untuk bidang yang ditampilkan.
   - Bidang yang diperlukan: id kontak
   - Bidang Opsional: nama depan, nama belakang, Tanggal Lahir, Jenis Kelamin, Email Utama, dan Telepon Utama

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Petakan atribut data kontak Anda ke bidang wajib dan opsional yang disediakan.":::

1. Untuk melanjutkan, klik **Berikutnya**.

1. Pada langkah **Tinjauan**, lihat konfigurasi pemetaan semantis. Pilih **Edit** untuk bagian yang sesuai untuk membuat perubahan.

1. Pilih **Simpan** untuk menyimpan **pemetaan Semantik** baru.

1. Setelah menyimpan, Anda dapat memilih **Jalankan** proses pemetaan semantis atau Anda dapat memilih **Tutup** untuk menyimpan pemetaan semantis tanpa memprosesnya.

1. Untuk menjalankan pemetaan semantis di titik kemudian, pilih pemetaan semantik dan pilih **Segarkan**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Mengelola pemetaan semantis yang ada

Pada **Data** > **pemetaan Semantik (pratinjau)**, Anda dapat melihat semua pemetaan semantis yang tersimpan, dan mengelolanya. Setiap pemetaan semantis ditunjukkan dengan baris terpisah. Anda akan menemukan rincian tentang entitas sumber, jenis semantis, jenis pemetaan, dan statusnya.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Pilihan untuk mengelola pemetaan semantis.":::

- **Edit**: membuka konfigurasi pengaturan pemetaan semantis di langkah tinjauan. Anda dapat mengubah konfigurasi saat ini. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.

- **Segarkan**: Menyegarkan pemetaan semantis yang dipilih dengan data terbaru dari entitas yang merupakan bagian dari konfigurasinya. Menyegarkan pemetaan semantis tertentu akan me-refresh semua pemetaan semantis dari jenis yang sama.

- **Ganti nama**: membuka dialog yang memungkinkan Anda memasukkan nama lain untuk pemetaan semantis yang dipilih. Pilih **Simpan** untuk menerapkan perubahan.

- **Hapus**: Membuka dialog untuk mengkonfirmasi penghapusan pemetaan semantis yang dipilih. Anda juga dapat menghapus lebih dari satu pemetaan semantis sekaligus dengan memilih pemetaan semantis dan ikon hapus. Klik **Hapus**, untuk mengonfirmasi penghapusan tersebut.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Menggunakan pemetaan entitas semantik ContactProfile untuk membuat aktivitas tingkat kontak

Setelah membuat *pemetaan entitas semantik ContactProfile, Anda dapat menangkap aktivitas* kontak. Ini memungkinkan Anda untuk melihat di timeline aktivitas untuk akun yang kontaknya bertanggung jawab untuk setiap aktivitas. Sebagian besar langkah mengikuti konfigurasi pemetaan aktivitas yang khas.

   > [!NOTE]
   > Agar aktivitas tingkat kontak berfungsi, Anda harus memiliki **atribut AccountID** dan **ContactID untuk setiap catatan dalam data** aktivitas Anda.

1. [Tentukan *pemetaan entitas semantik ContactProfile.*](#define-a-contactprofile-semantic-entity-mapping) Dan menjalankan pemetaan semantik.

1. Di wawasan audiens, buka **Data** > **aktivitas**.

1. Pilih **Tambahkan Aktivitas untuk membuat aktivitas** baru.

1. Beri nama aktivitas, pilih entitas aktivitas sumber, dan pilih kunci utama entitas aktivitas.

1. Dalam **langkah** Relasi, buat hubungan tidak langsung antara data sumber aktivitas Anda ke akun, menggunakan data kontak Anda sebagai entitas perantara. Untuk informasi lebih lanjut, lihat [jalur hubungan langsung dan tidak](relationships.md#relationship-paths) langsung.
   - Contoh hubungan untuk aktivitas yang disebut *Pembelian*:
      - **Membeli Data Kontak Data Aktivitas Sumber** > **pada** atribut **ContactID**
      - **Data Akun Data Kontak** > **pada** atribut **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Contoh pengaturan hubungan.":::

1. Setelah menyiapkan Relasi, pilih **Berikutnya** dan lengkapi konfigurasi pemetaan aktivitas Anda. Untuk langkah-langkah terperinci tentang pembuatan aktivitas, lihat [menentukan](activities.md) aktivitas.

1. Jalankan pemetaan aktivitas Anda.

1. Aktivitas tingkat kontak Anda sekarang akan terlihat di timeline pelanggan Anda.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Hasil akhir setelah mengonfigurasi aktivitas kontak":::

### <a name="contact-level-activity-timeline-filtering"></a>Pemfilteran garis waktu aktivitas tingkat kontak

Setelah mengonfigurasi pemetaan aktivitas tingkat kontak dan menjalankannya, garis waktu aktivitas untuk pelanggan Anda akan diperbarui. Ini termasuk ID atau nama mereka, tergantung pada *konfigurasi ContactProfile* Anda, untuk kegiatan yang mereka tindak lanjuti. Anda dapat memfilter aktivitas dengan kontak di garis waktu untuk melihat kontak spesifik yang Anda minati. Selain itu, Anda dapat melihat semua aktivitas yang tidak ditugaskan ke kontak tertentu dengan memilih **Aktivitas yang tidak dipetakan ke Kontak**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opsi pemfilteran tersedia untuk aktivitas tingkat kontak.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]
