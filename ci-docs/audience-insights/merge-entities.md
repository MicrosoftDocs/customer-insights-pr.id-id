---
title: Gabungkan entitas dalam penyatuan data
description: Gabungkan entitas untuk membuat profil pelanggan terpadu.
ms.date: 01/28/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: c7743104bf89d9a2a741f1b358a89ed0240be024
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355849"
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

1.  Anda dapat menambahkan bidang lainnya untuk berpartisipasi dalam proses penggabungan.

1.  Anda dapat mengganti nama bidang gabungan.

1. Pilih **Selesai** untuk menerapkan perubahan.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan. 

## <a name="combine-fields-manually"></a>Menggabungkan bidang secara manual

Tentukan atribut gabungan secara manual.

1. **Pada halaman Gabungkan**, pilih **Gabungkan**.

1. **Pilih opsi Bidang**.

1. Tentukan kebijakan pemenang gabungan di dropdown **Gabungkan bidang berdasarkan**.

1. Pilih bidang untuk ditambahkan. pilih **Tambahkan bidang** untuk mengombinasikan bidang lainnya.

1. Berikan **Nama** dan **nama bidang Output**.

1. Pilih **Selesai** untuk menerapkan perubahan.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan. 

## <a name="combine-a-group-of-fields"></a>Menggabungkan sekelompok bidang

Perlakukan sekelompok bidang sebagai satu unit. Misalnya, saat jika catatan kami berisi bidang Alamat1, Alamat2, Kota, Negara Bagian, dan Zip. Kami mungkin tidak ingin bergabung dalam Alamat 2 rekaman yang berbeda, berpikir itu akan membuat data kami lebih lengkap

1. **Pada halaman Gabungkan**, pilih **Gabungkan**.

1. **Pilih opsi Grup bidang**.

1. Tentukan kebijakan penggabungan pemenang di **grup Peringkat menurut** turun bawah.

1. Pilih **Tambahkan** dan pilih apakah Anda ingin menambahkan lebih banyak bidang atau grup tambahan ke bidang.

1. **Berikan Nama** dan **nama** Output untuk setiap bidang gabungan.

1. **Berikan Nama** untuk grup bidang. 

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

CustomerId dalam entitas Pelanggan didasarkan pada hash nilai pertama kunci utama pemenang non-nihil. Kunci ini berasal dari entitas yang digunakan dalam fase pencocokan dan penggabungan dan terpengaruh oleh urutan kecocokan. Jadi CustomerID yang dihasilkan dapat berubah ketika nilai utama utama berubah di entitas utama dari urutan kecocokan. Jadi nilai kunci utama mungkin tidak selalu mewakili pelanggan yang sama.

Mengkonfigurasi ID pelanggan yang stabil memungkinkan Anda menghindari perilaku tersebut.

**Konfigurasikan ID pelanggan unik**

1. Buka **Satukan** > **Gabungkan**.

1. Pilih tab **Kunci**. 

1. Layangkan mouse di baris **CustomerId**, lalu pilih opsi **Konfigurasi**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kontrol untuk menyesuaikan pembuatan ID.":::

1. Pilih hingga lima bidang yang akan berisi ID pelanggan unik dan lebih stabil. Rekaman yang tidak sesuai dengan konfigurasi Anda akan menggunakan ID yang dikonfigurasi sistem.  

1. Pilih **Selesai** dan jalankan proses penggabungan untuk menerapkan perubahan Anda.

## <a name="group-profiles-into-households-or-clusters"></a>Mengelompokkan profil ke rumah tangga atau kluster

Sebagai bagian dari proses konfigurasi pembuatan profil pelanggan, Anda dapat menentukan aturan untuk mengelompokkan profil terkait ke kluster. Saat ini ada dua jenis kluster yang tersedia – kluster rumah tangga dan kustom. Sistem secara otomatis memilih rumah tangga dengan aturan yang ditetapkan sebelumnya jika entitas *Pelanggan* berisi bidang semantis *Person.LastName* dan *Location.Address*. Anda juga dapat membuat kluster dengan aturan dan kondisi Anda sendiri, yang mirip dengan [cocokkan aturan](match-entities.md#define-rules-for-match-pairs).

**Menentukan rumah tangga atau kluster**

1. Buka **Satukan** > **Gabungkan**.

1. Pada tab **Gabung**, pilih **lanjutan** > **Buat kluster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kontrol untuk membuat kluster baru.":::

1. Pilih antara **Rumah Tangga** atau kluster **Kustom**. Jika bidang semantis *Person.LastName* dan *Location.Address* ada di entitas *Pelanggan*, rumah tangga akan secara otomatis dipilih.

1. Berikan nama untuk kluster, lalu pilih **Selesai**.

1. Pilih tab **Kluster** untuk menemukan kluster yang Anda buat.

1. Tentukan aturan dan kondisi untuk mendefinisikan kluster Anda.

1. Pilih **Jalankan** untuk menjalankan proses penggabungan dan buat kluster.

Setelah menjalankan proses penggabungan, pengidentifikasi kluster ditambahkan sebagai bidang baru ke entitas *Pelanggan*.

## <a name="run-your-merge"></a>Jalankan gabungan

Apakah Anda menggabungkan atribut secara manual atau membiarkan sistem menggabungkannya, Anda dapat menjalankan gabungan. Pada halaman **Gabungkan**, pilih **Jalankan** untuk memulai proses.

> [!div class="mx-imgBorder"]
> ![menyimpan dan menjalankan Gabungan data.](media/configure-data-merge-save-run.png "menyimpan dan menjalankan Gabungan data")

Pilih **Jalankan hanya penggabungan** jika Anda hanya ingin melihat output yang tercermin di entitas pelanggan terpadu. Proses hilir akan di-refresh sebagaimana [ditentukan dalam jadwal refresh](system.md#schedule-tab).

Pilih **Jalankan Proses Penggabungan dan hilir** untuk me-refresh sistem dengan perubahan Anda. Semua proses, termasuk pengayaan, segmen, dan langkah-langkah akan berjalan secara otomatis. Setelah semua proses hilir selesai, profil pelanggan mencerminkan perubahan yang Anda buat.

Untuk membuat perubahan lebih banyak dan menjalankan ulang langkah, Anda dapat membatalkan penggabungan yang sedang berlangsung. Pilih teks **menyegarkan...** dan pilih **Batalkan pekerjaan**  di panel sisi yang muncul.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Jalur telusuri paling detail untuk mendapatkan detail proses dari link status tugas.":::

## <a name="next-step"></a>Langkah Berikutnya

Konfigurasikan [aktivitas](activities.md), [pengayaan](enrichment-hub.md), atau [Relasi](relationships.md) untuk mendapatkan wawasan lebih tentang pelanggan anda.

Jika Anda telah mengkonfigurasi aktivitas, pengayaan, atau segmen, maka aktivitas akan diproses secara otomatis untuk menggunakan data pelanggan terbaru.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
