---
title: Ekspor data Customer Insights ke Autopilot
description: Pelajari cara mengkonfigurasi sambungan ke Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269242"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="7189d-103">Konektor untuk Autopilot (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="7189d-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="7189d-104">Ekspor segmen profil pelanggan terpadu ke Autopilot dan gunakan untuk pemasaran email di Autopilot.</span><span class="sxs-lookup"><span data-stu-id="7189d-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="7189d-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="7189d-105">Prerequisites</span></span>

-   <span data-ttu-id="7189d-106">Anda memiliki [akun Autopilot](https://www.autopilothq.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="7189d-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7189d-107">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="7189d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="7189d-108">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="7189d-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="7189d-109">Sambungkan ke Autopilot</span><span class="sxs-lookup"><span data-stu-id="7189d-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="7189d-110">Buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="7189d-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7189d-111">Dalam **Autopilot**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="7189d-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="7189d-112">Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="7189d-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Panel konfigurasi untuk sambungan Autopilot.":::

1. <span data-ttu-id="7189d-114">Masukkan **kunci API Autopilot** [kunci API Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="7189d-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="7189d-115">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="7189d-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7189d-116">Pilih **Sambungkan** untuk menginisialisasi sambungan ke Autopilot.</span><span class="sxs-lookup"><span data-stu-id="7189d-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="7189d-117">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="7189d-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7189d-118">Pilih **berikutnya** untuk mengkonfigurasi ekspor.</span><span class="sxs-lookup"><span data-stu-id="7189d-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="7189d-119">Konfigurasikan konektor</span><span class="sxs-lookup"><span data-stu-id="7189d-119">Configure the connector</span></span>

1. <span data-ttu-id="7189d-120">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="7189d-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7189d-121">Ulangi langkah yang sama untuk bidang opsional lainnya seperti **nama depan**, **nama belakang**.</span><span class="sxs-lookup"><span data-stu-id="7189d-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="7189d-122">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="7189d-122">Select the segments you want to export.</span></span> <span data-ttu-id="7189d-123">Kami sangat **menyarankan untuk tidak mengekspor lebih dari 100'000 profil pelanggan secara total** ke Autopilot.</span><span class="sxs-lookup"><span data-stu-id="7189d-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="7189d-124">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="7189d-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7189d-125">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="7189d-125">Export the data</span></span>

<span data-ttu-id="7189d-126">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7189d-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7189d-127">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7189d-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7189d-128">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="7189d-128">Known limitations</span></span>

- <span data-ttu-id="7189d-129">Anda dapat mengekspor hingga 100.000 profil pelanggan secara total ke Autopilot.</span><span class="sxs-lookup"><span data-stu-id="7189d-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="7189d-130">Mengekspor ke Autopilot terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="7189d-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="7189d-131">Mengekspor hingga 100.000 profil ke Autopilot dapat memakan waktu hingga beberapa jam untuk menyelesaikannya.</span><span class="sxs-lookup"><span data-stu-id="7189d-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="7189d-132">Jumlah profil yang dapat Anda ekspor ke Autopilot tergantung dan terbatas pada kontrak Anda dengan Autopilot.</span><span class="sxs-lookup"><span data-stu-id="7189d-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7189d-133">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="7189d-133">Data privacy and compliance</span></span>

<span data-ttu-id="7189d-134">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Autopilot, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="7189d-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7189d-135">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Autopilot memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="7189d-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="7189d-136">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7189d-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7189d-137">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="7189d-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]