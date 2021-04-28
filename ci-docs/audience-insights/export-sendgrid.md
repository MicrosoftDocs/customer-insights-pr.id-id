---
title: Ekspor data Customer Insights ke SendGrid
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759769"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="53f5d-103">Mengekspor segmen ke SendGrid (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="53f5d-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="53f5d-104">Ekspor segmen profil pelanggan terpadu ke daftar kontak SendGrid dan gunakan untuk kampanye dan pemasaran email di SendGrid.</span><span class="sxs-lookup"><span data-stu-id="53f5d-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="53f5d-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="53f5d-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="53f5d-106">Anda memiliki [akun SendGrid](https://sendgrid.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="53f5d-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="53f5d-107">Daftar kontak sudah ada di SendGrid dan id yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="53f5d-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="53f5d-108">Untuk informasi lebih lanjut, lihat [SendGrid - Mengelola kontak](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="53f5d-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="53f5d-109">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="53f5d-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="53f5d-110">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="53f5d-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="53f5d-111">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="53f5d-111">Known limitations</span></span>

- <span data-ttu-id="53f5d-112">Hingga 100.000 profil secara total ke SendGrid.</span><span class="sxs-lookup"><span data-stu-id="53f5d-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="53f5d-113">Mengekspor ke SendGrid terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="53f5d-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="53f5d-114">Mengekspor hingga 100.000 profil ke SendGrid dapat memakan waktu hingga beberapa jam untuk menyelesaikannya.</span><span class="sxs-lookup"><span data-stu-id="53f5d-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="53f5d-115">Jumlah profil yang dapat Anda ekspor ke SendGrid tergantung dan terbatas pada kontrak Anda dengan SendGrid.</span><span class="sxs-lookup"><span data-stu-id="53f5d-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="53f5d-116">Konfigurasikan koneksi ke SendGrid</span><span class="sxs-lookup"><span data-stu-id="53f5d-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="53f5d-117">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="53f5d-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="53f5d-118">Pilih **Tambahkan koneksi** dan pilih **SendGrid** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="53f5d-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="53f5d-119">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="53f5d-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="53f5d-120">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="53f5d-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="53f5d-121">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="53f5d-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="53f5d-122">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="53f5d-122">Choose who can use this connection.</span></span> <span data-ttu-id="53f5d-123">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="53f5d-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="53f5d-124">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="53f5d-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="53f5d-125">Masukkan **kunci API SendGrid** [kunci API SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/) Anda.</span><span class="sxs-lookup"><span data-stu-id="53f5d-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="53f5d-126">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="53f5d-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="53f5d-127">Pilih **Sambungkan** untuk menginisialisasi sambungan ke SendGrid.</span><span class="sxs-lookup"><span data-stu-id="53f5d-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="53f5d-128">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="53f5d-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="53f5d-129">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="53f5d-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="53f5d-130">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="53f5d-130">Configure an export</span></span>

<span data-ttu-id="53f5d-131">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="53f5d-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="53f5d-132">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="53f5d-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="53f5d-133">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="53f5d-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="53f5d-134">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="53f5d-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="53f5d-135">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian SendGrid.</span><span class="sxs-lookup"><span data-stu-id="53f5d-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="53f5d-136">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="53f5d-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="53f5d-137">Masukkan **[id daftar SendGrid Anda](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="53f5d-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="53f5d-138">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="53f5d-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="53f5d-139">Ulangi langkah yang sama untuk bidang opsional lainnya seperti **nama depan**, **nama belakang**, **negara/Kawasan**, **Negara Bagian**, **Kota**, dan **Kode pos**.</span><span class="sxs-lookup"><span data-stu-id="53f5d-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="53f5d-140">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="53f5d-140">Select the segments you want to export.</span></span> <span data-ttu-id="53f5d-141">Kami sangat **menyarankan untuk tidak mengekspor lebih dari 100'000 profil pelanggan secara total** ke SendGrid.</span><span class="sxs-lookup"><span data-stu-id="53f5d-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="53f5d-142">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="53f5d-142">Select **Save**.</span></span>

<span data-ttu-id="53f5d-143">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="53f5d-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="53f5d-144">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="53f5d-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="53f5d-145">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="53f5d-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="53f5d-146">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="53f5d-146">Data privacy and compliance</span></span>

<span data-ttu-id="53f5d-147">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke SendGrid, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="53f5d-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="53f5d-148">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa SendGrid memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="53f5d-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="53f5d-149">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="53f5d-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="53f5d-150">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="53f5d-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]