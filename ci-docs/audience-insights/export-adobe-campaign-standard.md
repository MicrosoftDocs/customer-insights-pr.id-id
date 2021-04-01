---
title: Mengekspor data Customer Insights ke Adobe Campaign Standard
description: Pelajari bagaimana menggunakan segmen wawasan audiens dalam Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596319"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="46633-103">Gunakan segmen Customer Insights dalam Adobe Campaign Standard (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="46633-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="46633-104">Sebagai pengguna wawasan audiens untuk Dynamics 365 Customer Insights, Anda mungkin telah membuat segmen untuk membuat kampanye pemasaran yang lebih efisien dengan menargetkan audiens yang relevan.</span><span class="sxs-lookup"><span data-stu-id="46633-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="46633-105">Agar dapat menggunakan segmen audiens wawasan dalam Adobe Experience Platform dan aplikasi seperti Adobe Campaign Standard, Anda harus mengikuti beberapa langkah yang diuraikan dalam artikel ini.</span><span class="sxs-lookup"><span data-stu-id="46633-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram proses dari langkah-langkah yang diuraikan dalam artikel ini.":::

## <a name="prerequisites"></a><span data-ttu-id="46633-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="46633-107">Prerequisites</span></span>

-   <span data-ttu-id="46633-108">Lisensi Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="46633-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="46633-109">Lisensi Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="46633-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="46633-110">Akun Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="46633-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="46633-111">Ikhtisar Kampanye</span><span class="sxs-lookup"><span data-stu-id="46633-111">Campaign Overview</span></span>

<span data-ttu-id="46633-112">Untuk lebih memahami bagaimana Anda dapat menggunakan segmen wawasan audiens dalam Adobe Experience Platform, lihat kampanye sampel fiktif.</span><span class="sxs-lookup"><span data-stu-id="46633-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="46633-113">Misalnya, perusahaan Anda menawarkan layanan berbasis langganan bulanan kepada pelanggan Anda di Amerika Serikat.</span><span class="sxs-lookup"><span data-stu-id="46633-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="46633-114">Anda ingin mengidentifikasi pelanggan yang langganannya harus diperpanjang dalam delapan hari berikutnya tetapi belum memperbarui langganan mereka.</span><span class="sxs-lookup"><span data-stu-id="46633-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="46633-115">Untuk menjaga pelanggan ini, Anda perlu mengirimkan penawaran promosi melalui email, menggunakan Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="46633-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="46633-116">Di contoh ini, kita ingin menjalankan kampanye email promosi sekali.</span><span class="sxs-lookup"><span data-stu-id="46633-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="46633-117">Artikel ini tidak mencakup kasus penggunaan dalam menjalankan kampanye lebih dari satu kali.</span><span class="sxs-lookup"><span data-stu-id="46633-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="46633-118">Namun, audiens dan Adobe Campaign Standard juga dapat dikonfigurasi untuk mengerjakan skenario kampanye berulang.</span><span class="sxs-lookup"><span data-stu-id="46633-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="46633-119">Identifikasikan target audiens</span><span class="sxs-lookup"><span data-stu-id="46633-119">Identify your target audience</span></span>

<span data-ttu-id="46633-120">Dalam skenario kami, kami mengasumsikan bahwa alamat email pelanggan tersedia di wawasan audiens dan preferensi promosi mereka dianalisis untuk mengidentifikasi anggota segmen.</span><span class="sxs-lookup"><span data-stu-id="46633-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="46633-121">[Segmen yang Anda tentukan dalam wawasan audiens](segments.md) disebut **ChurnProneCustomers** dan Anda berencana mengirimkan promosi email kepada pelanggan ini.</span><span class="sxs-lookup"><span data-stu-id="46633-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Tangkapan layar halaman segmen dengan segmen ChurnProneCustomers dibuat.":::

<span data-ttu-id="46633-123">Email penawaran yang ingin Anda kirim akan berisi nama depan, nama belakang, dan tanggal berakhir langganan pelanggan.</span><span class="sxs-lookup"><span data-stu-id="46633-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="46633-124">Ini akan menginformasikan kepada pelanggan tentang diskon yang akan mereka dapatkan jika mereka memperpanjang langganan sebelum berakhir.</span><span class="sxs-lookup"><span data-stu-id="46633-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="46633-125">Ekspor target audiens</span><span class="sxs-lookup"><span data-stu-id="46633-125">Export your target audience</span></span>

<span data-ttu-id="46633-126">Dengan target audiens, kita dapat mengkonfigurasi ekspor dari wawasan audiens ke akun Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="46633-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="46633-127">Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="46633-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="46633-128">Di petak **Adobe Campaign** pilih **Konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="46633-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Petak konfigurasi untuk Adobe Campaign Standard.":::

1. <span data-ttu-id="46633-130">Berikan **nama tampilan** untuk tujuan ekspor baru ini, lalu masukkan **nama Akun**, **Kunci akun**, dan **Wadah** akun Azure Blob Storage untuk tempat mengekspor segmen.</span><span class="sxs-lookup"><span data-stu-id="46633-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurasi akun penyimpanan. "::: 

   - <span data-ttu-id="46633-132">Untuk mempelajari lebih lanjut tentang cara menemukan kunci akun dan nama akun penyimpanan Azure Blob, lihat [mengelola pengaturan akun penyimpanan di portal Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="46633-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="46633-133">Untuk mempelajari cara membuat penampung, lihat [membuat penampung](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="46633-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="46633-134">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="46633-134">Select **Next**.</span></span>

1. <span data-ttu-id="46633-135">Pilih segmen yang ingin Anda ekspor.</span><span class="sxs-lookup"><span data-stu-id="46633-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="46633-136">Di contoh ini, itu adalah **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="46633-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Tangkapan layar dari antarmuka pengguna pilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. <span data-ttu-id="46633-138">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="46633-138">Select **Next**.</span></span>

1. <span data-ttu-id="46633-139">Sekarang kami memetakan bidang **Sumber** dari segmen wawasan audiens ke nama bidang **Target** dalam skema profil Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="46633-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Pemetaan bidang untuk konektor Adobe Campaign Standard.":::

   <span data-ttu-id="46633-141">Jika Anda ingin menambahkan atribut lainnya, pilih **Tambah atribut**.</span><span class="sxs-lookup"><span data-stu-id="46633-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="46633-142">Nama target dapat berbeda dari nama bidang sumber, sehingga Anda tetap dapat memetakan output segmen dari wawasan audiens ke Adobe Campaign Standard jika bidang tidak memiliki nama yang sama di kedua sistem.</span><span class="sxs-lookup"><span data-stu-id="46633-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="46633-143">Alamat email digunakan sebagai bidang identitas, namun Anda dapat menggunakan pengidentifikasi lainnya dari profil pelanggan wawasan audiens untuk memetakan data ke Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="46633-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="46633-144">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="46633-144">Select **Save**.</span></span>

<span data-ttu-id="46633-145">Setelah menyimpan tujuan ekspor, Anda dapat menemukannya di **Admin** > **Ekspor** > **Tujuan ekspor Saya**.</span><span class="sxs-lookup"><span data-stu-id="46633-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Tangkapan layar dengan daftar ekspor dan segmen sampel disorot.":::

<span data-ttu-id="46633-147">Anda sekarang dapat [mengekspor segmen sesuai permintaan](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="46633-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="46633-148">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md).</span><span class="sxs-lookup"><span data-stu-id="46633-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="46633-149">Pastikan jumlah rekaman dalam segmen yang diekspor berada dalam batas yang diizinkan untuk lisensi Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="46633-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="46633-150">Data yang diekspor disimpan dalam wadah Azure Blob storage yang dikonfigurasi di atas.</span><span class="sxs-lookup"><span data-stu-id="46633-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="46633-151">Jalur folder berikut dibuat secara otomatis dalam wadah Anda:</span><span class="sxs-lookup"><span data-stu-id="46633-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="46633-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="46633-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="46633-153">Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="46633-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="46633-154">Konfigurasikan Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="46633-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="46633-155">Bila segmen dari wawasan audiens diekspor, segmen tersebut berisi kolom yang Anda pilih saat menentukan tujuan ekspor pada langkah sebelumnya.</span><span class="sxs-lookup"><span data-stu-id="46633-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="46633-156">Data ini dapat digunakan untuk [membuat profil di Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="46633-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="46633-157">Agar dapat menggunakan segmen dalam Adobe Campaign Standard, kita harus memperluas skema profil di Adobe Campaign Standard agar dapat mencakup dua bidang tambahan.</span><span class="sxs-lookup"><span data-stu-id="46633-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="46633-158">Pelajari lebih lanjut cara [memperluas sumber daya profil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) dengan bidang baru di Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="46633-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="46633-159">Di contoh kami, bidang ini adalah *Nama Segmen dan Tanggal Segmen (opsional).*</span><span class="sxs-lookup"><span data-stu-id="46633-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="46633-160">Kita akan menggunakan bidang ini untuk mengidentifikasi profil dalam Adobe Campaign Standard yang akan ditargetkan untuk kampanye ini.</span><span class="sxs-lookup"><span data-stu-id="46633-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="46633-161">Jika tidak ada rekaman lain dalam Adobe Campaign Standard, selain yang akan diimpor, Anda dapat melewatkan langkah ini.</span><span class="sxs-lookup"><span data-stu-id="46633-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="46633-162">Mengimpor data ke Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="46633-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="46633-163">Setelah semuanya tersedia, kita harus mengimpor data audiens yang disiapkan dari wawasan audiens ke Adobe Campaign Standard untuk membuat profil.</span><span class="sxs-lookup"><span data-stu-id="46633-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="46633-164">Pelajari [cara mengimpor profil di Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) menggunakan alur kerja.</span><span class="sxs-lookup"><span data-stu-id="46633-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="46633-165">Alur kerja impor pada gambar di bawah ini telah dikonfigurasi untuk dijalankan setiap 8 jam dan mencari segmen wawasan audiens yang diekspor (file .csv dalam Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="46633-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="46633-166">Alur kerja mengekstrak konten file .csv dalam urutan kolom yang ditentukan.</span><span class="sxs-lookup"><span data-stu-id="46633-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="46633-167">Alur kerja ini telah dibuat untuk melakukan penanganan kesalahan dasar dan memastikan setiap rekaman memiliki alamat email sebelum menghidrasi data di Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="46633-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="46633-168">Alur kerja juga mengekstrak nama segmen dari nama file sebelum melakukan upserting ke data Profil ACS.</span><span class="sxs-lookup"><span data-stu-id="46633-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Cuplikan layar alur kerja impor di antarmuka pengguna Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="46633-170">Mengambil audiens di Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="46633-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="46633-171">Setelah data diimpor ke Adobe Campaign Standard, Anda dapat [membuat alur kerja](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) dan [mengkueri](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) pelanggan berdasarkan *Nama Segmen* dan *Tanggal Segmen* untuk memilih profil yang diidentifikasi untuk kampanye sampel kita.</span><span class="sxs-lookup"><span data-stu-id="46633-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="46633-172">Membuat dan mengirim email menggunakan Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="46633-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="46633-173">Buat konten email, lalu [uji dan kirim](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email Anda.</span><span class="sxs-lookup"><span data-stu-id="46633-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Contoh email dengan penawaran perpanjangan dari Adobe Campaign Standard.":::