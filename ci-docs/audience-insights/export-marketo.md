---
title: Ekspor data Customer Insights ke Marketo
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759825"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="e28c3-103">Mengekspor segmen ke Marketo (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="e28c3-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="e28c3-104">Ekspor segmen profil pelanggan terpadu untuk membuat kampanye, menyediakan pemasaran melalui email, dan gunakan grup pelanggan tertentu dengan Marketo.</span><span class="sxs-lookup"><span data-stu-id="e28c3-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e28c3-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="e28c3-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="e28c3-106">Anda memiliki [akun Marketo](https://login.marketo.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="e28c3-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e28c3-107">Daftar sudah ada di Marketo dan id yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="e28c3-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="e28c3-108">Untuk informasi lebih lanjut, lihat [daftar Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="e28c3-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="e28c3-109">Anda telah [mengonfigurasi segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e28c3-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="e28c3-110">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="e28c3-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e28c3-111">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="e28c3-111">Known limitations</span></span>

- <span data-ttu-id="e28c3-112">Hingga 1 juta profil per ekspor ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="e28c3-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="e28c3-113">Mengekspor ke Marketo terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="e28c3-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="e28c3-114">Mengekspor segmen dengan total 1 juta profil dapat memakan waktu hingga 3 jam.</span><span class="sxs-lookup"><span data-stu-id="e28c3-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="e28c3-115">Jumlah profil yang dapat Anda ekspor ke Marketo tergantung dan terbatas pada kontrak Anda dengan Marketo.</span><span class="sxs-lookup"><span data-stu-id="e28c3-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="e28c3-116">Konfigurasikan koneksi ke Marketo</span><span class="sxs-lookup"><span data-stu-id="e28c3-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="e28c3-117">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="e28c3-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e28c3-118">Pilih **Tambahkan koneksi** dan pilih **Marketo** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="e28c3-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="e28c3-119">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="e28c3-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e28c3-120">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="e28c3-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e28c3-121">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="e28c3-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e28c3-122">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="e28c3-122">Choose who can use this connection.</span></span> <span data-ttu-id="e28c3-123">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="e28c3-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e28c3-124">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e28c3-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e28c3-125">Masukkan **[ID klien marketo anda, rahasia klien dan Hostname titik akhir REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="e28c3-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="e28c3-126">Pilih **saya setuju** untuk mengkonfirmasi **privasi data dan kepatuhan** dan pilih **Sambungkan** untuk menginisialisasi sambungan ke marketo.</span><span class="sxs-lookup"><span data-stu-id="e28c3-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="e28c3-127">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="e28c3-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e28c3-128">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="e28c3-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e28c3-129">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="e28c3-129">Configure an export</span></span>

<span data-ttu-id="e28c3-130">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="e28c3-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e28c3-131">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e28c3-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e28c3-132">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="e28c3-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e28c3-133">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="e28c3-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e28c3-134">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Marketo.</span><span class="sxs-lookup"><span data-stu-id="e28c3-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="e28c3-135">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="e28c3-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e28c3-136">Masukkan **[id daftar marketo Anda](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="e28c3-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="e28c3-137">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="e28c3-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e28c3-138">Secara opsional, Anda dapat mengekspor **nama depan**, **nama belakang**, **Kota**, dan **Negara Bagian**, dan **Negara/Kawasan**  untuk membuat email yang lebih dipersonalisasi.</span><span class="sxs-lookup"><span data-stu-id="e28c3-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="e28c3-139">Pilih **Tambah atribut** untuk memetakan bidang ini.</span><span class="sxs-lookup"><span data-stu-id="e28c3-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e28c3-140">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="e28c3-140">Select the segments you want to export.</span></span> <span data-ttu-id="e28c3-141">Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="e28c3-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="e28c3-142">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="e28c3-142">Select **Save**.</span></span>

<span data-ttu-id="e28c3-143">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="e28c3-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e28c3-144">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e28c3-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e28c3-145">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e28c3-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="e28c3-146">Di Marketo, Anda sekarang dapat menemukan segmen Anda dalam [daftar Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="e28c3-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e28c3-147">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="e28c3-147">Data privacy and compliance</span></span>

<span data-ttu-id="e28c3-148">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Marketo, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="e28c3-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e28c3-149">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Marketo memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="e28c3-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e28c3-150">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e28c3-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e28c3-151">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="e28c3-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]