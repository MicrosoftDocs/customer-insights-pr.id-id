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
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095719"
---
# <a name="predictions-overview"></a><span data-ttu-id="563f9-103">Ikhtisar prediksi</span><span class="sxs-lookup"><span data-stu-id="563f9-103">Predictions overview</span></span>

<span data-ttu-id="563f9-104">Dynamics 365 Customer Insights hadir dengan berbagai opsi yang memanfaatkan AI dan Pembelajaran Mesin untuk memprediksi data.</span><span class="sxs-lookup"><span data-stu-id="563f9-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="563f9-105">Model siap pakai</span><span class="sxs-lookup"><span data-stu-id="563f9-105">Out-of-box models</span></span>

<span data-ttu-id="563f9-106">Cara termudah untuk memulai dengan memprediksi data adalah model yang sudah ditentukan sebelumnya, sering disebut sebagai model siap pakai.</span><span class="sxs-lookup"><span data-stu-id="563f9-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="563f9-107">Mereka hanya memerlukan data dan struktur tertentu untuk menghasilkan wawasan dengan cepat.</span><span class="sxs-lookup"><span data-stu-id="563f9-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="563f9-108">Saat ini, model berikut tersedia:</span><span class="sxs-lookup"><span data-stu-id="563f9-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="563f9-109">[Nilai seumur hidup pelanggan](predict-customer-lifetime-value.md): Memprediksi potensi pendapatan pelanggan di seluruh interaksi dengan bisnis.</span><span class="sxs-lookup"><span data-stu-id="563f9-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="563f9-110">[Rekomendasi produk](predict-product-recommendation.md): Menyarankan set rekomendasi produk prediktif berdasarkan perilaku pembelian dan pelanggan dengan pola pembelian yang sama.</span><span class="sxs-lookup"><span data-stu-id="563f9-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="563f9-111">[Kehilangan langganan](predict-subscription-churn.md): Memprediksi apakah pelanggan berisiko karena tidak lagi menggunakan produk atau layanan langganan perusahaan Anda.</span><span class="sxs-lookup"><span data-stu-id="563f9-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="563f9-112">[Kehilangan transaksional](predict-transactional-churn.md): Prediksi apakah pelanggan tidak akan lagi membeli produk atau layanan Anda dalam jangka waktu tertentu.</span><span class="sxs-lookup"><span data-stu-id="563f9-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="563f9-113">Integasi Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="563f9-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="563f9-114">Jika organisasi sudah menggunakan Pembelajaran Mesin berdasarkan eksperimen Azure Pembelajaran Mesin, fitur model kustom di Customer Insights membantu menghubungkan titik-titik.</span><span class="sxs-lookup"><span data-stu-id="563f9-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="563f9-115">Buat alur kerja yang membantu Anda memilih data yang ingin Anda hasilkan wawasannya dan petakan hasilnya ke profil pelanggan terpadu Anda.</span><span class="sxs-lookup"><span data-stu-id="563f9-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="563f9-116">Untuk informasi lebih lanjut, lihat [model Pembelajaran Mesin kustom](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="563f9-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="563f9-117">Menggunakan prediksi AI Builder</span><span class="sxs-lookup"><span data-stu-id="563f9-117">AI Builder prediction</span></span>

<span data-ttu-id="563f9-118">Terkadang, himpunan data tidak lengkap dan beberapa nilai hilang.</span><span class="sxs-lookup"><span data-stu-id="563f9-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="563f9-119">Customer Insights dapat membantu memprediksi nilai yang hilang untuk entitas dan segmen Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="563f9-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="563f9-120">Untuk informasi selengkapnya, lihat [Melengkapi data parsial Anda dengan prediksi](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="563f9-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
