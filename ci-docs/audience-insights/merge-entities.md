---
title: Gabungkan entitas dalam penyatuan data
description: Gabungkan entitas untuk membuat profil pelanggan terpadu.
ms.date: 09/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b038cd3f5b433fedf918d34bbfaf2261e11c5c17
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494323"
---
# <a name="merge-entities"></a>Gabungkan Entitas

Fase gabungkan adalah fase terakhir dalam proses penyatuan data. Tujuannya adalah merekonsiliasi data yang berkonflik. Contoh data yang berkonflik dapat mencakup nama pelanggan yang berada di dua dataset, namun ditampilkan sedikit berbeda di masing-masing ("Grant Marshall" versus "Grant"), atau format nomor telepon yang berbeda format (617-803-091X versus 617803091X). Penggabungan titik data yang berkonflik dilakukan pada basis atribut demi atribut.

:::image type="content" source="media/merge-fields-page.png" alt-text="Halaman gabungan dalam proses penyatuan data yang menampilkan tabel dengan bidang gabungan yang mendefinisikan profil pelanggan terpadu.":::

Setelah menyelesaikan [fase kecocokan](match-entities.md), Anda memulai fase penggabungan dengan memilih ubin **gabungkan** pada halaman **satukan**.

## <a name="review-system-recommendations"></a>Tinjau rekomendasi sistem

Pada **Data** > **Satukan** > **Gabungkan**, Anda memilih dan mengecualikan atribut untuk digabungkan dalam entitas profil pelanggan terpadu Anda. Profil pelanggan terpadu adalah hasil dari proses penyatuan data. Beberapa atribut secara otomatis digabungkan oleh sistem.

Untuk melihat atribut yang tercakup di salah satu atribut gabungan otomatis Anda, pilih atribut gabungan tersebut di tab **Bidang pelanggan** pada tabel. Atribut yang membentuk atribut gabungan ditampilkan dalam dua baris baru di bawah atribut gabungan.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Memisahkan, mengganti nama, mengecualikan, dan mengedit bidang gabungan

Anda dapat mengubah cara sistem memproses atribut gabungan untuk menghasilkan profil pelanggan terpadu. Pilih **Tampilkan lainnya**, lalu pilih yang akan diubah.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Pilihan di menu dropdown Tampilkan lainnya untuk mengelola atribut gabungan.":::

Untuk informasi lebih lanjut, lihat bagian berikut.

## <a name="separate-merged-fields"></a>Pisahkan bidang gabungan

Untuk memisahkan bidang gabungan, cari atribut di tabel. Bidang terpisah ditampilkan sebagai poin data individual di profil pelanggan terpadu. 

1. Pilih bidang gabungan.
  
1. Pilih **Tampilkan lainnya** dan pilih **Bidang terpisah**.
 
1. Konfirmasikan pemisahan.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.

## <a name="rename-merged-fields"></a>Ganti nama bidang yang digabungkan

Ubah nama tampilan atribut gabungan. Anda tidak dapat mengubah nama entitas output.

1. Pilih bidang gabungan.
  
1. Pilih **Tampilkan lainnya** dan pilih **Ganti nama**.

1. Konfirmasikan perubahan nama tampilan. 

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.

## <a name="exclude-merged-fields"></a>Pisahkan bidang gabungan

Pisahkan atribut dari profil pelanggan terpadu. Jika bidang digunakan dalam proses lain, misalnya dalam segmen, hilangkan dari proses ini sebelum mengecualikannya dari profil pelanggan. 

1. Pilih bidang gabungan.
  
1. Pilih **Tampilkan lainnya** dan pilih **Pisahkan**.

1. Konfirmasikan pengecualian.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan. 

Pada halaman **Gabung**, pilih **Bidang yang dikecualikan** untuk melihat daftar semua bidang yang dipisahkan. Panel ini memungkinkan Anda menambahkan kembali bidang yang dipisahkan.

## <a name="edit-a-merged-field"></a>Edit bidang gabungan

1.  Pilih bidang gabungan.

1.  Pilih **Tampilkan lainnya** dan pilih **Edit**.

1.  Tentukan cara mengombinasikan atau menggabungkan bidang dari salah satu dari tiga pilihan:
    - **Kepentingan**: Mengidentifikasi nilai pemenang berdasarkan peringkat kepentingan yang ditentukan untuk bidang yang berpartisipasi. Ini adalah pilihan penggabungan default. Pilih **Pindahkan ke atas/bawah** untuk menetapkan peringkat nilai penting.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Pilihan nilai penting dalam dialog bidang gabungan."::: 
    - **Terbaru**: Mengidentifikasi nilai pemenang berdasarkan yang paling terkini. Memerlukan tanggal atau bidang angka untuk setiap entitas yang berpartisipasi dalam cakupan bidang gabungan untuk menentukan keterkinian.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Pilihan keterkinian dalam dialog bidang gabungan.":::
    - **Paling lama**: Mengidentifikasi nilai pemenang berdasarkan yang paling lama. Memerlukan tanggal atau bidang angka untuk setiap entitas yang berpartisipasi dalam cakupan bidang gabungan untuk menentukan keterkinian.

1.  Anda dapat menambahkan bidang tambahan untuk berpartisipasi dalam proses penggabungan.

1.  Anda dapat mengganti nama bidang gabungan.

1. Pilih **Selesai** untuk menerapkan perubahan.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan. 

## <a name="manually-combine-fields"></a>Gabungkan bidang secara manual

Tentukan atribut gabungan secara manual. 

1. Pada halaman **Gabung**, pilih **Gabungkan bidang**.

1. Tentukan kebijakan pemenang gabungan di dropdown **Gabungkan bidang berdasarkan**.

1. Pilih bidang untuk ditambahkan. pilih **Tambahkan bidang** untuk mengombinasikan bidang lainnya.

1. Berikan **Nama** dan **nama bidang Output**.

1. Pilih **Selesai** untuk menerapkan perubahan.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan. 

## <a name="change-the-order-of-fields"></a>Ubah urutan bidang

Beberapa entitas berisi rincian lebih banyak daripada entitas lain. Jika entitas mencakup data terbaru tentang bidang, Anda dapat memprioritaskan entitas lain saat menggabungkan nilai.

1. Pilih bidang gabungan.
  
1. Pilih **Tampilkan lainnya** dan pilih **Edit**.

1. Di panel **Gabungkan bidang**, pilih **Pindahkan ke atas/bawah** untuk mengatur urutan atau menarik dan melepasnya dalam posisi yang diinginkan.

1. Konfirmasikan perubahan.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.

## <a name="configure-customer-id-generation"></a>Konfigurasikan pembuatan ID pelanggan 

Setelah mengkonfigurasi penggabungan bidang, Anda dapat menentukan cara membuat nilai CustomerId, pengidentifikasi profil pelanggan unik. Langkah penggabungan dalam proses penyatuan data menghasilkan pengidentifikasi profil pelanggan yang unik. Pengidentifikasi adalah CustomerId dalam entitas *Pelanggan* yang dihasilkan dari proses penyatuan data. 

CustomerId dalam entitas Pelanggan didasarkan pada hash nilai pertama kunci utama pemenang non-nihil. Kunci ini berasal dari entitas yang digunakan dalam fase pencocokan dan penggabungan dan terpengaruh oleh urutan kecocokan. Jadi CustomerID yang dihasilkan dapat berubah ketika nilai utama utama berubah di entitas utama dari urutan kecocokan. Akibatnya, nilai kunci utama mungkin tidak selalu mewakili pelanggan yang sama.

Mengkonfigurasi Id pelanggan yang stabil memungkinkan Anda menghindari perilaku tersebut.

**Konfigurasikan ID pelanggan unik**

1. Buka **Satukan** > **Gabungkan**.

1. Pada halaman **Gabungkan**, pilih tab **Kunci**. 

1. Layangkan mouse di baris **CustomerId**, lalu pilih opsi **Konfigurasi**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrol untuk menyesuaikan pembuatan ID.":::

1. Pilih hingga lima bidang yang akan berisi ID pelanggan unik dan lebih stabil. Rekaman yang tidak sesuai dengan konfigurasi Anda akan menggunakan ID yang dikonfigurasi sistem.  

1. Pilih **Selesai** dan jalankan proses penggabungan untuk menerapkan perubahan Anda.

## <a name="run-your-merge"></a>Jalankan gabungan

Apakah Anda menggabungkan atribut secara manual atau membiarkan sistem menggabungkannya, Anda dapat menjalankan gabungan. Pada halaman **Gabungkan**, pilih **Jalankan** untuk memulai proses.

> [!div class="mx-imgBorder"]
> ![menyimpan dan menjalankan Gabungan data.](media/configure-data-merge-save-run.png "menyimpan dan menjalankan Gabungan data")

Pilih **Jalankan hanya penggabungan** jika Anda hanya ingin melihat output yang tercermin di entitas pelanggan terpadu. Proses hilir akan di-refresh sebagaimana [ditentukan dalam jadwal refresh](system.md#schedule-tab).

Pilih **Jalankan Proses Penggabungan dan hilir** untuk me-refresh sistem dengan perubahan Anda. Semua proses, termasuk pengayaan, segmen, dan langkah-langkah akan berjalan secara otomatis. Setelah semua proses hilir selesai, profil pelanggan mencerminkan perubahan yang Anda buat.

Untuk membuat perubahan lebih banyak dan menjalankan ulang langkah, Anda dapat membatalkan penggabungan yang sedang berlangsung. Pilih teks **menyegarkan...** dan pilih **Batalkan pekerjaan**  di panel sisi yang muncul.

> [!TIP]
> Setelah menjalankan proses penggabungan, pilih status proses untuk membuka panel **Detail tugas**. Ini memberikan gambaran umum tentang waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan dan peringatan yang terkait dengan tugas. Pilih **Lihat detail** untuk melihat entitas mana yang berpartisipasi dalam proses pencocokan, apakah resolusi konflik berhasil, dan apakah pembaruan berhasil diterbitkan.  
> Ada [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Jalur telusuri paling detail untuk mendapatkan detail proses dari link status tugas.":::

## <a name="next-step"></a>Langkah Berikutnya

Konfigurasikan [aktivitas](activities.md), [pengayaan](enrichment-hub.md), atau [Relasi](relationships.md) untuk mendapatkan wawasan lebih tentang pelanggan anda.

Jika Anda telah mengkonfigurasi aktivitas, pengayaan, atau segmen, maka aktivitas akan diproses secara otomatis untuk menggunakan data pelanggan terbaru.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
