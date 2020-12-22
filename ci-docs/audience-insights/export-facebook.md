---
title: Ekspor data Customer Insights ke Facebook Ads Manager
description: Pelajari cara mengkonfigurasi sambungan ke pengelola iklan Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643687"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="75e0a-103">Konektor untuk pengelola iklan Facebook (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="75e0a-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="75e0a-104">Ekspor segmen profil pelanggan terpadu ke pengelola iklan Facebook untuk membuat kampanye di Facebook dan Instagram.</span><span class="sxs-lookup"><span data-stu-id="75e0a-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75e0a-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="75e0a-105">Prerequisites</span></span>

- <span data-ttu-id="75e0a-106">Anda harus memiliki akun [**iklan Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) yang mencakup akun [**bisnis Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="75e0a-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="75e0a-107">Anda harus menjadi administrator pada akun [**iklan Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="75e0a-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="75e0a-108">Terhubung ke pengelola iklan Facebook</span><span class="sxs-lookup"><span data-stu-id="75e0a-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="75e0a-109">Buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="75e0a-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="75e0a-110">Di **pengelola iklan Facebook**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="75e0a-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="75e0a-111">Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="75e0a-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="75e0a-112">Pilih **Lanjutkan dengan Facebook** untuk masuk ke akun iklan Facebook Anda.</span><span class="sxs-lookup"><span data-stu-id="75e0a-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="75e0a-113">Izinkan izin **ads_management** setelah mengautentikasi dengan Facebook.</span><span class="sxs-lookup"><span data-stu-id="75e0a-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="75e0a-114">Pilih **Akun Iklan Facebook** yang ingin Anda kerjakan.</span><span class="sxs-lookup"><span data-stu-id="75e0a-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="75e0a-115">Pilih **audiens kustom yang ada** dari daftar drop-down atau buat **audiens kustom baru**.</span><span class="sxs-lookup"><span data-stu-id="75e0a-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="75e0a-116">Untuk informasi lebih lanjut, lihat [**audiens di pengelola iklan Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="75e0a-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="75e0a-117">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="75e0a-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="75e0a-118">Pilih **berikutnya** untuk mengkonfigurasi ekspor.</span><span class="sxs-lookup"><span data-stu-id="75e0a-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="75e0a-119">Konfigurasikan konektor</span><span class="sxs-lookup"><span data-stu-id="75e0a-119">Configure the connector</span></span>

1. <span data-ttu-id="75e0a-120">Di bidang **Pilih pengidentifikasi utama Anda**, pilih **email**, **nama dan alamat**, atau **telepon** untuk dikirim ke pengelola iklan Facebook.</span><span class="sxs-lookup"><span data-stu-id="75e0a-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="75e0a-121">Petakan atribut yang terkait dari entitas pelanggan terpadu Anda untuk pengidentifikasi kunci yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="75e0a-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="75e0a-122">[KIAT] Peluang terbaik untuk kecocokan terjadi jika Anda memilih **email** sebagai pengidentifikasi utama.</span><span class="sxs-lookup"><span data-stu-id="75e0a-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="75e0a-123">Menambahkan pengidentifikasi tambahan dapat meningkatkan pencocokan.</span><span class="sxs-lookup"><span data-stu-id="75e0a-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="75e0a-124">Pilih **Tambah atribut** untuk memetakan atribut tambahan agar dapat dikirim ke pengelola iklan Facebook.</span><span class="sxs-lookup"><span data-stu-id="75e0a-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="75e0a-125">Atribut dari manajer iklan Facebook melakukan pemetaan ke nama rumah pengguna berikut: **FN** = **Nama Depan**, **LN** = **Nama Belakang**, **FI** = **Inisial Depan**, **TELEPON** = **Telepon**, **GEN** = **Gender**, **DOB** = **Tanggal Lahir**, **ST** = **Negara Bagian**, **CT** = **Kota**, **ZIP** = **Kode pos/Zip**, **NEGARA** = **Negara/Wilayah**</span><span class="sxs-lookup"><span data-stu-id="75e0a-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="75e0a-126">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="75e0a-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="75e0a-127">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="75e0a-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="75e0a-128">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="75e0a-128">Export the data</span></span>

<span data-ttu-id="75e0a-129">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="75e0a-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="75e0a-130">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="75e0a-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="75e0a-131">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="75e0a-131">Data privacy and compliance</span></span>

<span data-ttu-id="75e0a-132">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Facebook Ads Manager, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="75e0a-132">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="75e0a-133">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Facebook Ads memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="75e0a-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="75e0a-134">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="75e0a-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="75e0a-135">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="75e0a-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
