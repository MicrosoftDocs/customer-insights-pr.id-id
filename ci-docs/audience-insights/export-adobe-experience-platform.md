---
title: Mengekspor data Customer Insights ke Adobe Experience Platform
description: Pelajari bagaimana menggunakan segmen wawasan audiens dalam Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596273"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="177b2-103">Gunakan segmen Customer Insights dalam Adobe Experience Platform (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="177b2-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="177b2-104">Sebagai pengguna wawasan audiens untuk Dynamics 365 Customer Insights, Anda mungkin telah membuat segmen untuk membuat kampanye pemasaran yang lebih efisien dengan menargetkan audiens yang relevan.</span><span class="sxs-lookup"><span data-stu-id="177b2-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="177b2-105">Agar dapat menggunakan segmen audiens wawasan dalam Adobe Experience Platform dan aplikasi seperti Adobe Campaign Standard, Anda harus mengikuti beberapa langkah yang diuraikan dalam artikel ini.</span><span class="sxs-lookup"><span data-stu-id="177b2-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram proses dari langkah-langkah yang diuraikan dalam artikel ini.":::

## <a name="prerequisites"></a><span data-ttu-id="177b2-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="177b2-107">Prerequisites</span></span>

-   <span data-ttu-id="177b2-108">Lisensi Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="177b2-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="177b2-109">Lisensi Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="177b2-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="177b2-110">Lisensi Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="177b2-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="177b2-111">Akun Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="177b2-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="177b2-112">Ikhtisar Kampanye</span><span class="sxs-lookup"><span data-stu-id="177b2-112">Campaign Overview</span></span>

<span data-ttu-id="177b2-113">Untuk lebih memahami bagaimana Anda dapat menggunakan segmen wawasan audiens dalam Adobe Experience Platform, lihat kampanye sampel fiktif.</span><span class="sxs-lookup"><span data-stu-id="177b2-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="177b2-114">Misalnya, perusahaan Anda menawarkan layanan berbasis langganan bulanan kepada pelanggan Anda di Amerika Serikat.</span><span class="sxs-lookup"><span data-stu-id="177b2-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="177b2-115">Anda ingin mengidentifikasi pelanggan yang langganannya harus diperpanjang dalam delapan hari berikutnya tetapi belum memperbarui langganan mereka.</span><span class="sxs-lookup"><span data-stu-id="177b2-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="177b2-116">Untuk menjaga pelanggan ini, Anda perlu mengirimkan penawaran promosi melalui email, menggunakan Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="177b2-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="177b2-117">Di contoh ini, kita ingin menjalankan kampanye email promosi sekali.</span><span class="sxs-lookup"><span data-stu-id="177b2-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="177b2-118">Artikel ini tidak mencakup kasus penggunaan dalam menjalankan kampanye lebih dari satu kali.</span><span class="sxs-lookup"><span data-stu-id="177b2-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="177b2-119">Identifikasikan target audiens</span><span class="sxs-lookup"><span data-stu-id="177b2-119">Identify your target audience</span></span>

<span data-ttu-id="177b2-120">Dalam skenario kami, kami mengasumsikan bahwa alamat email pelanggan tersedia di wawasan audiens dan preferensi promosi mereka dianalisis untuk mengidentifikasi anggota segmen.</span><span class="sxs-lookup"><span data-stu-id="177b2-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="177b2-121">[Segmen yang Anda tentukan dalam wawasan audiens](segments.md) disebut **ChurnProneCustomers** dan Anda berencana mengirimkan promosi email kepada pelanggan ini.</span><span class="sxs-lookup"><span data-stu-id="177b2-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Tangkapan layar halaman segmen dengan segmen ChurnProneCustomers dibuat.":::

<span data-ttu-id="177b2-123">Email penawaran yang ingin Anda kirim akan berisi nama depan, nama belakang, dan tanggal berakhir langganan pelanggan.</span><span class="sxs-lookup"><span data-stu-id="177b2-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="177b2-124">Ini akan menginformasikan kepada pelanggan tentang diskon yang akan mereka dapatkan jika mereka memperpanjang langganan sebelum berakhir.</span><span class="sxs-lookup"><span data-stu-id="177b2-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="177b2-125">Ekspor target audiens</span><span class="sxs-lookup"><span data-stu-id="177b2-125">Export your target audience</span></span>

<span data-ttu-id="177b2-126">Dengan target audiens, kita dapat mengkonfigurasi ekspor dari wawasan audiens ke akun Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="177b2-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="177b2-127">Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="177b2-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="177b2-128">Pada petak **Azure Blob Storage**, pilih **Atur**.</span><span class="sxs-lookup"><span data-stu-id="177b2-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="petak konfigurasi untuk Azure Blob Storage.":::

1. <span data-ttu-id="177b2-130">Berikan **nama tampilan** untuk tujuan ekspor baru ini, lalu masukkan **nama Akun**, **Kunci akun**, dan **Wadah** akun Azure Blob Storage untuk tempat mengekspor segmen.</span><span class="sxs-lookup"><span data-stu-id="177b2-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurasi akun penyimpanan. "::: 

   - <span data-ttu-id="177b2-132">Untuk mempelajari lebih lanjut tentang cara menemukan kunci akun dan nama akun penyimpanan Azure Blob, lihat [mengelola pengaturan akun penyimpanan di portal Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="177b2-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="177b2-133">Untuk mempelajari cara membuat penampung, lihat [membuat penampung](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="177b2-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="177b2-134">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="177b2-134">Select **Next**.</span></span>

1. <span data-ttu-id="177b2-135">Pilih segmen yang ingin Anda ekspor.</span><span class="sxs-lookup"><span data-stu-id="177b2-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="177b2-136">Di contoh ini, itu adalah **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="177b2-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Tangkapan layar dari antarmuka pengguna pilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. <span data-ttu-id="177b2-138">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="177b2-138">Select **Save**.</span></span>

<span data-ttu-id="177b2-139">Setelah menyimpan tujuan ekspor, Anda dapat menemukannya di **Admin** > **Ekspor** > **Tujuan ekspor Saya**.</span><span class="sxs-lookup"><span data-stu-id="177b2-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Tangkapan layar dengan daftar ekspor dan segmen sampel disorot.":::

<span data-ttu-id="177b2-141">Anda sekarang dapat [mengekspor segmen sesuai permintaan](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="177b2-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="177b2-142">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md).</span><span class="sxs-lookup"><span data-stu-id="177b2-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="177b2-143">Pastikan jumlah rekaman dalam segmen yang diekspor berada dalam batas yang diizinkan untuk lisensi Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="177b2-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="177b2-144">Data yang diekspor disimpan dalam wadah Azure Blob storage yang dikonfigurasi di atas.</span><span class="sxs-lookup"><span data-stu-id="177b2-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="177b2-145">Jalur folder berikut dibuat secara otomatis dalam wadah Anda:</span><span class="sxs-lookup"><span data-stu-id="177b2-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="177b2-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="177b2-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="177b2-147">Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="177b2-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="177b2-148">*Model.json* untuk entitas yang diekspor berada di tingkat *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="177b2-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="177b2-149">Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="177b2-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="177b2-150">Mendefinisikan Model Data Pengalaman (XDM) di Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="177b2-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="177b2-151">Sebelum data yang diekspor dari wawasan audiens dapat digunakan dalam Adobe Experience Platform, kita harus mendefinisikan skema Model Data Pengalaman dan [mengkonfigurasikan data untuk Profil Pelanggan Real-time](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="177b2-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="177b2-152">Ketahui [apa itu XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) dan pahami [dasar-dasar susunan skema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="177b2-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="177b2-153">Mengimpor data ke Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="177b2-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="177b2-154">Setelah semuanya tersedia, kita harus mengimpor data audiens yang disiapkan dari wawasan audiens ke Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="177b2-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="177b2-155">Pertama, [buat sambungan sumber Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="177b2-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="177b2-156">Setelah menentukan sambungan sumber, [konfigurasikan aliran data](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) untuk sambungan kumpulan penyimpanan cloud agar dapat mengimpor output segmen dari wawasan audiens ke Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="177b2-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="177b2-157">Buat audiens di Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="177b2-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="177b2-158">Untuk mengirim email tentang kampanye ini, kami akan menggunakan Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="177b2-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="177b2-159">Setelah mengimpor data ke Adobe Experience Platform, kita harus [membuat audiens](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) di Adobe Campaign Standard menggunakan data di Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="177b2-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="177b2-160">Pelajari cara [menggunakan pembuat segmen](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) di Adobe Campaign Standard untuk menentukan audiens berdasarkan data dalam Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="177b2-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="177b2-161">Membuat dan mengirim email menggunakan Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="177b2-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="177b2-162">Buat konten email, lalu [uji dan kirim](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email Anda.</span><span class="sxs-lookup"><span data-stu-id="177b2-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Contoh email dengan penawaran perpanjangan dari Adobe Campaign Standard.":::