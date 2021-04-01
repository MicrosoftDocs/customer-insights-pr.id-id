---
title: Ekspor data Customer Insights ke SendGrid
description: Pelajari cara mengkonfigurasi sambungan ke SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597285"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="19b3b-103">Konektor untuk SendGrid (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="19b3b-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="19b3b-104">Ekspor segmen profil pelanggan terpadu ke daftar kontak SendGrid dan gunakan untuk kampanye dan pemasaran email di SendGrid.</span><span class="sxs-lookup"><span data-stu-id="19b3b-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="19b3b-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="19b3b-105">Prerequisites</span></span>

-   <span data-ttu-id="19b3b-106">Anda memiliki [akun SendGrid](https://sendgrid.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="19b3b-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="19b3b-107">Daftar kontak sudah ada di SendGrid dan id yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="19b3b-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="19b3b-108">Untuk informasi lebih lanjut, lihat [SendGrid - Mengelola kontak](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="19b3b-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="19b3b-109">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="19b3b-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="19b3b-110">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="19b3b-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="19b3b-111">Sambungkan ke SendGrid</span><span class="sxs-lookup"><span data-stu-id="19b3b-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="19b3b-112">Buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="19b3b-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="19b3b-113">Dalam **SendGrid**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="19b3b-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="19b3b-114">Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="19b3b-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Panel konfigurasi ekspor SendGrid.":::

1. <span data-ttu-id="19b3b-116">Masukkan **kunci API SendGrid** [kunci API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) Anda.</span><span class="sxs-lookup"><span data-stu-id="19b3b-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="19b3b-117">Masukkan **[id daftar SendGrid Anda](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="19b3b-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="19b3b-118">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="19b3b-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="19b3b-119">Pilih **Sambungkan** untuk menginisialisasi sambungan ke SendGrid.</span><span class="sxs-lookup"><span data-stu-id="19b3b-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="19b3b-120">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="19b3b-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="19b3b-121">Pilih **berikutnya** untuk mengkonfigurasi ekspor.</span><span class="sxs-lookup"><span data-stu-id="19b3b-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="19b3b-122">Konfigurasikan konektor</span><span class="sxs-lookup"><span data-stu-id="19b3b-122">Configure the connector</span></span>

1. <span data-ttu-id="19b3b-123">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="19b3b-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="19b3b-124">Ulangi langkah yang sama untuk bidang opsional lainnya seperti **nama depan**, **nama belakang**, **negara/Kawasan**, **Negara Bagian**, **Kota**, dan **Kode pos**.</span><span class="sxs-lookup"><span data-stu-id="19b3b-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="19b3b-125">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="19b3b-125">Select the segments you want to export.</span></span> <span data-ttu-id="19b3b-126">Kami sangat **menyarankan untuk tidak mengekspor lebih dari 100'000 profil pelanggan secara total** ke SendGrid.</span><span class="sxs-lookup"><span data-stu-id="19b3b-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="19b3b-127">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="19b3b-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="19b3b-128">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="19b3b-128">Export the data</span></span>

<span data-ttu-id="19b3b-129">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="19b3b-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="19b3b-130">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="19b3b-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="19b3b-131">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="19b3b-131">Known limitations</span></span>

- <span data-ttu-id="19b3b-132">Hingga 100.000 profil secara total ke SendGrid.</span><span class="sxs-lookup"><span data-stu-id="19b3b-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="19b3b-133">Mengekspor ke SendGrid terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="19b3b-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="19b3b-134">Mengekspor hingga 100.000 profil ke SendGrid dapat memakan waktu hingga beberapa jam untuk menyelesaikannya.</span><span class="sxs-lookup"><span data-stu-id="19b3b-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="19b3b-135">Jumlah profil yang dapat Anda ekspor ke SendGrid tergantung dan terbatas pada kontrak Anda dengan SendGrid.</span><span class="sxs-lookup"><span data-stu-id="19b3b-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="19b3b-136">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="19b3b-136">Data privacy and compliance</span></span>

<span data-ttu-id="19b3b-137">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke SendGrid, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="19b3b-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="19b3b-138">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa SendGrid memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="19b3b-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="19b3b-139">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="19b3b-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="19b3b-140">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="19b3b-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]