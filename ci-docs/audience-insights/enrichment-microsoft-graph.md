---
title: Memperkaya profil pelanggan dengan Microsoft graph
description: Gunakan data kepemilikan dari Microsoft graph untuk memperkaya data pelanggan Anda dengan merek dan keterikatan minat.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: aa46dac4f9c0d27881371877b14a92a6725710da
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596457"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="096ab-103">Memperkaya profil pelanggan dengan merek dan afinitas minat (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="096ab-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="096ab-104">Gunakan data kepemilikan dari Microsoft graph untuk memperkaya data pelanggan Anda dengan merek dan keterikatan minat.</span><span class="sxs-lookup"><span data-stu-id="096ab-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="096ab-105">Afinitas ini ditentukan berdasarkan data dari orang yang memiliki demografi serupa dengan pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="096ab-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="096ab-106">Informasi ini membantu Anda lebih memahami dan menyegmentasikan pelanggan berdasarkan minat mereka terhadap merek dan minat tertentu.</span><span class="sxs-lookup"><span data-stu-id="096ab-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="096ab-107">Di wawasan audiens, buka **data** > **pengayaan** untuk [mengkonfigurasi dan melihat pengayaan](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="096ab-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="096ab-108">Untuk mengkonfigurasi pengayaan afinitas merek, buka tab **temukan** dan pilih **Perkaya data saya** di ubin **merek**.</span><span class="sxs-lookup"><span data-stu-id="096ab-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="096ab-109">Untuk mengkonfigurasi pengayaan afinitas minat, buka tab **temukan** dan pilih **Perkaya data saya** di ubin **minat**.</span><span class="sxs-lookup"><span data-stu-id="096ab-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="096ab-110">![Ubin Merek & minat](media/BrandsInterest-tile-Hub.png "Ubin Merek & minat")</span><span class="sxs-lookup"><span data-stu-id="096ab-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="096ab-111">Tentang Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="096ab-111">About Microsoft Graph</span></span>

<span data-ttu-id="096ab-112">Kita menggunakan data pencarian online dari Microsoft Graph untuk menemukan minat terhadap merek dan minat di berbagai segmen demografis (ditentukan berdasarkan usia, jenis kelamin, atau lokasi).</span><span class="sxs-lookup"><span data-stu-id="096ab-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="096ab-113">Volume pencarian online untuk merek atau minat menentukan seberapa besar afinitas yang dimiliki segmen demografis, dibandingkan dengan segmen lain, atas merek atau minat tersebut.</span><span class="sxs-lookup"><span data-stu-id="096ab-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="096ab-114">[Selengkapnya tentang Microsoft Graph](/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="096ab-114">[Learn more about Microsoft Graph](/graph/overview).</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="096ab-115">Tingkat afinitas dan skor</span><span class="sxs-lookup"><span data-stu-id="096ab-115">Affinity level and score</span></span>

<span data-ttu-id="096ab-116">Pada setiap profil pelanggan yang diperkaya, kami menyediakan dua nilai terkait, tingkat afinitas dan skor afinitas.</span><span class="sxs-lookup"><span data-stu-id="096ab-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="096ab-117">Nilai ini akan membantu Anda menentukan seberapa kuat afinitas untuk segmen demografi profil tersebut, untuk merek atau minat, dibandingkan dengan segmen demografi lainnya.</span><span class="sxs-lookup"><span data-stu-id="096ab-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="096ab-118">*Tingkat afinitas* terdiri dari empat tingkat dan *skor afinitas* dihitung pada skala 100 poin yang di petakan ke tingkat afinitas.</span><span class="sxs-lookup"><span data-stu-id="096ab-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="096ab-119">Tingkat afinitas</span><span class="sxs-lookup"><span data-stu-id="096ab-119">Affinity level</span></span> |<span data-ttu-id="096ab-120">Skor afinitas</span><span class="sxs-lookup"><span data-stu-id="096ab-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="096ab-121">Sangat tinggi</span><span class="sxs-lookup"><span data-stu-id="096ab-121">Very high</span></span>     | <span data-ttu-id="096ab-122">85-100</span><span class="sxs-lookup"><span data-stu-id="096ab-122">85-100</span></span>       |
|<span data-ttu-id="096ab-123">Sangat Penting</span><span class="sxs-lookup"><span data-stu-id="096ab-123">High</span></span>     | <span data-ttu-id="096ab-124">70-84</span><span class="sxs-lookup"><span data-stu-id="096ab-124">70-84</span></span>        |
|<span data-ttu-id="096ab-125">Sedang</span><span class="sxs-lookup"><span data-stu-id="096ab-125">Medium</span></span>     | <span data-ttu-id="096ab-126">35-69</span><span class="sxs-lookup"><span data-stu-id="096ab-126">35-69</span></span>        |
|<span data-ttu-id="096ab-127">Kurang Penting</span><span class="sxs-lookup"><span data-stu-id="096ab-127">Low</span></span>     | <span data-ttu-id="096ab-128">1-34</span><span class="sxs-lookup"><span data-stu-id="096ab-128">1-34</span></span>        |

<span data-ttu-id="096ab-129">Tergantung pada perincian yang ingin Anda ukur afinitasnya, Anda dapat menggunakan tingkat afinitas atau skor.</span><span class="sxs-lookup"><span data-stu-id="096ab-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="096ab-130">Skor afinitas memberi Anda kontrol yang lebih akurat.</span><span class="sxs-lookup"><span data-stu-id="096ab-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="096ab-131">Negara/kawasan yang didukung</span><span class="sxs-lookup"><span data-stu-id="096ab-131">Supported countries/regions</span></span>

<span data-ttu-id="096ab-132">Saat ini kami mendukung pilihan negara/kawasan berikut: Australia, Kanada (Inggris), Prancis, Jerman, Inggris Raya, atau Amerika Serikat (Inggris).</span><span class="sxs-lookup"><span data-stu-id="096ab-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="096ab-133">Untuk memilih negara, buka **pengayaan merek** atau **pengayaan mina**, lalu pilih **Ubah** di samping **negara/kawasan**.</span><span class="sxs-lookup"><span data-stu-id="096ab-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="096ab-134">Di panel **pengaturan negara/kawasan**, pilih pilihan, lalu pilih **Terapkan**.</span><span class="sxs-lookup"><span data-stu-id="096ab-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="096ab-135">Implikasi terkait pemilihan negara</span><span class="sxs-lookup"><span data-stu-id="096ab-135">Implications related to country selection</span></span>

- <span data-ttu-id="096ab-136">Saat [memilih merek Anda sendiri](#define-your-brands-or-interests), sistem memberikan saran berdasarkan negara atau kawasan yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="096ab-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="096ab-137">Saat [memilih industri](#define-your-brands-or-interests), Anda akan mendapatkan merek atau minat yang paling relevan berdasarkan negara atau kawasan yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="096ab-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="096ab-138">Bila [memperkaya profil](#refresh-enrichment), kami akan memperkaya semua profil pelanggan dengan data yang kami dapatkan untuk merek dan minat yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="096ab-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="096ab-139">Termasuk profil yang tidak berada di negara atau kawasan tertentu.</span><span class="sxs-lookup"><span data-stu-id="096ab-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="096ab-140">Misalnya, jika Anda memilih Jerman, kami akan memperkaya profil yang terletak di Amerika Serikat jika kami memiliki data Microsoft graph yang tersedia untuk merek dan minat tertentu di AS.</span><span class="sxs-lookup"><span data-stu-id="096ab-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="096ab-141">Konfigurasi pengayaan</span><span class="sxs-lookup"><span data-stu-id="096ab-141">Configure Enrichment</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="096ab-142">Definisikan merek atau minat Anda</span><span class="sxs-lookup"><span data-stu-id="096ab-142">Define your brands or interests</span></span>

<span data-ttu-id="096ab-143">pilih salah satu dari opsi berikut ini:</span><span class="sxs-lookup"><span data-stu-id="096ab-143">Select one of the following options:</span></span>

- <span data-ttu-id="096ab-144">**Industri**: sistem mengidentifikasi merek atau minat teratas yang relevan dengan industri Anda dan memperkaya data pelanggan Anda dengannya.</span><span class="sxs-lookup"><span data-stu-id="096ab-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="096ab-145">**Pilih punya Anda sendiri**: Pilih hingga lima item dari daftar merek atau minat yang paling relevan dengan organisasi Anda.</span><span class="sxs-lookup"><span data-stu-id="096ab-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="096ab-146">Untuk menambahkan merek atau minat, masukkan di area input untuk mendapatkan saran berdasarkan persyaratan kecocokan.</span><span class="sxs-lookup"><span data-stu-id="096ab-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="096ab-147">Jika kami tidak mencantumkan merek atau minat yang Anda Cari, kirim masukan kepada kami menggunakan tautan **Usulkan**.</span><span class="sxs-lookup"><span data-stu-id="096ab-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="096ab-148">Tinjau Preferensi pengayaan</span><span class="sxs-lookup"><span data-stu-id="096ab-148">Review enrichment preferences</span></span>

<span data-ttu-id="096ab-149">Tinjau preferensi pengayaan default dan perbarui jika diperlukan.</span><span class="sxs-lookup"><span data-stu-id="096ab-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Cuplikan layar jendela preferensi pengayaan.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="096ab-151">Pilih entitas yang akan diperkaya</span><span class="sxs-lookup"><span data-stu-id="096ab-151">Select entity to enrich</span></span>

<span data-ttu-id="096ab-152">Pilih **Entitas yang diperkaya** dan pilih himpunan data yang anda ingin perkaya dengan data perusahaan dari Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="096ab-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft Graph.</span></span> <span data-ttu-id="096ab-153">Anda dapat memilih entitas Pelanggan untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="096ab-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="096ab-154">Petakan bidang Anda</span><span class="sxs-lookup"><span data-stu-id="096ab-154">Map your fields</span></span>

<span data-ttu-id="096ab-155">Petakan bidang dari entitas pelanggan terpadu untuk menentukan segmen demografi yang akan digunakan sistem untuk memperkaya data pelanggan.</span><span class="sxs-lookup"><span data-stu-id="096ab-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="096ab-156">Petakan Negara/Kawasan dan sekurangnya atribut Tanggal Lahir atau Jenis Kelamin.</span><span class="sxs-lookup"><span data-stu-id="096ab-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="096ab-157">Atau, Anda harus memetakan minimal satu Kota (dan Negara Bagian/Provinsi) atau Kode Pos.</span><span class="sxs-lookup"><span data-stu-id="096ab-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="096ab-158">Pilih **Edit** untuk menentukan pemetaan bidang, lalu pilih **Terapkan** setelah selesai.</span><span class="sxs-lookup"><span data-stu-id="096ab-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="096ab-159">Pilih **Simpan** untuk menyelesaikan pemetaan bidang.</span><span class="sxs-lookup"><span data-stu-id="096ab-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="096ab-160">Format dan nilai berikut didukung, nilai tidak peka terhadap besar huruf:</span><span class="sxs-lookup"><span data-stu-id="096ab-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="096ab-161">**Tanggal lahir**: sebaiknya tanggal lahir dikonversi ke jenis datetime selama proses transfer data.</span><span class="sxs-lookup"><span data-stu-id="096ab-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="096ab-162">Atau, dapat berupa string dalam format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "yyyy-MM-dd" atau "yyyy-MM-ddTHH:mm:ssZ."</span><span class="sxs-lookup"><span data-stu-id="096ab-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="096ab-163">**Jenis kelamin**: laki-laki, perempuan, tidak diketahui</span><span class="sxs-lookup"><span data-stu-id="096ab-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="096ab-164">**Kode pos**: lima digit kode pos untuk AS, kode pos standar di tempat lainnya</span><span class="sxs-lookup"><span data-stu-id="096ab-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="096ab-165">**Kota**: nama kota dalam bahasa Inggris</span><span class="sxs-lookup"><span data-stu-id="096ab-165">**City**: City name in English</span></span>
- <span data-ttu-id="096ab-166">**Negara bagian/propinsi**: singkatan dua huruf untuk AS dan Kanada.</span><span class="sxs-lookup"><span data-stu-id="096ab-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="096ab-167">Dua atau tiga huruf singkatan untuk Australia.</span><span class="sxs-lookup"><span data-stu-id="096ab-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="096ab-168">Tidak berlaku untuk Prancis, Jerman, atau Inggris.</span><span class="sxs-lookup"><span data-stu-id="096ab-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="096ab-169">**Negara/Kawasan**:</span><span class="sxs-lookup"><span data-stu-id="096ab-169">**Country/Region**:</span></span>

  - <span data-ttu-id="096ab-170">AS: Amerika Serikat, USA, AS, Amerika</span><span class="sxs-lookup"><span data-stu-id="096ab-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="096ab-171">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="096ab-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="096ab-172">GB: Inggris, Inggris, Britania Raya, GB, Britania Raya dan Irlandia Utara, Inggris Raya</span><span class="sxs-lookup"><span data-stu-id="096ab-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="096ab-173">AU: Australia, AU, Persemakmuran Australia</span><span class="sxs-lookup"><span data-stu-id="096ab-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="096ab-174">FR: Prancis, Republik Prancis</span><span class="sxs-lookup"><span data-stu-id="096ab-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="096ab-175">DE: Jerman, Jerman, Deutschland, Allemagne, DE, Republik Federal Jerman, Republik Jerman</span><span class="sxs-lookup"><span data-stu-id="096ab-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="096ab-176">Segarkan pengayaan</span><span class="sxs-lookup"><span data-stu-id="096ab-176">Refresh enrichment</span></span>

<span data-ttu-id="096ab-177">Jalankan pengayaan setelah mengonfigurasi merek, minat, dan pemetaan bidang untuk demografi.</span><span class="sxs-lookup"><span data-stu-id="096ab-177">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="096ab-178">Untuk memulai proses, pilih **Jalankan** pada halaman konfigurasi merek atau minat.</span><span class="sxs-lookup"><span data-stu-id="096ab-178">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="096ab-179">Selain itu, Anda dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari penyegaran terjadwal.</span><span class="sxs-lookup"><span data-stu-id="096ab-179">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="096ab-180">Tergantung pada ukuran data pelanggan Anda, diperlukan waktu beberapa menit untuk pengayaan yang dijalankan untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="096ab-180">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="096ab-181">Ada [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="096ab-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="096ab-182">Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="096ab-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="096ab-183">Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan.</span><span class="sxs-lookup"><span data-stu-id="096ab-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="096ab-184">Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="096ab-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="096ab-185">Hasil pengayaan</span><span class="sxs-lookup"><span data-stu-id="096ab-185">Enrichment results</span></span>

<span data-ttu-id="096ab-186">Setelah menjalankan proses pengayaan, buka **Pengayaan saya** untuk meninjau total jumlah pelanggan yang diperkaya dan perincian merek atau minat atas profil pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="096ab-186">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Pratinjau hasil setelah menjalankan proses pengayaan":::

<span data-ttu-id="096ab-188">Tinjau data yang diperkaya dengan memilih **Lihat data yang diperkaya** di diagram.</span><span class="sxs-lookup"><span data-stu-id="096ab-188">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="096ab-189">Data yang diperkaya untuk merek beralih ke entitas **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="096ab-189">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="096ab-190">Data untuk minat ada di entitas **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="096ab-190">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="096ab-191">Anda juga akan menemukan entitas yang tercantum di grup **pengayaan** dalam **data** > **entitas**.</span><span class="sxs-lookup"><span data-stu-id="096ab-191">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="096ab-192">Melihat data pengayaan pada kartu pelanggan</span><span class="sxs-lookup"><span data-stu-id="096ab-192">See enrichment data on the customer card</span></span>

<span data-ttu-id="096ab-193">afinitas Merek dan minat juga dapat dilihat pada kartu Pelanggan perorangan.</span><span class="sxs-lookup"><span data-stu-id="096ab-193">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="096ab-194">Buka **pelanggan** dan pilih profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="096ab-194">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="096ab-195">Di kartu pelanggan, Anda akan menemukan diagram untuk merek atau minat yang dimiliki afinitasnya oleh orang dalam profil demografi pelanggan.</span><span class="sxs-lookup"><span data-stu-id="096ab-195">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kartu pelanggan dengan data yang diperkaya":::

## <a name="next-steps"></a><span data-ttu-id="096ab-197">Langkah-langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="096ab-197">Next steps</span></span>

<span data-ttu-id="096ab-198">Bangun di atas data pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="096ab-198">Build on top of your enriched customer data.</span></span> <span data-ttu-id="096ab-199">Buat [segmen](segments.md), [tindakan](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan bagi pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="096ab-199">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]