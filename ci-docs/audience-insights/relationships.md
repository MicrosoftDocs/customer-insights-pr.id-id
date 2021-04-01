---
title: Hubungan antara entitas dan jalur entitas
description: Buat dan kelola Relasi antara entitas dari beberapa sumber data.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595216"
---
# <a name="relationships-between-entities"></a>Relasi di antara dua entitas

Relasi membantu anda menghubungkan entitas dan menghasilkan grafik data saat entitas memiliki pengidentifikasi umum yang sama (kunci asing) yang dapat dirujuk dari satu entitas ke entitas lain. Entitas tersambung memungkinkan Anda menentukan segmen dan ukuran berdasarkan beberapa sumber data.

Ada dua jenis dasbor di relasi. Relasi sistem yang tidak dapat diedit, yang dibuat secara otomatis, dan Relasi kustom yang dibuat dan dikonfigurasi oleh pengguna.

Selama proses pencocokan dan penggabungan, Relasi sistem dibuat di belakang layar berdasarkan pencocokan cerdas. Relasi ini membantu mengaitkan rekaman profil pelanggan dengan rekaman entitas terkait lainnya. Diagram berikut mengilustrasikan pembuatan tiga Relasi sistem saat entitas pelanggan dicocokkan dengan entitas tambahan untuk menghasilkan entitas profil pelanggan akhir.

> [!div class="mx-imgBorder"]
> ![Pembuatan Relasi](media/relationships-entities-merge.png "Pembuatan Relasi")

- **Relasi *CustomerToContact*** dibuat antara entitas pelanggan dan entitas kontak. Entitas pelanggan mendapatkan bidang penting **Contact_contactId** untuk dikaitkan dengan bidang kunci entitas kontak **contactId**.
- **Relasi *CustomerToAccount*** dibuat antara entitas pelanggan dan entitas Akun. Entitas pelanggan mendapatkan bidang penting **Account_accountId** untuk dikaitkan dengan bidang kunci entitas Akun **accountId**.
- **Relasi *CustomerToWebAccount*** dibuat antara entitas pelanggan dan entitas WebAccount. Entitas pelanggan mendapatkan bidang penting **WebAccount_webaccountId** untuk dikaitkan dengan bidang kunci entitas WebAccount **webaccountId**.

## <a name="create-a-relationship"></a>Buat Relasi

Tentukan Relasi kustom pada halaman **Relasi**. Setiap relasi terdiri dari entitas sumber (entitas yang memegang kunci asing) dan entitas target (entitas yang ditunjuk oleh kunci asing entitas sumber).

1. Di wawasan audiens, buka **Data** > **Relasi**.

2. Pilih **relasi baru**.

3. Di panel **Tambahkan Relasi**, berikan informasi berikut:

   > [!div class="mx-imgBorder"]
   > ![masukkan rincian relasi](media/relationships-add.png "masukkan rincian relasi")

   - **Nama relasi**: Nama yang mencerminkan tujuan relasi (misalnya, **AccountWebLogs**).
   - **Deskripsi** deskripsi relasi.
   - **Entitas sumber**: pilih entitas yang digunakan sebagai sumber di relasi (misalnya, WebLog).
   - **Kardinalitas**: pilih Kardinalitas rekaman entitas sumber. Misalnya, "banyak" berarti bahwa beberapa rekaman weblog terkait dengan satu WebAccount.
   - **Bidang kunci sumber**: ini menunjukkan bidang foreign key di entitas sumber. Misalnya, WebLog memiliki bidang foreign key **accountId**.
   - **Entitas target**: pilih entitas yang digunakan sebagai target di relasi (misalnya, WebAccount).
   - **Kardinalitas target**: pilih menunjukkan Kardinalitas rekaman entitas target. Misalnya, "satu" berarti bahwa beberapa rekaman weblog terkait dengan satu WebAccount.
   - **Bidang kunci target**: bidang ini mewakili bidang kunci dari entitas target. Misalnya, WebAccount memiliki bidang kunci **accountId**.

> [!NOTE]
> Hanya Relasi banyak ke satu dan satu-ke-satu yang didukung. Relasi banyak ke banyak dapat dibuat menggunakan dua Relasi banyak ke satu dan entitas tautan — (entitas yang digunakan untuk menghubungkan entitas sumber dan entitas target).

## <a name="delete-a-relationship"></a>Hapus relasi

1. Di wawasan audiens, buka **Data** > **Relasi**.

2. Pilih kotak centang untuk relasi yang akan dihapus.

3. Pilih **hapus** di bagian atas tabel **Relasi**.

4. Konfirmasikan penghapusan.

## <a name="next-step"></a>Langkah berikutnya

Relasi sistem dan kustom digunakan untuk membuat segmen berdasarkan beberapa sumber data yang tidak lagi diisolasi. Untuk informasi lebih lanjut, lihat [Segmen](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]