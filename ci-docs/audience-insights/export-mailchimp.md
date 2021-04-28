---
title: Ekspor data Customer Insights ke Mailchimp
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759882"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="71aef-103">Mengekspor daftar segmen ke Mailchimp (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="71aef-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="71aef-104">Ekspor segmen profil pelanggan terpadu ke MailChimp untuk membuat kampanye newsletter dan email.</span><span class="sxs-lookup"><span data-stu-id="71aef-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="71aef-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="71aef-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="71aef-106">Anda memiliki [akun Mailchimp](https://mailchimp.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="71aef-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="71aef-107">Audiens sudah ada di Mailchimp dan id yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="71aef-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="71aef-108">Untuk informasi lebih lanjut, lihat [audiens Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="71aef-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="71aef-109">Anda telah [mengonfigurasi segmen](segments.md)</span><span class="sxs-lookup"><span data-stu-id="71aef-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="71aef-110">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="71aef-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="71aef-111">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="71aef-111">Known limitations</span></span>

- <span data-ttu-id="71aef-112">Hingga 1 juta profil per ekspor ke Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="71aef-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="71aef-113">Mengekspor ke Mailchimp terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="71aef-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="71aef-114">Mengekspor segmen dengan 1 juta profil dapat memakan waktu hingga tiga jam.</span><span class="sxs-lookup"><span data-stu-id="71aef-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="71aef-115">Jumlah profil yang dapat Anda ekspor ke Mailchimp tergantung dan terbatas pada kontrak Anda dengan Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="71aef-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="71aef-116">Konfigurasikan koneksi ke Mailchimp</span><span class="sxs-lookup"><span data-stu-id="71aef-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="71aef-117">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="71aef-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="71aef-118">Pilih **Tambahkan koneksi** dan pilih **Mailchimp** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="71aef-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="71aef-119">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="71aef-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="71aef-120">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="71aef-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="71aef-121">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="71aef-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="71aef-122">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="71aef-122">Choose who can use this connection.</span></span> <span data-ttu-id="71aef-123">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="71aef-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="71aef-124">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="71aef-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="71aef-125">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="71aef-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="71aef-126">Pilih **Sambungkan** untuk menginisialisasi koneksi ke Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="71aef-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="71aef-127">Pilih **autentikasi dengan Mailchimp** dan berikan kredensial Mailchimp Anda.</span><span class="sxs-lookup"><span data-stu-id="71aef-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="71aef-128">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="71aef-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="71aef-129">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="71aef-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="71aef-130">Konfigurasikan konektor</span><span class="sxs-lookup"><span data-stu-id="71aef-130">Configure the connector</span></span>

<span data-ttu-id="71aef-131">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="71aef-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="71aef-132">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="71aef-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="71aef-133">Buka **Data**> **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="71aef-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="71aef-134">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="71aef-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="71aef-135">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="71aef-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="71aef-136">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="71aef-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="71aef-137">Masukkan **[ID audiens Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="71aef-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="71aef-138">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="71aef-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="71aef-139">Secara opsional, Anda dapat mengekspor **nama depan** dan **nama belakang** untuk membuat email yang lebih dipersonalisasi.</span><span class="sxs-lookup"><span data-stu-id="71aef-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="71aef-140">Pilih **Tambah atribut** untuk memetakan bidang ini.</span><span class="sxs-lookup"><span data-stu-id="71aef-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="71aef-141">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="71aef-141">Select the segments you want to export.</span></span> <span data-ttu-id="71aef-142">Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="71aef-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="71aef-143">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="71aef-143">Select **Save**.</span></span>

<span data-ttu-id="71aef-144">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="71aef-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="71aef-145">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="71aef-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="71aef-146">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="71aef-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="71aef-147">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="71aef-147">Data privacy and compliance</span></span>

<span data-ttu-id="71aef-148">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Mailchimp, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="71aef-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="71aef-149">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Mailchimp memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="71aef-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="71aef-150">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="71aef-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="71aef-151">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="71aef-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
