---
title: Ekspor data Customer Insights ke Facebook Ads Manager
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976046"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="73fdf-103">Mengekspor daftar segmen ke Facebook Ads Manager (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="73fdf-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="73fdf-104">Ekspor segmen profil pelanggan terpadu ke pengelola iklan Facebook untuk membuat kampanye di Facebook dan Instagram.</span><span class="sxs-lookup"><span data-stu-id="73fdf-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="73fdf-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="73fdf-105">Prerequisites for connection</span></span>

- <span data-ttu-id="73fdf-106">Anda harus memiliki [**Akun Iklan Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) yang mencakup [**Akun Bisnis Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="73fdf-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="73fdf-107">Anda harus menjadi administrator pada akun [**iklan Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="73fdf-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="73fdf-108">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="73fdf-108">Known limitations</span></span>

- <span data-ttu-id="73fdf-109">Hingga 10 juta profil pelanggan per ekspor ke Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="73fdf-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="73fdf-110">Mengekspor ke Facebook Ads Manager terbatas untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="73fdf-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="73fdf-111">Buat atau perbarui audiens kustom dalam Facebook dengan jenis *daftar pelanggan* saja.</span><span class="sxs-lookup"><span data-stu-id="73fdf-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="73fdf-112">Mengekspor segmen dengan total 10 juta profil dapat memakan waktu hingga 90 menit untuk diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="73fdf-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="73fdf-113">Menyiapkan koneksi ke Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="73fdf-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="73fdf-114">Sebelum pengguna dapat membuat ekspor, administrator harus mengonfigurasi koneksi ke layanan dan mengizinkan kontributor untuk menggunakan koneksi.</span><span class="sxs-lookup"><span data-stu-id="73fdf-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="73fdf-115">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="73fdf-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="73fdf-116">Pilih **Tambahkan koneksi** dan pilih **Facebook Ads Manager** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="73fdf-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="73fdf-117">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="73fdf-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="73fdf-118">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="73fdf-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="73fdf-119">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="73fdf-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="73fdf-120">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="73fdf-120">Choose who can use this connection.</span></span> <span data-ttu-id="73fdf-121">Jika Anda tidak mengambil tindakan, defaultnya adalah **Administrator**.</span><span class="sxs-lookup"><span data-stu-id="73fdf-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="73fdf-122">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="73fdf-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="73fdf-123">Autentikasikan dengan Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="73fdf-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="73fdf-124">Pilih **Lanjutkan dengan Facebook** untuk masuk ke akun iklan Facebook Anda.</span><span class="sxs-lookup"><span data-stu-id="73fdf-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="73fdf-125">Izinkan izin **ads_management** setelah mengautentikasi dengan Facebook.</span><span class="sxs-lookup"><span data-stu-id="73fdf-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="73fdf-126">Pilih **Akun Iklan Facebook** yang ingin Anda kerjakan.</span><span class="sxs-lookup"><span data-stu-id="73fdf-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="73fdf-127">Pilih **audiens kustom yang ada** dari daftar drop-down atau buat **audiens kustom baru**.</span><span class="sxs-lookup"><span data-stu-id="73fdf-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="73fdf-128">Untuk informasi lebih lanjut, lihat [**audiens di pengelola iklan Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="73fdf-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="73fdf-129">Anda hanya dapat membuat atau memperbarui audiens kustom di Facebook dengan jenis *daftar pelanggan* dengan ekspor ini.</span><span class="sxs-lookup"><span data-stu-id="73fdf-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="73fdf-130">Dalam beberapa kasus, Anda akan melihat pemirsa kustom dari berbagai tipe di daftar tarik-turun.</span><span class="sxs-lookup"><span data-stu-id="73fdf-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="73fdf-131">Memilih tipe yang berbeda dari *daftar pelanggan* akan mengakibatkan kegagalan ekspor.</span><span class="sxs-lookup"><span data-stu-id="73fdf-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="73fdf-132">Tinjau **privasi dan kepatuhan Data** dan pilih **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="73fdf-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="73fdf-133">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="73fdf-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="73fdf-134">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="73fdf-134">Configure an export</span></span>

<span data-ttu-id="73fdf-135">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="73fdf-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="73fdf-136">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="73fdf-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="73fdf-137">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="73fdf-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="73fdf-138">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="73fdf-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="73fdf-139">Pada **Koneksi untuk ekspor**, pilih koneksi dari bagian **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="73fdf-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="73fdf-140">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="73fdf-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="73fdf-141">Di bidang **Pilih pengidentifikasi utama Anda**, pilih **email**, **nama dan alamat**, atau **telepon** untuk dikirim ke pengelola iklan Facebook.</span><span class="sxs-lookup"><span data-stu-id="73fdf-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="73fdf-142">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="73fdf-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="73fdf-143">Petakan atribut yang terkait dari entitas pelanggan terpadu Anda untuk pengidentifikasi kunci yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="73fdf-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="73fdf-144">[KIAT] Peluang terbaik untuk kecocokan terjadi jika Anda memilih **email** sebagai pengidentifikasi utama.</span><span class="sxs-lookup"><span data-stu-id="73fdf-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="73fdf-145">Menambahkan pengidentifikasi tambahan dapat meningkatkan pencocokan.</span><span class="sxs-lookup"><span data-stu-id="73fdf-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="73fdf-146">Pilih **Tambahkan atribut** untuk memetakan lebih banyak atribut untuk dikirim ke Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="73fdf-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="73fdf-147">Atribut dari manajer iklan Facebook melakukan pemetaan ke nama rumah pengguna berikut: **FN** = **Nama Depan**, **LN** = **Nama Belakang**, **FI** = **Inisial Depan**, **TELEPON** = **Telepon**, **GEN** = **Gender**, **DOB** = **Tanggal Lahir**, **ST** = **Negara Bagian**, **CT** = **Kota**, **ZIP** = **Kode pos/Zip**, **NEGARA** = **Negara/Wilayah**</span><span class="sxs-lookup"><span data-stu-id="73fdf-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="73fdf-148">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="73fdf-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="73fdf-149">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="73fdf-149">Select **Save**.</span></span>

<span data-ttu-id="73fdf-150">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="73fdf-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="73fdf-151">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="73fdf-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="73fdf-152">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="73fdf-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="73fdf-153">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="73fdf-153">Data privacy and compliance</span></span>

<span data-ttu-id="73fdf-154">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Facebook Ads Manager, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="73fdf-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="73fdf-155">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Facebook Ads memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="73fdf-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="73fdf-156">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="73fdf-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="73fdf-157">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="73fdf-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
