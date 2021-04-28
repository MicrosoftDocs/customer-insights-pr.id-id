---
title: Mengekspor data Customer Insights ke Adobe Campaign Standard
description: Pelajari bagaimana menggunakan segmen wawasan audiens dalam Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760285"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="e2024-103">Gunakan segmen Customer Insights dalam Adobe Campaign Standard (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="e2024-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="e2024-104">Sebagai pengguna wawasan audiens untuk Dynamics 365 Customer Insights, Anda mungkin telah membuat segmen untuk membuat kampanye pemasaran yang lebih efisien dengan menargetkan audiens yang relevan.</span><span class="sxs-lookup"><span data-stu-id="e2024-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="e2024-105">Agar dapat menggunakan segmen audiens wawasan dalam Adobe Experience Platform dan aplikasi seperti Adobe Campaign Standard, Anda harus mengikuti beberapa langkah yang diuraikan dalam artikel ini.</span><span class="sxs-lookup"><span data-stu-id="e2024-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram proses dari langkah-langkah yang diuraikan dalam artikel ini.":::

## <a name="prerequisites"></a><span data-ttu-id="e2024-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="e2024-107">Prerequisites</span></span>

-   <span data-ttu-id="e2024-108">Lisensi Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="e2024-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="e2024-109">Lisensi Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e2024-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="e2024-110">Akun Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="e2024-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="e2024-111">Ikhtisar Kampanye</span><span class="sxs-lookup"><span data-stu-id="e2024-111">Campaign Overview</span></span>

<span data-ttu-id="e2024-112">Untuk lebih memahami bagaimana Anda dapat menggunakan segmen wawasan audiens dalam Adobe Experience Platform, lihat kampanye sampel fiktif.</span><span class="sxs-lookup"><span data-stu-id="e2024-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="e2024-113">Misalnya, perusahaan Anda menawarkan layanan berbasis langganan bulanan kepada pelanggan Anda di Amerika Serikat.</span><span class="sxs-lookup"><span data-stu-id="e2024-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="e2024-114">Anda ingin mengidentifikasi pelanggan yang langganannya harus diperpanjang dalam delapan hari berikutnya tetapi belum memperbarui langganan mereka.</span><span class="sxs-lookup"><span data-stu-id="e2024-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="e2024-115">Untuk menjaga pelanggan ini, Anda perlu mengirimkan penawaran promosi melalui email, menggunakan Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e2024-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="e2024-116">Di contoh ini, kita ingin menjalankan kampanye email promosi sekali.</span><span class="sxs-lookup"><span data-stu-id="e2024-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="e2024-117">Artikel ini tidak mencakup kasus penggunaan dalam menjalankan kampanye lebih dari satu kali.</span><span class="sxs-lookup"><span data-stu-id="e2024-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="e2024-118">Namun, audiens dan Adobe Campaign Standard juga dapat dikonfigurasi untuk mengerjakan skenario kampanye berulang.</span><span class="sxs-lookup"><span data-stu-id="e2024-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="e2024-119">Identifikasikan target audiens</span><span class="sxs-lookup"><span data-stu-id="e2024-119">Identify your target audience</span></span>

<span data-ttu-id="e2024-120">Dalam skenario kami, kami mengasumsikan bahwa alamat email pelanggan tersedia di wawasan audiens dan preferensi promosi mereka dianalisis untuk mengidentifikasi anggota segmen.</span><span class="sxs-lookup"><span data-stu-id="e2024-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="e2024-121">[Segmen yang Anda tentukan dalam wawasan audiens](segments.md) disebut **ChurnProneCustomers** dan Anda berencana mengirimkan promosi email kepada pelanggan ini.</span><span class="sxs-lookup"><span data-stu-id="e2024-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Tangkapan layar halaman segmen dengan segmen ChurnProneCustomers dibuat.":::

<span data-ttu-id="e2024-123">Email penawaran yang ingin Anda kirim akan berisi nama depan, nama belakang, dan tanggal berakhir langganan pelanggan.</span><span class="sxs-lookup"><span data-stu-id="e2024-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="e2024-124">Ini akan menginformasikan kepada pelanggan tentang diskon yang akan mereka dapatkan jika mereka memperpanjang langganan sebelum berakhir.</span><span class="sxs-lookup"><span data-stu-id="e2024-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="e2024-125">Ekspor target audiens</span><span class="sxs-lookup"><span data-stu-id="e2024-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="e2024-126">Mengonfigurasi koneksi</span><span class="sxs-lookup"><span data-stu-id="e2024-126">Configure a connection</span></span>

<span data-ttu-id="e2024-127">Dengan target audiens, kita dapat mengkonfigurasi ekspor dari wawasan audiens ke akun Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="e2024-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="e2024-128">Dalam audiens wawasan, buka **Koneksi** > **Admin**.</span><span class="sxs-lookup"><span data-stu-id="e2024-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e2024-129">Pilih **Tambah koneksi** dan pilih **Kampanye Adobe** untuk mengkonfigurasi koneksi atau pilih **Konfigurasi** dalam petak **Kampanye Adobe**</span><span class="sxs-lookup"><span data-stu-id="e2024-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Petak konfigurasi untuk Adobe Campaign Standard.":::

1. <span data-ttu-id="e2024-131">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="e2024-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e2024-132">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="e2024-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e2024-133">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="e2024-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e2024-134">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="e2024-134">Choose who can use this connection.</span></span> <span data-ttu-id="e2024-135">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="e2024-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e2024-136">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e2024-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e2024-137">Masukkan **nama Akun**, **Kunci akun**, dan **Wadah** akun Penyimpanan Blob Azure untuk diekspor segmennya.</span><span class="sxs-lookup"><span data-stu-id="e2024-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurasi akun penyimpanan. "::: 

   - <span data-ttu-id="e2024-139">Untuk mempelajari lebih lanjut tentang cara menemukan kunci akun dan nama akun penyimpanan Azure Blob, lihat [mengelola pengaturan akun penyimpanan di portal Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="e2024-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="e2024-140">Untuk mempelajari cara membuat penampung, lihat [membuat penampung](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="e2024-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="e2024-141">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="e2024-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="e2024-142">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="e2024-142">Configure an export</span></span>

<span data-ttu-id="e2024-143">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="e2024-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e2024-144">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e2024-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e2024-145">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="e2024-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e2024-146">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="e2024-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="e2024-147">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Kampanye Adobe.</span><span class="sxs-lookup"><span data-stu-id="e2024-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="e2024-148">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="e2024-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e2024-149">Pilih segmen yang ingin Anda ekspor.</span><span class="sxs-lookup"><span data-stu-id="e2024-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="e2024-150">Di contoh ini, itu adalah **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="e2024-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Tangkapan layar dari antarmuka pengguna pilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. <span data-ttu-id="e2024-152">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="e2024-152">Select **Next**.</span></span>

1. <span data-ttu-id="e2024-153">Sekarang kami memetakan bidang **Sumber** dari segmen wawasan audiens ke nama bidang **Target** dalam skema profil Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e2024-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Pemetaan bidang untuk konektor Adobe Campaign Standard.":::

   <span data-ttu-id="e2024-155">Jika Anda ingin menambahkan atribut lainnya, pilih **Tambah atribut**.</span><span class="sxs-lookup"><span data-stu-id="e2024-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="e2024-156">Nama target dapat berbeda dari nama bidang sumber, sehingga Anda tetap dapat memetakan output segmen dari wawasan audiens ke Adobe Campaign Standard jika bidang tidak memiliki nama yang sama di kedua sistem.</span><span class="sxs-lookup"><span data-stu-id="e2024-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e2024-157">Alamat email digunakan sebagai bidang identitas, namun Anda dapat menggunakan pengidentifikasi lainnya dari profil pelanggan wawasan audiens untuk memetakan data ke Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e2024-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="e2024-158">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="e2024-158">Select **Save**.</span></span>

<span data-ttu-id="e2024-159">Setelah menyimpan tujuan ekspor, Anda menemukannya di **Ekspor** > **Data**.</span><span class="sxs-lookup"><span data-stu-id="e2024-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="e2024-160">Anda sekarang dapat [mengekspor segmen sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e2024-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="e2024-161">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md).</span><span class="sxs-lookup"><span data-stu-id="e2024-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e2024-162">Pastikan jumlah rekaman dalam segmen yang diekspor berada dalam batas yang diizinkan untuk lisensi Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e2024-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="e2024-163">Data yang diekspor disimpan dalam wadah Azure Blob storage yang dikonfigurasi di atas.</span><span class="sxs-lookup"><span data-stu-id="e2024-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="e2024-164">Jalur folder berikut dibuat secara otomatis dalam wadah Anda:</span><span class="sxs-lookup"><span data-stu-id="e2024-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="e2024-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="e2024-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="e2024-166">Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="e2024-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="e2024-167">Konfigurasikan Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e2024-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="e2024-168">Bila segmen dari wawasan audiens diekspor, segmen tersebut berisi kolom yang Anda pilih saat menentukan tujuan ekspor pada langkah sebelumnya.</span><span class="sxs-lookup"><span data-stu-id="e2024-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="e2024-169">Data ini dapat digunakan untuk [membuat profil di Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="e2024-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="e2024-170">Agar dapat menggunakan segmen dalam Adobe Campaign Standard, kita harus memperluas skema profil di Adobe Campaign Standard agar dapat mencakup dua bidang tambahan.</span><span class="sxs-lookup"><span data-stu-id="e2024-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="e2024-171">Pelajari lebih lanjut cara [memperluas sumber daya profil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) dengan bidang baru di Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e2024-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="e2024-172">Di contoh kami, bidang ini adalah *Nama Segmen dan Tanggal Segmen (opsional).*</span><span class="sxs-lookup"><span data-stu-id="e2024-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="e2024-173">Kita akan menggunakan bidang ini untuk mengidentifikasi profil dalam Adobe Campaign Standard yang akan ditargetkan untuk kampanye ini.</span><span class="sxs-lookup"><span data-stu-id="e2024-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="e2024-174">Jika tidak ada rekaman lain dalam Adobe Campaign Standard, selain yang akan diimpor, Anda dapat melewatkan langkah ini.</span><span class="sxs-lookup"><span data-stu-id="e2024-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="e2024-175">Mengimpor data ke Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e2024-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="e2024-176">Setelah semuanya tersedia, kita harus mengimpor data audiens yang disiapkan dari wawasan audiens ke Adobe Campaign Standard untuk membuat profil.</span><span class="sxs-lookup"><span data-stu-id="e2024-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="e2024-177">Pelajari [cara mengimpor profil di Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) menggunakan alur kerja.</span><span class="sxs-lookup"><span data-stu-id="e2024-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="e2024-178">Alur kerja impor pada gambar di bawah ini telah dikonfigurasi untuk dijalankan setiap 8 jam dan mencari segmen wawasan audiens yang diekspor (file .csv dalam Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="e2024-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="e2024-179">Alur kerja mengekstrak konten file .csv dalam urutan kolom yang ditentukan.</span><span class="sxs-lookup"><span data-stu-id="e2024-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="e2024-180">Alur kerja ini telah dibuat untuk melakukan penanganan kesalahan dasar dan memastikan setiap rekaman memiliki alamat email sebelum menghidrasi data di Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="e2024-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="e2024-181">Alur kerja juga mengekstrak nama segmen dari nama file sebelum melakukan upserting ke data Profil ACS.</span><span class="sxs-lookup"><span data-stu-id="e2024-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Cuplikan layar alur kerja impor di antarmuka pengguna Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="e2024-183">Mengambil audiens di Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e2024-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="e2024-184">Setelah data diimpor ke Adobe Campaign Standard, Anda dapat [membuat alur kerja](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) dan [mengkueri](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) pelanggan berdasarkan *Nama Segmen* dan *Tanggal Segmen* untuk memilih profil yang diidentifikasi untuk kampanye sampel kita.</span><span class="sxs-lookup"><span data-stu-id="e2024-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="e2024-185">Membuat dan mengirim email menggunakan Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="e2024-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="e2024-186">Buat konten email, lalu [uji dan kirim](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email Anda.</span><span class="sxs-lookup"><span data-stu-id="e2024-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Contoh email dengan penawaran perpanjangan dari Adobe Campaign Standard.":::
