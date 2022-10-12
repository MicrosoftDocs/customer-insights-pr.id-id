---
title: Membuat segmen berdasarkan model prediksi
description: Buat segmen berdasarkan entitas output model prediksi.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610424"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Membuat segmen berdasarkan model prediksi (pratinjau)

Hasil prediksi terkadang hanya berlaku untuk subkumpulan pelanggan Anda. Tingkatkan personalisasi rekomendasi dengan membuat segmen dari hasil model prediksi. Misalnya, Anda mungkin ingin memberikan rekomendasi khusus kepada pelanggan yang lebih suka jenis layanan tertentu.

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md) di Customer Insights.

- Rekomendasi produk, kehilangan transaksi, kehilangan langganan, atau model nilai seumur hidup pelanggan yang dikonfigurasi di Customer Insights. Tinjau persyaratan untuk menyiapkan model yang berbeda:

  - [Model rekomendasi produk](predict-product-recommendation.md)
  - [Model kehilangan langganan](predict-subscription-churn.md)
  - [Model kehilangan transaksi](predict-transactional-churn.md)
  - [Nilai masa pakai pelanggan](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Membuat segmen pelanggan berdasarkan prediksi

1. Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.

1. Pilih model yang ingin Anda tinjau dan pilih **Lihat**.

1. Pada halaman hasil, pilih **Buat segmen**. Untuk informasi selengkapnya tentang halaman hasil, tinjau artikel tentang model tersebut.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Cuplikan layar halaman hasil prediksi dengan sorotan pada tindakan Buat segmen.":::

1. Buat segmen baru menggunakan atribut dari entitas output dari model yang dipilih. Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).

> [!TIP]
> Anda juga dapat membuat segmen untuk model prediksi dari **halaman Segmen** dengan **memilih Baru** dan memilih **Buat dari** > **Kecerdasan**. Untuk informasi selengkapnya, lihat [Membuat segmen baru dengan segmen](segment-quick.md) cepat.

[!INCLUDE [footer-include](includes/footer-banner.md)]
