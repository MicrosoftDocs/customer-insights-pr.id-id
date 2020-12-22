---
title: Aktivitas pelanggan
description: Menentukan aktivitas pelanggan dan melihatnya di Timeline pelanggan.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667233"
---
# <a name="customer-activities"></a><span data-ttu-id="e4acd-103">Aktivitas pelanggan</span><span class="sxs-lookup"><span data-stu-id="e4acd-103">Customer activities</span></span>

<span data-ttu-id="e4acd-104">Kombinasikan aktivitas pelanggan dari [berbagai sumber data](data-sources.md) di Dynamics 365 Customer Insights untuk membuat Timeline Pelanggan yang berisi daftar aktivitas dalam urutan kronologis.</span><span class="sxs-lookup"><span data-stu-id="e4acd-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="e4acd-105">Anda dapat menyertakan kronologi di aplikasi keterlibatan pelanggan di Dynamics 365 melalui [Add-in kartu pelanggan](customer-card-add-in.md), atau di dasbor Power BI.</span><span class="sxs-lookup"><span data-stu-id="e4acd-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="e4acd-106">Menentukan Aktivitas</span><span class="sxs-lookup"><span data-stu-id="e4acd-106">Define an activity</span></span>

<span data-ttu-id="e4acd-107">Sumber data Anda mencakup entitas dengan data transaksional dan aktivitas dari beberapa sumber data.</span><span class="sxs-lookup"><span data-stu-id="e4acd-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="e4acd-108">Identifikasi entitas tersebut dan pilih aktivitas yang ingin Anda lihat pada kronologi pelanggan.</span><span class="sxs-lookup"><span data-stu-id="e4acd-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="e4acd-109">Pilih entitas yang mencakup aktivitas atau aktivitas target Anda.</span><span class="sxs-lookup"><span data-stu-id="e4acd-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="e4acd-110">Di wawasan audiens, buka **Data** > **aktivitas**.</span><span class="sxs-lookup"><span data-stu-id="e4acd-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="e4acd-111">Pilih **Tambah aktivitas**.</span><span class="sxs-lookup"><span data-stu-id="e4acd-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e4acd-112">Entitas harus memiliki minimal satu atribut jenis **tanggal** untuk disertakan dalam kronologi pelanggan dan Anda tidak dapat menambahkan entitas tanpa bidang **tanggal**.</span><span class="sxs-lookup"><span data-stu-id="e4acd-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="e4acd-113">Kontrol **Tambah aktivitas** dinonaktifkan jika tidak ada entitas yang ditemukan.</span><span class="sxs-lookup"><span data-stu-id="e4acd-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="e4acd-114">Di panel **Tambah aktivitas**, atur nilai untuk bidang berikut:</span><span class="sxs-lookup"><span data-stu-id="e4acd-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="e4acd-115">**Entitas**: Pilih entitas yang mencakup data transaksi atau aktivitas.</span><span class="sxs-lookup"><span data-stu-id="e4acd-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="e4acd-116">**Kunci utama**: Pilih bidang yang secara unik mengidentifikasi rekaman.</span><span class="sxs-lookup"><span data-stu-id="e4acd-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="e4acd-117">Ini tidak boleh berisi nilai duplikat, nilai kosong, atau nilai yang tidak ada.</span><span class="sxs-lookup"><span data-stu-id="e4acd-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="e4acd-118">**Cap waktu**: pilih bidang yang menunjukkan waktu mulai aktivitas Anda.</span><span class="sxs-lookup"><span data-stu-id="e4acd-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="e4acd-119">**Aktivitas**: pilih bidang yang merupakan peristiwa aktivitas.</span><span class="sxs-lookup"><span data-stu-id="e4acd-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="e4acd-120">**Alamat web**: pilih bidang yang menunjukkan URL yang menyediakan informasi tambahan tentang aktivitas ini.</span><span class="sxs-lookup"><span data-stu-id="e4acd-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="e4acd-121">Misalnya, sistem transaksional yang menjadi sumber aktivitas ini.</span><span class="sxs-lookup"><span data-stu-id="e4acd-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="e4acd-122">URL ini dapat berupa bidang apa pun dari sumber data, atau dapat dibangun sebagai bidang baru menggunakan transformasi Power Query.</span><span class="sxs-lookup"><span data-stu-id="e4acd-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="e4acd-123">Data URL ini akan disimpan di entitas aktivitas terpadu, yang dapat dikonsumsi ke hilir menggunakan api.</span><span class="sxs-lookup"><span data-stu-id="e4acd-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="e4acd-124">**Rincian**: opsional, pilih bidang yang ditambahkan untuk rincian tambahan.</span><span class="sxs-lookup"><span data-stu-id="e4acd-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="e4acd-125">**Ikon**: opsional, pilih ikon yang menunjukkan aktivitas ini.</span><span class="sxs-lookup"><span data-stu-id="e4acd-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="e4acd-126">**Jenis aktivitas**: Tentukan referensi jenis aktivitas ke Common Data Model yang paling sesuai dengan definisi semantik aktivitas.</span><span class="sxs-lookup"><span data-stu-id="e4acd-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="e4acd-127">Di Bagian **Atur relasi**, konfigurasikan rincian untuk menghubungkan data aktivitas Anda dengan pelanggan yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="e4acd-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e4acd-128">![Tentukan relasi entitas](media/activities-entities-define.png "Tentukan relasi entitas.").</span><span class="sxs-lookup"><span data-stu-id="e4acd-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="e4acd-129">Bidang **entitas aktivitas**: pilih bidang di entitas aktivitas yang akan digunakan untuk menjalin relasi dengan entitas lain.</span><span class="sxs-lookup"><span data-stu-id="e4acd-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="e4acd-130">**Entitas pelanggan**: Pilih entitas pelanggan sumber terkait yang memiliki relasi dengan entitas aktivitas Anda.</span><span class="sxs-lookup"><span data-stu-id="e4acd-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="e4acd-131">Anda hanya dapat berhubungan dengan entitas pelanggan sumber yang digunakan dalam proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="e4acd-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="e4acd-132">**Bidang entitas pelanggan**: bidang ini menampilkan kunci primer dari entitas pelanggan sumber yang dipilih dalam proses peta.</span><span class="sxs-lookup"><span data-stu-id="e4acd-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="e4acd-133">Bidang kunci primer di entitas pelanggan sumber digunakan untuk menjalin relasi dengan entitas aktivitas.</span><span class="sxs-lookup"><span data-stu-id="e4acd-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="e4acd-134">**Nama**: jika relasi antara entitas aktivitas ini dan entitas pelanggan sumber yang dipilih sudah ada, nama relasi hanya akan berada dalam mode baca-saja.</span><span class="sxs-lookup"><span data-stu-id="e4acd-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="e4acd-135">Jika hubungan tersebut tidak ada, relasi baru akan dibuat dengan nama yang diberikan di sini.</span><span class="sxs-lookup"><span data-stu-id="e4acd-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="e4acd-136">Pilih **Simpan** untuk menerapkan perubahan.</span><span class="sxs-lookup"><span data-stu-id="e4acd-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="e4acd-137">Pada halaman **aktivitas**, pilih **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="e4acd-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="e4acd-138">Ada [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="e4acd-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e4acd-139">Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e4acd-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e4acd-140">Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan.</span><span class="sxs-lookup"><span data-stu-id="e4acd-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e4acd-141">Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="e4acd-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="e4acd-142">Edit aktivitas</span><span class="sxs-lookup"><span data-stu-id="e4acd-142">Edit an activity</span></span>

1. <span data-ttu-id="e4acd-143">Di wawasan audiens, buka **Data** > **aktivitas**.</span><span class="sxs-lookup"><span data-stu-id="e4acd-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="e4acd-144">Pilih entitas aktivitas yang akan diedit dan pilih **Edit**.</span><span class="sxs-lookup"><span data-stu-id="e4acd-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="e4acd-145">Atau, Anda dapat mengarahkan kursor ke baris entitas dan memilih **ikon Edit**.</span><span class="sxs-lookup"><span data-stu-id="e4acd-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="e4acd-146">Klik ikon **Edit**.</span><span class="sxs-lookup"><span data-stu-id="e4acd-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="e4acd-147">Di panel **Edit aktivitas**, perbarui nilai dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="e4acd-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="e4acd-148">Pada halaman **aktivitas**, pilih **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="e4acd-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="e4acd-149">Hapus Aktivitas</span><span class="sxs-lookup"><span data-stu-id="e4acd-149">Delete an activity</span></span>

1. <span data-ttu-id="e4acd-150">Di wawasan audiens, buka **Data** > **aktivitas**.</span><span class="sxs-lookup"><span data-stu-id="e4acd-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="e4acd-151">Pilih entitas aktivitas yang akan dihapus dan pilih **Hapus**.</span><span class="sxs-lookup"><span data-stu-id="e4acd-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="e4acd-152">Atau, Anda dapat mengarahkan kursor ke baris entitas dan memilih ikon **Hapus**.</span><span class="sxs-lookup"><span data-stu-id="e4acd-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="e4acd-153">Selain itu, Anda dapat memilih beberapa entitas aktivitas untuk dihapus sekaligus.</span><span class="sxs-lookup"><span data-stu-id="e4acd-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e4acd-154">![Mengedit atau menghapus relasi entitas](media/activities-entities-edit-delete.png "Mengedit atau menghapus relasi entitas")</span><span class="sxs-lookup"><span data-stu-id="e4acd-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="e4acd-155">Pilih ikon **Hapus**.</span><span class="sxs-lookup"><span data-stu-id="e4acd-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="e4acd-156">Konfirmasikan penghapusan.</span><span class="sxs-lookup"><span data-stu-id="e4acd-156">Confirm your deletion.</span></span>
