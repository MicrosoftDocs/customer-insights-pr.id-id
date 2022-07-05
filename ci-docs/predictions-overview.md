---
title: Ikhtisar prediksi
description: Prediksi dan opsi yang dicakup oleh aplikasi Dynamics 365 Customer Insights.
ms.date: 03/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: a87af80fa713a1ac70493345c0c920e416692b0f
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083101"
---
# <a name="predictions-overview"></a>Ikhtisar prediksi

Dynamics 365 Customer Insights hadir dengan berbagai opsi yang memanfaatkan AI dan Pembelajaran Mesin untuk memprediksi data. 

## <a name="out-of-box-models"></a>Model siap pakai

Cara termudah untuk memulai dengan memprediksi data adalah model yang sudah ditentukan sebelumnya, sering disebut sebagai model siap pakai. Mereka hanya memerlukan data dan struktur tertentu untuk menghasilkan wawasan dengan cepat. Saat ini, model berikut tersedia: 

# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

- [Nilai seumur hidup pelanggan](predict-customer-lifetime-value.md): Memprediksi potensi pendapatan pelanggan di seluruh interaksi dengan bisnis.
- [Rekomendasi produk](predict-product-recommendation.md): Menyarankan set rekomendasi produk prediktif berdasarkan perilaku pembelian dan pelanggan dengan pola pembelian yang sama.
- [Kehilangan langganan](predict-subscription-churn.md): Memprediksi apakah pelanggan berisiko karena tidak lagi menggunakan produk atau layanan langganan perusahaan Anda.
- [Kehilangan transaksional](predict-transactional-churn.md): Prediksi apakah pelanggan tidak akan lagi membeli produk atau layanan Anda dalam jangka waktu tertentu.
- [Analisis sentimen](sentiment-analysis.md): Menganalisis sentimen umpan balik pelanggan dan mengidentifikasi aspek bisnis yang sering disebutkan.

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

- [Kehilangan transaksional](predict-transactional-churn.md): Prediksi apakah pelanggan tidak akan lagi membeli produk atau layanan Anda dalam jangka waktu tertentu.

---

> [!TIP]
> Sebaiknya refresh model out-of-the-box secara teratur dengan data yang diperbarui untuk memastikan model tersebut menginformasikan kasus penggunaan bisnis Anda secara akurat. Data disegarkan secara ad-hoc saat sistem menyerap sumber data baru atau yang diperbarui. Namun, model hanya akan menggarisbawahi ulang dalam kasus ini dan terus menggunakan data pelatihan yang ada.
> 
> Anda dapat mengonfigurasi **jadwal** Pembaruan dengan mengatur jadwal pelatihan ulang model dalam pengalaman konfigurasi. Model akan melatih kembali dan menggarisbawahi ulang pada jadwal ini, yang dapat Anda ubah kapan saja.


## <a name="azure-machine-learning-integration"></a>Integasi Pembelajaran Mesin Azure

Jika organisasi sudah menggunakan Pembelajaran Mesin berdasarkan eksperimen Azure Pembelajaran Mesin, fitur model kustom di Customer Insights membantu menghubungkan titik-titik. Buat alur kerja yang membantu Anda memilih data yang ingin Anda hasilkan wawasannya dan petakan hasilnya ke profil pelanggan terpadu Anda. Untuk informasi lebih lanjut, lihat [model Pembelajaran Mesin kustom](custom-models.md).

## <a name="ai-builder-prediction"></a>AI Builder prediksi

Terkadang, himpunan data tidak lengkap dan beberapa nilai hilang. Customer Insights dapat membantu memprediksi nilai yang hilang untuk entitas dan segmen Pelanggan. Untuk informasi selengkapnya, lihat [Melengkapi data parsial Anda dengan prediksi](predictions.md).
