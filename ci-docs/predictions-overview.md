---
title: Ikhtisar prediksi
description: Prediksi dan opsi yang dicakup oleh aplikasi Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610194"
---
# <a name="predictions-overview"></a>Ikhtisar prediksi

Dynamics 365 Customer Insights hadir dengan berbagai opsi yang memanfaatkan AI dan Pembelajaran Mesin untuk memprediksi data.

## <a name="out-of-box-models"></a>Model siap pakai

Cara termudah untuk memulai dengan memprediksi data adalah model yang sudah ditentukan sebelumnya, sering disebut sebagai model siap pakai. Mereka hanya memerlukan data dan struktur tertentu untuk menghasilkan wawasan dengan cepat. Model-model berikut tersedia:

# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

- [Nilai seumur hidup pelanggan](predict-customer-lifetime-value.md): Memprediksi potensi pendapatan pelanggan di seluruh interaksi dengan bisnis.
- [Rekomendasi produk](predict-product-recommendation.md): Menyarankan set rekomendasi produk prediktif berdasarkan perilaku pembelian dan pelanggan dengan pola pembelian yang sama.
- [Kehilangan langganan](predict-subscription-churn.md): Memprediksi apakah pelanggan berisiko karena tidak lagi menggunakan produk atau layanan langganan perusahaan Anda.
- [Churn](predict-transactional-churn.md) transaksional: Memprediksi apakah pelanggan individu tidak akan lagi membeli produk atau layanan Anda dalam jangka waktu tertentu.
- [Analisis sentimen](sentiment-analysis.md): Menganalisis sentimen umpan balik pelanggan dan mengidentifikasi aspek bisnis yang sering disebutkan.

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

- [Churn](predict-transactional-churn.md) transaksional: Memprediksi apakah akun pelanggan tidak akan lagi membeli produk atau layanan Anda dalam jangka waktu tertentu.

---

> [!TIP]
> Sebaiknya refresh model out-of-the-box secara teratur dengan data yang diperbarui untuk memastikan model tersebut menginformasikan kasus penggunaan bisnis Anda secara akurat. Data disegarkan secara ad-hoc saat sistem menyerap sumber data baru atau yang diperbarui. Namun, model hanya akan menggarisbawahi ulang dalam kasus ini dan terus menggunakan data pelatihan yang ada.
>
> **Konfigurasikan jadwal** Pembaruan dengan mengatur jadwal pelatihan ulang model selama konfigurasi. Model akan melatih kembali dan menggarisbawahi ulang pada jadwal ini, yang dapat Anda ubah kapan saja.

## <a name="azure-machine-learning-integration"></a>Integasi Pembelajaran Mesin Azure

Jika organisasi sudah menggunakan Pembelajaran Mesin berdasarkan eksperimen Azure Pembelajaran Mesin, fitur model kustom di Customer Insights membantu menghubungkan titik-titik. Buat alur kerja yang membantu Anda memilih data yang ingin Anda hasilkan wawasannya dan petakan hasilnya ke profil pelanggan terpadu Anda. Untuk informasi lebih lanjut, lihat [model Pembelajaran Mesin kustom](custom-models.md).

## <a name="manage-existing-predictions"></a>Mengelola prediksi yang sudah ada

Buka halaman **Prediksi** > **Intelijen**. Pada tab **Prediksi** saya, lihat prediksi yang Anda buat, jenis prediksi, nama entitas keluaran, status, terakhir kali prediksi diedit, dan terakhir kali data disegarkan. Anda dapat mengurutkan daftar prediksi berdasarkan kolom mana pun.

Pilih prediksi untuk melihat tindakan yang tersedia.

:::image type="content" source="media/predictions.png" alt-text="Halaman prediksi saya.":::

- **Edit** prediksi untuk mengubah propertinya.
- [**Refresh**](#refresh-a-prediction) prediksi untuk menyertakan data terbaru.
- **Lihat** detail prediksi.
- [**Masukkan laporan**](#view-the-input-data-usability-report) kegunaan data untuk melihat kesalahan, peringatan, dan rekomendasi.
- **Hapus** prediksi.

### <a name="refresh-a-prediction"></a>Segarkan prediksi

Prediksi dapat disegarkan pada jadwal otomatis atau disegarkan secara manual sesuai permintaan. Untuk me-refresh semua prediksi secara manual, pilih **Refresh semua**. Untuk me-refresh prediksi secara manual, pilih dan pilih **Refresh**. Untuk [menjadwalkan refresh](schedule-refresh.md) otomatis, buka **Jadwal** > **Sistem** > **Admin**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Lihat Laporan penggunaan data input

Laporan kegunaan data input memberikan tampilan konsolidasi tentang kesalahan dan peringatan yang mungkin dihasilkan oleh prediksi standar Anda. Ini juga memberikan rekomendasi tentang cara meningkatkan kinerja model.

Laporan tersedia setelah model menyelesaikan proses pelatihannya. Ini dibuat untuk setiap model secara terpisah, terlepas dari apakah itu menyelesaikan pelatihan dengan sukses atau tidak.

Pada tab **Prediksi** saya, pilih prediksi dan pilih **Masukkan laporan** kegunaan data. Atau dari tampilan detail prediksi, pilih **Masukkan laporan** kegunaan data.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Contoh laporan kegunaan data input yang memperlihatkan tabel dengan kesalahan, peringatan, dan rekomendasi.":::

Laporan tersebut meliputi:

- **Nama:** Nama deskriptif dari kesalahan, peringatan, atau rekomendasi.
- **Langkah:** Fase model, kereta api atau skor, informasi yang dimaksud.
- **Status:** Tingkat keparahan informasi (kesalahan, peringatan, rekomendasi).
- **Nama kolom:** Kolom dalam entitas yang perlu dimodifikasi untuk meningkatkan performa model.
- **Nama entitas:** Nama entitas yang perlu dimodifikasi untuk meningkatkan performa model.
- **Detail:** Detail tentang kesalahan, peringatan, atau rekomendasi.

[!INCLUDE [footer-include](includes/footer-banner.md)]
