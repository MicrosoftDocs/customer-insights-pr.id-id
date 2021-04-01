---
title: Membuat dan mengelola ukuran
description: Menentukan ukuran untuk menganalisis dan mencerminkan kinerja bisnis Anda.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654736"
---
# <a name="define-and-manage-measures"></a>Menentukan dan mengelola ukuran

Ukuran membantu Anda memahami lebih baik perilaku pelanggan dan kinerja bisnis dengan mengambil nilai yang relevan dari [profil terpadu](data-unification.md). Misalnya, bisnis ingin melihat *total pengeluaran per pelanggan* untuk memahami riwayat pembelian pelanggan individual. Atau ukur *total penjualan perusahaan* untuk memahami pendapatan tingkat agregat dalam seluruh bisnis.  

Ukuran dibuat menggunakan pembuat ukuran, platform kueri data dengan berbagai operator, dan pilihan pemetaan sederhana. Alat ini memungkinkan Anda memfilter data, mengelompokkan hasil, mendeteksi [jalur relasi entitas](relationships.md), dan mempratinjau output.

Gunakan pembuat ukuran untuk merencanakan aktivitas bisnis dengan mengkueri data pelanggan dan mengekstrak wawasan. Contohnya, membuat ukuran *total pengeluaran per pelanggan* dan *penghasilan total per pelanggan* membantu mengidentifikasi grup pelanggan dengan pengeluaran tinggi namun penghasilan yang tinggi. Anda dapat [membuat segmen](segments.md) untuk mendorong tindakan terbaik berikutnya. 

## <a name="create-a-measure"></a>Membuat ukuran

Bagian ini akan memandu Anda membuat pengukuran baru dari awal. Anda dapat membuat pengukuran dengan atribut data dari entitas data yang telah diatur relasinya untuk terhubung dengan entitas Pelanggan. 

1. Di wawasan audiens, buka **Ukuran**.

1. Pilih **baru**.

1. Pilih **Edit nama** dan berikan **Nama** untuk ukurannya. 
   > [!NOTE]
   > Jika konfigurasi pengukuran baru Anda hanya memiliki dua bidang, misalnya CustomerID dan satu perhitungan, output akan ditambahkan sebagai kolom baru ke entitas yang dihasilkan sistem yang disebut Customer_Measure. Anda akan dapat melihat nilai pengukuran di profil pelanggan terpadu. Ukuran lain akan menghasilkan entitas mereka sendiri.

1. Di area konfigurasi, pilih fungsi agresi dari menu drop-down **Pilih Fungsi**. Fungsi agresi mencakup: 
   - **Sum**
   - **Rata-rata**
   - **Count**
   - **Jumlah Unik**
   - **Max**
   - **Min**
   - **Pertama**: mengambil nilai pertama rekaman data
   - **Terakhir**: mengambil nilai terakhir yang ditambahkan ke rekaman data

   :::image type="content" source="media/measure-operators.png" alt-text="Operator untuk menghitung pengukuran.":::

1. Pilih **Tambah atribut** untuk memilih data yang diperlukan untuk membuat pengukuran ini.
   
   1. Pilih tab **atribut**. 
   1. Entitas data: Pilih entitas yang mencakup atribut yang ingin Anda ukur. 
   1. Atribut data: Pilih atribut yang ingin Anda gunakan di fungsi agresi untuk menghitung ukuran. Anda hanya dapat memilih satu atribut setiap kali.
   1. Anda juga dapat memilih atribut data dari ukuran yang ada dengan memilih tab **Ukuran**. Atau, Anda dapat mencari entitas atau nama ukuran. 
   1. Pilih **Tambah** untuk menambahkan atribut yang dipilih ke ukuran.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Pilih atribut untuk digunakan dalam penghitungan.":::

1. Untuk membuat ukuran yang lebih kompleks, Anda dapat menambahkan lebih banyak atribut atau menggunakan operator hitung pada fungsi pengukuran Anda.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Buat pengukuran yang kompleks dengan operator hitung.":::

1. Untuk menambahkan filter, pilih **Filter** pada area konfigurasi. 
  
   1. Di bagian **Tambah atribut** pada panel **Filter**, pilih atribut yang akan digunakan untuk membuat filter.
   1. Atur operator filter untuk menentukan filter untuk setiap atribut yang dipilih.
   1. Pilih **Terapkan** untuk menambahkan filter ke ukuran.

1. Untuk menambahkan dimensi, pilih **Dimensi** pada area konfigurasi. Dimensi akan ditampilkan sebagai kolom dalam entitas output pengukuran.
   1. Pilih **Edit dimensi** untuk menambahkan atribut data untuk mengelompokkan nilai ukuran. Misalnya, kota atau jenis kelamin. Secara default, dimensi *CustomerID* dipilih untuk membuat *ukuran tingkat pelanggan*. Anda dapat menghilangkan dimensi default jika ingin membuat *ukuran tingkat bisnis*.
   1. Pilih **Selesai** untuk menambahkan dimensi ke ukuran.

1. Jika ada beberapa jalur antara entitas data yang Anda petakan dan entitas *Pelanggan*, Anda harus memilih salah satu jalur relasi [entitas yang diidentifikasi](relationships.md). Hasil ukuran dapat bervariasi, tergantung pada jalur yang dipilih. 
   1. Pilih **preferensi Data** dan pilih jalur entitas yang harus digunakan untuk mengidentifikasi ukuran Anda. Jika hanya ada satu jalur ke entitas *Pelanggan*, kontrol ini tidak akan ditampilkan.
   1. Pilih **Selesai** untuk menerapkan pilihan Anda. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Pilih jalur entitas untuk ukuran.":::

1. Untuk menambahkan perhitungan lainnya untuk pengukuran, pilih **Penghitungan baru**. Anda hanya dapat menggunakan entitas pada jalur entitas yang sama untuk perhitungan baru. Perhitungan lainnya akan ditampilkan sebagai kolom baru dalam entitas output pengukuran.

1. Pilih **...** pada penghitungan untuk **membuat duplikat**, **Mengganti Nama**, atau **Menghapus perhitungan** dari pengukuran.

1. Di area **Pratinjau**, Anda akan melihat skema data dari entitas output pengukuran, termasuk filter dan dimensi. Pratinjau merespons secara dinamis terhadap perubahan dalam konfigurasi.

1. Pilih **Jalankan** untuk menghitung hasil pengukuran yang dikonfigurasi. Pilih **Simpan dan tutup** jika Anda ingin menyimpan konfigurasi saat ini dan menjalankan pengukuran nanti.

1. Buka **Ukuran** untuk melihat ukuran yang baru dibuat dalam daftar.

## <a name="manage-your-measures"></a>Kelola ukuran Anda

Setelah [membuat pengukuran](#create-a-measure), Anda akan melihat daftar ukuran pada halaman **Ukuran**.

Anda akan menemukan informasi tentang jenis pengukuran, pembuat, tanggal pembuatan, status, dan status. Bila Anda memilih ukuran dari daftar, Anda dapat mempratinjau output dan mengunduh file .CSV.

Untuk me-refresh semua ukuran Anda pada waktu yang sama, pilih **Segarkan semua** tanpa memilih ukuran tertentu.

> [!div class="mx-imgBorder"]
> ![Tindakan untuk mengelola ukuran tunggal](media/measure-actions.png "Tindakan untuk mengelola langkah tunggal")

Pilih ukuran dari daftar untuk pilihan berikut:

- Pilih nama ukuran untuk melihat rinciannya.
- **Edit** konfigurasi ukuran.
- **segarkan** pengukuran berdasarkan data terbaru.
- **Ubah nama** ukuran.
- **Hapus** ukuran.
- **Aktifkan** atau **Nonaktifkan**. Ukuran yang tidak aktif tidak akan di-refresh selama [refresh terjadwal](system.md#schedule-tab).

> [!TIP]
> Ada [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies). Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan. Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.

## <a name="next-step"></a>Langkah selanjutnya

Anda dapat menggunakan ukuran yang ada untuk membuat [segmen pelanggan](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]