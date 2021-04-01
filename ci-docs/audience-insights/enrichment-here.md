---
title: Pengayaan dengan pengayaan pihak ketiga HERE Technologies
description: Informasi umum tentang pengayaan pihak ketiga HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597745"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="a07a9-103">Pengayaan profil pelanggan dengan HERE Technologies (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="a07a9-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="a07a9-104">HERE Technologies adalah perusahaan platform lokasi yang menyediakan data dan layanan yang berpusat lokasi.</span><span class="sxs-lookup"><span data-stu-id="a07a9-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="a07a9-105">Dengan layanan pengayaan data HERE Technologies, Anda dapat membangun pemahaman lokasi yang lebih tepat tentang pelanggan Anda dengan normalisasi alamat, ekstraksi garis lintang dan bujur, dan banyak lagi.</span><span class="sxs-lookup"><span data-stu-id="a07a9-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a07a9-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="a07a9-106">Prerequisites</span></span>

<span data-ttu-id="a07a9-107">Untuk mengkonfigurasikan pengayaan HERE Technologies, persyaratan berikut harus dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="a07a9-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a07a9-108">Anda memiliki langganan aktif HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a07a9-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="a07a9-109">Untuk mendapatkan langganan, Anda dapat [mendaftar di sini](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) atau [hubungi langsung HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="a07a9-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="a07a9-110">Selengkapnya tentang pengayaan lokasi HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a07a9-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="a07a9-111">Anda memiliki kunci API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a07a9-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="a07a9-112">Anda memiliki izin [administratif](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="a07a9-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="a07a9-113">Konfigurasi</span><span class="sxs-lookup"><span data-stu-id="a07a9-113">Configuration</span></span>

1. <span data-ttu-id="a07a9-114">Buka **Data** > **Pengayaan**.</span><span class="sxs-lookup"><span data-stu-id="a07a9-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="a07a9-115">Pilih **Perkaya data saya** di petak HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a07a9-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a07a9-116">![petak HERE Technologies](media/HERE-tile.png "petak HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="a07a9-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="a07a9-117">Masukkan **kunci API aktif HERE Technologies**.</span><span class="sxs-lookup"><span data-stu-id="a07a9-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="a07a9-118">Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="a07a9-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="a07a9-119">Konfirmasikan kedua input dengan memilih **Sambungkan ke HERE**.</span><span class="sxs-lookup"><span data-stu-id="a07a9-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="a07a9-120">Pilih **Tambah data** dan pilih **himpunan data Pelanggan** yang anda ingin perkaya dengan data lokasi dari HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a07a9-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="a07a9-121">Anda dapat memilih entitas **Pelanggan** untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="a07a9-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Tangkapan layar saat memilih himpunan data pelanggan.":::

1. <span data-ttu-id="a07a9-123">Pilih jika Anda ingin memetakan bidang ke alamat utama dan/atau sekunder.</span><span class="sxs-lookup"><span data-stu-id="a07a9-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="a07a9-124">Anda dapat menentukan pemetaan bidang untuk kedua alamat (misalnya, alamat rumah dan bisnis) dan memperkaya profil untuk kedua alamat secara terpisah.</span><span class="sxs-lookup"><span data-stu-id="a07a9-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="a07a9-125">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="a07a9-125">Select **Next**.</span></span>

1. <span data-ttu-id="a07a9-126">Tentukan bidang dari profil terpadu mana yang harus digunakan untuk mencari data lokasi yang cocok dari HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a07a9-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="a07a9-127">Bidang **jalan 1** dan **Kode Zip/Pos** diperlukan untuk alamat utama dan/atau sekunder yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="a07a9-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="a07a9-128">Untuk akurasi kecocokan yang lebih tinggi, lebih banyak bidang dapat ditambahkan.</span><span class="sxs-lookup"><span data-stu-id="a07a9-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a07a9-129">![Halaman konfigurasi pengayaan HERE Technologies](media/enrichment-HERE-configuration.png "Halaman konfigurasi pengayaan HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="a07a9-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="a07a9-130">Pilih **Terapkan** untuk menyelesaikan pemetaan bidang.</span><span class="sxs-lookup"><span data-stu-id="a07a9-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="a07a9-131">Hasil pengayaan</span><span class="sxs-lookup"><span data-stu-id="a07a9-131">Enrichment results</span></span>

<span data-ttu-id="a07a9-132">Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="a07a9-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a07a9-133">Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a07a9-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a07a9-134">Waktu pemrosesan akan tergantung pada ukuran data pelanggan dan waktu respons API dari HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="a07a9-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="a07a9-135">Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan baru yang diperkaya di dalam **pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="a07a9-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="a07a9-136">Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="a07a9-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a07a9-137">Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.</span><span class="sxs-lookup"><span data-stu-id="a07a9-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a07a9-138">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="a07a9-138">Next steps</span></span>

<span data-ttu-id="a07a9-139">Bangun di atas data pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="a07a9-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a07a9-140">Buat [segmen](segments.md), [tindakan](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan bagi pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="a07a9-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a07a9-141">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="a07a9-141">Data privacy and compliance</span></span>

<span data-ttu-id="a07a9-142">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke HERE Technologies, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="a07a9-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a07a9-143">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa HERE Technologies memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="a07a9-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a07a9-144">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a07a9-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a07a9-145">Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="a07a9-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]