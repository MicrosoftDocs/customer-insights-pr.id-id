---
title: Pengayaan profil perusahaan dengan pengayaan pihak ketiga Leadspace
description: Informasi umum tentang pengayaan pihak ketiga Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597653"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="78a5e-103">Pengayaan profil perusahaan dengan Leadspace (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="78a5e-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="78a5e-104">Leadspace adalah perusahaan ilmu data yang menyediakan platform data pelanggan B2B.</span><span class="sxs-lookup"><span data-stu-id="78a5e-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="78a5e-105">Hal ini memungkinkan pelanggan dengan profil pelanggan terpadu untuk perusahaan untuk memperkaya data mereka.</span><span class="sxs-lookup"><span data-stu-id="78a5e-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="78a5e-106">Pengayaan mencakup atribut tambahan seperti ukuran perusahaan, lokasi, industri, dan lainnya.</span><span class="sxs-lookup"><span data-stu-id="78a5e-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="78a5e-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="78a5e-107">Prerequisites</span></span>

<span data-ttu-id="78a5e-108">Untuk mengonfigurasikan Leadspace, prasyarat berikut harus dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="78a5e-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="78a5e-109">Anda memiliki lisensi Leadspace aktif dan "kunci permanen" (disebut sebagai **token leadspace**).</span><span class="sxs-lookup"><span data-stu-id="78a5e-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="78a5e-110">Hubungi langsung [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) untuk rincian tentang produk mereka.</span><span class="sxs-lookup"><span data-stu-id="78a5e-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="78a5e-111">Anda memiliki izin [administratif](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="78a5e-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="78a5e-112">Anda memiliki [profil pelanggan terpadu](customer-profiles.md) untuk perusahaan.</span><span class="sxs-lookup"><span data-stu-id="78a5e-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="78a5e-113">Konfigurasi</span><span class="sxs-lookup"><span data-stu-id="78a5e-113">Configuration</span></span>

1. <span data-ttu-id="78a5e-114">Di wawasan audiens, buka **Data** > **pengayaan**.</span><span class="sxs-lookup"><span data-stu-id="78a5e-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="78a5e-115">Pilih **Perkaya data saya** di ubin Leadspace.</span><span class="sxs-lookup"><span data-stu-id="78a5e-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Tangkapan layar petak Leadspace.":::

1. <span data-ttu-id="78a5e-117">Pilih **persiapan,** lalu masukkan **token leadspace** aktif (kunci permanen).</span><span class="sxs-lookup"><span data-stu-id="78a5e-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="78a5e-118">Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="78a5e-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="78a5e-119">Konfirmasikan kedua input dengan memilih **Sambungkan ke Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="78a5e-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="78a5e-120">Pilih **Petakan data** dan pilih himpunan data yang anda ingin perkaya dengan data perusahaan dari Leadspace.</span><span class="sxs-lookup"><span data-stu-id="78a5e-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="78a5e-121">Anda dapat memilih entitas *Pelanggan* untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="78a5e-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Pilih antara profil pelanggan dan pengayaan segmen.":::

1. <span data-ttu-id="78a5e-123">Klik **selanjutnya** dan tentukan bidang mana dari profil terpadu yang Anda harus gunakan untuk mencari data perusahaan yang cocok dari leadspace.</span><span class="sxs-lookup"><span data-stu-id="78a5e-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="78a5e-124">Bidang **Nama perusahaan** diperlukan.</span><span class="sxs-lookup"><span data-stu-id="78a5e-124">The **Name of company** field is required.</span></span> <span data-ttu-id="78a5e-125">Untuk akurasi kecocokan yang lebih tinggi, hingga dua bidang lainnya, **situs web perusahaan** dan **lokasi perusahaan**, dapat ditambahkan.</span><span class="sxs-lookup"><span data-stu-id="78a5e-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel pemetaan bidang leadspace.":::
   
1. <span data-ttu-id="78a5e-127">Pilih **Terapkan** untuk menyelesaikan pemetaan bidang.</span><span class="sxs-lookup"><span data-stu-id="78a5e-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="78a5e-128">Pilih **Jalankan** untuk memperkaya profil perusahaan.</span><span class="sxs-lookup"><span data-stu-id="78a5e-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="78a5e-129">Berapa lama pengayaan diperlukan tergantung pada jumlah profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="78a5e-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="78a5e-130">Hasil pengayaan</span><span class="sxs-lookup"><span data-stu-id="78a5e-130">Enrichment results</span></span>

<span data-ttu-id="78a5e-131">Setelah menyegarkan pengayaan, Anda dapat meninjau data perusahaan yang diperkaya di dalam [pengayaan saya](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="78a5e-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="78a5e-132">Anda dapat menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="78a5e-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="78a5e-133">Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.</span><span class="sxs-lookup"><span data-stu-id="78a5e-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="78a5e-134">Untuk informasi lebih lanjut, lihat [api leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="78a5e-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="78a5e-135">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="78a5e-135">Next steps</span></span>

<span data-ttu-id="78a5e-136">Bangun di atas data pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="78a5e-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="78a5e-137">Buat [segmen](segments.md), [tindakan](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan bagi pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="78a5e-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="78a5e-138">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="78a5e-138">Data privacy and compliance</span></span>

<span data-ttu-id="78a5e-139">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Leadspace, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="78a5e-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="78a5e-140">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Leadspace memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="78a5e-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="78a5e-141">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="78a5e-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="78a5e-142">Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="78a5e-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]