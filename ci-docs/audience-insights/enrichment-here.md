---
title: Pengayaan dengan pengayaan pihak ketiga HERE Technologies
description: Informasi umum tentang pengayaan pihak ketiga HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305298"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="01778-103">Pengayaan profil pelanggan dengan HERE Technologies (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="01778-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="01778-104">HERE Technologies adalah perusahaan platform lokasi yang menyediakan data dan layanan yang berpusat lokasi.</span><span class="sxs-lookup"><span data-stu-id="01778-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="01778-105">Dengan layanan pengayaan data HERE Technologies, Anda dapat membangun pemahaman lokasi yang lebih tepat tentang pelanggan Anda dengan normalisasi alamat, ekstraksi garis lintang dan bujur, dan banyak lagi.</span><span class="sxs-lookup"><span data-stu-id="01778-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="01778-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="01778-106">Prerequisites</span></span>

<span data-ttu-id="01778-107">Untuk mengkonfigurasikan pengayaan HERE Technologies, persyaratan berikut harus dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="01778-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="01778-108">Anda memiliki langganan aktif HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="01778-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="01778-109">Untuk mendapatkan langganan, Anda dapat [mendaftar di sini](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) atau [hubungi langsung HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="01778-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="01778-110">Selengkapnya tentang pengayaan lokasi HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="01778-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="01778-111">[Koneksi](connections.md) HERE tersedia *atau* Anda memiliki izin [administrator](permissions.md#administrator) dan kunci API HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="01778-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="01778-112">Konfigurasi pengayaan</span><span class="sxs-lookup"><span data-stu-id="01778-112">Configure the enrichment</span></span>

1. <span data-ttu-id="01778-113">Buka **Data** > **Pengayaan**.</span><span class="sxs-lookup"><span data-stu-id="01778-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="01778-114">Pilih **Perkaya data** saya di petak HERE Technologies dan pilih **Mulai**.</span><span class="sxs-lookup"><span data-stu-id="01778-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01778-115">![petak HERE Technologies](media/HERE-tile.png "petak HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="01778-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="01778-116">Pilih [koneksi](connections.md) dari daftar drop-down.</span><span class="sxs-lookup"><span data-stu-id="01778-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="01778-117">Hubungi administrator jika tidak ada koneksi yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="01778-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="01778-118">Jika Anda adalah administrator, Anda bisa membuat koneksi dengan memilih **Tambahkan koneksi**.</span><span class="sxs-lookup"><span data-stu-id="01778-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="01778-119">Pilih **HERE Technologies** dari daftar dropdown.</span><span class="sxs-lookup"><span data-stu-id="01778-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="01778-120">Pilih **Sambungkan ke HERE Technologies** untuk mengonfirmasi pilihan.</span><span class="sxs-lookup"><span data-stu-id="01778-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="01778-121">Pilih **Berikutnya** dan pilih **himpunan data Pelanggan** yang ingin Anda perkaya dengan data lokasi dari HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="01778-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="01778-122">Anda dapat memilih entitas **Pelanggan** untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="01778-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Tangkapan layar saat memilih himpunan data pelanggan.":::

1. <span data-ttu-id="01778-124">Pilih jika Anda ingin memetakan bidang ke alamat utama dan/atau sekunder.</span><span class="sxs-lookup"><span data-stu-id="01778-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="01778-125">Anda dapat menentukan pemetaan bidang untuk kedua alamat dan memperkaya profil untuk kedua alamat secara terpisah.</span><span class="sxs-lookup"><span data-stu-id="01778-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="01778-126">Misalnya, jika ada alamat rumah dan bisnis.</span><span class="sxs-lookup"><span data-stu-id="01778-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="01778-127">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="01778-127">Select **Next**.</span></span>

1. <span data-ttu-id="01778-128">Tentukan bidang dari profil terpadu mana yang harus digunakan untuk mencari data lokasi yang cocok dari HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="01778-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="01778-129">Bidang **jalan 1** dan **Kode Zip/Pos** diperlukan untuk alamat utama dan/atau sekunder yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="01778-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="01778-130">Untuk akurasi kecocokan yang lebih tinggi, lebih banyak bidang dapat ditambahkan.</span><span class="sxs-lookup"><span data-stu-id="01778-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01778-131">![Halaman konfigurasi pengayaan HERE Technologies](media/enrichment-HERE-configuration.png "Halaman konfigurasi pengayaan HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="01778-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="01778-132">Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="01778-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="01778-133">Berikan nama untuk pengayaan.</span><span class="sxs-lookup"><span data-stu-id="01778-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="01778-134">Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.</span><span class="sxs-lookup"><span data-stu-id="01778-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="01778-135">Mengonfigurasi koneksi untuk HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="01778-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="01778-136">Anda perlu menjadi administrator untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="01778-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="01778-137">Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan *atau* masuk ke **Admin** > **Koneksi** dan pilih **Konfigurasi** pada petak HERE technologies.</span><span class="sxs-lookup"><span data-stu-id="01778-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="01778-138">Masukkan nama untuk koneksi dalam kotak **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="01778-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="01778-139">Berikan kunci API HERE Technologies yang valid.</span><span class="sxs-lookup"><span data-stu-id="01778-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="01778-140">Baca dan berikan persetujuan Anda untuk **privasi dan kesesuaian Data** dengan memilih **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="01778-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="01778-141">Pilih **Verifikasi** untuk memvalidasi konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="01778-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="01778-142">Setelah menyelesaikan verifikasi, pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="01778-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01778-143">![Halaman konfigurasi koneksi HERE technologies](media/enrichment-HERE-connection.png "Halaman konfigurasi koneksi HERE technologies")</span><span class="sxs-lookup"><span data-stu-id="01778-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="01778-144">Hasil pengayaan</span><span class="sxs-lookup"><span data-stu-id="01778-144">Enrichment results</span></span>

<span data-ttu-id="01778-145">Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="01778-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="01778-146">Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="01778-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="01778-147">Waktu pemrosesan akan tergantung pada ukuran data pelanggan dan waktu respons API dari HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="01778-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="01778-148">Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan baru yang diperkaya di dalam **pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="01778-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="01778-149">Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="01778-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="01778-150">Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.</span><span class="sxs-lookup"><span data-stu-id="01778-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="01778-151">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="01778-151">Next steps</span></span>

<span data-ttu-id="01778-152">Bangun di atas data pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="01778-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="01778-153">Buat [segmen](segments.md) dan [ukuran](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman pribadi kepada pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="01778-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="01778-154">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="01778-154">Data privacy and compliance</span></span>

<span data-ttu-id="01778-155">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke HERE Technologies, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="01778-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="01778-156">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa HERE Technologies memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="01778-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="01778-157">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="01778-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="01778-158">Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="01778-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
