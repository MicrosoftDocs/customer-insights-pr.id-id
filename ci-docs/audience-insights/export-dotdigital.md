---
title: Ekspor data Customer Insights ke DotDigital
description: Pelajari cara mengkonfigurasi sambungan ke DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269104"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="94c67-103">Konektor untuk DotDigital (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="94c67-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="94c67-104">Ekspor segmen profil pelanggan terpadu ke buku alamat DotDigital dan gunakan untuk kampanye, pemasaran email, dan untuk membangun segmen pelanggan dengan DotDigital.</span><span class="sxs-lookup"><span data-stu-id="94c67-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="94c67-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="94c67-105">Prerequisites</span></span>

-   <span data-ttu-id="94c67-106">Anda memiliki [akun dotdigital](https://dotdigital.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="94c67-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="94c67-107">Buku alamat sudah ada di DotDigital dan id yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="94c67-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="94c67-108">ID dapat ditemukan di URL saat Anda memilih dan membuka buku alamat.</span><span class="sxs-lookup"><span data-stu-id="94c67-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="94c67-109">Untuk informasi lebih lanjut, lihat [buku alamat dotdigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="94c67-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="94c67-110">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="94c67-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="94c67-111">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="94c67-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="94c67-112">Menyambung ke DotDigital</span><span class="sxs-lookup"><span data-stu-id="94c67-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="94c67-113">Buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="94c67-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="94c67-114">Dalam **dotdigital**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="94c67-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="94c67-115">Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="94c67-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Konfigurasi panel untuk ekspor DotDigital.":::

1. <span data-ttu-id="94c67-117">Masukkan **nama pengguna dan sandi DotDigital** Anda.</span><span class="sxs-lookup"><span data-stu-id="94c67-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="94c67-118">Masukkan **[id buku alamat dotdigital Anda](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="94c67-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="94c67-119">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="94c67-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="94c67-120">Pilih **Sambungkan** untuk menginisialisasi sambungan ke dotdigital.</span><span class="sxs-lookup"><span data-stu-id="94c67-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="94c67-121">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="94c67-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="94c67-122">Pilih **berikutnya** untuk mengkonfigurasi ekspor.</span><span class="sxs-lookup"><span data-stu-id="94c67-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="94c67-123">Konfigurasikan konektor</span><span class="sxs-lookup"><span data-stu-id="94c67-123">Configure the connector</span></span>

1. <span data-ttu-id="94c67-124">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="94c67-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="94c67-125">Ulangi langkah yang sama untuk bidang opsional lainnya seperti **nama depan**, **nama belakang**, **nama lengkap**, **jenis kelamin**, dan **kode posting**.</span><span class="sxs-lookup"><span data-stu-id="94c67-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="94c67-126">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="94c67-126">Select the segments you want to export.</span></span> <span data-ttu-id="94c67-127">Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke DotDigital.</span><span class="sxs-lookup"><span data-stu-id="94c67-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="94c67-128">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="94c67-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="94c67-129">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="94c67-129">Export the data</span></span>

<span data-ttu-id="94c67-130">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="94c67-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="94c67-131">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="94c67-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="94c67-132">Di DotDigital, Anda sekarang dapat menemukan segmen dalam [buku alamat dotdigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="94c67-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="94c67-133">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="94c67-133">Known limitations</span></span>

- <span data-ttu-id="94c67-134">Hingga 1 juta profil per ekspor ke DotDigital.</span><span class="sxs-lookup"><span data-stu-id="94c67-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="94c67-135">Mengekspor ke DotDigital terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="94c67-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="94c67-136">Mengekspor segmen dengan total 1 juta profil dapat memakan waktu hingga 3 jam karena keterbatasan pada sisi Provider.</span><span class="sxs-lookup"><span data-stu-id="94c67-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="94c67-137">Jumlah profil yang dapat Anda ekspor ke DotDigital tergantung dan terbatas pada kontrak Anda dengan DotDigital.</span><span class="sxs-lookup"><span data-stu-id="94c67-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="94c67-138">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="94c67-138">Data privacy and compliance</span></span>

<span data-ttu-id="94c67-139">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke DotDigital, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="94c67-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="94c67-140">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa DotDigital memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="94c67-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="94c67-141">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="94c67-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="94c67-142">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="94c67-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]