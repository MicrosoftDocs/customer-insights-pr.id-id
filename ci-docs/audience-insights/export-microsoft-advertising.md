---
title: Mengekspor data Customer Insights ke Microsoft Advertising
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124504"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="3c729-103">Mengekspor segmen ke Microsoft Advertising (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="3c729-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="3c729-104">Ekspor segmen Customer Insights ke Microsoft Advertising untuk membuat audiens Customer Match.</span><span class="sxs-lookup"><span data-stu-id="3c729-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="3c729-105">Gunakan audiens ini untuk kampanye iklan Anda.</span><span class="sxs-lookup"><span data-stu-id="3c729-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3c729-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="3c729-106">Prerequisites</span></span>

-   <span data-ttu-id="3c729-107">[Akun Microsoft Advertising](https://ads.microsoft.com/) dan kredensial administrator terkait.</span><span class="sxs-lookup"><span data-stu-id="3c729-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3c729-108">Anda telah menerima ketentuan penggunaan Customer Match.</span><span class="sxs-lookup"><span data-stu-id="3c729-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="3c729-109">[Mengonfigurasi segmen](segments.md) dalam wawasan audiens anda.</span><span class="sxs-lookup"><span data-stu-id="3c729-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="3c729-110">Profil pelanggan terpadu di segmen yang diekspor berisi bidang dengan alamat email.</span><span class="sxs-lookup"><span data-stu-id="3c729-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3c729-111">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="3c729-111">Known limitations</span></span>

- <span data-ttu-id="3c729-112">Anda dapat mengekspor hingga 500 ribu profil per ekspor ke Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="3c729-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="3c729-113">Mengekspor ke Microsoft Advertising terbatas pada segmen.</span><span class="sxs-lookup"><span data-stu-id="3c729-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="3c729-114">Mengekspor hingga 500 ribu profil ke Microsoft Advertising dapat memakan waktu hingga 10 menit untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="3c729-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="3c729-115">Siapkan sambungan ke Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="3c729-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="3c729-116">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="3c729-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3c729-117">Pilih **Tambahkan koneksi** dan pilih **Microsoft Advertising** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="3c729-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="3c729-118">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="3c729-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3c729-119">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="3c729-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3c729-120">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="3c729-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3c729-121">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="3c729-121">Choose who can use this connection.</span></span> <span data-ttu-id="3c729-122">Default-nya adalah administrator.</span><span class="sxs-lookup"><span data-stu-id="3c729-122">The default is administrators.</span></span> <span data-ttu-id="3c729-123">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3c729-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3c729-124">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="3c729-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3c729-125">Pilih **Sambungkan** untuk menginisialisasi koneksi ke Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="3c729-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="3c729-126">Pilih **Autentikasi dengan Microsoft Advertising** dan berikan kredensial admin Anda untuk Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="3c729-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="3c729-127">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="3c729-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="3c729-128">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="3c729-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="3c729-129">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="3c729-129">Configure an export</span></span>

<span data-ttu-id="3c729-130">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="3c729-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3c729-131">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3c729-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3c729-132">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="3c729-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3c729-133">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="3c729-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3c729-134">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="3c729-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="3c729-135">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="3c729-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3c729-136">Pilih segmen yang akan diekspor.</span><span class="sxs-lookup"><span data-stu-id="3c729-136">Select the segments to export.</span></span> <span data-ttu-id="3c729-137">Audiens Customer Match di Microsoft Advertising secara otomatis dibuat dengan nama segmen yang dipilih untuk diekspor.</span><span class="sxs-lookup"><span data-stu-id="3c729-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="3c729-138">Setiap segmen akan menghasilkan audiens Customer Match terpisah.</span><span class="sxs-lookup"><span data-stu-id="3c729-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="3c729-139">Masukkan **ID Pelanggan Microsoft Advertising dan ID Akun** Anda.</span><span class="sxs-lookup"><span data-stu-id="3c729-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="3c729-140">Anda dapat menemukan ID Pelanggan (`cid`) dan ID Akun (`aid`) dalam parameter URL saat Anda masuk ke Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="3c729-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="3c729-141">Di bagian **Pencocokan data**, di bidang **email** pilih bidang di profil pelanggan terpadu Anda dengan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="3c729-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="3c729-142">Segmen harus diekspor ke Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="3c729-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="3c729-143">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="3c729-143">Select **Save**.</span></span>

<span data-ttu-id="3c729-144">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="3c729-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3c729-145">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3c729-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3c729-146">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3c729-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3c729-147">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="3c729-147">Data privacy and compliance</span></span>

<span data-ttu-id="3c729-148">Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Microsoft Advertising, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi.</span><span class="sxs-lookup"><span data-stu-id="3c729-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3c729-149">Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa Microsoft Advertising memenuhi kewajiban privasi atau keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="3c729-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3c729-150">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3c729-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="3c729-151">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="3c729-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
