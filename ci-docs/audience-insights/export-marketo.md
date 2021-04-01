---
title: Ekspor data Customer Insights ke Marketo
description: Pelajari cara mengkonfigurasi sambungan ke Marketo.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597975"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="a804d-103">Konektor untuk Marketo (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="a804d-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="a804d-104">Ekspor segmen profil pelanggan terpadu untuk membuat kampanye, menyediakan pemasaran melalui email, dan gunakan grup pelanggan tertentu dengan Marketo.</span><span class="sxs-lookup"><span data-stu-id="a804d-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a804d-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="a804d-105">Prerequisites</span></span>

-   <span data-ttu-id="a804d-106">Anda memiliki [akun Marketo](https://login.marketo.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="a804d-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a804d-107">Daftar sudah ada di Marketo dan id yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="a804d-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="a804d-108">Untuk informasi lebih lanjut, lihat [daftar Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="a804d-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="a804d-109">Anda telah [mengonfigurasi segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a804d-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="a804d-110">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="a804d-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="a804d-111">Sambungkan ke Marketo</span><span class="sxs-lookup"><span data-stu-id="a804d-111">Connect to Marketo</span></span>

1. <span data-ttu-id="a804d-112">Buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="a804d-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a804d-113">Dalam **Marketo**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="a804d-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="a804d-114">Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="a804d-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a804d-115">Masukkan **[ID klien marketo anda, rahasia klien dan Hostname titik akhir REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="a804d-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="a804d-116">Masukkan **[id daftar marketo Anda](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="a804d-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="a804d-117">Pilih **saya setuju** untuk mengkonfirmasi **privasi data dan kepatuhan** dan pilih **Sambungkan** untuk menginisialisasi sambungan ke marketo.</span><span class="sxs-lookup"><span data-stu-id="a804d-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="a804d-118">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="a804d-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Mengekspor tangkapan layar untuk sambungan Marketo":::

1. <span data-ttu-id="a804d-120">Pilih **berikutnya** untuk mengkonfigurasi ekspor.</span><span class="sxs-lookup"><span data-stu-id="a804d-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="a804d-121">Konfigurasikan konektor</span><span class="sxs-lookup"><span data-stu-id="a804d-121">Configure the connector</span></span>

1. <span data-ttu-id="a804d-122">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="a804d-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="a804d-123">Atau, anda dapat mengekspor **nama depan** dan **nama belakang**, **Kota**, **Negara Bagian**, dan **Negara/Kawasan**  sebagai bidang tambahan untuk membuat email yang lebih disesuaikan.</span><span class="sxs-lookup"><span data-stu-id="a804d-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="a804d-124">Pilih **Tambah atribut** untuk memetakan bidang ini.</span><span class="sxs-lookup"><span data-stu-id="a804d-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="a804d-125">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="a804d-125">Select the segments you want to export.</span></span> <span data-ttu-id="a804d-126">Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="a804d-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Pilih bidang dan segmen untuk diekspor ke Marketo":::

1. <span data-ttu-id="a804d-128">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="a804d-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a804d-129">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="a804d-129">Export the data</span></span>

<span data-ttu-id="a804d-130">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a804d-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a804d-131">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a804d-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a804d-132">Di Marketo, Anda sekarang dapat menemukan segmen Anda dalam [daftar Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="a804d-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a804d-133">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="a804d-133">Known limitations</span></span>

- <span data-ttu-id="a804d-134">Hingga 1 juta profil per ekspor ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="a804d-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="a804d-135">Mengekspor ke Marketo terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="a804d-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="a804d-136">Mengekspor segmen dengan total 1 juta profil dapat memakan waktu hingga 3 jam.</span><span class="sxs-lookup"><span data-stu-id="a804d-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="a804d-137">Jumlah profil yang dapat Anda ekspor ke Marketo tergantung dan terbatas pada kontrak Anda dengan Marketo.</span><span class="sxs-lookup"><span data-stu-id="a804d-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a804d-138">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="a804d-138">Data privacy and compliance</span></span>

<span data-ttu-id="a804d-139">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Marketo, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="a804d-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a804d-140">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Marketo memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="a804d-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a804d-141">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a804d-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a804d-142">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="a804d-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]