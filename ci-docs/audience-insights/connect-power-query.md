---
title: Serap data melalui Power Query connector
description: Konektor untuk sumber data berdasarkan Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: b9a1b30e37c3792aa7bdfcfc177da9e8a32c324d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596917"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="4c38d-103">Sambungkan ke sumber data Power Query</span><span class="sxs-lookup"><span data-stu-id="4c38d-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="4c38d-104">Power Query menawarkan seperangkat konektor yang luas untuk menyerap data.</span><span class="sxs-lookup"><span data-stu-id="4c38d-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="4c38d-105">Sebagian besar konektor ini didukung oleh Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4c38d-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="4c38d-106">Menambahkan sumber data berdasarkan Power Query connectors biasanya mengikuti langkah yang diuraikan di bagian berikutnya.</span><span class="sxs-lookup"><span data-stu-id="4c38d-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="4c38d-107">Namun, tergantung pada konektor yang Anda gunakan, informasi yang berbeda diperlukan.</span><span class="sxs-lookup"><span data-stu-id="4c38d-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="4c38d-108">Untuk informasi lebih lanjut, lihat dokumentasi tentang konektor individual di [Power Query connector](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="4c38d-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="4c38d-109">Buat sumber data baru</span><span class="sxs-lookup"><span data-stu-id="4c38d-109">Create a new data source</span></span>

1. <span data-ttu-id="4c38d-110">Di wawasan audiens, buka **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="4c38d-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="4c38d-111">Pilih **Tambahkan sumber data**.</span><span class="sxs-lookup"><span data-stu-id="4c38d-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="4c38d-112">Pilih metode **impor data** dan pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="4c38d-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="4c38d-113">Berikan **nama** untuk sumber data, lalu pilih **berikutnya** untuk membuat sumber data.</span><span class="sxs-lookup"><span data-stu-id="4c38d-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="4c38d-114">Panduan nama:</span><span class="sxs-lookup"><span data-stu-id="4c38d-114">Name guidelines:</span></span> 
   - <span data-ttu-id="4c38d-115">Diawali dengan huruf.</span><span class="sxs-lookup"><span data-stu-id="4c38d-115">Start with a letter.</span></span>
   - <span data-ttu-id="4c38d-116">Gunakan huruf dan angka saja.</span><span class="sxs-lookup"><span data-stu-id="4c38d-116">Use letters and numbers only.</span></span> <span data-ttu-id="4c38d-117">Spasi atau karakter khusus tidak dibolehkan.</span><span class="sxs-lookup"><span data-stu-id="4c38d-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="4c38d-118">Gunakan antara 3 hingga 64 karakter.</span><span class="sxs-lookup"><span data-stu-id="4c38d-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="4c38d-119">Pilih salah satu dari [konektor yang tersedia](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="4c38d-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="4c38d-120">Untuk contoh ini, kita pilih konektor **teks/CSV**.</span><span class="sxs-lookup"><span data-stu-id="4c38d-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="4c38d-121">Masukkan rincian yang diperlukan dalam **pengaturan sambungan** untuk konektor yang dipilih dan pilih **berikutnya** untuk melihat pratinjau data.</span><span class="sxs-lookup"><span data-stu-id="4c38d-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="4c38d-122">Pilih **Transformasi data**.</span><span class="sxs-lookup"><span data-stu-id="4c38d-122">Select **Transform data**.</span></span> <span data-ttu-id="4c38d-123">Pada langkah ini, Anda akan menambahkan entitas ke sumber data.</span><span class="sxs-lookup"><span data-stu-id="4c38d-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="4c38d-124">Entitas adalah dataset.</span><span class="sxs-lookup"><span data-stu-id="4c38d-124">Entities are datasets.</span></span> <span data-ttu-id="4c38d-125">Jika Anda memiliki database yang mencakup beberapa dataset, maka setiap himpunan data adalah entitas sendiri.</span><span class="sxs-lookup"><span data-stu-id="4c38d-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="4c38d-126">Dialog **Power Query Edit kueri** memungkinkan anda meninjau dan menyempurnakan data.</span><span class="sxs-lookup"><span data-stu-id="4c38d-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="4c38d-127">Entitas yang diidentifikasi dalam sumber data yang dipilih muncul di panel kiri.</span><span class="sxs-lookup"><span data-stu-id="4c38d-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4c38d-128">![Dialog Edit kueri](media/data-manager-configure-edit-queries.png "Dialog Edit kueri")</span><span class="sxs-lookup"><span data-stu-id="4c38d-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="4c38d-129">Anda juga dapat mengubah data Anda.</span><span class="sxs-lookup"><span data-stu-id="4c38d-129">You can also transform your data.</span></span> <span data-ttu-id="4c38d-130">Pilih entitas untuk mengedit atau mengubah.</span><span class="sxs-lookup"><span data-stu-id="4c38d-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="4c38d-131">Gunakan pilihan di jendela Power Query untuk menerapkan transformasi.</span><span class="sxs-lookup"><span data-stu-id="4c38d-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="4c38d-132">Setiap transformasi akan terdaftar di dalam **langkah yang diterapkan**.</span><span class="sxs-lookup"><span data-stu-id="4c38d-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="4c38d-133">Power Query menyediakan banyak pilihan transformasi yang telah dibuat sebelumnya.</span><span class="sxs-lookup"><span data-stu-id="4c38d-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="4c38d-134">Lihat [Transformasi Power Query](/power-query/power-query-what-is-power-query#transformations) Untuk informasi lebih lanjut.</span><span class="sxs-lookup"><span data-stu-id="4c38d-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="4c38d-135">Anda dapat menambahkan entitas tambahan ke sumber data dengan memilih **dapatkan data**, dalam dialog **Edit kueri**.</span><span class="sxs-lookup"><span data-stu-id="4c38d-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="4c38d-136">Transformasi ini sangat dianjurkan:</span><span class="sxs-lookup"><span data-stu-id="4c38d-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="4c38d-137">Jika Anda menyerap data dari file CSV, baris pertama sering berisi header.</span><span class="sxs-lookup"><span data-stu-id="4c38d-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="4c38d-138">Buka **Transformasi tabel** dan pilih **Gunakan header sebagai baris pertama**.</span><span class="sxs-lookup"><span data-stu-id="4c38d-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="4c38d-139">Pastikan jenis data diatur dengan benar.</span><span class="sxs-lookup"><span data-stu-id="4c38d-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="4c38d-140">Pilih **Simpan** di bawah jendela Power Query untuk menyimpan transformasi.</span><span class="sxs-lookup"><span data-stu-id="4c38d-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="4c38d-141">Setelah menyimpan, anda akan menemukan sumber data anda di **Data** > **sumber data**.</span><span class="sxs-lookup"><span data-stu-id="4c38d-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="4c38d-142">Di halaman **sumber data**, anda akan melihat sumber data baru berada dalam status yang **Menyegarkan**.</span><span class="sxs-lookup"><span data-stu-id="4c38d-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="4c38d-143">Sumber data Power Query yang tersedia</span><span class="sxs-lookup"><span data-stu-id="4c38d-143">Available Power Query data sources</span></span>

<span data-ttu-id="4c38d-144">Lihat referensi [Power Query connector](/power-query/connectors/) untuk daftar konektor terkini yang dapat Anda pilih untuk mengimpor data ke Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4c38d-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="4c38d-145">Konektor dengan tanda centang di kolom **Customer Insights (aliran data)** tersedia untuk membuat sumber data baru berdasarkan Power query.</span><span class="sxs-lookup"><span data-stu-id="4c38d-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="4c38d-146">Tinjau dokumentasi konektor tertentu untuk mempelajari lebih lanjut tentang prasyarat, batasan, dan rincian lainnya.</span><span class="sxs-lookup"><span data-stu-id="4c38d-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="4c38d-147">Edit sumber data Power Query</span><span class="sxs-lookup"><span data-stu-id="4c38d-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="4c38d-148">Anda mungkin tidak dapat melakukan perubahan pada sumber data yang saat ini sedang digunakan di salah satu proses aplikasi *(segmentasi*, *kecocokan*, atau *penggabungan*, misalnya).</span><span class="sxs-lookup"><span data-stu-id="4c38d-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="4c38d-149">Dengan menggunakan halaman **pengaturan**, Anda dapat melacak progres setiap proses aktif.</span><span class="sxs-lookup"><span data-stu-id="4c38d-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="4c38d-150">Setelah proses selesai, Anda dapat kembali ke halaman **sumber data** dan melakukan perubahan.</span><span class="sxs-lookup"><span data-stu-id="4c38d-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="4c38d-151">Di wawasan audiens, buka **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="4c38d-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="4c38d-152">Pilih elipsis vertikal di sebelah sumber data yang akan diubah dan pilih **Edit** dari menu drop-down.</span><span class="sxs-lookup"><span data-stu-id="4c38d-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4c38d-153">![Opsi edit](media/edit-option-data-sources.png "Opsi edit")</span><span class="sxs-lookup"><span data-stu-id="4c38d-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="4c38d-154">Terapkan perubahan dan transformasi anda di **dialog Power Query-Edit kueri** seperti yang dijelaskan di bagian [buat sumber data baru](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="4c38d-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="4c38d-155">Pilih **simpan** di Power Query setelah menyelesaikan pengeditan untuk menyimpan perubahan.</span><span class="sxs-lookup"><span data-stu-id="4c38d-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]