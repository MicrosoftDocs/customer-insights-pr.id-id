---
title: Gambaran umum tentang skenario prediksi yang didukung
description: Prediksi dan opsi yang dicakup oleh aplikasi Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 57c61895d636273fc90a0ac5a942fd0c9abf583c687ae20621949554e581cdf8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036013"
---
# <a name="predictions-overview"></a>Ikhtisar prediksi

Dynamics 365 Customer Insights hadir dengan berbagai opsi yang memanfaatkan AI dan Pembelajaran Mesin untuk memprediksi data. 

## <a name="out-of-box-models"></a>Model siap pakai

Cara termudah untuk memulai dengan memprediksi data adalah model yang sudah ditentukan sebelumnya, sering disebut sebagai model siap pakai. Mereka hanya memerlukan data dan struktur tertentu untuk menghasilkan wawasan dengan cepat. Saat ini, model berikut tersedia: 
- [Nilai seumur hidup pelanggan](predict-customer-lifetime-value.md): Memprediksi potensi pendapatan pelanggan di seluruh interaksi dengan bisnis. 
- [Rekomendasi produk](predict-product-recommendation.md): Menyarankan set rekomendasi produk prediktif berdasarkan perilaku pembelian dan pelanggan dengan pola pembelian yang sama.
- [Kehilangan langganan](predict-subscription-churn.md): Memprediksi apakah pelanggan berisiko karena tidak lagi menggunakan produk atau layanan langganan perusahaan Anda.
- [Kehilangan transaksional](predict-transactional-churn.md): Prediksi apakah pelanggan tidak akan lagi membeli produk atau layanan Anda dalam jangka waktu tertentu.

## <a name="azure-machine-learning-integration"></a>Integasi Pembelajaran Mesin Azure

Jika organisasi sudah menggunakan Pembelajaran Mesin berdasarkan eksperimen Azure Pembelajaran Mesin, fitur model kustom di Customer Insights membantu menghubungkan titik-titik. Buat alur kerja yang membantu Anda memilih data yang ingin Anda hasilkan wawasannya dan petakan hasilnya ke profil pelanggan terpadu Anda. Untuk informasi lebih lanjut, lihat [model Pembelajaran Mesin kustom](custom-models.md).

## <a name="ai-builder-prediction"></a>Menggunakan prediksi AI Builder

Terkadang, himpunan data tidak lengkap dan beberapa nilai hilang. Customer Insights dapat membantu memprediksi nilai yang hilang untuk entitas dan segmen Pelanggan. Untuk informasi selengkapnya, lihat [Melengkapi data parsial Anda dengan prediksi](predictions.md).
