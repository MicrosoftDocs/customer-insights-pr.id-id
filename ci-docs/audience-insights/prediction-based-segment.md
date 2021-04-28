---
title: Segmen berdasarkan output prediksi
description: Buat segmen berdasarkan entitas output model prediksi.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741433"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="f9d05-103">Membuat segmen berdasarkan model prediksi (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="f9d05-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="f9d05-104">Hasil prediksi terkadang hanya berlaku untuk subkumpulan pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="f9d05-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="f9d05-105">Tingkatkan personalisasi rekomendasi dengan membuat segmen dari hasil model prediksi.</span><span class="sxs-lookup"><span data-stu-id="f9d05-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="f9d05-106">Misalnya, Anda mungkin ingin memberikan rekomendasi khusus kepada pelanggan yang lebih suka jenis layanan tertentu.</span><span class="sxs-lookup"><span data-stu-id="f9d05-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f9d05-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="f9d05-107">Prerequisites</span></span>

- <span data-ttu-id="f9d05-108">Sekurangnya [izin kontributor](permissions.md) di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f9d05-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="f9d05-109">Rekomendasi produk, kehilangan transaksi, kehilangan langganan, atau model nilai seumur hidup pelanggan yang dikonfigurasi di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f9d05-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="f9d05-110">Tinjau persyaratan untuk menyiapkan model yang berbeda:</span><span class="sxs-lookup"><span data-stu-id="f9d05-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="f9d05-111">Model rekomendasi produk</span><span class="sxs-lookup"><span data-stu-id="f9d05-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="f9d05-112">Model kehilangan langganan</span><span class="sxs-lookup"><span data-stu-id="f9d05-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="f9d05-113">Model kehilangan transaksi</span><span class="sxs-lookup"><span data-stu-id="f9d05-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="f9d05-114">Nilai masa pakai pelanggan</span><span class="sxs-lookup"><span data-stu-id="f9d05-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="f9d05-115">Membuat segmen pelanggan berdasarkan prediksi</span><span class="sxs-lookup"><span data-stu-id="f9d05-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="f9d05-116">Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.</span><span class="sxs-lookup"><span data-stu-id="f9d05-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="f9d05-117">Pilih elipsis vertikal di samping model yang ingin Anda tinjau dan pilih **Tampilkan**.</span><span class="sxs-lookup"><span data-stu-id="f9d05-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="f9d05-118">Pada halaman hasil, pilih **Buat segmen**.</span><span class="sxs-lookup"><span data-stu-id="f9d05-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="f9d05-119">Untuk informasi selengkapnya tentang halaman hasil, tinjau artikel tentang model tersebut.</span><span class="sxs-lookup"><span data-stu-id="f9d05-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Cuplikan layar halaman hasil prediksi dengan sorotan pada tindakan Buat segmen.":::

1. <span data-ttu-id="f9d05-121">Buat segmen baru berdasarkan entitas output model yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="f9d05-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="f9d05-122">Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f9d05-122">For more information, see [Create and manage segments](segments.md).</span></span>