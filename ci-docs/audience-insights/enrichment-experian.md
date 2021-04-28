---
title: Pengayaan dengan Experian pengayaan pihak ketiga
description: Informasi umum tentang pengayaan pihak ketiga Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896377"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="a8082-103">Memperkaya profil pelanggan dengan demografi dari Experian (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="a8082-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="a8082-104">Experian adalah pemimpin global dalam pelaporan kredit konsumen dan bisnis serta layanan pemasaran.</span><span class="sxs-lookup"><span data-stu-id="a8082-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="a8082-105">Dengan layanan pengayaan data Experian, Anda dapat membangun pemahaman yang lebih mendalam tentang pelanggan Anda dengan memperkaya profil pelanggan Anda dengan data demografis seperti ukuran rumah tangga, pendapatan, dan lainnya.</span><span class="sxs-lookup"><span data-stu-id="a8082-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a8082-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="a8082-106">Prerequisites</span></span>

<span data-ttu-id="a8082-107">Untuk mengonfigurasikan Experian, prasyarat berikut harus dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="a8082-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a8082-108">Anda memiliki langganan Experian aktif.</span><span class="sxs-lookup"><span data-stu-id="a8082-108">You have an active Experian subscription.</span></span> <span data-ttu-id="a8082-109">Untuk mendapatkan langganan, [Hubungi Experian](https://www.experian.com/marketing-services/contact) secara langsung.</span><span class="sxs-lookup"><span data-stu-id="a8082-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="a8082-110">[Pelajari selengkapnya tentang pengayaan data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="a8082-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="a8082-111">Koneksi Experian telah dikonfigurasi oleh administrator *atau* Anda memiliki izin [administrator](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="a8082-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="a8082-112">Anda juga memerlukan ID Pengguna, ID Pesta, dan Nomor Model untuk akun Secure Transport (ST) berkemampuan SSH yang dibuat Experian untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="a8082-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="a8082-113">Konfigurasi pengayaan</span><span class="sxs-lookup"><span data-stu-id="a8082-113">Configure the enrichment</span></span>

1. <span data-ttu-id="a8082-114">Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.</span><span class="sxs-lookup"><span data-stu-id="a8082-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="a8082-115">Pilih **Perkaya data saya** di petak Experian.</span><span class="sxs-lookup"><span data-stu-id="a8082-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a8082-116">![petak Experian](media/experian-tile.png "petak Experian")</span><span class="sxs-lookup"><span data-stu-id="a8082-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="a8082-117">Pilih [koneksi](connections.md) dari menu tarik-turun.</span><span class="sxs-lookup"><span data-stu-id="a8082-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="a8082-118">Hubungi administrator jika tidak ada koneksi yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="a8082-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="a8082-119">Jika Anda adalah administrator, Anda bisa membuat koneksi dengan memilih **Tambahkan koneksi** dan memilih Experian dari menu tarik-turun.</span><span class="sxs-lookup"><span data-stu-id="a8082-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="a8082-120">Pilih **Sambungkan ke Experian** untuk mengonfirmasi pilihan koneksi.</span><span class="sxs-lookup"><span data-stu-id="a8082-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="a8082-121">Pilih **Berikutnya** dan pilih **himpunan data Pelanggan** yang ingin Anda perkaya dengan data demografis dari Experian.</span><span class="sxs-lookup"><span data-stu-id="a8082-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="a8082-122">Anda dapat memilih entitas **Pelanggan** untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="a8082-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Tangkapan layar saat memilih himpunan data pelanggan.":::

1. <span data-ttu-id="a8082-124">Pilih **Berikutnya** dan tentukan tipe bidang mana dari profil terpadu Anda yang harus digunakan untuk mencari data demografis yang cocok dari Experian.</span><span class="sxs-lookup"><span data-stu-id="a8082-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="a8082-125">Setidaknya salah satu bidang **Nama dan alamat**, **Telepon**, atau **Email** diperlukan.</span><span class="sxs-lookup"><span data-stu-id="a8082-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="a8082-126">Untuk akurasi pencocokan yang lebih tinggi, hingga dua bidang lain dapat ditambahkan.</span><span class="sxs-lookup"><span data-stu-id="a8082-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="a8082-127">Pilihan ini akan memengaruhi bidang pemetaan yang dapat Anda akses di langkah berikutnya.</span><span class="sxs-lookup"><span data-stu-id="a8082-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="a8082-128">Atribut pengidentifikasi kunci lainnya yang dikirim ke Experian kemungkinan menghasilkan tingkat kecocokan yang lebih tinggi.</span><span class="sxs-lookup"><span data-stu-id="a8082-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="a8082-129">Untuk memulai pemetaan bidang, pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="a8082-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="a8082-130">Tentukan bidang mana dari profil terpadu Anda yang harus digunakan untuk mencari data demografis yang cocok dari Experian.</span><span class="sxs-lookup"><span data-stu-id="a8082-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="a8082-131">Bidang yang diperlukan ditandai.</span><span class="sxs-lookup"><span data-stu-id="a8082-131">Required fields are marked.</span></span>

1. <span data-ttu-id="a8082-132">Berikan nama untuk pengayaan dan nama untuk entitas output.</span><span class="sxs-lookup"><span data-stu-id="a8082-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="a8082-133">Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.</span><span class="sxs-lookup"><span data-stu-id="a8082-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="a8082-134">Mengonfigurasi koneksi untuk Experian</span><span class="sxs-lookup"><span data-stu-id="a8082-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="a8082-135">Anda perlu menjadi administrator untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="a8082-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="a8082-136">Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan *atau* masuk ke **Admin** > **Koneksi** dan pilih **Konfigurasi** pada petak Experian.</span><span class="sxs-lookup"><span data-stu-id="a8082-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="a8082-137">Pilih **Mulai**.</span><span class="sxs-lookup"><span data-stu-id="a8082-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="a8082-138">Masukkan nama untuk koneksi dalam kotak **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="a8082-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="a8082-139">Masukkan ID pengguna, ID pesta, dan Nomor Model yang valid untuk akun Secure Transport Experian Anda.</span><span class="sxs-lookup"><span data-stu-id="a8082-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="a8082-140">Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**</span><span class="sxs-lookup"><span data-stu-id="a8082-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="a8082-141">Pilih **Verifikasi** untuk memvalidasi konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="a8082-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="a8082-142">Setelah menyelesaikan verifikasi, pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="a8082-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Panel konfigurasi koneksi Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="a8082-144">Hasil pengayaan</span><span class="sxs-lookup"><span data-stu-id="a8082-144">Enrichment results</span></span>

<span data-ttu-id="a8082-145">Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="a8082-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a8082-146">Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a8082-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a8082-147">Waktu pemrosesan akan tergantung pada ukuran data pelanggan Anda dan proses pengayaan diatur untuk akun Anda oleh Experian.</span><span class="sxs-lookup"><span data-stu-id="a8082-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="a8082-148">Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan baru yang diperkaya di dalam **pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="a8082-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="a8082-149">Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="a8082-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a8082-150">Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.</span><span class="sxs-lookup"><span data-stu-id="a8082-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a8082-151">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="a8082-151">Next steps</span></span>

<span data-ttu-id="a8082-152">Bangun di atas data pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="a8082-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a8082-153">Buat [segmen](segments.md), [tindakan](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan bagi pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="a8082-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a8082-154">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="a8082-154">Data privacy and compliance</span></span>

<span data-ttu-id="a8082-155">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Experian, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="a8082-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a8082-156">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Experian memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="a8082-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a8082-157">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a8082-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a8082-158">Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="a8082-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
