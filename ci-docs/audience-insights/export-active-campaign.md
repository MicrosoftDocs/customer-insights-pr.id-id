---
title: Mengekspor data Customer Insights ke ActiveCampaign
description: Pelajari lebih lanjut cara mengkonfigurasi sambungan dan mengekspor ke ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314629"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="bd764-103">Mengekspor segmen ke ActiveCampaign (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="bd764-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="bd764-104">Mengekspor segmen profil pelanggan terpadu ke ActiveCampaign dan menggunakannya untuk aktivitas pemasaran.</span><span class="sxs-lookup"><span data-stu-id="bd764-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bd764-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="bd764-105">Prerequisites</span></span>

-   <span data-ttu-id="bd764-106">Anda memiliki [akun ActiveCampaign](https://www.activecampaign.com/) dan kredensial administrator yang terkait.</span><span class="sxs-lookup"><span data-stu-id="bd764-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="bd764-107">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="bd764-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="bd764-108">Profil pelanggan terpadu di segmen yang diekspor berisi bidang dengan alamat email.</span><span class="sxs-lookup"><span data-stu-id="bd764-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bd764-109">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="bd764-109">Known limitations</span></span>

- <span data-ttu-id="bd764-110">Anda dapat mengekspor hingga 1 juta profil per ekspor ke ActiveCampaign dan membutuhkan waktu hingga 90 menit untuk menyelesaikannya.</span><span class="sxs-lookup"><span data-stu-id="bd764-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="bd764-111">Mengekspor ke ActiveCampaign terbatas pada segmen.</span><span class="sxs-lookup"><span data-stu-id="bd764-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="bd764-112">Jumlah profil yang dapat Anda ekspor ke ActiveCampaign tergantung pada kontrak Anda dengan ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="bd764-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="bd764-113">Siapkan sambungan ke ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="bd764-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="bd764-114">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="bd764-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bd764-115">Pilih **Tambah koneksi** dan pilih **ActiveCampaign** untuk mengkonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="bd764-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="bd764-116">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="bd764-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bd764-117">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="bd764-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bd764-118">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="bd764-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bd764-119">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="bd764-119">Choose who can use this connection.</span></span> <span data-ttu-id="bd764-120">Secara default hanya administrator.</span><span class="sxs-lookup"><span data-stu-id="bd764-120">By default, it's only administrators.</span></span> <span data-ttu-id="bd764-121">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bd764-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bd764-122">Masukkan [Hostname titik akhir REST dan Kunci API ActiveCampaign](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="bd764-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="bd764-123">Hostname titik akhir REST adalah hanya hostname, tanpa https://.</span><span class="sxs-lookup"><span data-stu-id="bd764-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="bd764-124">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="bd764-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="bd764-125">Pilih **Sambungkan** untuk memulai koneksi ke ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="bd764-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="bd764-126">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="bd764-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="bd764-127">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="bd764-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bd764-128">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="bd764-128">Configure an export</span></span>

<span data-ttu-id="bd764-129">Anda bisa mengonfigurasi ekspor jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="bd764-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="bd764-130">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bd764-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bd764-131">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="bd764-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bd764-132">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="bd764-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bd764-133">Di bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="bd764-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="bd764-134">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="bd764-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bd764-135">Masukkan [**ID daftar ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign) Anda.</span><span class="sxs-lookup"><span data-stu-id="bd764-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="bd764-136">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="bd764-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="bd764-137">Mengekspor segmen ke ActiveCampaign harus dilakukan.</span><span class="sxs-lookup"><span data-stu-id="bd764-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="bd764-138">Atau, Anda dapat mengekspor nama depan, nama belakang, dan Telepon untuk membuat email yang lebih dipersonalisasi.</span><span class="sxs-lookup"><span data-stu-id="bd764-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="bd764-139">Pilih Tambah atribut untuk memetakan bidang ini.</span><span class="sxs-lookup"><span data-stu-id="bd764-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="bd764-140">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="bd764-140">Select **Save**.</span></span>

<span data-ttu-id="bd764-141">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="bd764-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bd764-142">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bd764-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bd764-143">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bd764-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bd764-144">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="bd764-144">Data privacy and compliance</span></span>

<span data-ttu-id="bd764-145">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mentransmisikan data ke ActiveCampaign, Anda mengizinkan transfer data di luar batas kesesuaian untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi.</span><span class="sxs-lookup"><span data-stu-id="bd764-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bd764-146">Microsoft akan mengalihkan data tersebut berdasarkan instruksi Anda, namun Anda bertanggung jawab untuk memastikan bahwa ActiveCampaign memenuhi privasi atau jaminan keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="bd764-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bd764-147">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bd764-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="bd764-148">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="bd764-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
