---
title: Tugas bersama untuk skenario prediksi
description: Pelajari cara mengelola, memecahkan masalah, dan menyempurnakan prediksi.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c4d269e1b542e84ade8c6e63c1dadace51ddde32
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643862"
---
# <a name="manage-predictions"></a>Kelola prediksi

Artikel ini membahas beberapa tugas yang dibagikan sebagian besar skenario prediksi.

## <a name="troubleshoot-a-failed-prediction"></a>Memecahkan masalah prediksi gagal

1. Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.

1. Pilih elipsis vertikal di sebelah prediksi yang ingin anda lihat log kesalahannya.

1. Pilih **Log**.

1. Memeriksa semua kesalahan. Ada beberapa jenis kesalahan yang dapat terjadi, dan menjelaskan kondisi yang menyebabkan kesalahan. Misalnya, kesalahan bahwa tidak ada cukup data yang dapat diprediksi secara akurat biasanya ditangani dengan memuat data tambahan ke dalam Customer Insights.

## <a name="input-data-usability-report"></a>Laporan penggunaan data input

Laporan kegunaan data input memberikan tampilan konsolidasi tentang kesalahan dan peringatan yang mungkin dihasilkan oleh prediksi standar Anda. Ini juga memberikan rekomendasi bagaimana meningkatkan kinerja model.

Laporan tersedia setelah model menyelesaikan proses pelatihannya. Ini dibuat untuk setiap model secara terpisah, terlepas dari apakah itu berhasil diselesaikan atau tidak.

### <a name="view-the-input-data-usability-report"></a>Lihat Laporan penggunaan data input

Setelah model standar menyelesaikan langkah pelatihannya, lihat laporan:
- Pilih elipsis di samping nama model dan pilih **Laporan kegunaan data input**.
- Pilih status model pilih Lihat **Lihat Laporan kegunaan data input** di panel samping.
- Memilih salah satu model dalam daftar dan pilih **laporan kegunaan data input** di bilah perintah.
- Buka halaman hasil model dan pilih **laporan kegunaan data input** di bilah perintah.

### <a name="information-in-the-input-data-usability-report"></a>Informasi di laporan penggunaan data input

Kolom berikut dalam laporan berisi informasi bermanfaat untuk meningkatkan data untuk model.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Contoh laporan kegunaan data input yang memperlihatkan tabel dengan kesalahan, peringatan, dan rekomendasi.":::

- **Nama:** Nama deskriptif kesalahan, peringatan, atau rekomendasi.
- **Langkah:** Fase model, kereta api atau skor, informasi mengacu pada.
- **Status:** Tingkat keparahan informasi (kesalahan, peringatan, rekomendasi).
- **Nama kolom:** Kolom dalam entitas yang perlu dimodifikasi untuk meningkatkan kinerja model.
- **Nama entitas:** Nama entitas yang perlu dimodifikasi untuk meningkatkan kinerja model.
- **Detail:** Detail tentang kesalahan, peringatan, atau rekomendasi.

## <a name="refresh-a-prediction"></a>Segarkan prediksi

Prediksi akan secara otomatis diperbarui pada jadwal yang sama [dengan penyegaran data Anda](system.md#schedule-tab) seperti dikonfigurasi dalam pengaturan. Anda juga dapat me-refresh secara manual.

1. Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.

1. Pilih elipsis vertikal di sebelah prediksi yang ingin Anda segarkan.

1. Pilih **Segarkan**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Hapus prediksi

Menghapus prediksi juga akan menghapus entitas keluarannya.

1. Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.

1. Pilih elipsis vertikal di sebelah prediksi yang ingin Anda hapus.

1. Pilih **Hapus**.
