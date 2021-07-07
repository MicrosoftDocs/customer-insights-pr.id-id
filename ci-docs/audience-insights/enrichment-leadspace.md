---
title: Pengayaan profil perusahaan dengan pengayaan pihak ketiga Leadspace
description: Informasi umum tentang pengayaan pihak ketiga Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305206"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="b3621-103">Pengayaan profil perusahaan dengan Leadspace (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="b3621-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="b3621-104">Leadspace adalah perusahaan ilmu data yang menyediakan platform data pelanggan B2B.</span><span class="sxs-lookup"><span data-stu-id="b3621-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="b3621-105">Hal ini memungkinkan pelanggan dengan profil pelanggan terpadu untuk perusahaan untuk memperkaya data mereka.</span><span class="sxs-lookup"><span data-stu-id="b3621-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="b3621-106">Pengayaan mencakup atribut seperti ukuran perusahaan, lokasi, industri, dan lainnya.</span><span class="sxs-lookup"><span data-stu-id="b3621-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3621-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="b3621-107">Prerequisites</span></span>

<span data-ttu-id="b3621-108">Untuk mengonfigurasikan Leadspace, prasyarat berikut harus dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="b3621-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b3621-109">Anda memiliki lisensi Leadspace aktif.</span><span class="sxs-lookup"><span data-stu-id="b3621-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="b3621-110">Anda memiliki [profil pelanggan terpadu](customer-profiles.md) untuk perusahaan.</span><span class="sxs-lookup"><span data-stu-id="b3621-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="b3621-111">Koneksi Leadspace telah dikonfigurasi oleh administrator atau Anda memiliki izin [administrator](permissions.md#administrator) dan "kunci abadi" (disebut sebagai **token Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="b3621-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="b3621-112">Hubungi [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) secara langsung untuk detail tentang produk mereka.</span><span class="sxs-lookup"><span data-stu-id="b3621-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="b3621-113">Konfigurasi pengayaan</span><span class="sxs-lookup"><span data-stu-id="b3621-113">Configure the enrichment</span></span>

1. <span data-ttu-id="b3621-114">Di wawasan audiens, buka **Data** > **pengayaan**.</span><span class="sxs-lookup"><span data-stu-id="b3621-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="b3621-115">Pilih **Perkaya data** saya di petak Leadspace dan pilih **Mulai**.</span><span class="sxs-lookup"><span data-stu-id="b3621-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Tangkapan layar petak Leadspace.":::

1. <span data-ttu-id="b3621-117">Pilih [koneksi](connections.md) dari daftar drop-down.</span><span class="sxs-lookup"><span data-stu-id="b3621-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="b3621-118">Hubungi administrator jika tidak ada koneksi yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="b3621-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="b3621-119">Jika Anda adalah administrator, Anda bisa membuat koneksi dengan memilih **Tambahkan koneksi** dan memilih **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="b3621-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="b3621-120">Pilih **Sambungkan ke Leadspace** untuk mengonfirmasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="b3621-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="b3621-121">Pilih **Berikutnya** dan pilih **himpunan data Pelanggan** yang ingin Anda perkaya dengan data perusahaan dari Leadspace.</span><span class="sxs-lookup"><span data-stu-id="b3621-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="b3621-122">Anda dapat memilih entitas **Pelanggan** untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="b3621-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Tangkapan layar saat memilih himpunan data pelanggan.":::

1. <span data-ttu-id="b3621-124">Pilih **Berikutnya** dan tentukan bidang mana dari profil terpadu Anda yang digunakan untuk mencari data perusahaan yang cocok dari Leadspace.</span><span class="sxs-lookup"><span data-stu-id="b3621-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="b3621-125">Bidang **Nama perusahaan** diperlukan.</span><span class="sxs-lookup"><span data-stu-id="b3621-125">The **Name of company** field is required.</span></span> <span data-ttu-id="b3621-126">Untuk akurasi kecocokan yang lebih tinggi, hingga dua bidang lainnya, **situs web perusahaan** dan **lokasi perusahaan**, dapat ditambahkan.</span><span class="sxs-lookup"><span data-stu-id="b3621-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel pemetaan bidang leadspace.":::

1. <span data-ttu-id="b3621-128">Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="b3621-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="b3621-129">Berikan nama untuk pengayaan dan pilih **Simpan pengayaan** setelah meninjau pilihan Anda.</span><span class="sxs-lookup"><span data-stu-id="b3621-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="b3621-130">Mengonfigurasi koneksi untuk Leadspace</span><span class="sxs-lookup"><span data-stu-id="b3621-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="b3621-131">Anda perlu menjadi administrator untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="b3621-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="b3621-132">Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan *atau* masuk ke **Admin** > **Koneksi** dan pilih **Konfigurasi** pada petak Leadspace.</span><span class="sxs-lookup"><span data-stu-id="b3621-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="b3621-133">Pilih **Mulai**.</span><span class="sxs-lookup"><span data-stu-id="b3621-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="b3621-134">Masukkan nama untuk koneksi dalam kotak **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="b3621-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="b3621-135">Berikan token Leadspace yang valid.</span><span class="sxs-lookup"><span data-stu-id="b3621-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="b3621-136">Baca dan berikan persetujuan Anda untuk **privasi dan kesesuaian Data** dengan memilih **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="b3621-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="b3621-137">Pilih **Verifikasi** untuk memvalidasi konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="b3621-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="b3621-138">Setelah menyelesaikan verifikasi, pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="b3621-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Halaman konfigurasi koneksi Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="b3621-140">Hasil pengayaan</span><span class="sxs-lookup"><span data-stu-id="b3621-140">Enrichment results</span></span>

<span data-ttu-id="b3621-141">Setelah menyegarkan pengayaan, Anda dapat meninjau data perusahaan yang diperkaya di dalam [pengayaan saya](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="b3621-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="b3621-142">Anda dapat menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="b3621-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b3621-143">Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.</span><span class="sxs-lookup"><span data-stu-id="b3621-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="b3621-144">Untuk informasi lebih lanjut, lihat [api leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="b3621-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3621-145">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="b3621-145">Next steps</span></span>

<span data-ttu-id="b3621-146">Bangun di atas data pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="b3621-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b3621-147">Buat [segmen](segments.md) dan [ukuran](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman pribadi kepada pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="b3621-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b3621-148">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="b3621-148">Data privacy and compliance</span></span>

<span data-ttu-id="b3621-149">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Leadspace, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="b3621-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b3621-150">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Leadspace memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="b3621-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b3621-151">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b3621-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b3621-152">Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="b3621-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
