---
title: Mengekspor data Customer Insights ke LinkedIn Ads
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124506"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="d8909-103">Mengekspor segmen ke LinkedIn Ads (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="d8909-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="d8909-104">Ekspor segmen profil pelanggan terpadu ke Iklan LinkedIn untuk membuat audiens yang cocok.</span><span class="sxs-lookup"><span data-stu-id="d8909-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="d8909-105">Gunakan Matched Audiences untuk penargetan perusahaan dan penargetan kontak.</span><span class="sxs-lookup"><span data-stu-id="d8909-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d8909-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="d8909-106">Prerequisites</span></span>

-   <span data-ttu-id="d8909-107">Anda memiliki [akun LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) dan kredensial administrator terkait.</span><span class="sxs-lookup"><span data-stu-id="d8909-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d8909-108">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="d8909-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d8909-109">Profil pelanggan di segmen yang diekspor berisi bidang dengan alamat email.</span><span class="sxs-lookup"><span data-stu-id="d8909-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d8909-110">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="d8909-110">Known limitations</span></span>

- <span data-ttu-id="d8909-111">Anda dapat mengekspor hingga 100.000 profil per ekspor ke LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="d8909-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="d8909-112">Mengekspor ke LinkedIn Ads terbatas pada segmen.</span><span class="sxs-lookup"><span data-stu-id="d8909-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="d8909-113">Mengekspor hingga 100.000 profil ke LinkedIn Ads dapat memakan waktu hingga 10 menit untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="d8909-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="d8909-114">Siapkan sambungan ke LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="d8909-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="d8909-115">Dalam audiens wawasan, buka **Koneksi** > **Admin**.</span><span class="sxs-lookup"><span data-stu-id="d8909-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d8909-116">Pilih **Tambahkan koneksi** dan pilih **LinkedIn Ads** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="d8909-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="d8909-117">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="d8909-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d8909-118">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="d8909-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d8909-119">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="d8909-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d8909-120">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="d8909-120">Choose who can use this connection.</span></span> <span data-ttu-id="d8909-121">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="d8909-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="d8909-122">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d8909-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d8909-123">Berikan [ID Akun LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270) Anda.</span><span class="sxs-lookup"><span data-stu-id="d8909-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="d8909-124">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="d8909-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d8909-125">Pilih **Sambungkan** untuk menginisialisasi koneksi ke Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="d8909-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="d8909-126">Pilih **Autentikasi dengan LinkedIn** dan berikan kredensial admin Anda untuk LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="d8909-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="d8909-127">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="d8909-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d8909-128">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="d8909-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d8909-129">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="d8909-129">Configure an export</span></span>

<span data-ttu-id="d8909-130">Anda bisa mengonfigurasi ekspor jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="d8909-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="d8909-131">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d8909-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d8909-132">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="d8909-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d8909-133">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="d8909-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d8909-134">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="d8909-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="d8909-135">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="d8909-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d8909-136">Pilih apakah Anda ingin mengekspor data untuk melakukan [penargetan kontak](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) atau [penargetan perusahaan](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) di LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="d8909-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="d8909-137">Di bagian **Pencocokan data**, pilih bidang di profil pelanggan terpadu Anda yang mewakili alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="d8909-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d8909-138">Segmen harus diekspor ke LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="d8909-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="d8909-139">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="d8909-139">Select the segments you want to export.</span></span> <span data-ttu-id="d8909-140">Audiens yang cocok di LinkedIn Campaign Manager akan secara otomatis dibuat dengan nama segmen yang Anda pilih untuk diekspor.</span><span class="sxs-lookup"><span data-stu-id="d8909-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="d8909-141">Setiap segmen akan menghasilkan audiens yang cocok terpisah.</span><span class="sxs-lookup"><span data-stu-id="d8909-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="d8909-142">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="d8909-142">Select **Save**.</span></span>

<span data-ttu-id="d8909-143">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="d8909-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d8909-144">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d8909-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d8909-145">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d8909-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d8909-146">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="d8909-146">Data privacy and compliance</span></span>

<span data-ttu-id="d8909-147">Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke LinkedIn Ads, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi.</span><span class="sxs-lookup"><span data-stu-id="d8909-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d8909-148">Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa LinkedIn Ads memenuhi kewajiban privasi atau keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="d8909-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d8909-149">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d8909-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d8909-150">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="d8909-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
