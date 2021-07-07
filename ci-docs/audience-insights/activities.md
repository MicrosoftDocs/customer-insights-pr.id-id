---
title: Aktivitas pelanggan
description: Menentukan aktivitas pelanggan dan melihatnya di Timeline pelanggan.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304930"
---
# <a name="customer-activities"></a><span data-ttu-id="38287-103">Aktivitas pelanggan</span><span class="sxs-lookup"><span data-stu-id="38287-103">Customer activities</span></span>

<span data-ttu-id="38287-104">Gabungkan aktivitas pelanggan dari [berbagai sumber data](data-sources.md) di Dynamics 365 Customer Insights untuk membuat timeline yang mencantumkan aktivitas secara kronologis.</span><span class="sxs-lookup"><span data-stu-id="38287-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="38287-105">Sertakan timeline di aplikasi Dynamics 365 dengan solusi [add-in Kartu Pelanggan](customer-card-add-in.md), atau di dasbor Power BI.</span><span class="sxs-lookup"><span data-stu-id="38287-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="38287-106">Menentukan Aktivitas</span><span class="sxs-lookup"><span data-stu-id="38287-106">Define an activity</span></span>

<span data-ttu-id="38287-107">Sumber data Anda dapat mencakup entitas dengan data transaksional dan aktivitas dari beberapa sumber data.</span><span class="sxs-lookup"><span data-stu-id="38287-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="38287-108">Identifikasi entitas tersebut dan pilih aktivitas yang ingin Anda lihat pada kronologi pelanggan.</span><span class="sxs-lookup"><span data-stu-id="38287-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="38287-109">Pilih entitas yang mencakup aktivitas atau aktivitas target Anda.</span><span class="sxs-lookup"><span data-stu-id="38287-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="38287-110">Entitas harus memiliki minimal satu atribut jenis **tanggal** untuk disertakan dalam kronologi pelanggan dan Anda tidak dapat menambahkan entitas tanpa bidang **tanggal**.</span><span class="sxs-lookup"><span data-stu-id="38287-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="38287-111">Kontrol **Tambah aktivitas** dinonaktifkan jika tidak ada entitas yang ditemukan.</span><span class="sxs-lookup"><span data-stu-id="38287-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="38287-112">Di wawasan audiens, buka **Data** > **aktivitas**.</span><span class="sxs-lookup"><span data-stu-id="38287-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="38287-113">Pilih **Tambahkan aktivitas** untuk memulai pengalaman terpandu untuk proses penyetelan aktivitas.</span><span class="sxs-lookup"><span data-stu-id="38287-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="38287-114">Dalam langkah **Data aktivitas**, atur nilai untuk bidang berikut ini:</span><span class="sxs-lookup"><span data-stu-id="38287-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="38287-115">**Nama aktivitas**: Pilih nama untuk aktivitas Anda.</span><span class="sxs-lookup"><span data-stu-id="38287-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="38287-116">**Entitas**: Pilih entitas yang mencakup data transaksi atau aktivitas.</span><span class="sxs-lookup"><span data-stu-id="38287-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="38287-117">**Kunci utama**: Pilih bidang yang secara unik mengidentifikasi rekaman.</span><span class="sxs-lookup"><span data-stu-id="38287-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="38287-118">Ini tidak boleh berisi nilai duplikat, nilai kosong, atau nilai yang tidak ada.</span><span class="sxs-lookup"><span data-stu-id="38287-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Siapkan data aktivitas dengan nama, entitas, dan kunci utama.":::

1. <span data-ttu-id="38287-120">Pilih **Berikutnya** untuk masuk ke langkah berikutnya.</span><span class="sxs-lookup"><span data-stu-id="38287-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="38287-121">Dalam langkah **Relasi**, konfigurasikan detail untuk menghubungkan data aktivitas Anda ke pelanggan yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="38287-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="38287-122">Langkah ini memvisualisasikan hubungan antar entitas.</span><span class="sxs-lookup"><span data-stu-id="38287-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="38287-123">**Pertama:** Bidang asing dalam entitas aktivitas Anda yang akan digunakan untuk menjalin hubungan dengan entitas lain.</span><span class="sxs-lookup"><span data-stu-id="38287-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="38287-124">**Kedua**: Entitas pelanggan sumber yang sesuai dengan entitas aktivitas Anda akan menjalin hubungan.</span><span class="sxs-lookup"><span data-stu-id="38287-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="38287-125">Anda hanya dapat berhubungan dengan entitas pelanggan sumber yang digunakan dalam proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="38287-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="38287-126">**Ketiga**: Jika hubungan antara entitas aktivitas ini dan entitas pelanggan sumber yang dipilih sudah ada, nama hubungan akan berada dalam mode baca-saja.</span><span class="sxs-lookup"><span data-stu-id="38287-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="38287-127">Jika tidak ada relasi tersebut, relasi baru akan dibuat dengan nama yang Anda berikan di kotak ini.</span><span class="sxs-lookup"><span data-stu-id="38287-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Tentukan relasi entitas.":::

1. <span data-ttu-id="38287-129">Pilih **Berikutnya** untuk masuk ke langkah berikutnya.</span><span class="sxs-lookup"><span data-stu-id="38287-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="38287-130">Dalam langkah **Penyatuan aktivitas**, pilih peristiwa aktivitas dan waktu mulai aktivitas Anda.</span><span class="sxs-lookup"><span data-stu-id="38287-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="38287-131">**Bidang yang diperlukan**</span><span class="sxs-lookup"><span data-stu-id="38287-131">**Required fields**</span></span>
      - <span data-ttu-id="38287-132">**Aktivitas peristiwa**: Bidang yang menjadi ajang aktivitas ini.</span><span class="sxs-lookup"><span data-stu-id="38287-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="38287-133">**Cap waktu**: Bidang yang mewakili waktu mulai aktivitas Anda.</span><span class="sxs-lookup"><span data-stu-id="38287-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="38287-134">**Bidang Opsional**</span><span class="sxs-lookup"><span data-stu-id="38287-134">**Optional fields**</span></span>
      - <span data-ttu-id="38287-135">**Detail tambahan**: Bidang dengan informasi yang relevan untuk kegiatan ini.</span><span class="sxs-lookup"><span data-stu-id="38287-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="38287-136">**Ikon**: Ikon yang paling mewakili jenis aktivitas ini.</span><span class="sxs-lookup"><span data-stu-id="38287-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="38287-137">**Alamat web**: Bidang yang berisi URL dengan informasi tentang aktivitas ini.</span><span class="sxs-lookup"><span data-stu-id="38287-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="38287-138">Misalnya, sistem transaksional yang menjadi sumber aktivitas ini.</span><span class="sxs-lookup"><span data-stu-id="38287-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="38287-139">URL ini dapat berupa bidang apa pun dari sumber data, atau dapat dibangun sebagai bidang baru menggunakan transformasi Power Query.</span><span class="sxs-lookup"><span data-stu-id="38287-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="38287-140">Data URL akan disimpan di entitas *Aktivitas Terpadu*, yang dapat dikonsumsi di hilir menggunakan [API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="38287-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Tentukan data aktivitas pelanggan dalam entitas Aktivitas Terpadu.":::

1. <span data-ttu-id="38287-142">Pilih **berikutnya** untuk beralih ke langkah berikutnya.</span><span class="sxs-lookup"><span data-stu-id="38287-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="38287-143">Anda dapat memilih **Selesai dan tinjau** untuk menyimpan aktivitas sekarang dengan tipe aktivitas yang diatur ke **Lainnya**.</span><span class="sxs-lookup"><span data-stu-id="38287-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="38287-144">Dalam langkah **Jenis Aktivitas**, pilih jenis aktivitas dan pilih secara opsional jika Anda ingin memetakan beberapa jenis aktivitas untuk digunakan di area lain dari Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="38287-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="38287-145">Saat ini, jenis aktivitas *Langganan* dan *SalesOrderLine* dapat dipetakan secara semantis setelah setuju untuk memetakan bidang.</span><span class="sxs-lookup"><span data-stu-id="38287-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="38287-146">Jika jenis aktivitas tidak relevan untuk aktivitas baru, Anda dapat memilih *Lainnya* atau *buat yang baru* untuk jenis aktivitas kustom.</span><span class="sxs-lookup"><span data-stu-id="38287-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="38287-147">Pilih **berikutnya** untuk beralih ke langkah berikutnya.</span><span class="sxs-lookup"><span data-stu-id="38287-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="38287-148">Di langkah **Tinjau**, verifikasi pilihan Anda.</span><span class="sxs-lookup"><span data-stu-id="38287-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="38287-149">Kembali ke langkah-langkah sebelumnya dan perbarui informasi jika perlu.</span><span class="sxs-lookup"><span data-stu-id="38287-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Meninjau bidang yang ditentukan untuk aktivitas.":::
   
1. <span data-ttu-id="38287-151">Pilih **Simpan aktivitas** untuk menerapkan perubahan Anda dan pilih **Selesai** untuk kembali ke **Data** > **Aktivitas**.</span><span class="sxs-lookup"><span data-stu-id="38287-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="38287-152">Di sini Anda melihat aktivitas mana yang diatur untuk ditampilkan di timeline.</span><span class="sxs-lookup"><span data-stu-id="38287-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="38287-153">Pada halaman **Aktivitas**, pilih **Jalankan** untuk memproses aktivitas.</span><span class="sxs-lookup"><span data-stu-id="38287-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="38287-154">Ada [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="38287-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="38287-155">Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="38287-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="38287-156">Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan.</span><span class="sxs-lookup"><span data-stu-id="38287-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="38287-157">Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="38287-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="38287-158">Mengelola aktivitas yang ada</span><span class="sxs-lookup"><span data-stu-id="38287-158">Manage existing activities</span></span>

<span data-ttu-id="38287-159">Pada **Data** > **Aktivitas**, Anda dapat melihat semua aktivitas yang disimpan, dan mengelolanya.</span><span class="sxs-lookup"><span data-stu-id="38287-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="38287-160">Setiap aktivitas diwakili oleh baris yang juga menyertakan detail tentang sumber, entitas, dan jenis aktivitas.</span><span class="sxs-lookup"><span data-stu-id="38287-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="38287-161">Tindakan berikut ini tersedia saat Anda memilih aktivitas.</span><span class="sxs-lookup"><span data-stu-id="38287-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="38287-162">**Edit**: Membuka penyiapan aktivitas pada langkah peninjauan.</span><span class="sxs-lookup"><span data-stu-id="38287-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="38287-163">Anda dapat mengubah salah satu atau semua konfigurasi saat ini dari langkah ini.</span><span class="sxs-lookup"><span data-stu-id="38287-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="38287-164">Setelah mengubah konfigurasi, pilih **Simpan aktivitas** lalu pilih **Jalankan** untuk memproses perubahan.</span><span class="sxs-lookup"><span data-stu-id="38287-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="38287-165">**Ganti nama**: Buka dialog yang memungkinkan Anda memasukkan nama lain untuk aktivitas yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="38287-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="38287-166">Pilih **Simpan** untuk menerapkan perubahan.</span><span class="sxs-lookup"><span data-stu-id="38287-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="38287-167">**Hapus**: Membuka dialog untuk mengonfirmasi penghapusan aktivitas yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="38287-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="38287-168">Anda juga dapat menghapus lebih dari satu aktivitas sekaligus dengan memilih aktivitas lalu memilih ikon hapus.</span><span class="sxs-lookup"><span data-stu-id="38287-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="38287-169">Klik **Hapus**, untuk mengonfirmasi penghapusan tersebut.</span><span class="sxs-lookup"><span data-stu-id="38287-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
