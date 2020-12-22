---
title: Membuat dan mengedit ukuran
description: Tentukan ukuran terkait pelanggan untuk menganalisis dan mencerminkan performa area bisnis tertentu.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406078"
---
# <a name="define-and-manage-measures"></a>Menentukan dan mengelola ukuran

**Ukuran** menunjukkan KPI (indikator performa utama) yang mencerminkan performa dan kesehatan area bisnis tertentu. Wawasan audiens memberikan pengalaman yang intuitif untuk membuat berbagai jenis tindakan, dengan menggunakan pembuat kueri yang tidak mengharuskan Anda untuk mengkode, atau memvalidasi ukuran Anda secara manual. Anda dapat melacak tindakan bisnis Anda di halaman **Beranda**, melihat tindakan untuk pelanggan tertentu di **kartu pelanggan**, dan menggunakan tindakan untuk menentukan segmen pelanggan di halaman **segmen**.

## <a name="create-a-measure"></a>Membuat ukuran

Bagian ini menuntun Anda dalam membuat ukuran dari awal. Anda dapat membuat ukuran dengan data dari beberapa sumber data yang terhubung melalui entitas pelanggan. Beberapa [batas Layanan](service-limits.md) berlaku.

1. Di wawasan audiens, buka **Ukuran**.

2. Pilih **ukuran baru**.

3. Pilih **jenis** ukuran:

   - **Atribut pelanggan**: Satu bidang per pelanggan yang mencerminkan Skor, nilai, atau status untuk pelanggan. Atribut pelanggan dibuat sebagai atribut dalam entitas yang dihasilkan sistem baru yang disebut **Customer_Measure**.

   - **Ukuran pelanggan**: Wawasan tentang perilaku pelanggan dengan perincian berdasarkan dimensi yang dipilih. Entitas baru dibuat untuk setiap ukuran, mungkin dengan beberapa rekaman per pelanggan.

   - **Ukuran bisnis**: Melacak kinerja bisnis dan kesehatan bisnis. Langkah bisnis dapat memiliki dua output yang berbeda: output numerik yang ditampilkan di halaman **Beranda** atau entitas baru yang Anda temukan pada halaman **entitas**.

4. Berikan **nama** dan **nama tampilan** opsional, lalu pilih **berikutnya**.

5. Di bagian **Entitas**, pilih entitas pertama dari daftar menurun. Pada titik ini, Anda harus memutuskan apakah entitas tambahan diperlukan sebagai bagian dari definisi ukuran Anda.

   > [!div class="mx-imgBorder"]
   > ![Definisi Pengukuran](media/measure-definition.png "Definisi Pengukuran")

   Untuk menambahkan lebih banyak entitas, pilih **Tambah entitas** dan pilih entitas yang akan digunakan untuk mengukur.

   > [!NOTE]
   > Anda dapat memilih hanya entitas yang memiliki Relasi ke entitas awal. Untuk informasi lebih lanjut tentang cara mendefinisikan relasi, lihat [Relasi](relationships.md).

6. Atau, Anda dapat mengkonfigurasi variabel. Di bagian **variabel**, pilih **variabel baru**.

   Variabel adalah penghitungan yang dibuat pada setiap rekaman yang Anda pilih. Misalnya, menjumlahkan penjualan Point-of-Sale (POS) dan penjualan online untuk setiap rekaman pelanggan.

7. Beri **Nama** variabel tersebut.

8. Di area **ekspresi**, pilih bidang untuk memulai penghitungan.

9. Ketik ekspresi di area **ekspresi** saat memilih bidang yang akan disertakan dalam penghitungan Anda.

   > [!NOTE]
   > Saat ini, hanya ekspresi aritmetika yang didukung. Selain itu, penghitungan variabel tidak didukung untuk entitas dari [jalur entitas](relationships.md) yang berbeda.

10. Pilih **Selesai**.

11. Di bagian **definisi ukuran**, Anda akan menentukan cara entitas yang Anda pilih dan variabel yang dihitung digabungkan di entitas atau atribut ukuran baru.

12. Pilih **Dimensi baru**. Anda dapat menganggap dimensi sebagai fungsi *grup berdasarkan*. Output data entitas ukuran atau atribut akan dikelompokkan berdasarkan semua dimensi yang ditentukan.

    > [!div class="mx-imgBorder"]
    > ![Pilih siklus agregat](media/measures-businessreport-measure-definition2.png "Pilih siklus agregat")

    Pilih atau masukkan informasi berikut sebagai bagian dari definisi dimensi:

    - **Entitas**: jika Anda mendefinisikan entitas ukuran, harus mencakup sekurangnya satu atribut. Jika Anda mendefinisikan atribut ukuran, atribut ukuran hanya akan mencakup satu atribut secara default. Pilihan ini adalah tentang memilih entitas yang mencakup atribut tersebut.
    - **Bidang**: Pilih atribut khusus yang akan disertakan baik di entitas atau atribut ukuran Anda.
    - **wadah**: memilih apakah akan menggabungkan data secara harian, bulanan, atau tahunan. Ini adalah pilihan yang diperlukan hanya jika Anda telah memilih jenis tanggal dari atribut.
    - **Sebagai**: menentukan nama bidang baru Anda.
    - **nama tampilan**: menentukan nama tampilan bidang anda.

    > [!NOTE]
    > Ukuran bisnis Anda akan disimpan sebagai entitas nomor tunggal dan akan muncul di halaman **Beranda**, kecuali Anda menambahkan dimensi lainnya ke ukuran Anda. Setelah menambahkan dimensi lainnya , ukuran *tidak* akan muncul di halaman **Beranda**.

13. Atau, tambahkan fungsi agregat. Agregasi apa pun yang Anda buat menghasilkan nilai baru dalam entitas atau atribut Ukuran Anda. Fungsi agregasi yang didukung adalah **:** min **,** Max **,** Average **,** median **,** Sum **, Count Unique**, **First** (mengambil record pertama dari nilai dimensi), dan **Last** (mengambil record terakhir yang ditambahkan ke nilai dimensi).

14. Pilih **Simpan** untuk menerapkan perubahan ke ukuran.

## <a name="manage-your-measures"></a>Kelola ukuran Anda

Setelah membuat minimal satu pengukuran, Anda akan melihat daftar ukuran pada halaman **Ukuran**.

Anda akan menemukan informasi tentang jenis ukuran, pembuat, tanggal pembuatan dan waktu, terakhir mengedit tanggal dan waktu, status (Apakah ukuran aktif, tidak aktif, atau gagal), dan refresh tanggal dan waktu terakhir. Bila Anda memilih ukuran dari daftar, Anda dapat melihat pratinjau outputnya.

Untuk me-refresh semua ukuran Anda pada waktu yang sama, pilih **Segarkan semua** tanpa memilih ukuran tertentu.

> [!div class="mx-imgBorder"]
> ![Tindakan untuk mengelola ukuran tunggal](media/measure-actions.png "Tindakan untuk mengelola langkah tunggal")

Atau, Pilih ukuran dari daftar dan lakukan salah satu tindakan berikut:

- Pilih nama ukuran untuk melihat rinciannya.
- **Edit** konfigurasi ukuran.
- **Ubah nama** ukuran.
- **Hapus** ukuran.
- Pilih elipsis (...) dan kemudian **refresh** untuk memulai proses refresh untuk ukuran.
- Pilih elipsis (...) dan kemudian **Unduh** untuk mendapatkan File .CSV ukuran.

> [!TIP]
> Ada [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies). Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan. Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.

## <a name="next-step"></a>Langkah selanjutnya

Anda dapat menggunakan langkah yang ada untuk membuat segmen pelanggan pertama pada halaman **segmen**. Untuk informasi lebih lanjut, lihat [Segmen](segments.md).
