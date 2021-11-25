---
title: Pemetaan semantik (pratinjau)
description: Ikhtisar pemetaan semantis dan cara menggunakannya.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: f23c622572ff9f967eca07de7898419d1ffc18b0
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "7731947"
---
# <a name="semantic-mappings"></a>Pemetaan semantik

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
