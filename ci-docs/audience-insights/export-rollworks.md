---
title: Mengekspor data Customer Insights ke RollWorks
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760558"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="d25ca-103">Mengekspor daftar segmen ke RollWorks (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="d25ca-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="d25ca-104">Ekspor segmen profil pelanggan terpadu ke RollWorks dan gunakan untuk periklanan.</span><span class="sxs-lookup"><span data-stu-id="d25ca-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d25ca-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="d25ca-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="d25ca-106">Anda memiliki [akun RollWorks](https://www.rollworks.com/) dan kredensial administrator terkait.</span><span class="sxs-lookup"><span data-stu-id="d25ca-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d25ca-107">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="d25ca-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d25ca-108">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="d25ca-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d25ca-109">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="d25ca-109">Known limitations</span></span>

- <span data-ttu-id="d25ca-110">Anda dapat mengekspor hingga 250.000 profil per ekspor ke RollWorks.</span><span class="sxs-lookup"><span data-stu-id="d25ca-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="d25ca-111">Anda tidak dapat mengekspor segmen dengan kurang dari 100 profil ke RollWorks.</span><span class="sxs-lookup"><span data-stu-id="d25ca-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="d25ca-112">Mengekspor ke RollWorks terbatas pada segmen.</span><span class="sxs-lookup"><span data-stu-id="d25ca-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="d25ca-113">Mengekspor hingga 250.000 profil ke RollWorks dapat memakan waktu hingga 10 menit untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="d25ca-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="d25ca-114">Jumlah profil yang dapat Anda ekspor ke RollWorks tergantung dan terbatas pada kontrak Anda dengan RollWorks.</span><span class="sxs-lookup"><span data-stu-id="d25ca-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="d25ca-115">Konfigurasikan koneksi ke RollWorks</span><span class="sxs-lookup"><span data-stu-id="d25ca-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="d25ca-116">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="d25ca-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d25ca-117">Pilih **Tambahkan koneksi** dan pilih **RollWorks** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="d25ca-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="d25ca-118">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="d25ca-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d25ca-119">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="d25ca-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d25ca-120">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="d25ca-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d25ca-121">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="d25ca-121">Choose who can use this connection.</span></span> <span data-ttu-id="d25ca-122">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="d25ca-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d25ca-123">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d25ca-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d25ca-124">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="d25ca-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d25ca-125">Pilih **Sambungkan** untuk menginisialisasi koneksi ke RollWorks.</span><span class="sxs-lookup"><span data-stu-id="d25ca-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="d25ca-126">Pilih **Autentikasi dengan RollWorks** dan berikan kredensial admin Anda untuk RollWorks.</span><span class="sxs-lookup"><span data-stu-id="d25ca-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="d25ca-127">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="d25ca-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d25ca-128">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="d25ca-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d25ca-129">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="d25ca-129">Configure an export</span></span>

<span data-ttu-id="d25ca-130">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="d25ca-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d25ca-131">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d25ca-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d25ca-132">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="d25ca-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d25ca-133">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="d25ca-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d25ca-134">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian RollWorks.</span><span class="sxs-lookup"><span data-stu-id="d25ca-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="d25ca-135">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="d25ca-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d25ca-136">Masukkan **ID Pengiklan RollWorks** [RollWorks yang Dapat Diiklankan](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="d25ca-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="d25ca-137">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="d25ca-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d25ca-138">Segmen harus diekspor ke RollWorks.</span><span class="sxs-lookup"><span data-stu-id="d25ca-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="d25ca-139">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="d25ca-139">Select the segments you want to export.</span></span> <span data-ttu-id="d25ca-140">Pilih segmen dengan minimal 100 anggota.</span><span class="sxs-lookup"><span data-stu-id="d25ca-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="d25ca-141">Anda tidak dapat mengekspor segmen yang lebih kecil.</span><span class="sxs-lookup"><span data-stu-id="d25ca-141">You can't export smaller segments.</span></span> <span data-ttu-id="d25ca-142">Selain itu, ukuran maksimum segmen untuk diekspor adalah 250.000 anggota per ekspor.</span><span class="sxs-lookup"><span data-stu-id="d25ca-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="d25ca-143">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="d25ca-143">Select **Save**.</span></span>

<span data-ttu-id="d25ca-144">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="d25ca-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d25ca-145">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d25ca-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d25ca-146">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d25ca-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d25ca-147">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="d25ca-147">Data privacy and compliance</span></span>

<span data-ttu-id="d25ca-148">Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke RollWorks, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi.</span><span class="sxs-lookup"><span data-stu-id="d25ca-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d25ca-149">Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa RollWorks memenuhi kewajiban privasi atau keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="d25ca-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d25ca-150">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d25ca-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d25ca-151">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="d25ca-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
