---
title: Pengayaan dengan Experian pengayaan pihak ketiga
description: Informasi umum tentang pengayaan pihak ketiga Experian.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269564"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="be49b-103">Memperkaya profil pelanggan dengan demografi dari Experian (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="be49b-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="be49b-104">Experian adalah pemimpin global dalam pelaporan kredit konsumen dan bisnis serta layanan pemasaran.</span><span class="sxs-lookup"><span data-stu-id="be49b-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="be49b-105">Dengan layanan pengayaan data Experian, Anda dapat membangun pemahaman yang lebih mendalam tentang pelanggan Anda dengan memperkaya profil pelanggan Anda dengan data demografis seperti ukuran rumah tangga, pendapatan, dan lainnya.</span><span class="sxs-lookup"><span data-stu-id="be49b-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="be49b-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="be49b-106">Prerequisites</span></span>

<span data-ttu-id="be49b-107">Untuk mengonfigurasikan Experian, prasyarat berikut harus dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="be49b-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="be49b-108">Anda memiliki langganan Experian aktif.</span><span class="sxs-lookup"><span data-stu-id="be49b-108">You have an active Experian subscription.</span></span> <span data-ttu-id="be49b-109">Untuk mendapatkan langganan, [Hubungi Experian](https://www.experian.com/marketing-services/contact) secara langsung.</span><span class="sxs-lookup"><span data-stu-id="be49b-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="be49b-110">[Pelajari selengkapnya tentang pengayaan data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="be49b-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="be49b-111">Anda memiliki ID pengguna, ID pihak, dan nomor model untuk akun transpor aman (ST) yang diaktifkan SSH yang dibuat Experian untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="be49b-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="be49b-112">Anda memiliki izin [Administrator](permissions.md#administrator) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="be49b-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="be49b-113">Konfigurasi</span><span class="sxs-lookup"><span data-stu-id="be49b-113">Configuration</span></span>

1. <span data-ttu-id="be49b-114">Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.</span><span class="sxs-lookup"><span data-stu-id="be49b-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="be49b-115">Pilih **Perkaya data saya** di petak Experian.</span><span class="sxs-lookup"><span data-stu-id="be49b-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="be49b-116">![petak Experian](media/experian-tile.png "petak Experian")</span><span class="sxs-lookup"><span data-stu-id="be49b-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="be49b-117">Pilih **persiapan** dan masukkan ID pengguna, id pihak, dan nomor model untuk akun transportasi aman Experian Anda.</span><span class="sxs-lookup"><span data-stu-id="be49b-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="be49b-118">Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="be49b-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="be49b-119">Konfirmasikan semua input dengan memilih **Terapkan**.</span><span class="sxs-lookup"><span data-stu-id="be49b-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="be49b-120">Petakan bidang Anda</span><span class="sxs-lookup"><span data-stu-id="be49b-120">Map your fields</span></span>

1.  <span data-ttu-id="be49b-121">Pilih **Tambah data** dan pilih **himpunan data Pelanggan** yang anda ingin perkaya dengan data demografi dari Experian.</span><span class="sxs-lookup"><span data-stu-id="be49b-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="be49b-122">Anda dapat memilih entitas **Pelanggan** untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="be49b-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="be49b-123">Pilih pengidentifikasi utama dari **Nama dan Alamat**, **Email**, atau **Telepon** untuk dikirim ke Experian untuk resolusi identitas.</span><span class="sxs-lookup"><span data-stu-id="be49b-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="be49b-124">Atribut pengidentifikasi kunci lainnya yang dikirim ke Experian kemungkinan menghasilkan tingkat kecocokan yang lebih tinggi.</span><span class="sxs-lookup"><span data-stu-id="be49b-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="be49b-125">Pilih **berikutnya** dan Petakan atribut terkait dari entitas pelanggan terpadu Anda untuk bidang pengidentifikasi kunci yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="be49b-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="be49b-126">Pilih **Tambah atribut** untuk memetakan atribut tambahan yang ingin Anda kirim ke Experian.</span><span class="sxs-lookup"><span data-stu-id="be49b-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="be49b-127">Pilih **Simpan** untuk menyelesaikan pemetaan bidang.</span><span class="sxs-lookup"><span data-stu-id="be49b-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="be49b-128">![Pemetaan bidang Experian](media/experian-field-mapping.png "Pemetaan bidang Experian")</span><span class="sxs-lookup"><span data-stu-id="be49b-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="be49b-129">Hasil pengayaan</span><span class="sxs-lookup"><span data-stu-id="be49b-129">Enrichment results</span></span>

<span data-ttu-id="be49b-130">Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="be49b-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="be49b-131">Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="be49b-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="be49b-132">Waktu pemrosesan akan tergantung pada ukuran data pelanggan Anda dan proses pengayaan diatur untuk akun Anda oleh Experian.</span><span class="sxs-lookup"><span data-stu-id="be49b-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="be49b-133">Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan baru yang diperkaya di dalam **pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="be49b-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="be49b-134">Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="be49b-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="be49b-135">Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.</span><span class="sxs-lookup"><span data-stu-id="be49b-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="be49b-136">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="be49b-136">Next steps</span></span>

<span data-ttu-id="be49b-137">Bangun di atas data pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="be49b-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="be49b-138">Buat [segmen](segments.md), [tindakan](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan bagi pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="be49b-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="be49b-139">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="be49b-139">Data privacy and compliance</span></span>

<span data-ttu-id="be49b-140">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Experian, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="be49b-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="be49b-141">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Experian memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="be49b-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="be49b-142">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="be49b-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="be49b-143">Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="be49b-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]