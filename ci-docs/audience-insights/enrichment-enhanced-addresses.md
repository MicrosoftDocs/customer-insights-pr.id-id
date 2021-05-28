---
title: Pengayaan peningkatan alamat
description: Perkaya dan normalisasi informasi alamat profil pelanggan dengan model Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965582"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="b1e7f-103">Pengayaan profil pelanggan dengan alamat yang disempurnakan</span><span class="sxs-lookup"><span data-stu-id="b1e7f-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="b1e7f-104">Alamat pada data dapat tidak terstruktur, tidak lengkap, atau salah.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="b1e7f-105">Gunakan model Microsoft untuk menormalkan dan memperkaya alamat Anda ke dalam [format Common Data Model](/common-data-model/schema/core/applicationcommon/address) untuk keakuratan dan wawasan yang lebih baik.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="b1e7f-106">Cara kami meningkatkan alamat</span><span class="sxs-lookup"><span data-stu-id="b1e7f-106">How we enhance addresses</span></span>

<span data-ttu-id="b1e7f-107">Model kami melalui proses dua langkah untuk meningkatkan alamat.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="b1e7f-108">Pertama, ia mengurai alamat untuk mengidentifikasi komponennya dan memasukkannya ke dalam format terstruktur.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="b1e7f-109">Selanjutnya, kami akan menggunakan inteligensi buatan untuk mengoreksi, menyelesaikan, dan membuat standar nilai di alamat.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="b1e7f-110">Contoh</span><span class="sxs-lookup"><span data-stu-id="b1e7f-110">Example</span></span>

<span data-ttu-id="b1e7f-111">Informasi alamat mungkin dalam format non-standar dan berisi kesalahan ejaan.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="b1e7f-112">Model dapat memperbaiki masalah ini dan membuat alamat yang konsisten di profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="b1e7f-113">Pembatasan</span><span class="sxs-lookup"><span data-stu-id="b1e7f-113">Limitations</span></span>

<span data-ttu-id="b1e7f-114">Alamat yang disempurnakan hanya berfungsi dengan nilai yang sudah ada di data alamat yang diserap.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="b1e7f-115">Model tidak:</span><span class="sxs-lookup"><span data-stu-id="b1e7f-115">The model doesn't:</span></span> 

1. <span data-ttu-id="b1e7f-116">Memverifikasikan apakah alamat tersebut adalah alamat yang valid.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="b1e7f-117">Memverifikasikan apakah salah satu nilai, seperti kode ZIP atau nama jalan, valid.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="b1e7f-118">Mengubah nilai yang tidak dikenali.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="b1e7f-119">Model menggunakan teknik berbasis pembelajaran mesin untuk meningkatkan alamat.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="b1e7f-120">Meskipun kami menerapkan ambang batas keyakinan tinggi bila model mengubah nilai input, seperti model berbasis ML, keakuratan 100% tidak dijamin.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="b1e7f-121">Negara atau kawasan yang didukung</span><span class="sxs-lookup"><span data-stu-id="b1e7f-121">Supported countries or regions</span></span>

<span data-ttu-id="b1e7f-122">Saat ini kami mendukung pengayaan alamat di negara atau kawasan berikut:</span><span class="sxs-lookup"><span data-stu-id="b1e7f-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="b1e7f-123">Australia</span><span class="sxs-lookup"><span data-stu-id="b1e7f-123">Australia</span></span>
- <span data-ttu-id="b1e7f-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="b1e7f-124">Canada</span></span>
- <span data-ttu-id="b1e7f-125">Inggris Raya</span><span class="sxs-lookup"><span data-stu-id="b1e7f-125">United Kingdom</span></span>
- <span data-ttu-id="b1e7f-126">Amerika Serikat</span><span class="sxs-lookup"><span data-stu-id="b1e7f-126">United States</span></span>

<span data-ttu-id="b1e7f-127">Alamat harus berisi nilai negara/kawasan.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="b1e7f-128">Kami tidak memproses alamat untuk negara atau kawasan yang tidak didukung dan alamat yang tidak memiliki negara atau kawasan yang disediakan.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="b1e7f-129">Konfigurasi pengayaan</span><span class="sxs-lookup"><span data-stu-id="b1e7f-129">Configure the enrichment</span></span>

1. <span data-ttu-id="b1e7f-130">Buka **Data** > **Pengayaan**.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="b1e7f-131">Pilih **Perkaya data saya** pada ubin **Alamat yang disempurnakan**.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Tangkapan layar ubin Alamat yang Disempurnakan.":::

1. <span data-ttu-id="b1e7f-133">Pilih **himpunan data Pelanggan** dan pilih entitas berisi alamat yang akan diperkaya.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="b1e7f-134">Anda dapat memilih entitas *Pelanggan* untuk memperkaya alamat di semua profil pelanggan atau memilih entitas segmen untuk memperkaya alamat hanya dalam profil pelanggan yang terdapat dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="b1e7f-135">Pilih format alamat dalam himpunan data Anda.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="b1e7f-136">Pilih **Alamat atribut tunggal** jika alamat di data Anda menggunakan satu bidang.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="b1e7f-137">Pilih **Beberapa atribut Alamat** jika alamat di data Anda menggunakan lebih dari satu bidang data.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b1e7f-138">Negara/Kawasan adalah wajib di alamat atribut tunggal dan beberapa atribut.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="b1e7f-139">Alamat yang tidak berisi nilai negara/kawasan yang valid atau yang didukung tidak akan diperkaya</span><span class="sxs-lookup"><span data-stu-id="b1e7f-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="b1e7f-140">Petakan bidang alamat dari entitas pelanggan terpadu Anda.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Halaman pemetaan bidang alamat yang disempurnakan.":::

1. <span data-ttu-id="b1e7f-142">Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="b1e7f-143">Berikan nama untuk pengayaan dan entitas output.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="b1e7f-144">Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b1e7f-145">Hasil pengayaan</span><span class="sxs-lookup"><span data-stu-id="b1e7f-145">Enrichment results</span></span>

<span data-ttu-id="b1e7f-146">Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="b1e7f-147">Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b1e7f-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b1e7f-148">Waktu pemrosesan tergantung pada ukuran data pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="b1e7f-149">Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan baru yang diperkaya di dalam **pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="b1e7f-150">Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="b1e7f-151">Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b1e7f-152">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="b1e7f-152">Next steps</span></span>

<span data-ttu-id="b1e7f-153">Bangun di atas data pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b1e7f-154">Buat [segmen](segments.md), [tindakan](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan bagi pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="b1e7f-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
