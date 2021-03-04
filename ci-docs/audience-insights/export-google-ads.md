---
title: Ekspor data Customer Insights ke Google Ads
description: Pelajari cara mengkonfigurasi sambungan ke Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268966"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="661ce-103">Konektor untuk Google Ads (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="661ce-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="661ce-104">Ekspor segmen profil pelanggan terpadu ke daftar audiens Google Ads dan gunakan untuk beriklan di Google Search, Gmail, YouTube, dan Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="661ce-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="661ce-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="661ce-105">Prerequisites</span></span>

-   <span data-ttu-id="661ce-106">Anda memiliki [akun Google Ads](https://ads.google.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="661ce-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="661ce-107">Audiens sudah ada di Google Ads dan id yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="661ce-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="661ce-108">Untuk informasi lebih lanjut, lihat [audiens Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="661ce-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="661ce-109">Anda telah [mengonfigurasi segmen](segments.md)</span><span class="sxs-lookup"><span data-stu-id="661ce-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="661ce-110">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email, nama depan, dan nama belakang</span><span class="sxs-lookup"><span data-stu-id="661ce-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="661ce-111">Sambungkan ke Google Ads</span><span class="sxs-lookup"><span data-stu-id="661ce-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="661ce-112">Buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="661ce-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="661ce-113">Di dalam **Google Ads**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="661ce-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="661ce-114">Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="661ce-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="661ce-115">Masukkan **[ID pelanggan Google Ads](https://support.google.com/google-ads/answer/1704344)** Anda.</span><span class="sxs-lookup"><span data-stu-id="661ce-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="661ce-116">Masukkan **[token Developer yang disetujui Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="661ce-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="661ce-117">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="661ce-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="661ce-118">Masukkan **[ID audiens dan google ads anda](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**, lalu pilih **sambungkan** untuk menginisialisasi sambungan ke google ads.</span><span class="sxs-lookup"><span data-stu-id="661ce-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="661ce-119">Pilih **autentikasi dengan Google Ads** dan berikan kredensial Google Ads Anda.</span><span class="sxs-lookup"><span data-stu-id="661ce-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="661ce-120">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="661ce-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Mengekspor tangkapan layar untuk sambungan Google Ads":::

1. <span data-ttu-id="661ce-122">Pilih **berikutnya** untuk mengkonfigurasi ekspor.</span><span class="sxs-lookup"><span data-stu-id="661ce-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="661ce-123">Konfigurasikan konektor</span><span class="sxs-lookup"><span data-stu-id="661ce-123">Configure the connector</span></span>

1. <span data-ttu-id="661ce-124">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="661ce-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="661ce-125">Ulangi langkah yang sama untuk bidang **nama depan** dan **nama belakang**.</span><span class="sxs-lookup"><span data-stu-id="661ce-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="661ce-126">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="661ce-126">Select the segments you want to export.</span></span> <span data-ttu-id="661ce-127">Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke Google Ads.</span><span class="sxs-lookup"><span data-stu-id="661ce-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="661ce-128">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="661ce-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="661ce-129">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="661ce-129">Export the data</span></span>

<span data-ttu-id="661ce-130">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="661ce-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="661ce-131">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="661ce-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="661ce-132">Di Google Ads, Anda sekarang dapat menemukan segmen Anda dalam [audiens Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="661ce-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="661ce-133">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="661ce-133">Known limitations</span></span>

- <span data-ttu-id="661ce-134">Hingga 1 juta profil per ekspor ke Google Ads.</span><span class="sxs-lookup"><span data-stu-id="661ce-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="661ce-135">Mengekspor ke Google Ads.terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="661ce-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="661ce-136">Mengekspor segmen dengan total 1 juta profil dapat memakan waktu hingga 5 menit karena keterbatasan pada sisi Provider.</span><span class="sxs-lookup"><span data-stu-id="661ce-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="661ce-137">Pencocokan di Google Ads dapat berlangsung hingga 48 jam.</span><span class="sxs-lookup"><span data-stu-id="661ce-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="661ce-138">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="661ce-138">Data privacy and compliance</span></span>

<span data-ttu-id="661ce-139">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Google Ads, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="661ce-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="661ce-140">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Google Ads memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="661ce-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="661ce-141">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="661ce-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="661ce-142">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="661ce-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]