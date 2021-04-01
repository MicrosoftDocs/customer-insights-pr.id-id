---
title: Ekspor data Customer Insights ke Facebook Ads Manager
description: Pelajari cara mengkonfigurasi sambungan ke pengelola iklan Facebook.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596687"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="b07d0-103">Konektor untuk pengelola iklan Facebook (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="b07d0-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="b07d0-104">Ekspor segmen profil pelanggan terpadu ke pengelola iklan Facebook untuk membuat kampanye di Facebook dan Instagram.</span><span class="sxs-lookup"><span data-stu-id="b07d0-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b07d0-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="b07d0-105">Prerequisites</span></span>

- <span data-ttu-id="b07d0-106">Anda harus memiliki akun [**iklan Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) yang mencakup akun [**bisnis Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="b07d0-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="b07d0-107">Anda harus menjadi administrator pada akun [**iklan Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="b07d0-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="b07d0-108">Terhubung ke pengelola iklan Facebook</span><span class="sxs-lookup"><span data-stu-id="b07d0-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="b07d0-109">Buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="b07d0-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b07d0-110">Di **pengelola iklan Facebook**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="b07d0-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="b07d0-111">Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="b07d0-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b07d0-112">Pilih **Lanjutkan dengan Facebook** untuk masuk ke akun iklan Facebook Anda.</span><span class="sxs-lookup"><span data-stu-id="b07d0-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="b07d0-113">Izinkan izin **ads_management** setelah mengautentikasi dengan Facebook.</span><span class="sxs-lookup"><span data-stu-id="b07d0-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="b07d0-114">Pilih **Akun Iklan Facebook** yang ingin Anda kerjakan.</span><span class="sxs-lookup"><span data-stu-id="b07d0-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="b07d0-115">Pilih **audiens kustom yang ada** dari daftar drop-down atau buat **audiens kustom baru**.</span><span class="sxs-lookup"><span data-stu-id="b07d0-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="b07d0-116">Untuk informasi lebih lanjut, lihat [**audiens di pengelola iklan Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="b07d0-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="b07d0-117">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="b07d0-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b07d0-118">Pilih **berikutnya** untuk mengkonfigurasi ekspor.</span><span class="sxs-lookup"><span data-stu-id="b07d0-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b07d0-119">Konfigurasikan konektor</span><span class="sxs-lookup"><span data-stu-id="b07d0-119">Configure the connector</span></span>

1. <span data-ttu-id="b07d0-120">Di bidang **Pilih pengidentifikasi utama Anda**, pilih **email**, **nama dan alamat**, atau **telepon** untuk dikirim ke pengelola iklan Facebook.</span><span class="sxs-lookup"><span data-stu-id="b07d0-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="b07d0-121">Petakan atribut yang terkait dari entitas pelanggan terpadu Anda untuk pengidentifikasi kunci yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="b07d0-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="b07d0-122">[KIAT] Peluang terbaik untuk kecocokan terjadi jika Anda memilih **email** sebagai pengidentifikasi utama.</span><span class="sxs-lookup"><span data-stu-id="b07d0-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="b07d0-123">Menambahkan pengidentifikasi tambahan dapat meningkatkan pencocokan.</span><span class="sxs-lookup"><span data-stu-id="b07d0-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="b07d0-124">Pilih **Tambah atribut** untuk memetakan atribut tambahan agar dapat dikirim ke pengelola iklan Facebook.</span><span class="sxs-lookup"><span data-stu-id="b07d0-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="b07d0-125">Atribut dari manajer iklan Facebook melakukan pemetaan ke nama rumah pengguna berikut: **FN** = **Nama Depan**, **LN** = **Nama Belakang**, **FI** = **Inisial Depan**, **TELEPON** = **Telepon**, **GEN** = **Gender**, **DOB** = **Tanggal Lahir**, **ST** = **Negara Bagian**, **CT** = **Kota**, **ZIP** = **Kode pos/Zip**, **NEGARA** = **Negara/Wilayah**</span><span class="sxs-lookup"><span data-stu-id="b07d0-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="b07d0-126">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="b07d0-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="b07d0-127">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="b07d0-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b07d0-128">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="b07d0-128">Export the data</span></span>

<span data-ttu-id="b07d0-129">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b07d0-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b07d0-130">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b07d0-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b07d0-131">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="b07d0-131">Known limitations</span></span>

- <span data-ttu-id="b07d0-132">Hingga 10 juta profil pelanggan per ekspor ke Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="b07d0-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="b07d0-133">Mengekspor ke Facebook Ads Manager terbatas untuk segmen</span><span class="sxs-lookup"><span data-stu-id="b07d0-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="b07d0-134">Mengekspor segmen dengan total 10 juta profil dapat memakan waktu hingga 90 menit untuk diselesaikan</span><span class="sxs-lookup"><span data-stu-id="b07d0-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b07d0-135">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="b07d0-135">Data privacy and compliance</span></span>

<span data-ttu-id="b07d0-136">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Facebook Ads Manager, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="b07d0-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b07d0-137">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Facebook Ads memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="b07d0-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b07d0-138">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b07d0-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b07d0-139">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="b07d0-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]