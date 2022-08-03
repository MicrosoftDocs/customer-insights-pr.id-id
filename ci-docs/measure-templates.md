---
title: Membuat ukuran dari templat
description: Tentukan ukuran menggunakan templat untuk kasus penggunaan umum.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170777"
---
# <a name="create-measures-from-templates"></a>Membuat ukuran dari templat

Gunakan templat yang telah ditentukan sebelumnya dari tindakan [yang umum digunakan](measures.md) untuk membuatnya. Templat dibuat berdasarkan data yang dipetakan dari entitas *Aktivitas Terpadu*. Jadi pastikan Anda telah mengonfigurasi [aktivitas pelanggan](activities.md) sebelum membuat ukuran dari templat.

Templat pengukuran hanya didukung di lingkungan untuk **pelanggan individu**. Untuk membuat pengukuran kustom atau membuat pengukuran untuk B-ke-B, lihat [Menggunakan penyusun pengukuran](measure-builder.md).

Template ukuran yang tersedia:
- Nilai transaksi rata-rata (ATV)
- Nilai transaksi total
- Pendapatan rata-rata harian
- Pendapatan rata-rata bulanan
- Pendapatan rata-rata tahunan
- Jumlah transaksi
- Poin loyalitas yang diperoleh
- Poin loyalitas yang ditukarkan
- Saldo poin loyalitas
- Rentang periode aktif pelanggan aktif
- Durasi keanggotaan loyalitas
- Waktu sejak pembelian terakhir

## <a name="build-a-new-measure-using-a-template"></a>Membuat pengukuran baru menggunakan templat

1. Pergi ke **Tindakan**.

1. Pilih **Baru** dan pilih **pilih template**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Cuplikan layar menu dropdown saat membuat pengukuran baru dengan sorotan di template.":::

1. Temukan templat yang sesuai dengan kebutuhan Anda dan pilih **Pilih templat**.

1. Tinjau data yang diperlukan dan pilih **Mulai** jika Anda memiliki semua data yang ada.

1. Pilih **Edit detail** di samping Ukur nama. Berikan nama untuk ukuran tersebut. Secara opsional, tambahkan [tag](work-with-tags-columns.md#manage-tags) ke pengukuran.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Kotak dialog Edit detail.":::

1. Pilih **Selesai**.

1. Di bagian **Atur periode** waktu, tentukan jangka waktu data. Pilih jika Anda menginginkan ukuran baru mencakup seluruh rangkaian data dengan memilih **Sepanjang waktu**, atau jika Anda ingin agar pengukuran fokus pada **periode waktu Tertentu**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Cuplikan layar memperlihatkan bagian periode waktu saat mengonfigurasi ukuran dari templat.":::

1. Di bagian berikutnya, pilih **Tambahkan data** untuk memilih aktivitas dan memetakan data terkait dari entitas *Aktivitas Terpadu* Anda.

    1. Langkah 1 dari 2: Di bawah **Tipe aktivitas**, pilih tipe entitas yang ingin Anda gunakan. Untuk **Aktivitas**, pilih entitas yang ingin Anda petakan, lalu pilih **Berikutnya**.
    1. Langkah 2 dari 2: Pilih atribut dari entitas *Aktivitas Terpadu* untuk komponen yang diperlukan oleh rumus. Misalnya, untuk nilai transaksi rata-rata, itu adalah atribut yang mewakili nilai Transaksi. Untuk **stempel waktu Aktivitas**, pilih atribut dari *entitas Aktivitas* Terpadu yang mewakili tanggal dan waktu aktivitas.
    1. Pilih **Simpan**.

    Ketika pemetaan data berhasil, status menunjukkan **Lengkap** dan nama aktivitas dan atribut yang dipetakan ditampilkan.

1. Pilih **Jalankan** untuk menghitung hasil pengukuran. Pilih **Simpan draf** jika Anda ingin mempertahankan konfigurasi saat ini dan menjalankan pengukuran nanti. Halaman **Pengukuran** ditampilkan.

## <a name="next-step"></a>Langkah selanjutnya

Gunakan langkah-langkah yang ada untuk membuat [segmen](segments.md) pelanggan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
