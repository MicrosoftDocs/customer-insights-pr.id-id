---
title: Mengekspor data Customer Insights ke Constant Contact
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760556"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="f9681-103">Mengekspor daftar segmen ke Constant Contact (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="f9681-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="f9681-104">Ekspor segmen profil pelanggan terpadu ke Constant Contact dan gunakan untuk aktivitas pemasaran.</span><span class="sxs-lookup"><span data-stu-id="f9681-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f9681-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="f9681-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f9681-106">Anda memiliki [akun Constant Contact](https://www.constantcontact.com/account-home) dan kredensial administrator terkait.</span><span class="sxs-lookup"><span data-stu-id="f9681-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f9681-107">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="f9681-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f9681-108">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="f9681-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f9681-109">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="f9681-109">Known limitations</span></span>

- <span data-ttu-id="f9681-110">Anda dapat mengekspor hingga 1 juta profil per ekspor ke Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="f9681-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="f9681-111">Mengekspor ke Constant Contact terbatas pada segmen.</span><span class="sxs-lookup"><span data-stu-id="f9681-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="f9681-112">Mengekspor hingga 1 juta profil ke Constant Contact dapat memakan waktu hingga 1 jam untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="f9681-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="f9681-113">Jumlah profil yang dapat Anda ekspor ke Constant Contact tergantung dan terbatas pada kontrak Anda dengan Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="f9681-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="f9681-114">Atur koneksi ke Constant Contact</span><span class="sxs-lookup"><span data-stu-id="f9681-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="f9681-115">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="f9681-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f9681-116">Pilih **Tambahkan koneksi** dan pilih **Constant Contact** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="f9681-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="f9681-117">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="f9681-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f9681-118">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="f9681-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f9681-119">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="f9681-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f9681-120">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="f9681-120">Choose who can use this connection.</span></span> <span data-ttu-id="f9681-121">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="f9681-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f9681-122">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f9681-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f9681-123">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="f9681-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f9681-124">Pilih **Sambungkan** untuk menginisialisasi koneksi ke Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="f9681-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="f9681-125">Pilih **Autentikasi dengan AdRoll** dan berikan kredensial admin Anda untuk Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="f9681-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="f9681-126">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="f9681-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f9681-127">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="f9681-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f9681-128">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="f9681-128">Configure an export</span></span>

<span data-ttu-id="f9681-129">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="f9681-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f9681-130">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f9681-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f9681-131">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="f9681-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f9681-132">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="f9681-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f9681-133">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="f9681-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="f9681-134">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="f9681-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f9681-135">Masukkan [**ID daftar Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="f9681-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="f9681-136">Buka daftar di Constant Contact untuk menemukan ID daftar di URL.</span><span class="sxs-lookup"><span data-stu-id="f9681-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="f9681-137">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="f9681-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f9681-138">Segmen harus diekspor ke Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="f9681-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="f9681-139">Atau, anda dapat mengekspor nama depan dan nama belakang sebagai bidang tambahan untuk membuat email yang lebih disesuaikan.</span><span class="sxs-lookup"><span data-stu-id="f9681-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="f9681-140">Pilih **Tambah atribut** untuk memetakan bidang ini.</span><span class="sxs-lookup"><span data-stu-id="f9681-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="f9681-141">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="f9681-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="f9681-142">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="f9681-142">Select **Save**.</span></span>

<span data-ttu-id="f9681-143">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="f9681-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f9681-144">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f9681-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f9681-145">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f9681-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f9681-146">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="f9681-146">Data privacy and compliance</span></span>

<span data-ttu-id="f9681-147">Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Constant Contact, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi.</span><span class="sxs-lookup"><span data-stu-id="f9681-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f9681-148">Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa Constant Contact memenuhi kewajiban privasi atau keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="f9681-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f9681-149">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f9681-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="f9681-150">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="f9681-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
