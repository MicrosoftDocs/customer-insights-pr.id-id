---
title: Ekspor data Customer Insights ke Mailchimp
description: Pelajari cara mengkonfigurasi sambungan ke Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406041"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="bc016-103">Konektor untuk Mailchimp (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="bc016-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="bc016-104">Ekspor segmen profil pelanggan terpadu ke MailChimp untuk membuat kampanye newsletter dan email.</span><span class="sxs-lookup"><span data-stu-id="bc016-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bc016-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="bc016-105">Prerequisites</span></span>

-   <span data-ttu-id="bc016-106">Anda memiliki [akun Mailchimp](https://mailchimp.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="bc016-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bc016-107">Audiens sudah ada di Mailchimp dan id yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="bc016-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="bc016-108">Untuk informasi lebih lanjut, lihat [audiens Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="bc016-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="bc016-109">Anda telah [mengonfigurasi segmen](segments.md)</span><span class="sxs-lookup"><span data-stu-id="bc016-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="bc016-110">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="bc016-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="bc016-111">Hubungkan ke Mailchimp</span><span class="sxs-lookup"><span data-stu-id="bc016-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="bc016-112">Buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="bc016-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bc016-113">Dalam **Mailchimp**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="bc016-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="bc016-114">Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="bc016-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="bc016-115">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="bc016-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bc016-116">Masukkan **[ID audiens Mailchimp](https://mailchimp.com/help/find-audience-id/)**, lalu pilih **sambungkan** untuk menginisialisasi sambungan ke Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bc016-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="bc016-117">Pilih **autentikasi dengan Mailchimp** dan berikan kredensial Mailchimp Anda.</span><span class="sxs-lookup"><span data-stu-id="bc016-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="bc016-118">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="bc016-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Mengekspor tangkapan layar untuk sambungan Mailchimp":::

1. <span data-ttu-id="bc016-120">Pilih **berikutnya** untuk mengkonfigurasi ekspor.</span><span class="sxs-lookup"><span data-stu-id="bc016-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="bc016-121">Konfigurasikan konektor</span><span class="sxs-lookup"><span data-stu-id="bc016-121">Configure the connector</span></span>

1. <span data-ttu-id="bc016-122">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="bc016-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="bc016-123">Atau, anda dapat mengekspor **nama depan** dan **nama belakang** sebagai bidang tambahan untuk membuat email yang lebih disesuaikan.</span><span class="sxs-lookup"><span data-stu-id="bc016-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="bc016-124">Pilih **Tambah atribut** untuk memetakan bidang ini.</span><span class="sxs-lookup"><span data-stu-id="bc016-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="bc016-125">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="bc016-125">Select the segments you want to export.</span></span> <span data-ttu-id="bc016-126">Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bc016-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Pilih bidang dan segmen untuk diekspor ke MailChimp":::

1. <span data-ttu-id="bc016-128">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="bc016-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="bc016-129">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="bc016-129">Export the data</span></span>

<span data-ttu-id="bc016-130">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bc016-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="bc016-131">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bc016-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bc016-132">Di Mailchimp, Anda sekarang dapat menemukan segmen Anda dalam [audiens Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="bc016-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bc016-133">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="bc016-133">Known limitations</span></span>

- <span data-ttu-id="bc016-134">Hingga 1 juta profil per ekspor ke Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bc016-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="bc016-135">Mengekspor ke Mailchimp terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="bc016-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="bc016-136">Mengekspor segmen dengan total 1 juta profil dapat memakan waktu hingga tiga jam karena keterbatasan pada sisi Provider.</span><span class="sxs-lookup"><span data-stu-id="bc016-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="bc016-137">Jumlah profil yang dapat Anda ekspor ke Mailchimp tergantung dan terbatas pada kontrak Anda dengan Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="bc016-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bc016-138">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="bc016-138">Data privacy and compliance</span></span>

<span data-ttu-id="bc016-139">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Mailchimp, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="bc016-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bc016-140">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Mailchimp memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="bc016-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bc016-141">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bc016-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bc016-142">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="bc016-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
