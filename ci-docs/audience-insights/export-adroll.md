---
title: Ekspor data Customer Insights ke AdRoll
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304833"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="61c02-103">Mengekspor segmen ke AdRoll (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="61c02-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="61c02-104">Mengekspor segmen profil pelanggan terpadu ke AdRoll dan menggunakannya untuk iklan.</span><span class="sxs-lookup"><span data-stu-id="61c02-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="61c02-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="61c02-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="61c02-106">Anda memiliki [akun AdRoll](https://www.adroll.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="61c02-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="61c02-107">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="61c02-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="61c02-108">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="61c02-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="61c02-109">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="61c02-109">Known limitations</span></span>

- <span data-ttu-id="61c02-110">Anda dapat mengekspor hingga 250.000 profil sekaligus ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="61c02-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="61c02-111">Anda tidak dapat mengekspor segmen dengan kurang dari 100 profil ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="61c02-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="61c02-112">Mengekspor ke AdRoll terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="61c02-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="61c02-113">Mengekspor hingga 250.000 profil ke AdRoll dapat berlangsung hingga 10 menit untuk menyelesaikannya.</span><span class="sxs-lookup"><span data-stu-id="61c02-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="61c02-114">Jumlah profil yang dapat Anda ekspor ke AdRoll tergantung pada kontrak Anda dengan AdRoll.</span><span class="sxs-lookup"><span data-stu-id="61c02-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="61c02-115">Konfigurasikan koneksi ke AdRoll</span><span class="sxs-lookup"><span data-stu-id="61c02-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="61c02-116">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="61c02-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="61c02-117">Pilih **Tambahkan koneksi** dan pilih **AdRoll** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="61c02-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="61c02-118">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="61c02-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="61c02-119">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="61c02-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="61c02-120">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="61c02-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="61c02-121">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="61c02-121">Choose who can use this connection.</span></span> <span data-ttu-id="61c02-122">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="61c02-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="61c02-123">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="61c02-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="61c02-124">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="61c02-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="61c02-125">Pilih **Sambungkan** untuk menginisialisasi sambungan ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="61c02-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="61c02-126">Pilih **autentikasi dengan AdRoll** dan berikan kredensial admin Anda untuk AdRoll.</span><span class="sxs-lookup"><span data-stu-id="61c02-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="61c02-127">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="61c02-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="61c02-128">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="61c02-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="61c02-129">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="61c02-129">Configure an export</span></span>

<span data-ttu-id="61c02-130">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="61c02-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="61c02-131">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="61c02-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="61c02-132">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="61c02-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="61c02-133">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="61c02-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="61c02-134">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian AdRoll.</span><span class="sxs-lookup"><span data-stu-id="61c02-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="61c02-135">Jika Anda tidak melihat nama bagian ini, maka tidak ada sambungan dari jenis ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="61c02-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="61c02-136">Masukkan **ID Pengiklan AdRoll** Anda.</span><span class="sxs-lookup"><span data-stu-id="61c02-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="61c02-137">Untuk informasi lebih lanjut, lihat [Profil Pemilik Iklan AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="61c02-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="61c02-138">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="61c02-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="61c02-139">Ini harus diekspor ke AdRoll.</span><span class="sxs-lookup"><span data-stu-id="61c02-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="61c02-140">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="61c02-140">Select the segments you want to export.</span></span> <span data-ttu-id="61c02-141">Pilih segmen dengan minimal 100 anggota.</span><span class="sxs-lookup"><span data-stu-id="61c02-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="61c02-142">Anda tidak dapat mengekspor segmen yang lebih kecil.</span><span class="sxs-lookup"><span data-stu-id="61c02-142">You can't export smaller segments.</span></span> <span data-ttu-id="61c02-143">Selain itu, ukuran maksimum segmen untuk diekspor adalah 250.000 anggota per ekspor.</span><span class="sxs-lookup"><span data-stu-id="61c02-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="61c02-144">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="61c02-144">Select **Save**.</span></span>

<span data-ttu-id="61c02-145">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="61c02-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="61c02-146">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="61c02-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="61c02-147">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="61c02-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="61c02-148">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="61c02-148">Data privacy and compliance</span></span>

<span data-ttu-id="61c02-149">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke AdRoll, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="61c02-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="61c02-150">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa AdRoll memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="61c02-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="61c02-151">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="61c02-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="61c02-152">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="61c02-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
