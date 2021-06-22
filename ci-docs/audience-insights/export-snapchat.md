---
title: Mengekspor data Customer Insights ke Snapchat
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124047"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="582ad-103">Mengekspor segmen ke Snapchat (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="582ad-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="582ad-104">Ekspor segmen profil pelanggan terpadu ke Snapchat dan gunakan untuk periklanan.</span><span class="sxs-lookup"><span data-stu-id="582ad-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="582ad-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="582ad-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="582ad-106">Anda memiliki [akun Snapchat Business](https://business.snapchat.com/), [akun Snapchat Ads](https://ads.snapchat.com/), dan kredensial administrator terkait.</span><span class="sxs-lookup"><span data-stu-id="582ad-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="582ad-107">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="582ad-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="582ad-108">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="582ad-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="582ad-109">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="582ad-109">Known limitations</span></span>

- <span data-ttu-id="582ad-110">Mengekspor ke Snapchat terbatas pada segmen.</span><span class="sxs-lookup"><span data-stu-id="582ad-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="582ad-111">Mengekspor hingga 1 juta profil ke Snapchat dapat memakan waktu hingga 15 menit untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="582ad-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="582ad-112">Konfigurasikan koneksi ke Snapchat</span><span class="sxs-lookup"><span data-stu-id="582ad-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="582ad-113">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="582ad-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="582ad-114">Pilih **Tambahkan koneksi** dan pilih **Snapchat** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="582ad-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="582ad-115">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="582ad-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="582ad-116">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="582ad-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="582ad-117">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="582ad-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="582ad-118">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="582ad-118">Choose who can use this connection.</span></span> <span data-ttu-id="582ad-119">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="582ad-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="582ad-120">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="582ad-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="582ad-121">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="582ad-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="582ad-122">Pilih **Sambungkan** untuk menginisialisasi koneksi ke Snapchat.</span><span class="sxs-lookup"><span data-stu-id="582ad-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="582ad-123">Pilih **Autentikasi dengan Snapchat** dan berikan kredensial admin Anda untuk Snapchat.</span><span class="sxs-lookup"><span data-stu-id="582ad-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="582ad-124">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="582ad-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="582ad-125">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="582ad-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="582ad-126">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="582ad-126">Configure an export</span></span>

<span data-ttu-id="582ad-127">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="582ad-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="582ad-128">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="582ad-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="582ad-129">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="582ad-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="582ad-130">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="582ad-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="582ad-131">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Snapchat.</span><span class="sxs-lookup"><span data-stu-id="582ad-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="582ad-132">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="582ad-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="582ad-133">Masukkan [**ID audiens Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="582ad-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="582ad-134">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="582ad-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="582ad-135">Segmen harus diekspor ke Snapchat.</span><span class="sxs-lookup"><span data-stu-id="582ad-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="582ad-136">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="582ad-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="582ad-137">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="582ad-137">Select **Save**.</span></span>

<span data-ttu-id="582ad-138">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="582ad-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="582ad-139">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="582ad-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="582ad-140">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="582ad-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="582ad-141">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="582ad-141">Data privacy and compliance</span></span>

<span data-ttu-id="582ad-142">Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Snapchat, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi.</span><span class="sxs-lookup"><span data-stu-id="582ad-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="582ad-143">Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa Snapchat memenuhi kewajiban privasi atau keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="582ad-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="582ad-144">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="582ad-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="582ad-145">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="582ad-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
