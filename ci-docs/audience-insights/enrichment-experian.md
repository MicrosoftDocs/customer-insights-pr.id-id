---
title: Pengayaan dengan pengayaan pihak ketiga Experian
description: Informasi umum tentang pengayaan pihak ketiga Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309824"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="a0c38-103">Perkaya profil pelanggan dengan demografi dari Experian (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="a0c38-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="a0c38-104">Experian adalah pemimpin global dalam pelaporan kredit konsumen dan bisnis serta layanan pemasaran.</span><span class="sxs-lookup"><span data-stu-id="a0c38-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="a0c38-105">Dengan layanan pengayaan data Experian, Anda dapat membangun pemahaman yang lebih mendalam tentang pelanggan dengan memperkaya profil pelanggan dengan data demografis seperti ukuran rumah tangga, penghasilan, dan banyak lagi.</span><span class="sxs-lookup"><span data-stu-id="a0c38-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a0c38-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="a0c38-106">Prerequisites</span></span>

<span data-ttu-id="a0c38-107">Untuk mengonfigurasikan Experian, prasyarat berikut harus dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="a0c38-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a0c38-108">Anda memiliki langganan Experian aktif.</span><span class="sxs-lookup"><span data-stu-id="a0c38-108">You have an active Experian subscription.</span></span> <span data-ttu-id="a0c38-109">Untuk mendapatkan langganan, [hubungi Experian](https://www.experian.com/marketing-services/contact) secara langsung.</span><span class="sxs-lookup"><span data-stu-id="a0c38-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="a0c38-110">[Pelajari selengkapnya tentang Pengayaan data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="a0c38-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="a0c38-111">Koneksi Experian telah dikonfigurasi oleh administrator *atau* Anda memiliki izin [administrator](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="a0c38-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="a0c38-112">Anda juga memerlukan ID Pengguna, ID Pihak, dan Nomor Model untuk akun ST (Secure Transport) berkemampuan SSH yang dibuat Experian untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="a0c38-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="a0c38-113">Negara/kawasan yang didukung</span><span class="sxs-lookup"><span data-stu-id="a0c38-113">Supported countries/regions</span></span>

<span data-ttu-id="a0c38-114">Kami saat ini hanya mendukung pengayaan profil pelanggan di Amerika Serikat.</span><span class="sxs-lookup"><span data-stu-id="a0c38-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="a0c38-115">Konfigurasi pengayaan</span><span class="sxs-lookup"><span data-stu-id="a0c38-115">Configure the enrichment</span></span>

1. <span data-ttu-id="a0c38-116">Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.</span><span class="sxs-lookup"><span data-stu-id="a0c38-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="a0c38-117">Pilih **Perkaya data saya** pada petak Experian.</span><span class="sxs-lookup"><span data-stu-id="a0c38-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a0c38-118">![Experian lain](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="a0c38-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="a0c38-119">Pilih [koneksi](connections.md) dari daftar drop-down.</span><span class="sxs-lookup"><span data-stu-id="a0c38-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="a0c38-120">Hubungi administrator jika tidak ada koneksi yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="a0c38-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="a0c38-121">Jika Anda administrator, Anda dapat membuat sambungan dengan memilih **Tambah sambungan** dan memilih Experian dari daftar dropdown.</span><span class="sxs-lookup"><span data-stu-id="a0c38-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="a0c38-122">Pilih **Sambungkan ke Experian** untuk mengkonfirmasi pilihan koneksi.</span><span class="sxs-lookup"><span data-stu-id="a0c38-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="a0c38-123">Pilih **Berikutnya** dan pilih **himpunan data Pelanggan** yang ingin Anda perkaya dengan data demografi dari Experian.</span><span class="sxs-lookup"><span data-stu-id="a0c38-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="a0c38-124">Anda dapat memilih entitas **Pelanggan** untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="a0c38-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Tangkapan layar saat memilih himpunan data pelanggan.":::

1. <span data-ttu-id="a0c38-126">Pilih **Berikutnya** dan tentukan jenis bidang dari profil terpadu yang akan digunakan untuk mencari data historis yang cocok dari Experian.</span><span class="sxs-lookup"><span data-stu-id="a0c38-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="a0c38-127">Setidaknya salah satu bidang **Nama dan alamat**, **Telepon**, atau **Email** diperlukan.</span><span class="sxs-lookup"><span data-stu-id="a0c38-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="a0c38-128">Untuk akurasi pencocokan yang lebih tinggi, hingga dua bidang lain dapat ditambahkan.</span><span class="sxs-lookup"><span data-stu-id="a0c38-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="a0c38-129">Pilihan ini akan memengaruhi bidang pemetaan yang dapat Anda akses di langkah berikutnya.</span><span class="sxs-lookup"><span data-stu-id="a0c38-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="a0c38-130">Atribut pengidentifikasi utama lainnya yang dikirim ke Experian cenderung menghasilkan tingkat kecocokan yang lebih tinggi.</span><span class="sxs-lookup"><span data-stu-id="a0c38-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="a0c38-131">Untuk memulai pemetaan bidang, pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="a0c38-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="a0c38-132">Tentukan bidang dari profil terpadu yang akan digunakan untuk mencari data historis yang cocok dari Experian.</span><span class="sxs-lookup"><span data-stu-id="a0c38-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="a0c38-133">Bidang yang diperlukan ditandai.</span><span class="sxs-lookup"><span data-stu-id="a0c38-133">Required fields are marked.</span></span>

1. <span data-ttu-id="a0c38-134">Berikan nama untuk pengayaan dan nama untuk entitas output.</span><span class="sxs-lookup"><span data-stu-id="a0c38-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="a0c38-135">Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.</span><span class="sxs-lookup"><span data-stu-id="a0c38-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="a0c38-136">Mengonfigurasi koneksi untuk Experian</span><span class="sxs-lookup"><span data-stu-id="a0c38-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="a0c38-137">Anda perlu menjadi administrator untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="a0c38-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="a0c38-138">Pilih **Tambah koneksi** saat mengkonfigurasi pengayaan *atau* buka **Admin** > **Koneksi**, lalu pilih **Atur** pada petak Experian.</span><span class="sxs-lookup"><span data-stu-id="a0c38-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="a0c38-139">Pilih **Mulai**.</span><span class="sxs-lookup"><span data-stu-id="a0c38-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="a0c38-140">Masukkan nama untuk koneksi dalam kotak **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="a0c38-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="a0c38-141">Masukkan ID Pengguna, ID Pihak, dan Nomor Model yang valid untuk akun Secure Transport Experian Anda.</span><span class="sxs-lookup"><span data-stu-id="a0c38-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="a0c38-142">Baca dan berikan persetujuan Anda untuk **privasi dan kesesuaian Data** dengan memilih **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="a0c38-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="a0c38-143">Pilih **Verifikasi** untuk memvalidasi konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="a0c38-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="a0c38-144">Setelah menyelesaikan verifikasi, pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="a0c38-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Panel Konfigurasi koneksi Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="a0c38-146">Hasil pengayaan</span><span class="sxs-lookup"><span data-stu-id="a0c38-146">Enrichment results</span></span>

<span data-ttu-id="a0c38-147">Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="a0c38-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a0c38-148">Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a0c38-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a0c38-149">Waktu pemrosesan akan tergantung pada ukuran data pelanggan dan proses pengayaan yang disiapkan untuk akun Anda oleh Experian.</span><span class="sxs-lookup"><span data-stu-id="a0c38-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="a0c38-150">Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan baru yang diperkaya di dalam **pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="a0c38-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="a0c38-151">Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="a0c38-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a0c38-152">Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.</span><span class="sxs-lookup"><span data-stu-id="a0c38-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a0c38-153">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="a0c38-153">Next steps</span></span>

<span data-ttu-id="a0c38-154">Bangun di atas data pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="a0c38-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a0c38-155">Buat [segmen](segments.md) dan [ukuran](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman pribadi kepada pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="a0c38-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a0c38-156">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="a0c38-156">Data privacy and compliance</span></span>

<span data-ttu-id="a0c38-157">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mentransmisikan data ke Experian, Anda mengizinkan transfer data di luar batas kesesuaian untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi.</span><span class="sxs-lookup"><span data-stu-id="a0c38-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a0c38-158">Microsoft akan mengalihkan data tersebut berdasarkan instruksi Anda, namun Anda bertanggung jawab untuk memastikan bahwa Experian memenuhi privasi atau jaminan keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="a0c38-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a0c38-159">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a0c38-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a0c38-160">Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="a0c38-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
