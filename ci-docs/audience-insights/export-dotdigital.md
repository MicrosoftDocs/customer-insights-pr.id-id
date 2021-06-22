---
title: Ekspor data Customer Insights ke DotDigital
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124415"
---
# <a name="export-segments-to-dotdigital-preview"></a><span data-ttu-id="961af-103">Mengekspor segmen ke DotDigital (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="961af-103">Export segments to DotDigital (preview)</span></span>

<span data-ttu-id="961af-104">Ekspor segmen profil pelanggan terpadu ke buku alamat DotDigital dan gunakan untuk kampanye, pemasaran email, dan untuk membangun segmen pelanggan dengan DotDigital.</span><span class="sxs-lookup"><span data-stu-id="961af-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="961af-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="961af-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="961af-106">Anda memiliki [akun dotdigital](https://dotdigital.com/) dan kredensial administrator yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="961af-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="961af-107">Buku alamat sudah ada di DotDigital dan id yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="961af-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="961af-108">ID dapat ditemukan di URL saat Anda memilih dan membuka buku alamat.</span><span class="sxs-lookup"><span data-stu-id="961af-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="961af-109">Untuk informasi lebih lanjut, lihat [buku alamat dotdigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="961af-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="961af-110">Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="961af-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="961af-111">Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email.</span><span class="sxs-lookup"><span data-stu-id="961af-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="961af-112">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="961af-112">Known limitations</span></span>

- <span data-ttu-id="961af-113">Hingga 1 juta profil per ekspor ke DotDigital.</span><span class="sxs-lookup"><span data-stu-id="961af-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="961af-114">Mengekspor ke DotDigital terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="961af-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="961af-115">Mengekspor segmen dengan total 1 juta profil dapat memakan waktu hingga 3 jam karena keterbatasan pada sisi Provider.</span><span class="sxs-lookup"><span data-stu-id="961af-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="961af-116">Jumlah profil yang dapat Anda ekspor ke DotDigital tergantung dan terbatas pada kontrak Anda dengan DotDigital.</span><span class="sxs-lookup"><span data-stu-id="961af-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="961af-117">Konfigurasikan koneksi ke DotDigital</span><span class="sxs-lookup"><span data-stu-id="961af-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="961af-118">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="961af-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="961af-119">Pilih **Tambahkan koneksi** dan pilih **DotDigital** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="961af-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="961af-120">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="961af-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="961af-121">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="961af-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="961af-122">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="961af-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="961af-123">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="961af-123">Choose who can use this connection.</span></span> <span data-ttu-id="961af-124">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="961af-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="961af-125">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="961af-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="961af-126">Masukkan **nama pengguna dan sandi DotDigital** Anda.</span><span class="sxs-lookup"><span data-stu-id="961af-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="961af-127">Masukkan **[id buku alamat dotdigital Anda](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="961af-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="961af-128">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="961af-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="961af-129">Pilih **Sambungkan** untuk menginisialisasi sambungan ke dotdigital.</span><span class="sxs-lookup"><span data-stu-id="961af-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="961af-130">Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="961af-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="961af-131">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="961af-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="961af-132">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="961af-132">Configure an export</span></span>

<span data-ttu-id="961af-133">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="961af-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="961af-134">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="961af-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="961af-135">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="961af-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="961af-136">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="961af-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="961af-137">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian DotDigital.</span><span class="sxs-lookup"><span data-stu-id="961af-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="961af-138">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="961af-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="961af-139">Di Bagian **pencocokan data**, di bidang **email**, pilih bidang di profil pelanggan terpadu Anda yang menunjukkan alamat email pelanggan.</span><span class="sxs-lookup"><span data-stu-id="961af-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="961af-140">Ulangi langkah yang sama untuk bidang opsional lainnya seperti **nama depan**, **nama belakang**, **nama lengkap**, **jenis kelamin**, dan **kode posting**.</span><span class="sxs-lookup"><span data-stu-id="961af-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="961af-141">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="961af-141">Select the segments you want to export.</span></span> <span data-ttu-id="961af-142">Anda dapat mengekspor hingga 1 juta profil pelanggan secara total ke DotDigital.</span><span class="sxs-lookup"><span data-stu-id="961af-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="961af-143">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="961af-143">Select **Save**.</span></span>

<span data-ttu-id="961af-144">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="961af-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="961af-145">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="961af-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="961af-146">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="961af-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="961af-147">Di DotDigital, Anda sekarang dapat menemukan segmen dalam [buku alamat dotdigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="961af-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="961af-148">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="961af-148">Data privacy and compliance</span></span>

<span data-ttu-id="961af-149">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke DotDigital, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="961af-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="961af-150">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa DotDigital memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="961af-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="961af-151">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="961af-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="961af-152">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="961af-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
