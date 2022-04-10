---
title: Membuat langkah-langkah dari templat
description: Tentukan langkah-langkah menggunakan templat untuk kasus penggunaan umum.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 0fe846691825b93732cbbe6d1c942a79e4a3934f
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359965"
---
# <a name="use-a-template-to-build-a-measure"></a>Gunakan templat untuk menyusun pengukuran

Anda dapat menggunakan templat yang telah ditentukan dari langkah-langkah [yang umum digunakan](measures.md) untuk membuatnya. Deskripsi terperinci tentang templat dan pengalaman terpandu membantu Anda mengukur pembuatan yang efisien. Templat dibuat berdasarkan data yang dipetakan dari entitas *Aktivitas Terpadu*. Jadi pastikan Anda telah mengonfigurasi [aktivitas pelanggan](activities.md) sebelum membuat ukuran dari templat.

Untuk membuat tindakan kustom, lihat [Menggunakan pengukur penyusun untuk membuat langkah-langkah dari awal](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

Template ukuran yang tersedia: 
- Nilai transaksi rata-rata (ATV)
- Nilai transaksi total
- Pendapatan rata-rata harian
- Pendapatan rata-rata tahunan
- Jumlah transaksi
- Poin loyalitas yang diperoleh
- Poin loyalitas yang ditukarkan
- Saldo poin loyalitas
- Rentang periode aktif pelanggan aktif
- Durasi keanggotaan loyalitas
- Waktu sejak pembelian terakhir

## <a name="build-a-new-measure-using-a-template"></a>Membuat ukuran baru menggunakan templat

1. Pergi ke **langkah-langkah**.

1. Pilih **Baru** dan pilih **pilih template**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Cuplikan layar menu dropdown saat membuat pengukuran baru dengan sorotan di template.":::

1. Temukan templat yang sesuai dengan kebutuhan Anda dan pilih **Pilih templat**.

1. Tinjau data yang diperlukan dan pilih **Mulai** jika Anda memiliki semua data yang ada.

1. Di panel **Edit nama**, atur nama untuk ukuran Anda dan entitas output. 

1. Pilih **Selesai**.

1. Di bagian **Atur periode waktu**, tentukan jangka waktu data yang akan digunakan. Pilih jika Anda menginginkan ukuran baru mencakup seluruh rangkaian data dengan memilih **Sepanjang waktu**, atau jika Anda ingin agar pengukuran fokus pada **periode waktu Tertentu**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Cuplikan layar memperlihatkan bagian periode waktu saat mengonfigurasi ukuran dari templat.":::

1. Di bagian berikutnya, pilih **Tambahkan data** untuk memilih aktivitas dan memetakan data terkait dari entitas *Aktivitas Terpadu* Anda.

    1. Langkah 1 dari 2: Di bawah **Tipe aktivitas**, pilih tipe entitas yang ingin Anda gunakan. Untuk **Aktivitas**, pilih entitas yang ingin Anda petakan.
    1. Langkah 2 dari 2: Pilih atribut dari entitas *Aktivitas Terpadu* untuk komponen yang diperlukan oleh rumus. Misalnya, untuk nilai transaksi rata-rata, itu adalah atribut yang mewakili nilai Transaksi. Untuk **Cap waktu Aktivitas**, pilih atribut dari entitas Aktivitas Terpadu yang menunjukkan tanggal dan waktu aktivitas.
   
1. Setelah pemetaan data berhasil, Anda dapat melihat status sebagai **Selesai** dan nama aktivitas dan atribut yang dipetakan.

1. Sekarang Anda dapat memilih **Jalankan** untuk menghitung hasil pengukuran. Untuk memperbaikinya nanti, pilih **Simpan draf**.

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

Fitur ini hanya tersedia untuk langkah-langkah yang dibuat di lingkungan dengan pelanggan individual sebagai target audiens.

---
