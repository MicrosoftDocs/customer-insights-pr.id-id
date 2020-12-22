---
title: Pengayaan dengan Experian pengayaan pihak ketiga
description: Informasi umum tentang pengayaan pihak ketiga Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668816"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="28281-103">Memperkaya profil pelanggan dengan demografi dari Experian (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="28281-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="28281-104">Experian adalah pemimpin global dalam pelaporan kredit konsumen dan bisnis serta layanan pemasaran.</span><span class="sxs-lookup"><span data-stu-id="28281-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="28281-105">Dengan layanan pengayaan data Experian, Anda dapat membangun pemahaman yang lebih mendalam tentang pelanggan Anda dengan memperkaya profil pelanggan Anda dengan data demografis seperti ukuran rumah tangga, pendapatan, dan lainnya.</span><span class="sxs-lookup"><span data-stu-id="28281-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28281-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="28281-106">Prerequisites</span></span>

<span data-ttu-id="28281-107">Untuk mengonfigurasikan Experian, prasyarat berikut harus dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="28281-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="28281-108">Anda memiliki langganan Experian aktif.</span><span class="sxs-lookup"><span data-stu-id="28281-108">You have an active Experian subscription.</span></span> <span data-ttu-id="28281-109">Untuk mendapatkan langganan, [Hubungi Experian](https://www.experian.com/marketing-services/contact) secara langsung.</span><span class="sxs-lookup"><span data-stu-id="28281-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="28281-110">[Pelajari selengkapnya tentang pengayaan data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="28281-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="28281-111">Anda memiliki ID pengguna, ID pihak, dan nomor model untuk akun transpor aman (ST) yang diaktifkan SSH yang dibuat Experian untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="28281-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="28281-112">Anda memiliki izin [Administrator](permissions.md#administrator) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="28281-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="28281-113">Konfigurasi</span><span class="sxs-lookup"><span data-stu-id="28281-113">Configuration</span></span>

1. <span data-ttu-id="28281-114">Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.</span><span class="sxs-lookup"><span data-stu-id="28281-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="28281-115">Pilih **Perkaya data saya** di petak Experian.</span><span class="sxs-lookup"><span data-stu-id="28281-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="28281-116">![petak Experian](media/experian-tile.png "petak Experian")</span><span class="sxs-lookup"><span data-stu-id="28281-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="28281-117">Pilih **persiapan** dan masukkan ID pengguna, id pihak, dan nomor model untuk akun transportasi aman Experian Anda.</span><span class="sxs-lookup"><span data-stu-id="28281-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="28281-118">Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="28281-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="28281-119">Konfirmasikan semua input dengan memilih **Terapkan**.</span><span class="sxs-lookup"><span data-stu-id="28281-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="28281-120">Petakan bidang Anda</span><span class="sxs-lookup"><span data-stu-id="28281-120">Map your fields</span></span>

1. <span data-ttu-id="28281-121">Pilih **Tambah data** dan pilih pengidentifikasi kunci Anda dari **nama dan alamat**, **email**, atau **telepon** untuk dikirim ke Experian untuk resolusi identitas.</span><span class="sxs-lookup"><span data-stu-id="28281-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="28281-122">Atribut pengidentifikasi kunci lainnya yang dikirim ke Experian kemungkinan menghasilkan tingkat kecocokan yang lebih tinggi.</span><span class="sxs-lookup"><span data-stu-id="28281-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="28281-123">Pilih **berikutnya** dan Petakan atribut terkait dari entitas pelanggan terpadu Anda untuk bidang pengidentifikasi kunci yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="28281-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="28281-124">Pilih **Tambah atribut** untuk memetakan atribut tambahan yang ingin Anda kirim ke Experian.</span><span class="sxs-lookup"><span data-stu-id="28281-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="28281-125">Pilih **Simpan** untuk menyelesaikan pemetaan bidang.</span><span class="sxs-lookup"><span data-stu-id="28281-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="28281-126">![Pemetaan bidang Experian](media/experian-field-mapping.png "Pemetaan bidang Experian")</span><span class="sxs-lookup"><span data-stu-id="28281-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="28281-127">Hasil pengayaan</span><span class="sxs-lookup"><span data-stu-id="28281-127">Enrichment results</span></span>

<span data-ttu-id="28281-128">Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="28281-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="28281-129">Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="28281-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="28281-130">Waktu pemrosesan akan tergantung pada ukuran data pelanggan Anda dan proses pengayaan diatur untuk akun Anda oleh Experian.</span><span class="sxs-lookup"><span data-stu-id="28281-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="28281-131">Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan baru yang diperkaya di dalam **pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="28281-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="28281-132">Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="28281-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="28281-133">Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.</span><span class="sxs-lookup"><span data-stu-id="28281-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="28281-134">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="28281-134">Next steps</span></span>

<span data-ttu-id="28281-135">Bangun di atas data pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="28281-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="28281-136">Buat [segmen](segments.md), [tindakan](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan bagi pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="28281-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="28281-137">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="28281-137">Data privacy and compliance</span></span>

<span data-ttu-id="28281-138">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Experian, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="28281-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="28281-139">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Experian memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="28281-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="28281-140">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="28281-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="28281-141">Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="28281-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
