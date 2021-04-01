---
title: Gabungkan entitas dalam penyatuan data
description: Gabungkan entitas untuk membuat profil pelanggan terpadu.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597837"
---
# <a name="merge-entities"></a>Gabungkan Entitas

Fase gabungkan adalah fase terakhir dalam proses penyatuan data. Tujuannya adalah merekonsiliasi data yang berkonflik. Contoh data yang berkonflik dapat mencakup nama pelanggan yang berada di dua dataset, namun ditampilkan sedikit berbeda di masing-masing ("Grant Marshall" versus "Grant"), atau format nomor telepon yang berbeda format (617-803-091X versus 617803091X). Penggabungan titik data yang berkonflik dilakukan pada basis atribut demi atribut.

Setelah menyelesaikan [fase kecocokan](match-entities.md), Anda memulai fase penggabungan dengan memilih ubin **gabungkan** pada halaman **satukan**.

## <a name="review-system-recommendations"></a>Tinjau rekomendasi sistem

Di halaman **Gabungkan**, Anda dapat memilih dan mengecualikan atribut yang harus digabungkan dalam entitas profil pelanggan terpadu (hasil dari proses konfigurasi). Beberapa atribut secara otomatis digabungkan oleh sistem.

### <a name="view-merged-attributes"></a>Lihat atribut yang digabungkan

Untuk melihat atribut yang disertakan dalam salah satu dari atribut yang digabungkan secara otomatis, pilih atribut gabungan tersebut. Dua atribut yang membentuk atribut gabungan akan muncul di dua baris baru di bawah atribut gabungan.

> [!div class="mx-imgBorder"]
> ![pilih atribut gabungan](media/configure-data-merge-profile-attributes.png "pilih atribut gabungan")

### <a name="separate-merged-attributes"></a>Pisahkan atribut yang digabungkan

Untuk memisahkan atau batal menggabungkan atribut yang digabungkan secara otomatis, temukan atribut di tabel **atribut profil**.

1. Pilih tombol elipsis (...).
  
2. Di daftar drop-down , pilih **Bidang terpisah**.

### <a name="remove-merged-attributes"></a>Hapus atribut yang digabungkan

Untuk mengecualikan atribut dari entitas profil pelanggan akhir, temukan di tabel **atribut profil**.

1. Pilih tombol elipsis (...).
  
2. Di daftar drop-down , pilih **Jangan gabungkan**.

   Atribut dipindahkan ke bagian **dihapus dari rekaman pelanggan**.

## <a name="manually-add-a-merged-attribute"></a>Tambahkan atribut gabungan secara manual

Untuk menambahkan atribut gabungan, buka halaman **gabungkan**.

1. Pilih **Tambah atribut gabungan**.

2. Berikan **nama** untuk mengidentifikasinya di halaman **gabungkan** nanti.

3. Atau, berikan **nama tampilan** untuk ditampilkan di entitas profil pelanggan terpadu.

4. Konfigurasi **Pilih atribut duplikat** untuk memilih atribut yang ingin Anda gabungkan dari entitas yang cocok. Anda juga dapat mencari atribut.

5. Tetapkan **peringkat menurut nilai penting** untuk memprioritaskan satu atribut di atas yang lain. Misalnya, jika entitas *WebAccountCSV* mencakup data yang paling akurat tentang atribut *nama lengkap*, Anda dapat memprioritaskan entitas ini melalui *ContactCSV* dengan memilih *WebAccountCSV*. Akibatnya, *WebAccountCSV* bergerak ke prioritas pertama, sementara *ContactCSV* bergerak ke prioritas kedua ketika menarik nilai untuk atribut *nama lengkap*.

## <a name="run-your-merge"></a>Jalankan gabungan

Apakah Anda menggabungkan atribut secara manual atau membiarkan sistem menggabungkannya, Anda dapat menjalankan gabungan. Pada halaman **Gabungkan**, pilih **Jalankan** untuk memulai proses.

> [!div class="mx-imgBorder"]
> ![menyimpan dan menjalankan Gabungan data](media/configure-data-merge-save-run.png "menyimpan dan menjalankan Gabungan data")

Untuk membuat perubahan tambahan dan menjalankan ulang langkah tersebut, Anda dapat membatalkan penggabungan yang sedang berlangsung. Pilih teks **menyegarkan...** dan pilih **Batalkan pekerjaan**  di panel sisi yang muncul.

Setelah teks **Menyegarkan...** berubah menjadi **sukses**, penggabungan telah diselesaikan dan mengatasi kontradiksi dalam data Anda sesuai dengan kebijakan yang ditentukan. Atribut yang digabung dan tidak digabung disertakan dalam entitas profil terpadu. Atribut yang dikeluarkan tidak disertakan dalam entitas profil terpadu.

Jika ini bukan pertama kali Anda menjalankan penggabungan dengan berhasil, semua proses hilir, termasuk pengayaan, segmentasi, dan langkah akan berjalan ulang secara otomatis. Setelah semua proses hilir telah jalankan kembali, profil pelanggan mencerminkan perubahan yang Anda buat.

> [!TIP]
> Ada [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies). Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan. Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.

## <a name="next-step"></a>Langkah Berikutnya

Konfigurasikan [aktivitas](activities.md), [pengayaan](enrichment-microsoft-graph.md), atau [Relasi](relationships.md) untuk mendapatkan wawasan lebih tentang pelanggan anda.

Jika anda telah mengonfigurasi aktivitas, pengayaan, atau Relasi, atau jika anda telah menentukan segmen, maka akan diproses secara otomatis untuk menggunakan data pelanggan terkini.




[!INCLUDE[footer-include](../includes/footer-banner.md)]