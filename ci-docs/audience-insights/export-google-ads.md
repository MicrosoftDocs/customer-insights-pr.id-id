---
title: Ekspor data Customer Insights ke Google Ads
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976322"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="8bfb3-103">Mengekspor segmen ke Google Ads (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="8bfb3-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="8bfb3-104">Ekspor segmen profil pelanggan terpadu ke daftar audiens Google Ads dan gunakan untuk beriklan di Google Search, Gmail, YouTube, dan Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="8bfb3-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="8bfb3-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="8bfb3-106">Anda memiliki [akun Google Ads](https://ads.google.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8bfb3-107">Anda memiliki [token Pengembang Google Ads yang disetujui](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="8bfb3-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="8bfb3-108">Anda memenuhi persyaratan [Kebijakan Customer Match](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="8bfb3-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="8bfb3-109">Anda memenuhi persyaratan [ukuran daftar pemasaran ulang](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="8bfb3-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="8bfb3-110">Audiens sudah ada di Google Ads dan id yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="8bfb3-111">Untuk informasi lebih lanjut, lihat [audiens Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="8bfb3-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="8bfb3-112">Anda telah [mengonfigurasi segmen](segments.md)</span><span class="sxs-lookup"><span data-stu-id="8bfb3-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="8bfb3-113">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email, nama depan, dan nama belakang</span><span class="sxs-lookup"><span data-stu-id="8bfb3-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8bfb3-114">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="8bfb3-114">Known limitations</span></span>

- <span data-ttu-id="8bfb3-115">Hingga 1 juta profil per ekspor ke Google Ads.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="8bfb3-116">Mengekspor ke Google Ads.terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="8bfb3-117">Mengekspor segmen dengan total 1 juta profil dapat memakan waktu hingga 5 menit karena keterbatasan pada sisi Provider.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="8bfb3-118">Pencocokan di Google Ads dapat berlangsung hingga 48 jam.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="8bfb3-119">Konfigurasikan koneksi ke Google Ads</span><span class="sxs-lookup"><span data-stu-id="8bfb3-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="8bfb3-120">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8bfb3-121">Pilih **Tambahkan koneksi** dan pilih **Google Ads** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="8bfb3-122">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8bfb3-123">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8bfb3-124">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8bfb3-125">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-125">Choose who can use this connection.</span></span> <span data-ttu-id="8bfb3-126">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8bfb3-127">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8bfb3-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8bfb3-128">Masukkan **[ID pelanggan Google Ads](https://support.google.com/google-ads/answer/1704344)** Anda.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="8bfb3-129">Masukkan **[token Developer yang disetujui Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="8bfb3-130">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8bfb3-131">Pilih **autentikasi dengan Google Ads** dan berikan kredensial Google Ads Anda.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="8bfb3-132">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8bfb3-133">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="8bfb3-134">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="8bfb3-134">Configure an export</span></span>

<span data-ttu-id="8bfb3-135">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8bfb3-136">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8bfb3-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8bfb3-137">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8bfb3-138">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8bfb3-139">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Google Ads.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="8bfb3-140">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8bfb3-141">Masukkan **[ID audiens dan google ads anda](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)**, lalu pilih **sambungkan** untuk menginisialisasi sambungan ke google ads.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="8bfb3-142">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8bfb3-143">Ulangi langkah yang sama untuk bidang **nama depan** dan **nama belakang**.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="8bfb3-144">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-144">Select the segments you want to export.</span></span> <span data-ttu-id="8bfb3-145">Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke Google Ads.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="8bfb3-146">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8bfb3-147">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8bfb3-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8bfb3-148">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8bfb3-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8bfb3-149">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="8bfb3-149">Data privacy and compliance</span></span>

<span data-ttu-id="8bfb3-150">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Google Ads, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8bfb3-151">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Google Ads memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="8bfb3-152">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8bfb3-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8bfb3-153">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="8bfb3-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
