---
title: Pemetaan semantik (pratinjau)
description: Ikhtisar pemetaan semantis dan cara menggunakannya.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303880"
---
# <a name="semantic-mappings-preview"></a>Pemetaan semantik (pratinjau)

> [!NOTE]
> Halaman **pemetaan** Semantik hanya tersedia untuk lingkungan bisnis (B-ke-B) di mana profil kontak telah dibuat menggunakan halaman ini. Anda dapat terus membuat dan mengelola profil kontak individu menggunakan **halaman Pemetaan semantik**. Atau, [satukan data](data-unification-contacts.md) kontak Anda untuk menghapus duplikat, mengidentifikasi kecocokan di seluruh entitas, dan membuat satu profil kontak terpadu. Anda kemudian dapat menggunakan profil kontak terpadu untuk membuat aktivitas tingkat kontak.

Pemetaan semantis memungkinkan Anda memetakan data non-aktivitas ke skema yang telah ditentukan sebelumnya. Skema ini membantu Customer Insights untuk lebih memahami atribut data Anda. Pemetaan semantik dan data yang disediakan memungkinkan wawasan dan fitur baru di Customer Insights. Untuk memetakan data aktivitas Anda ke skema, tinjau dokumentasi [aktivitas](activities.md).

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
