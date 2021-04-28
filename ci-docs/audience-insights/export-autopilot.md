---
title: Ekspor data Customer Insights ke Autopilot
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760147"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="a25cf-103">Mengekspor segmen ke Autopilot (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="a25cf-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="a25cf-104">Ekspor segmen profil pelanggan terpadu ke Autopilot dan gunakan untuk pemasaran email di Autopilot.</span><span class="sxs-lookup"><span data-stu-id="a25cf-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="a25cf-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="a25cf-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="a25cf-106">Anda memiliki [akun Autopilot](https://www.autopilothq.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="a25cf-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a25cf-107">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="a25cf-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a25cf-108">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="a25cf-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a25cf-109">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="a25cf-109">Known limitations</span></span>

- <span data-ttu-id="a25cf-110">Anda dapat mengekspor hingga 100.000 profil pelanggan secara total ke Autopilot.</span><span class="sxs-lookup"><span data-stu-id="a25cf-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="a25cf-111">Mengekspor ke Autopilot terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="a25cf-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="a25cf-112">Mengekspor hingga 100.000 profil ke Autopilot dapat memakan waktu hingga beberapa jam untuk menyelesaikannya.</span><span class="sxs-lookup"><span data-stu-id="a25cf-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="a25cf-113">Jumlah profil yang dapat Anda ekspor ke Autopilot tergantung dan terbatas pada kontrak Anda dengan Autopilot.</span><span class="sxs-lookup"><span data-stu-id="a25cf-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="a25cf-114">Konfigurasikan koneksi ke Autopilot</span><span class="sxs-lookup"><span data-stu-id="a25cf-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="a25cf-115">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="a25cf-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a25cf-116">Pilih **Tambahkan koneksi** dan pilih **Mailchimp** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="a25cf-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="a25cf-117">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="a25cf-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a25cf-118">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="a25cf-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a25cf-119">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="a25cf-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a25cf-120">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="a25cf-120">Choose who can use this connection.</span></span> <span data-ttu-id="a25cf-121">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="a25cf-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a25cf-122">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a25cf-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="a25cf-123">Masukkan [kunci API Autopilot](https://autopilot.docs.apiary.io/#) Anda.</span><span class="sxs-lookup"><span data-stu-id="a25cf-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="a25cf-124">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="a25cf-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a25cf-125">Pilih **Sambungkan** untuk menginisialisasi sambungan ke Autopilot.</span><span class="sxs-lookup"><span data-stu-id="a25cf-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="a25cf-126">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="a25cf-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a25cf-127">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="a25cf-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a25cf-128">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="a25cf-128">Configure an export</span></span>

<span data-ttu-id="a25cf-129">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="a25cf-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a25cf-130">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a25cf-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a25cf-131">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="a25cf-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a25cf-132">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="a25cf-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a25cf-133">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Autopilot.</span><span class="sxs-lookup"><span data-stu-id="a25cf-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="a25cf-134">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="a25cf-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="a25cf-135">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="a25cf-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a25cf-136">Ulangi langkah yang sama untuk bidang opsional lainnya seperti **nama depan**, **nama belakang**.</span><span class="sxs-lookup"><span data-stu-id="a25cf-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="a25cf-137">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="a25cf-137">Select the segments you want to export.</span></span> <span data-ttu-id="a25cf-138">Kami sangat **menyarankan untuk tidak mengekspor lebih dari 100'000 profil pelanggan secara total** ke Autopilot.</span><span class="sxs-lookup"><span data-stu-id="a25cf-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="a25cf-139">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="a25cf-139">Select **Save**.</span></span>

<span data-ttu-id="a25cf-140">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="a25cf-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a25cf-141">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a25cf-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a25cf-142">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a25cf-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a25cf-143">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="a25cf-143">Data privacy and compliance</span></span>

<span data-ttu-id="a25cf-144">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Autopilot, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="a25cf-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a25cf-145">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Autopilot memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="a25cf-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a25cf-146">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a25cf-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a25cf-147">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="a25cf-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
