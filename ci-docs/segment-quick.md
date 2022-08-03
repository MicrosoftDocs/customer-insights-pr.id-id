---
title: Buat segmen sederhana dengan segmen cepat
description: Buat segmen pelanggan sederhana untuk mengelompokkannya berdasarkan berbagai atribut.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171158"
---
# <a name="create-simple-segments-with-quick-segments"></a>Buat segmen sederhana dengan segmen cepat

Segmen singkat memungkinkan Anda membuat segmen sederhana dengan satu operator secara cepat untuk wawasan yang lebih cepat. Segmen singkat hanya didukung di lingkungan untuk **pelanggan individual**.

## <a name="create-a-new-segment-with-quick-segments"></a>Membuat segmen baru dengan segmen cepat

1. Buka **Segmen**.

1. Pilih **Buat Baru** > **dari**.
   - Pilih pilihan **profil** untuk membuat segmen yang didasarkan pada entitas *pelanggan terpadu*.
   - Pilih pilihan **Ukuran** untuk membuat segmen di sekitar ukuran yang telah Anda buat sebelumnya.
   - Pilih **pilihan intelijen** untuk membuat segmen di sekitar salah satu entitas output yang dihasilkan menggunakan **prediksi** maupun kemampuan **model kustom**.

1. Di kotak dialog **segmen ringkas baru**, pilih atribut dari dropdown **bidang**. Berdasarkan pilihan Anda, sistem memberikan nilai yang berbeda.
   - Untuk bidang kategoris, 10 jumlah pelanggan teratas ditampilkan. Pilih **nilai** dan pilih **tinjau**.
   - Untuk atribut numerik, sistem menunjukkan nilai atribut apa yang berada di bawah persentil setiap pelanggan. Pilih **operator** dan **nilai**, lalu pilih **tinjau**.

1. Sistem ini menyediakan **perkiraan ukuran segmen**. Pilih apakah akan membuat segmen yang telah Anda tentukan, atau kembali untuk memilih bidang yang berbeda.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nama dan estimasi untuk segmen cepat.":::

1. **Berikan nama entitas Nama** dan **Output** untuk segmen Anda. Secara opsional, tambahkan [tag](work-with-tags-columns.md#manage-tags).

1. Klik **Simpan** untuk membuat segmen Anda. Halaman **Segmen** ditampilkan.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Langkah berikutnya

[Ekspor segmen](export-destinations.md) dan jelajahi [integrasi Kartu Pelanggan](customer-card-add-in.md) untuk menggunakan segmen di aplikasi lain.

[!INCLUDE [footer-include](includes/footer-banner.md)]
