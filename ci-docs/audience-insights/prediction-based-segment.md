---
title: Segmen berdasarkan output prediksi
description: Buat segmen berdasarkan entitas output model prediksi.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0b3357cdf3c049bd92f6c3f690f27433df9117b
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226667"
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

1. Pilih elipsis vertikal di samping model yang ingin Anda tinjau dan pilih **Tampilkan**.

1. Pada halaman hasil, pilih **Buat segmen**. Untuk informasi selengkapnya tentang halaman hasil, tinjau artikel tentang model tersebut.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Cuplikan layar halaman hasil prediksi dengan sorotan pada tindakan Buat segmen.":::

1. Buat segmen baru berdasarkan entitas output model yang dipilih. Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).