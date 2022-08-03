---
title: Menyatukan bidang pelanggan untuk penyatuan data
description: Gabungkan entitas untuk membuat profil pelanggan terpadu.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 4a19b753e7a5979fe72d7e96bc4452d7795c2d48
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139661"
---
# <a name="unify-customer-fields-for-data-unification"></a>Menyatukan bidang pelanggan untuk penyatuan data

Dalam langkah proses penyatuan ini, pilih dan kecualikan atribut untuk digabungkan dalam entitas profil terpadu Anda. Misalnya, jika tiga entitas memiliki data email, Anda mungkin ingin menyimpan ketiga bidang email terpisah atau menggabungkannya menjadi satu bidang email untuk profil terpadu. Beberapa atribut secara otomatis digabungkan oleh sistem. Anda dapat membuat ID pelanggan yang stabil dan unik serta mengelompokkan profil terkait ke dalam kluster.

:::image type="content" source="media/m3_unify.png" alt-text="Halaman gabungan dalam proses penyatuan data yang menampilkan tabel dengan bidang gabungan yang mendefinisikan profil pelanggan terpadu.":::

## <a name="review-and-update-the-customer-fields"></a>Meninjau dan memperbarui bidang pelanggan

1. Tinjau daftar bidang yang akan disatukan di bawah tab **Bidang** pelanggan dari tabel. Buat perubahan apa pun jika berlaku.

   1. Untuk bidang gabungan apa pun, Anda dapat:
      - [Edit](#edit-a-merged-field)
      - [Ubah nama](#rename-fields)
      - [Pisahkan](#separate-merged-fields)
      - [Kecualikan](#exclude-fields)
      - [Berpindah ke atas atau ke bawah](#change-the-order-of-fields)

   1. Untuk bidang tunggal apa pun, Anda dapat:
      - [Gabungkan bidang](#combine-fields-manually)
      - [Menggabungkan grup bidang](#combine-a-group-of-fields)
      - [Ubah nama](#rename-fields)
      - [Kecualikan](#exclude-fields)
      - [Berpindah ke atas atau ke bawah](#change-the-order-of-fields)

1. Secara opsional, [buat konfigurasi ID pelanggan](#configure-customer-id-generation).

1. Secara opsional, [kelompokkan profil ke dalam rumah tangga atau kluster](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Langkah berikutnya: Meninjau penyatuan](review-unification.md)

### <a name="edit-a-merged-field"></a>Edit bidang gabungan

1. Pilih bidang yang digabungkan dan pilih **Edit**. Panel Gabungkan bidang ditampilkan.

1. Tentukan cara mengombinasikan atau menggabungkan bidang dari salah satu dari tiga pilihan:
    - **Kepentingan**: Mengidentifikasi nilai pemenang berdasarkan peringkat kepentingan yang ditentukan untuk bidang yang berpartisipasi. Ini adalah pilihan penggabungan default. Pilih **Pindahkan ke atas/bawah** untuk menetapkan peringkat nilai penting.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Pilihan nilai penting dalam dialog bidang gabungan.":::

    - **Terbaru**: Mengidentifikasi nilai pemenang berdasarkan yang paling terkini. Memerlukan tanggal atau bidang angka untuk setiap entitas yang berpartisipasi dalam cakupan bidang gabungan untuk menentukan keterkinian.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Pilihan keterkinian dalam dialog bidang gabungan.":::

    - **Paling lama**: Mengidentifikasi nilai pemenang berdasarkan yang paling lama. Memerlukan tanggal atau bidang angka untuk setiap entitas yang berpartisipasi dalam cakupan bidang gabungan untuk menentukan keterkinian.

1. Anda dapat menambahkan bidang lainnya untuk berpartisipasi dalam proses penggabungan.

1. Anda dapat mengganti nama bidang gabungan.

1. Pilih **Selesai** untuk menerapkan perubahan.

### <a name="rename-fields"></a>Mengganti nama bidang

Ubah nama tampilan bidang yang digabungkan atau terpisah. Anda tidak dapat mengubah nama entitas output.

1. Pilih bidang dan pilih **Ganti Nama**.

1. Masukkan nama tampilan baru.

1. Pilih **Selesai**.

### <a name="separate-merged-fields"></a>Pisahkan bidang gabungan

Untuk memisahkan bidang gabungan, cari atribut di tabel. Bidang terpisah ditampilkan sebagai poin data individual di profil pelanggan terpadu.

1. Pilih bidang yang digabungkan dan pilih **Pisahkan bidang**.

1. Konfirmasikan pemisahan.

### <a name="exclude-fields"></a>Mengecualikan bidang

Kecualikan bidang yang digabungkan atau terpisah dari profil pelanggan terpadu. Jika bidang digunakan dalam proses lain, misalnya dalam segmen, hilangkan dari proses ini sebelum mengecualikannya dari profil pelanggan.

1. Pilih bidang dan pilih **Kecualikan**.

1. Konfirmasikan pengecualian.

Untuk melihat daftar semua bidang yang dikecualikan, pilih **Bidang yang** dikecualikan. Jika perlu, Anda dapat membaca bidang yang dikecualikan.

### <a name="change-the-order-of-fields"></a>Ubah urutan bidang

Beberapa entitas berisi rincian lebih banyak daripada entitas lain. Jika entitas mencakup data terbaru tentang bidang, Anda dapat memprioritaskan entitas lain saat menggabungkan nilai.

1. Pilih bidang.
  
1. Pilih **Pindahkan ke atas/ bawah** untuk mengatur urutan atau seret dan lepas di posisi yang diinginkan.

### <a name="combine-fields-manually"></a>Menggabungkan bidang secara manual

Gabungkan bidang yang terpisah untuk membuat atribut gabungan.

1. Pilih **Gabungkan** > **Bidang**. Panel Gabungkan bidang ditampilkan.

1. Tentukan kebijakan pemenang gabungan di dropdown **Gabungkan bidang berdasarkan**.

1. Pilih **Tambahkan bidang** untuk menggabungkan bidang lainnya.

1. Berikan **Nama** dan **nama bidang Output**.

1. Pilih **Selesai** untuk menerapkan perubahan.

### <a name="combine-a-group-of-fields"></a>Menggabungkan grup bidang

Perlakukan sekelompok bidang sebagai satu unit. Misalnya, jika catatan kami berisi bidang Address1, Address2, City, State, dan Zip, kami tidak ingin menggabungkan dalam Address2 catatan yang berbeda, berpikir itu akan membuat data kami lebih lengkap.

1. Pilih **Gabungkan** > **Grup bidang**.

1. Tentukan kebijakan pemenang gabungan di **dropdown Grup peringkat menurut**.

1. Pilih **Tambahkan** dan pilih apakah Anda ingin menambahkan lebih banyak bidang atau grup ke bidang.

1. **Berikan Nama** dan **nama** Output untuk setiap bidang gabungan.

1. **Berikan Nama** untuk grup bidang.

1. Pilih **Selesai** untuk menerapkan perubahan.

## <a name="configure-customer-id-generation"></a>Mengonfigurasi pembuatan ID pelanggan

Tentukan cara menghasilkan nilai ID pelanggan, pengidentifikasi profil pelanggan yang unik. Langkah unify fields dalam proses penyatuan data menghasilkan pengidentifikasi profil pelanggan yang unik. Pengidentifikasi adalah *CustomerId* di *entitas Pelanggan* yang dihasilkan dari proses penyatuan data.

*CustomerId* didasarkan pada hash dari nilai pertama dari kunci utama pemenang non-null. Kunci ini berasal dari entitas yang digunakan dalam penyatuan data dan dipengaruhi oleh urutan kecocokan.Jadi ID pelanggan yang dihasilkan dapat berubah ketika nilai kunci utama berubah di entitas utama dari urutan pencocokan. Nilai kunci utama mungkin tidak selalu mewakili pelanggan yang sama.

Mengkonfigurasi ID pelanggan yang stabil memungkinkan Anda menghindari perilaku tersebut.

1. Pilih tab **Kunci**.

1. Arahkan kursor ke **baris CustomerId** dan pilih **Konfigurasikan**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrol untuk menyesuaikan pembuatan ID.":::

1. Pilih hingga lima bidang yang akan berisi ID pelanggan unik dan lebih stabil. Rekaman yang tidak sesuai dengan konfigurasi Anda akan menggunakan ID yang dikonfigurasi sistem.  

1. Pilih **Selesai**.

## <a name="group-profiles-into-households-or-clusters"></a>Mengelompokkan profil ke rumah tangga atau kluster

Anda dapat menentukan aturan untuk mengelompokkan profil terkait ke dalam kluster. Saat ini ada dua jenis kluster yang tersedia – kluster rumah tangga dan kustom. Sistem secara otomatis memilih rumah tangga dengan aturan yang ditetapkan sebelumnya jika entitas *Pelanggan* berisi bidang semantis *Person.LastName* dan *Location.Address*. Anda juga dapat membuat kluster dengan aturan dan kondisi Anda sendiri, yang mirip dengan [cocokkan aturan](match-entities.md#define-rules-for-match-pairs).

1. Pilih **Kluster** > **Buat Tingkat Lanjut**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kontrol untuk membuat kluster baru.":::

1. Pilih antara **Rumah Tangga** atau kluster **Kustom**. Jika bidang semantis *Person.LastName* dan *Location.Address* ada di entitas *Pelanggan*, rumah tangga akan secara otomatis dipilih.

1. Berikan nama untuk kluster, lalu pilih **Selesai**.

1. Pilih tab **Kluster** untuk menemukan kluster yang Anda buat.

1. Tentukan aturan dan kondisi untuk mendefinisikan kluster Anda.

1. Pilih **Selesai**. Kluster dibuat ketika proses penyatuan selesai. Pengidentifikasi kluster ditambahkan sebagai bidang baru ke *entitas Pelanggan*.

> [!div class="nextstepaction"]
> [Langkah berikutnya: Meninjau penyatuan](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
