---
title: Ekspor data Customer Insights ke AdRoll
description: Pelajari cara mengkonfigurasi sambungan ke AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697078"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="e8ee8-103">Konektor untuk AdRoll (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="e8ee8-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="e8ee8-104">Mengekspor segmen profil pelanggan terpadu ke AdRoll dan menggunakannya untuk iklan.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e8ee8-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="e8ee8-105">Prerequisites</span></span>

-   <span data-ttu-id="e8ee8-106">Anda memiliki [akun AdRoll](https://www.adroll.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e8ee8-107">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e8ee8-108">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="e8ee8-109">Sambungkan ke AdRoll</span><span class="sxs-lookup"><span data-stu-id="e8ee8-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="e8ee8-110">Buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e8ee8-111">Dalam **AdRoll**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="e8ee8-112">Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Panel konfigurasi untuk sambungan AdRoll.":::

1. <span data-ttu-id="e8ee8-114">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e8ee8-115">Pilih **Sambungkan** untuk menginisialisasi sambungan ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="e8ee8-116">Pilih **autentikasi dengan AdRoll** dan berikan kredensial admin Anda untuk AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="e8ee8-117">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e8ee8-118">Masukkan **ID Pengiklan AdRoll** [AdRoll Dapat Beriklan](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="e8ee8-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="e8ee8-119">Pilih **berikutnya** untuk mengkonfigurasi ekspor.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e8ee8-120">Konfigurasikan konektor</span><span class="sxs-lookup"><span data-stu-id="e8ee8-120">Configure the connector</span></span>

1. <span data-ttu-id="e8ee8-121">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e8ee8-122">Ini harus diekspor ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="e8ee8-123">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-123">Select the segments you want to export.</span></span> <span data-ttu-id="e8ee8-124">Pilih segmen dengan minimal 100 anggota.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="e8ee8-125">Anda tidak dapat mengekspor segmen yang lebih kecil.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-125">You can't export smaller segments.</span></span> <span data-ttu-id="e8ee8-126">Selain itu, ukuran maksimum segmen untuk diekspor adalah 250.000 anggota per ekspor.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="e8ee8-127">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e8ee8-128">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="e8ee8-128">Export the data</span></span>

<span data-ttu-id="e8ee8-129">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e8ee8-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e8ee8-130">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e8ee8-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e8ee8-131">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="e8ee8-131">Known limitations</span></span>

- <span data-ttu-id="e8ee8-132">Anda dapat mengekspor hingga 250.000 profil per ekspor ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="e8ee8-133">Anda tidak dapat mengekspor segmen dengan kurang dari 100 profil ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="e8ee8-134">Mengekspor ke AdRoll terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="e8ee8-135">Mengekspor hingga 250.000 profil ke AdRoll dapat berlangsung hingga 10 menit untuk menyelesaikannya.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="e8ee8-136">Jumlah profil yang dapat Anda ekspor ke AdRoll tergantung dan terbatas pada kontrak Anda dengan AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e8ee8-137">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="e8ee8-137">Data privacy and compliance</span></span>

<span data-ttu-id="e8ee8-138">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke AdRoll, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e8ee8-139">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa AdRoll memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e8ee8-140">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e8ee8-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e8ee8-141">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="e8ee8-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
