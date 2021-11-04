---
title: Gambaran umum tentang skenario prediksi yang didukung
description: Prediksi dan opsi yang dicakup oleh aplikasi Dynamics 365 Customer Insights.
ms.date: 09/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 63e22bf9a457ea43c65132643681cffb295ae7e5
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673966"
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

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

- [Kehilangan transaksional](predict-transactional-churn.md): Prediksi apakah pelanggan tidak akan lagi membeli produk atau layanan Anda dalam jangka waktu tertentu.

---


## <a name="azure-machine-learning-integration"></a>Integasi Pembelajaran Mesin Azure

Jika organisasi sudah menggunakan Pembelajaran Mesin berdasarkan eksperimen Azure Pembelajaran Mesin, fitur model kustom di Customer Insights membantu menghubungkan titik-titik. Buat alur kerja yang membantu Anda memilih data yang ingin Anda hasilkan wawasannya dan petakan hasilnya ke profil pelanggan terpadu Anda. Untuk informasi lebih lanjut, lihat [model Pembelajaran Mesin kustom](custom-models.md).

## <a name="ai-builder-prediction"></a>Menggunakan prediksi AI Builder

Terkadang, himpunan data tidak lengkap dan beberapa nilai hilang. Customer Insights dapat membantu memprediksi nilai yang hilang untuk entitas dan segmen Pelanggan. Untuk informasi selengkapnya, lihat [Melengkapi data parsial Anda dengan prediksi](predictions.md).
