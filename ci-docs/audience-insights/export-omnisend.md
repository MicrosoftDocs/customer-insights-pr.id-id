---
title: Mengekspor data Customer Insights ke Omnisend
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124505"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="02c98-103">Mengekspor segmen ke Omnisend (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="02c98-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="02c98-104">Ekspor segmen profil pelanggan terpadu ke Omnisend dan gunakan untuk aktivitas pemasaran.</span><span class="sxs-lookup"><span data-stu-id="02c98-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="02c98-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="02c98-105">Prerequisites</span></span>

-   <span data-ttu-id="02c98-106">Anda memiliki [akun Omnisend](https://www.omnisend.com/) dan kredensial administrator terkait.</span><span class="sxs-lookup"><span data-stu-id="02c98-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="02c98-107">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="02c98-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="02c98-108">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="02c98-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="02c98-109">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="02c98-109">Known limitations</span></span>

- <span data-ttu-id="02c98-110">Anda dapat mengekspor hingga 1 juta profil per ekspor ke Omnisend dan dapat memakan waktu hingga 4 jam untuk menyelesaikannya.</span><span class="sxs-lookup"><span data-stu-id="02c98-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="02c98-111">Mengekspor ke Omnisend terbatas pada segmen.</span><span class="sxs-lookup"><span data-stu-id="02c98-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="02c98-112">Jumlah profil yang dapat Anda ekspor ke Omnisend tergantung pada kontrak Anda dengan Omnisend.</span><span class="sxs-lookup"><span data-stu-id="02c98-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="02c98-113">Konfigurasikan koneksi ke Omnisend</span><span class="sxs-lookup"><span data-stu-id="02c98-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="02c98-114">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="02c98-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="02c98-115">Pilih **Tambahkan koneksi** dan pilih **Omnisend** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="02c98-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="02c98-116">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="02c98-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="02c98-117">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="02c98-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="02c98-118">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="02c98-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="02c98-119">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="02c98-119">Choose who can use this connection.</span></span> <span data-ttu-id="02c98-120">Secara default hanya administrator.</span><span class="sxs-lookup"><span data-stu-id="02c98-120">By default it's only administrators.</span></span> <span data-ttu-id="02c98-121">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="02c98-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="02c98-122">Masukkan [kunci API Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key) Anda.</span><span class="sxs-lookup"><span data-stu-id="02c98-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="02c98-123">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="02c98-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="02c98-124">Pilih **Sambungkan** untuk menginisialisasi koneksi ke Omnisend.</span><span class="sxs-lookup"><span data-stu-id="02c98-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="02c98-125">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="02c98-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="02c98-126">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="02c98-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="02c98-127">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="02c98-127">Configure an export</span></span>

<span data-ttu-id="02c98-128">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="02c98-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="02c98-129">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="02c98-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="02c98-130">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="02c98-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="02c98-131">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="02c98-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="02c98-132">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Omnisend.</span><span class="sxs-lookup"><span data-stu-id="02c98-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="02c98-133">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="02c98-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="02c98-134">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="02c98-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="02c98-135">Segmen harus diekspor ke Omnisend.</span><span class="sxs-lookup"><span data-stu-id="02c98-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="02c98-136">Secara opsional, Anda dapat mengekspor nama depan, nama belakang, Alamat, Negara/Kawasan, Negara bagian, kota, dan Kode Pos untuk membuat email yang lebih dipersonalisasi.</span><span class="sxs-lookup"><span data-stu-id="02c98-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="02c98-137">Pilih **Tambah atribut** untuk memetakan bidang ini.</span><span class="sxs-lookup"><span data-stu-id="02c98-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="02c98-138">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="02c98-138">Select **Save**.</span></span>

<span data-ttu-id="02c98-139">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="02c98-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="02c98-140">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="02c98-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="02c98-141">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="02c98-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="02c98-142">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="02c98-142">Data privacy and compliance</span></span>

<span data-ttu-id="02c98-143">Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Omnisend, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi.</span><span class="sxs-lookup"><span data-stu-id="02c98-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="02c98-144">Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa Omnisend memenuhi kewajiban privasi atau keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="02c98-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="02c98-145">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="02c98-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="02c98-146">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="02c98-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
