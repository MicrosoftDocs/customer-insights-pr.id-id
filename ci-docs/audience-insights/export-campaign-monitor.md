---
title: Mengekspor data Customer Insights ke Campaign Monitor
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760557"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a><span data-ttu-id="12523-103">Mengekspor daftar segmen ke Campaign Monitor (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="12523-103">Export segment lists to Campaign Monitor (preview)</span></span>

<span data-ttu-id="12523-104">Ekspor segmen profil pelanggan terpadu ke Campaign Monitor dan gunakan untuk aktivitas pemasaran.</span><span class="sxs-lookup"><span data-stu-id="12523-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="12523-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="12523-105">Prerequisites</span></span>

-   <span data-ttu-id="12523-106">Anda memiliki [akun Campaign Monitor](https://www.campaignmonitor.com/) dan kredensial administrator terkait.</span><span class="sxs-lookup"><span data-stu-id="12523-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="12523-107">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="12523-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="12523-108">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="12523-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="12523-109">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="12523-109">Known limitations</span></span>

- <span data-ttu-id="12523-110">Anda dapat mengekspor hingga 1 juta profil per ekspor ke Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="12523-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="12523-111">Mengekspor ke Campaign Monitor terbatas pada segmen.</span><span class="sxs-lookup"><span data-stu-id="12523-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="12523-112">Mengekspor hingga 1 juta profil ke Campaign Monitor dapat memakan waktu hingga 20 menit untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="12523-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="12523-113">Jumlah profil yang dapat Anda ekspor ke Campaign Monitor tergantung dan terbatas pada kontrak Anda dengan Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="12523-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="12523-114">Konfigurasikan koneksi ke Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="12523-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="12523-115">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="12523-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="12523-116">Pilih **Tambahkan koneksi** dan pilih **Campaign Monitor** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="12523-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="12523-117">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="12523-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="12523-118">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="12523-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="12523-119">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="12523-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="12523-120">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="12523-120">Choose who can use this connection.</span></span> <span data-ttu-id="12523-121">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="12523-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="12523-122">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="12523-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="12523-123">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="12523-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="12523-124">Pilih **Sambungkan** untuk menginisialisasi koneksi ke Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="12523-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="12523-125">Pilih **Autentikasi dengan Campaign Monitor** dan berikan kredensial admin Anda untuk Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="12523-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="12523-126">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="12523-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="12523-127">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="12523-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="12523-128">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="12523-128">Configure an export</span></span>

<span data-ttu-id="12523-129">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="12523-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="12523-130">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="12523-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="12523-131">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="12523-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="12523-132">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="12523-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="12523-133">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="12523-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="12523-134">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="12523-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="12523-135">Masukkan [**ID daftar Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="12523-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="12523-136">[Buat kunci API](https://www.campaignmonitor.com/api/getting-started/) dari **Pengaturan Akun** di Campaign Monitor terlebih dahulu untuk melihat ID daftar API.</span><span class="sxs-lookup"><span data-stu-id="12523-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="12523-137">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="12523-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="12523-138">Segmen harus diekspor ke Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="12523-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="12523-139">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="12523-139">Select **Save**.</span></span>

<span data-ttu-id="12523-140">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="12523-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="12523-141">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="12523-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="12523-142">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="12523-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="12523-143">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="12523-143">Data privacy and compliance</span></span>

<span data-ttu-id="12523-144">Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Campaign Monitor, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi.</span><span class="sxs-lookup"><span data-stu-id="12523-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="12523-145">Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa Campaign Monitor memenuhi kewajiban privasi atau keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="12523-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="12523-146">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="12523-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="12523-147">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="12523-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
