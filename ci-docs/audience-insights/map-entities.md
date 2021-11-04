---
title: Memetakan entitas dan atribut untuk penyatuan data
description: Pilih entitas, atribut, kunci utama, dan jenis semantik untuk memetakan data ke profil pelanggan terpadu.
ms.date: 10/18/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-map
ms.openlocfilehash: 8b84ed1a860e383e4eb3f7499be6d397ba3f1db1
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673267"
---
# <a name="map-entities-and-attributes"></a>Memetakan entitas dan atribut

**Peta** adalah tahap pertama dalam proses penyatuan data wawasan audiens. Pemetaan terdiri dari tiga tahapan:

- *Pilihan entitas*: mengidentifikasi entitas yang dapat dikombinasikan untuk mengarah ke himpunan data dengan informasi lebih lengkap tentang pelanggan Anda.
- *Pilihan atribut*: untuk setiap entitas, Identifikasikan kolom yang akan digabungkan dan direkonsiliasi dalam fase *pencocokan* dan *penggabungan*. Kolom ini disebut *atribut*.
- *Pilihan kunci primer dan jenis semantik*: untuk setiap entitas, Identifikasikan atribut yang ingin Anda definisikan sebagai kunci primer untuk entitas tersebut, dan untuk setiap atribut, Identifikasikan jenis semantik yang paling tepat menggambarkan atribut tersebut.

Untuk informasi lebih lanjut tentang aliran umum penyatuan data, lihat [menyatukan](data-unification.md).

## <a name="select-the-first-entities"></a>Pilih entitas pertama

1. Di wawasan audiens, buka **Data** > **Satukan** > **Peta**.

2. Mulai fase peta dengan memilih **pilih entitas**.

3. Pilih entitas dan atribut yang akan digunakan dalam fase *pencocokan* dan *penggabungan*. Anda dapat memilih atribut yang diperlukan secara terpisah dari entitas atau mencakup semua atribut dari entitas dengan memilih kotak centang **Sertakan semua bidang** di tingkat entitas. Sebaiknya Pilih minimal dua entitas untuk mendapatkan manfaat dari proses penyatuan data.

   > [!div class="mx-imgBorder"]
   > ![Tambah contoh entitas.](media/data-manager-configure-map-add-entities-example.png "Tambah contoh entitas")

   Dalam contoh ini, kami akan menambahkan entitas **ecommercecontacts** dan **loycustomer**. Dengan memilih entitas ini, Anda dapat memperoleh wawasan tentang pelanggan bisnis online mana yang merupakan anggota program loyalitas.
   
   Anda dapat mencari pada kata kunci di semua atribut dan entitas untuk memilih atribut yang diperlukan yang akan dipetakan.
   
     > [!div class="mx-imgBorder"]
   > ![Contoh bidang pencarian.](media/data-manager-configure-map-search-fields-example.png "Contoh bidang pencarian")

4. Pilih **Terapkan** untuk mengonfirmasi pilihan Anda.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Pilih kunci primer dan jenis semantik untuk atribut

Setelah memilih entitas, Halaman **peta** akan berisi entitas yang dipilih untuk peninjauan. Tentukan kunci primer untuk entitas dan identifikasi jenis semantik untuk atribut di entitas.

- **Kunci primer**: Pilih satu atribut sebagai Kunci primer untuk tiap entitas. Agar atribut menjadi kunci primer yang valid, ia seharusnya tidak menyertakan nilai duplikat, nilai yang tidak ada, atau nilai null. Atribut jenis data string, bilangan bulat, dan GUID didukung sebagai primary key dan akan ditampilkan di bidang agar Anda dapat memilih darinya.

- **Jenis semantik atribut**: Kategori atribut Anda, seperti alamat email atau nama. Untuk menggunakan model AI untuk prediksi cerdas dari semantik, menghemat waktu dan meningkatkan akurasi, atur **pemetaan cerdas** ke **aktif**. Pemetaan cerdas menyoroti rekomendasi semantik berbasis AI di bidang **jenis**. Jika Anda mengaturnya ke **NONAKTIF**, Anda akan melihat rekomendasi pemetaan rutin kami. Anda dapat memilih jenis semantik dari daftar pilihan yang tersedia dan menimpa pilihan yang disarankan.

> [!div class="mx-imgBorder"]
> ![jenis atribut dan prediksi semantik.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "jenis atribut dan prediksi semantik")

Menambahkan jenis semantik kustom juga dapat dilakukan. Pilih bidang jenis untuk atribut tersebut, dan ketik nama jenis semantik kustom Anda. Dengan demikian, Anda juga dapat mengubah jenis atribut yang diidentifikasi oleh sistem.

Semua atribut yang memiliki jenis semantik yang secara otomatis teridentifikasi dikelompokkan dalam Bagian **Tinjau bidang yang dipetakan**. Tinjau atribut dan jenis semantik mereka karena akan digunakan untuk menggabungkan entitas Anda dalam langkah gabungan penyatuan data.

Atribut yang tidak secara otomatis dipetakan ke jenis semantik dikelompokkan dalam bagian **Tentukan data di bidang yang tidak dipetakan**. Pilih bidang jenis semantik untuk atribut yang tidak dipetakan, atau masukkan nama jenis atribut kustom Anda.

> [!div class="mx-imgBorder"]
> ![Kunci primer dan jenis atribut.](media/data-manager-configure-map-add-attributes.png "Kunci primer dan jenis atribut")

> [!NOTE]
> Satu bidang harus dipetakan ke jenis semantik Person FullName untuk mengisi nama pelanggan di kartu pelanggan. Jika tidak, kartu pelanggan akan muncul tanpa nama. 

## <a name="add-and-remove-attributes-and-entities"></a>Menambah dan menghapus atribut dan entitas

1. Di **Satukan** > **peta**, pilih **Edit bidang**.

2. Di panel **edit bidang**, Tambah atau Hapus atribut dan entitas. Gunakan pencarian atau gulir untuk mencari dan memilih atribut dan entitas yang diinginkan. Anda tidak dapat menghapus atribut atau entitas jika sudah dicocokkan.

   > [!div class="mx-imgBorder"]
   > ![Tambah atau hapus atribut.](media/configure-data-map-edit.png "Tambah atau hapus atribut")

3. Pilih **Terapkan**.

## <a name="add-images-to-profiles"></a>Menambahkan gambar ke profil

Jika entitas berisi URL untuk gambar atau logo profil yang tersedia secara publik, Anda dapat menambahkannya ke profil pelanggan terpadu.

Pilih entitas dan Cari bidang yang berisi URL ke gambar profil. Di bidang input **jenis**, secara manual masukkan nilai berikut: 
- Untuk orang: Person.ProfileImage
- Untuk organisasi: Organization.LogoImage

Lanjutkan dengan langkah penyatuan dan pastikan atribut yang berisi URL gambar juga ditambahkan di langkah [penggabungan](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Mengatur atribut untuk organisasi

Untuk organisasi (pratinjau), jenis atribut harus dipetakan ke "Organization.Name"
> [!div class="mx-imgBorder"]
> ![Kunci utama dan jenis atribut B-ke-B.](media/configure-data-map-edit-b2b.png "Kunci utama dan jenis atribut B-ke-B")

## <a name="next-step"></a>Langkah berikutnya

Sebagai bagian dari proses penyatuan data, buka halaman **pencocokan**. Kunjungi [**kecocokan**](match-entities.md) untuk mempelajari fase ini.

> [!TIP]
> Lihat video berikut: [memulai: membuat profil pelanggan terpadu](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]