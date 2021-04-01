---
title: Aktivitas pelanggan
description: Menentukan aktivitas pelanggan dan melihatnya di Timeline pelanggan.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596733"
---
# <a name="customer-activities"></a>Aktivitas pelanggan

Kombinasikan aktivitas pelanggan dari [berbagai sumber data](data-sources.md) di Dynamics 365 Customer Insights untuk membuat Timeline Pelanggan yang berisi daftar aktivitas dalam urutan kronologis. Anda dapat menyertakan kronologi di aplikasi keterlibatan pelanggan di Dynamics 365 melalui [Add-in kartu pelanggan](customer-card-add-in.md), atau di dasbor Power BI.

## <a name="define-an-activity"></a>Menentukan Aktivitas

Sumber data Anda mencakup entitas dengan data transaksional dan aktivitas dari beberapa sumber data. Identifikasi entitas tersebut dan pilih aktivitas yang ingin Anda lihat pada kronologi pelanggan. Pilih entitas yang mencakup aktivitas atau aktivitas target Anda.

1. Di wawasan audiens, buka **Data** > **aktivitas**.

1. Pilih **Tambah aktivitas**.

   > [!NOTE]
   > Entitas harus memiliki minimal satu atribut jenis **tanggal** untuk disertakan dalam kronologi pelanggan dan Anda tidak dapat menambahkan entitas tanpa bidang **tanggal**. Kontrol **Tambah aktivitas** dinonaktifkan jika tidak ada entitas yang ditemukan.

1. Di panel **Tambah aktivitas**, atur nilai untuk bidang berikut:

   - **Entitas**: Pilih entitas yang mencakup data transaksi atau aktivitas.
   - **Kunci utama**: Pilih bidang yang secara unik mengidentifikasi rekaman. Ini tidak boleh berisi nilai duplikat, nilai kosong, atau nilai yang tidak ada.
   - **Cap waktu**: pilih bidang yang menunjukkan waktu mulai aktivitas Anda.
   - **Aktivitas**: pilih bidang yang merupakan peristiwa aktivitas.
   - **Alamat web**: pilih bidang yang menunjukkan URL yang menyediakan informasi tambahan tentang aktivitas ini. Misalnya, sistem transaksional yang menjadi sumber aktivitas ini. URL ini dapat berupa bidang apa pun dari sumber data, atau dapat dibangun sebagai bidang baru menggunakan transformasi Power Query. Data URL ini akan disimpan di entitas aktivitas terpadu, yang dapat dikonsumsi ke hilir menggunakan api.
   - **Rincian**: opsional, pilih bidang yang ditambahkan untuk rincian tambahan.
   - **Ikon**: opsional, pilih ikon yang menunjukkan aktivitas ini.
   - **Jenis aktivitas**: Tentukan referensi jenis aktivitas ke Common Data Model yang paling sesuai dengan definisi semantik aktivitas.

1. Di Bagian **Atur relasi**, konfigurasikan rincian untuk menghubungkan data aktivitas Anda dengan pelanggan yang sesuai.

    - Bidang **entitas aktivitas**: pilih bidang di entitas aktivitas yang akan digunakan untuk menjalin relasi dengan entitas lain.
    - **Entitas pelanggan**: Pilih entitas pelanggan sumber terkait yang memiliki relasi dengan entitas aktivitas Anda. Anda hanya dapat berhubungan dengan entitas pelanggan sumber yang digunakan dalam proses penyatuan data.
    - **Bidang entitas pelanggan**: bidang ini menampilkan kunci primer dari entitas pelanggan sumber yang dipilih dalam proses peta. Bidang kunci primer di entitas pelanggan sumber digunakan untuk menjalin relasi dengan entitas aktivitas.
    - **Nama**: jika relasi antara entitas aktivitas ini dan entitas pelanggan sumber yang dipilih sudah ada, nama relasi hanya akan berada dalam mode baca-saja. Jika hubungan tersebut tidak ada, relasi baru akan dibuat dengan nama yang diberikan di sini.
   
   > [!div class="mx-imgBorder"]
   > ![Tentukan relasi entitas](media/activities-entities-define.png "Tentukan relasi entitas.").

1. Pilih **Simpan** untuk menerapkan perubahan.

1. Pada halaman **aktivitas**, pilih **Jalankan**.

> [!TIP]
> Ada [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies). Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan. Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.

## <a name="edit-an-activity"></a>Edit aktivitas

1. Di wawasan audiens, buka **Data** > **aktivitas**.

2. Pilih entitas aktivitas yang akan diedit dan pilih **Edit**. Atau, Anda dapat mengarahkan kursor ke baris entitas dan memilih **ikon Edit**.

3. Klik ikon **Edit**.

4. Di panel **Edit aktivitas**, perbarui nilai dan pilih **Simpan**.

5. Pada halaman **aktivitas**, pilih **Jalankan**.

## <a name="delete-an-activity"></a>Hapus Aktivitas

1. Di wawasan audiens, buka **Data** > **aktivitas**.

2. Pilih entitas aktivitas yang akan dihapus dan pilih **Hapus**. Atau, Anda dapat mengarahkan kursor ke baris entitas dan memilih ikon **Hapus**. Selain itu, Anda dapat memilih beberapa entitas aktivitas untuk dihapus sekaligus.
   > [!div class="mx-imgBorder"]
   > ![Mengedit atau menghapus relasi entitas](media/activities-entities-edit-delete.png "Mengedit atau menghapus relasi entitas")

3. Pilih ikon **Hapus**.

4. Konfirmasikan penghapusan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]