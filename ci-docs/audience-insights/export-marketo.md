---
title: Ekspor data Customer Insights ke Marketo
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059320"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="13a12-103">Mengekspor segmen ke Marketo (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="13a12-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="13a12-104">Ekspor segmen profil pelanggan terpadu untuk membuat kampanye, menyediakan pemasaran melalui email, dan gunakan grup pelanggan tertentu dengan Marketo.</span><span class="sxs-lookup"><span data-stu-id="13a12-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="13a12-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="13a12-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="13a12-106">Anda memiliki [akun Marketo](https://login.marketo.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="13a12-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="13a12-107">Daftar sudah ada di Marketo dan id yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="13a12-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="13a12-108">Untuk informasi lebih lanjut, lihat [daftar Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="13a12-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="13a12-109">Anda telah [mengonfigurasi segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="13a12-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="13a12-110">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="13a12-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="13a12-111">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="13a12-111">Known limitations</span></span>

- <span data-ttu-id="13a12-112">Hingga 1 juta profil per ekspor ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="13a12-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="13a12-113">Mengekspor ke Marketo terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="13a12-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="13a12-114">Mengekspor segmen dengan total 1 juta profil dapat memakan waktu hingga 3 jam.</span><span class="sxs-lookup"><span data-stu-id="13a12-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="13a12-115">Jumlah profil yang dapat Anda ekspor ke Marketo tergantung dan terbatas pada kontrak Anda dengan Marketo.</span><span class="sxs-lookup"><span data-stu-id="13a12-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="13a12-116">Konfigurasikan koneksi ke Marketo</span><span class="sxs-lookup"><span data-stu-id="13a12-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="13a12-117">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="13a12-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="13a12-118">Pilih **Tambahkan koneksi** dan pilih **Marketo** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="13a12-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="13a12-119">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="13a12-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="13a12-120">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="13a12-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="13a12-121">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="13a12-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="13a12-122">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="13a12-122">Choose who can use this connection.</span></span> <span data-ttu-id="13a12-123">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="13a12-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="13a12-124">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="13a12-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="13a12-125">Masukkan **[ID klien marketo anda, rahasia klien dan Hostname titik akhir REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="13a12-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="13a12-126">Hostname titik akhir REST adalah hanya hostname, tanpa `https://`.</span><span class="sxs-lookup"><span data-stu-id="13a12-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="13a12-127">Contoh:`xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="13a12-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="13a12-128">Pilih **saya setuju** untuk mengkonfirmasi **privasi data dan kepatuhan** dan pilih **Sambungkan** untuk menginisialisasi sambungan ke marketo.</span><span class="sxs-lookup"><span data-stu-id="13a12-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="13a12-129">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="13a12-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="13a12-130">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="13a12-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="13a12-131">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="13a12-131">Configure an export</span></span>

<span data-ttu-id="13a12-132">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="13a12-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="13a12-133">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="13a12-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="13a12-134">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="13a12-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="13a12-135">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="13a12-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="13a12-136">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Marketo.</span><span class="sxs-lookup"><span data-stu-id="13a12-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="13a12-137">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="13a12-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="13a12-138">Masukkan **[id daftar marketo Anda](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="13a12-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="13a12-139">ID daftar adalah nilai yang semata-mata numerik.</span><span class="sxs-lookup"><span data-stu-id="13a12-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="13a12-140">Contohnya, jika ID daftar Marketo Anda adalah ST12345A7, hilangkan karakter sebelum dan setelah angka dan masukkan `12345`.</span><span class="sxs-lookup"><span data-stu-id="13a12-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="13a12-141">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="13a12-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="13a12-142">Secara opsional, Anda dapat mengekspor **nama depan**, **nama belakang**, **Kota**, dan **Negara Bagian**, dan **Negara/Kawasan**  untuk membuat email yang lebih dipersonalisasi.</span><span class="sxs-lookup"><span data-stu-id="13a12-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="13a12-143">Pilih **Tambah atribut** untuk memetakan bidang ini.</span><span class="sxs-lookup"><span data-stu-id="13a12-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="13a12-144">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="13a12-144">Select the segments you want to export.</span></span> <span data-ttu-id="13a12-145">Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke Marketo.</span><span class="sxs-lookup"><span data-stu-id="13a12-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="13a12-146">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="13a12-146">Select **Save**.</span></span>

<span data-ttu-id="13a12-147">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="13a12-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="13a12-148">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="13a12-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="13a12-149">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="13a12-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="13a12-150">Di Marketo, Anda sekarang dapat menemukan segmen Anda dalam [daftar Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="13a12-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="13a12-151">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="13a12-151">Data privacy and compliance</span></span>

<span data-ttu-id="13a12-152">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Marketo, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="13a12-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="13a12-153">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Marketo memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="13a12-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="13a12-154">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="13a12-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="13a12-155">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="13a12-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
