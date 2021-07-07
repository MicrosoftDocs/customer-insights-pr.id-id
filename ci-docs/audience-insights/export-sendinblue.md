---
title: Mengekspor data Customer Insights ke Sendinblue
description: Pelajari lebih lanjut cara mengkonfigurasi sambungan dan mengekspor ke Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314628"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="0d909-103">Mengekspor segmen ke Sendinblue (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="0d909-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="0d909-104">Ekspor segmen profil pelanggan terpadu untuk membuat kampanye, menyediakan pemasaran melalui email, dan menggunakan grup pelanggan tertentu dengan Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="0d909-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0d909-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="0d909-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="0d909-106">Anda memiliki [akun Sendinblue](https://www.sendinblue.com/) dan kredensial administrator yang terkait.</span><span class="sxs-lookup"><span data-stu-id="0d909-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0d909-107">Ada daftar lama di Sendinblue dan ID yang terkait.</span><span class="sxs-lookup"><span data-stu-id="0d909-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="0d909-108">Anda telah [mengonfigurasi segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0d909-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="0d909-109">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="0d909-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0d909-110">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="0d909-110">Known limitations</span></span>

- <span data-ttu-id="0d909-111">Hingga 1 juta profil per ekspor ke Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="0d909-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="0d909-112">Mengekspor ke Sendinblue terbatas pada segmen.</span><span class="sxs-lookup"><span data-stu-id="0d909-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="0d909-113">Mengekspor segmen dengan total 1 juta profil dapat berlangsung hingga 90 menit.</span><span class="sxs-lookup"><span data-stu-id="0d909-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="0d909-114">Jumlah profil yang dapat Anda ekspor ke Sendinblue tergantung dan terbatas pada kontrak Anda dengan Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="0d909-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="0d909-115">Konfigurasikan sambungan ke Sendinblue</span><span class="sxs-lookup"><span data-stu-id="0d909-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="0d909-116">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="0d909-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0d909-117">Pilih **Tambah koneksi** dan pilih **Sendinblue** untuk mengkonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="0d909-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="0d909-118">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="0d909-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0d909-119">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="0d909-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0d909-120">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="0d909-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0d909-121">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="0d909-121">Choose who can use this connection.</span></span> <span data-ttu-id="0d909-122">Secara default hanya administrator.</span><span class="sxs-lookup"><span data-stu-id="0d909-122">By default it's only administrators.</span></span> <span data-ttu-id="0d909-123">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0d909-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0d909-124">Masukkan kunci **[API SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="0d909-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="0d909-125">Pilih **Saya setuju** untuk mengkonfirmasi **privasi dan kesesuaian Data**, lalu pilih **Sambungkan** untuk menginisialisasi sambungan ke Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="0d909-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="0d909-126">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="0d909-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0d909-127">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="0d909-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0d909-128">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="0d909-128">Configure an export</span></span>

<span data-ttu-id="0d909-129">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="0d909-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0d909-130">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0d909-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0d909-131">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="0d909-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0d909-132">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="0d909-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0d909-133">Di bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="0d909-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="0d909-134">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="0d909-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0d909-135">Masukkan **ID daftar Sendinblue** Anda</span><span class="sxs-lookup"><span data-stu-id="0d909-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="0d909-136">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="0d909-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="0d909-137">Atau, Anda dapat mengekspor **nama depan**, **nama belakang**, dan **Telepon**  untuk membuat email yang lebih dipersonalisasi.</span><span class="sxs-lookup"><span data-stu-id="0d909-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="0d909-138">Pilih **Tambah atribut** untuk memetakan bidang ini.</span><span class="sxs-lookup"><span data-stu-id="0d909-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0d909-139">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="0d909-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="0d909-140">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="0d909-140">Select **Save**.</span></span>

<span data-ttu-id="0d909-141">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="0d909-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0d909-142">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0d909-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0d909-143">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0d909-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0d909-144">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="0d909-144">Data privacy and compliance</span></span>

<span data-ttu-id="0d909-145">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mentransmisikan data ke Sendinblue, Anda mengizinkan transfer data di luar batas kesesuaian untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi.</span><span class="sxs-lookup"><span data-stu-id="0d909-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0d909-146">Microsoft akan mengalihkan data tersebut berdasarkan instruksi Anda, namun Anda bertanggung jawab untuk memastikan bahwa Sendinblue memenuhi privasi atau jaminan keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="0d909-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0d909-147">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0d909-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0d909-148">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="0d909-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
