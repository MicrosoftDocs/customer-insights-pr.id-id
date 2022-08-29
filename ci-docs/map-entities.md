---
title: Pilih bidang sumber untuk penyatuan data
description: Langkah pertama dalam proses penyatuan adalah memilih entitas, atribut, kunci utama, dan jenis semantik untuk memetakan data ke profil pelanggan terpadu.
recommendations: false
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304569"
---
# <a name="select-source-fields-for-data-unification"></a>Pilih bidang sumber untuk penyatuan data

Langkah pertama dalam penyatuan adalah memilih entitas dan bidang dalam himpunan data Anda yang ingin Anda satukan. Pilih entitas yang berisi detail terkait pelanggan seperti nama, alamat, nomor telepon, dan email. Anda dapat memilih satu atau beberapa entitas.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Pilih entitas dan bidang

1. **Buka Data** > **Unify**.

   Untuk pelanggan individu (B-to-C), **halaman arahan Unify** menampilkan tampilan **Memulai** pada langkah pertama, **bidang Sumber**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Cuplikan layar halaman arahan satukan untuk pengalaman menjalankan pertama kali untuk masing-masing pelanggan.":::

   Untuk akun bisnis (B-to-B), **halaman landing Unify** menampilkan **akun Unify yang** memperlihatkan **Memulai** pada langkah pertama, **bidang** Sumber. Langkah-langkah **Unify contacts (pratinjau)** bersifat opsional dan menunggu penyelesaian penyatuan akun.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Cuplikan layar halaman arahan satukan untuk pengalaman menjalankan pertama kali untuk akun bisnis.":::

1. Pilih **Mulai**.

1. Pada halaman **Bidang** sumber, pilih **Pilih entitas dan bidang**. Panel **Pilih entitas dan bidang** ditampilkan.

1. Pilih setidaknya satu entitas.

1. Untuk setiap entitas yang dipilih, identifikasi bidang yang ingin Anda gunakan untuk mencocokkan catatan dan bidang pelanggan untuk disertakan dalam profil terpadu. Bidang ini disebut *Atribut*. Anda dapat memilih atribut yang diperlukan satu per satu dari entitas atau menyertakan semua atribut dari entitas dengan memilih kotak centang pada tingkat entitas. Anda dapat mencari pada kata kunci di semua atribut dan entitas untuk memilih atribut yang diperlukan yang akan dipetakan.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Cuplikan layar entitas dan atribut yang dipilih.":::

   Dalam contoh ini, kami menambahkan **entitas eCommerceContacts** dan **loyCustomer**. Dengan memilih entitas ini, Anda dapat memperoleh wawasan tentang pelanggan bisnis online mana yang merupakan anggota program loyalitas.

1. Pilih **Terapkan** untuk mengonfirmasi pilihan Anda. Entitas dan atribut yang dipilih ditampilkan.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Pilih kunci primer dan jenis semantik untuk atribut

   :::image type="content" source="media/m3_select_primary.png" alt-text="Cuplikan layar entitas yang dipilih dengan kunci utama belum dipilih." lightbox="media/m3_select_primary.png":::

Untuk setiap entitas, lakukan langkah-langkah berikut.

1. Pilih kunci **Utama**. Kunci utama adalah atribut yang unik untuk entitas. Agar atribut menjadi kunci primer yang valid, ia seharusnya tidak menyertakan nilai duplikat, nilai yang tidak ada, atau nilai null. Atribut tipe data string, integer, dan GUID didukung sebagai kunci utama.

1. Untuk menggunakan model AI untuk prediksi semantik pintar yang menghemat waktu dan meningkatkan akurasi, pastikan **Pemetaan** cerdas aktif. Pemetaan cerdas memberikan rekomendasi semantik berbasis AI di **bidang Tipe**.

1. Untuk setiap atribut, pilih Tipe **semantik** yang paling menggambarkan atribut tersebut, seperti nama, kota, atau alamat email.

   > [!NOTE]
   > Di B-to-C, satu bidang harus dipetakan ke tipe *semantik Person.FullName* untuk mengisi nama pelanggan di kartu pelanggan. Di B-to-B, nama akun harus dipetakan ke *Organization.Name*. Jika tidak, kartu pelanggan akan muncul tanpa nama.

   1. Untuk mengganti jenis atribut yang diidentifikasi oleh sistem, pilih opsi lain. Jika tipe tidak ada, buat tipe semantik kustom dengan **memilih bidang Tipe** untuk atribut dan masukkan nama tipe semantik kustom Anda.

   1. Untuk menambahkan atribut yang berisi URL ke gambar profil atau logo yang tersedia untuk umum, pilih entitas dan bidang yang berisi URL. **Di bidang Tipe**, masukkan yang berikut ini:
      - Untuk orang: Person.ProfileImage
      - Untuk organisasi: Organization.LogoImage

1. Tinjau atribut tempat tipe semantik diidentifikasi secara otomatis. Atribut ini tercantum di bawah Tinjau bidang **yang dipetakan**. Hanya atribut dengan jenis yang sama yang dapat digabungkan dalam **langkah Satukan bidang** pelanggan. Jenis semantik digunakan untuk secara otomatis menyarankan wawasan. Pastikan jenis yang Anda pilih konsisten di semua entitas yang dipilih.

1. Untuk atribut yang tidak secara otomatis dipetakan ke tipe semantik, pilih bidang tipe semantik, masukkan nama jenis atribut kustom Anda, atau biarkan atribut tersebut tidak dipetakan. Atribut ini tercantum di bawah **Tentukan data di bidang** yang belum dipetakan.

1. Setelah menyelesaikan langkah-langkah untuk setiap entitas, pilih **Simpan bidang** sumber.

1. Pilih **Selanjutnya**.

> [!div class="nextstepaction"]
> [Langkah berikutnya: Menghapus duplikat](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
