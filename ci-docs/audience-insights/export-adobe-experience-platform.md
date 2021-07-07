---
title: Mengekspor data Customer Insights ke Adobe Experience Platform
description: Pelajari cara menggunakan audiens wawasan dalam Platform Adobe Experience.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305528"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="f5b87-103">Gunakan segmen Customer Insights dalam Adobe Experience Platform (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="f5b87-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="f5b87-104">Sebagai pengguna wawasan audiens di Dynamics 365 Customer Insights, Anda mungkin telah membuat segmen untuk membuat kampanye pemasaran yang lebih efisien dengan menargetkan audiens yang relevan.</span><span class="sxs-lookup"><span data-stu-id="f5b87-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="f5b87-105">Agar dapat menggunakan segmen audiens wawasan dalam Adobe Experience Platform dan aplikasi seperti Adobe Campaign Standard, Anda harus mengikuti beberapa langkah yang diuraikan dalam artikel ini.</span><span class="sxs-lookup"><span data-stu-id="f5b87-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram proses dari langkah-langkah yang diuraikan dalam artikel ini.":::

## <a name="prerequisites"></a><span data-ttu-id="f5b87-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="f5b87-107">Prerequisites</span></span>

-   <span data-ttu-id="f5b87-108">Lisensi Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f5b87-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="f5b87-109">Lisensi Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="f5b87-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="f5b87-110">Lisensi Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="f5b87-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="f5b87-111">Akun Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="f5b87-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="f5b87-112">Ikhtisar Kampanye</span><span class="sxs-lookup"><span data-stu-id="f5b87-112">Campaign Overview</span></span>

<span data-ttu-id="f5b87-113">Untuk lebih memahami bagaimana Anda dapat menggunakan segmen wawasan audiens dalam Adobe Experience Platform, lihat kampanye sampel fiktif.</span><span class="sxs-lookup"><span data-stu-id="f5b87-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="f5b87-114">Misalnya, perusahaan Anda menawarkan layanan berbasis langganan bulanan kepada pelanggan Anda di Amerika Serikat.</span><span class="sxs-lookup"><span data-stu-id="f5b87-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="f5b87-115">Anda ingin mengidentifikasi pelanggan yang langganannya harus diperpanjang dalam delapan hari berikutnya tetapi belum memperbarui langganan mereka.</span><span class="sxs-lookup"><span data-stu-id="f5b87-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="f5b87-116">Untuk menjaga pelanggan ini, Anda perlu mengirimkan penawaran promosi melalui email, menggunakan Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="f5b87-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="f5b87-117">Di contoh ini, kita ingin menjalankan kampanye email promosi sekali.</span><span class="sxs-lookup"><span data-stu-id="f5b87-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="f5b87-118">Artikel ini tidak mencakup kasus penggunaan dalam menjalankan kampanye lebih dari satu kali.</span><span class="sxs-lookup"><span data-stu-id="f5b87-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="f5b87-119">Identifikasikan target audiens</span><span class="sxs-lookup"><span data-stu-id="f5b87-119">Identify your target audience</span></span>

<span data-ttu-id="f5b87-120">Dalam skenario kami, kami mengasumsikan bahwa alamat email pelanggan tersedia di wawasan audiens dan preferensi promosi mereka dianalisis untuk mengidentifikasi anggota segmen.</span><span class="sxs-lookup"><span data-stu-id="f5b87-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="f5b87-121">[Segmen yang Anda tentukan dalam wawasan audiens](segments.md) disebut **ChurnProneCustomers** dan Anda berencana mengirimkan promosi email kepada pelanggan ini.</span><span class="sxs-lookup"><span data-stu-id="f5b87-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Tangkapan layar halaman segmen dengan segmen ChurnProneCustomers dibuat.":::

<span data-ttu-id="f5b87-123">Email penawaran yang ingin Anda kirim akan berisi nama depan, nama belakang, dan tanggal berakhir langganan pelanggan.</span><span class="sxs-lookup"><span data-stu-id="f5b87-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="f5b87-124">Ini akan menginformasikan kepada pelanggan tentang diskon yang akan mereka dapatkan jika mereka memperpanjang langganan sebelum berakhir.</span><span class="sxs-lookup"><span data-stu-id="f5b87-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="f5b87-125">Ekspor target audiens</span><span class="sxs-lookup"><span data-stu-id="f5b87-125">Export your target audience</span></span>

<span data-ttu-id="f5b87-126">Dengan target audiens, kita dapat mengkonfigurasi ekspor dari wawasan audiens ke akun Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="f5b87-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="f5b87-127">Mengonfigurasi koneksi</span><span class="sxs-lookup"><span data-stu-id="f5b87-127">Configure a connection</span></span>

1. <span data-ttu-id="f5b87-128">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="f5b87-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f5b87-129">Pilih **Tambah koneksi** dan pilih **Penyimpanan Blob Azure** untuk mengkonfigurasi **Konfigurasi** dalam petak **Penyimpanan Blob Adobe** untuk mengonfigurasikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="f5b87-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="petak konfigurasi untuk Azure Blob Storage."::: 

1. <span data-ttu-id="f5b87-131">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="f5b87-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f5b87-132">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="f5b87-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f5b87-133">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="f5b87-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f5b87-134">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="f5b87-134">Choose who can use this connection.</span></span> <span data-ttu-id="f5b87-135">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="f5b87-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f5b87-136">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f5b87-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f5b87-137">Masukkan **nama Akun**, **Kunci akun**, dan **Wadah** untuk akun Penyimpanan Blob Anda yang ingin Anda ekspor segmennya.</span><span class="sxs-lookup"><span data-stu-id="f5b87-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurasi akun penyimpanan. "::: 
   
    - <span data-ttu-id="f5b87-139">Untuk mempelajari selengkapnya tentang cara menemukan nama akun penyimpanan Blob dan kunci akun, lihat [Mengelola pengaturan akun penyimpanan di portal Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="f5b87-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="f5b87-140">Untuk mempelajari cara membuat penampung, lihat [membuat penampung](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="f5b87-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="f5b87-141">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="f5b87-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="f5b87-142">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="f5b87-142">Configure an export</span></span>

<span data-ttu-id="f5b87-143">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="f5b87-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f5b87-144">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f5b87-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f5b87-145">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="f5b87-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f5b87-146">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="f5b87-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="f5b87-147">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Penyimpanan Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="f5b87-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="f5b87-148">Jika Anda tidak melihat nama bagian ini, maka tidak ada sambungan dari jenis ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="f5b87-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="f5b87-149">Pilih segmen yang ingin Anda ekspor.</span><span class="sxs-lookup"><span data-stu-id="f5b87-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="f5b87-150">Di contoh ini, itu adalah **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="f5b87-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Tangkapan layar dari antarmuka pengguna pilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. <span data-ttu-id="f5b87-152">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="f5b87-152">Select **Save**.</span></span>

<span data-ttu-id="f5b87-153">Setelah menyimpan tujuan ekspor, Anda menemukannya di **Ekspor** > **Data**.</span><span class="sxs-lookup"><span data-stu-id="f5b87-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="f5b87-154">Anda sekarang dapat [mengekspor segmen sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f5b87-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="f5b87-155">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md).</span><span class="sxs-lookup"><span data-stu-id="f5b87-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f5b87-156">Pastikan jumlah rekaman dalam segmen yang diekspor berada dalam batas yang diizinkan untuk lisensi Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="f5b87-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="f5b87-157">Data yang diekspor disimpan dalam wadah Azure Blob storage yang dikonfigurasi di atas.</span><span class="sxs-lookup"><span data-stu-id="f5b87-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="f5b87-158">Jalur folder berikut dibuat secara otomatis dalam wadah Anda:</span><span class="sxs-lookup"><span data-stu-id="f5b87-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="f5b87-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="f5b87-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="f5b87-160">Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="f5b87-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="f5b87-161">*Model.json* untuk entitas yang diekspor berada di tingkat *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="f5b87-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="f5b87-162">Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="f5b87-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="f5b87-163">Mendefinisikan Model Data Pengalaman (XDM) di Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="f5b87-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="f5b87-164">Sebelum data yang diekspor dari wawasan audiens dapat digunakan dalam Adobe Experience Platform, kita harus mendefinisikan skema Model Data Pengalaman dan [mengkonfigurasikan data untuk Profil Pelanggan Real-time](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="f5b87-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="f5b87-165">Ketahui [apa itu XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) dan pahami [dasar-dasar susunan skema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="f5b87-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="f5b87-166">Mengimpor data ke Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="f5b87-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="f5b87-167">Setelah semuanya tersedia, kita harus mengimpor data audiens yang disiapkan dari wawasan audiens ke Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="f5b87-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="f5b87-168">Pertama, [buat sambungan sumber Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="f5b87-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="f5b87-169">Setelah menentukan sambungan sumber, [konfigurasikan aliran data](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) untuk sambungan kumpulan penyimpanan cloud agar dapat mengimpor output segmen dari wawasan audiens ke Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="f5b87-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="f5b87-170">Buat audiens di Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="f5b87-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="f5b87-171">Untuk mengirim email tentang kampanye ini, kami akan menggunakan Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="f5b87-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="f5b87-172">Setelah mengimpor data ke Adobe Experience Platform, kita harus [membuat audiens](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) di Adobe Campaign Standard menggunakan data di Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="f5b87-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="f5b87-173">Pelajari cara [menggunakan pembuat segmen](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) di Adobe Campaign Standard untuk menentukan audiens berdasarkan data dalam Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="f5b87-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="f5b87-174">Membuat dan mengirim email menggunakan Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="f5b87-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="f5b87-175">Buat konten email, lalu [uji dan kirim](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email Anda.</span><span class="sxs-lookup"><span data-stu-id="f5b87-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Contoh email dengan penawaran perpanjangan dari Adobe Campaign Standard.":::