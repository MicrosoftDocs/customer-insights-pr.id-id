---
title: Membuat dan mengedit ukuran
description: Tentukan ukuran terkait pelanggan untuk menganalisis dan mencerminkan performa area bisnis tertentu.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406078"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="92568-103">Menentukan dan mengelola ukuran</span><span class="sxs-lookup"><span data-stu-id="92568-103">Define and manage measures</span></span>

<span data-ttu-id="92568-104">**Ukuran** menunjukkan KPI (indikator performa utama) yang mencerminkan performa dan kesehatan area bisnis tertentu.</span><span class="sxs-lookup"><span data-stu-id="92568-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="92568-105">Wawasan audiens memberikan pengalaman yang intuitif untuk membuat berbagai jenis tindakan, dengan menggunakan pembuat kueri yang tidak mengharuskan Anda untuk mengkode, atau memvalidasi ukuran Anda secara manual.</span><span class="sxs-lookup"><span data-stu-id="92568-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="92568-106">Anda dapat melacak tindakan bisnis Anda di halaman **Beranda**, melihat tindakan untuk pelanggan tertentu di **kartu pelanggan**, dan menggunakan tindakan untuk menentukan segmen pelanggan di halaman **segmen**.</span><span class="sxs-lookup"><span data-stu-id="92568-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="92568-107">Membuat ukuran</span><span class="sxs-lookup"><span data-stu-id="92568-107">Create a measure</span></span>

<span data-ttu-id="92568-108">Bagian ini menuntun Anda dalam membuat ukuran dari awal.</span><span class="sxs-lookup"><span data-stu-id="92568-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="92568-109">Anda dapat membuat ukuran dengan data dari beberapa sumber data yang terhubung melalui entitas pelanggan.</span><span class="sxs-lookup"><span data-stu-id="92568-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="92568-110">Beberapa [batas Layanan](service-limits.md) berlaku.</span><span class="sxs-lookup"><span data-stu-id="92568-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="92568-111">Di wawasan audiens, buka **Ukuran**.</span><span class="sxs-lookup"><span data-stu-id="92568-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="92568-112">Pilih **ukuran baru**.</span><span class="sxs-lookup"><span data-stu-id="92568-112">Select **New measure**.</span></span>

3. <span data-ttu-id="92568-113">Pilih **jenis** ukuran:</span><span class="sxs-lookup"><span data-stu-id="92568-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="92568-114">**Atribut pelanggan**: Satu bidang per pelanggan yang mencerminkan Skor, nilai, atau status untuk pelanggan.</span><span class="sxs-lookup"><span data-stu-id="92568-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="92568-115">Atribut pelanggan dibuat sebagai atribut dalam entitas yang dihasilkan sistem baru yang disebut **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="92568-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="92568-116">**Ukuran pelanggan**: Wawasan tentang perilaku pelanggan dengan perincian berdasarkan dimensi yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="92568-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="92568-117">Entitas baru dibuat untuk setiap ukuran, mungkin dengan beberapa rekaman per pelanggan.</span><span class="sxs-lookup"><span data-stu-id="92568-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="92568-118">**Ukuran bisnis**: Melacak kinerja bisnis dan kesehatan bisnis.</span><span class="sxs-lookup"><span data-stu-id="92568-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="92568-119">Langkah bisnis dapat memiliki dua output yang berbeda: output numerik yang ditampilkan di halaman **Beranda** atau entitas baru yang Anda temukan pada halaman **entitas**.</span><span class="sxs-lookup"><span data-stu-id="92568-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="92568-120">Berikan **nama** dan **nama tampilan** opsional, lalu pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="92568-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="92568-121">Di bagian **Entitas**, pilih entitas pertama dari daftar menurun.</span><span class="sxs-lookup"><span data-stu-id="92568-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="92568-122">Pada titik ini, Anda harus memutuskan apakah entitas tambahan diperlukan sebagai bagian dari definisi ukuran Anda.</span><span class="sxs-lookup"><span data-stu-id="92568-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="92568-123">![Definisi Pengukuran](media/measure-definition.png "Definisi Pengukuran")</span><span class="sxs-lookup"><span data-stu-id="92568-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="92568-124">Untuk menambahkan lebih banyak entitas, pilih **Tambah entitas** dan pilih entitas yang akan digunakan untuk mengukur.</span><span class="sxs-lookup"><span data-stu-id="92568-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="92568-125">Anda dapat memilih hanya entitas yang memiliki Relasi ke entitas awal.</span><span class="sxs-lookup"><span data-stu-id="92568-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="92568-126">Untuk informasi lebih lanjut tentang cara mendefinisikan relasi, lihat [Relasi](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="92568-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="92568-127">Atau, Anda dapat mengkonfigurasi variabel.</span><span class="sxs-lookup"><span data-stu-id="92568-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="92568-128">Di bagian **variabel**, pilih **variabel baru**.</span><span class="sxs-lookup"><span data-stu-id="92568-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="92568-129">Variabel adalah penghitungan yang dibuat pada setiap rekaman yang Anda pilih.</span><span class="sxs-lookup"><span data-stu-id="92568-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="92568-130">Misalnya, menjumlahkan penjualan Point-of-Sale (POS) dan penjualan online untuk setiap rekaman pelanggan.</span><span class="sxs-lookup"><span data-stu-id="92568-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="92568-131">Beri **Nama** variabel tersebut.</span><span class="sxs-lookup"><span data-stu-id="92568-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="92568-132">Di area **ekspresi**, pilih bidang untuk memulai penghitungan.</span><span class="sxs-lookup"><span data-stu-id="92568-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="92568-133">Ketik ekspresi di area **ekspresi** saat memilih bidang yang akan disertakan dalam penghitungan Anda.</span><span class="sxs-lookup"><span data-stu-id="92568-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="92568-134">Saat ini, hanya ekspresi aritmetika yang didukung.</span><span class="sxs-lookup"><span data-stu-id="92568-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="92568-135">Selain itu, penghitungan variabel tidak didukung untuk entitas dari [jalur entitas](relationships.md) yang berbeda.</span><span class="sxs-lookup"><span data-stu-id="92568-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="92568-136">Pilih **Selesai**.</span><span class="sxs-lookup"><span data-stu-id="92568-136">Select **Done**.</span></span>

11. <span data-ttu-id="92568-137">Di bagian **definisi ukuran**, Anda akan menentukan cara entitas yang Anda pilih dan variabel yang dihitung digabungkan di entitas atau atribut ukuran baru.</span><span class="sxs-lookup"><span data-stu-id="92568-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="92568-138">Pilih **Dimensi baru**.</span><span class="sxs-lookup"><span data-stu-id="92568-138">Select **New dimension**.</span></span> <span data-ttu-id="92568-139">Anda dapat menganggap dimensi sebagai fungsi *grup berdasarkan*.</span><span class="sxs-lookup"><span data-stu-id="92568-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="92568-140">Output data entitas ukuran atau atribut akan dikelompokkan berdasarkan semua dimensi yang ditentukan.</span><span class="sxs-lookup"><span data-stu-id="92568-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="92568-141">![Pilih siklus agregat](media/measures-businessreport-measure-definition2.png "Pilih siklus agregat")</span><span class="sxs-lookup"><span data-stu-id="92568-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="92568-142">Pilih atau masukkan informasi berikut sebagai bagian dari definisi dimensi:</span><span class="sxs-lookup"><span data-stu-id="92568-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="92568-143">**Entitas**: jika Anda mendefinisikan entitas ukuran, harus mencakup sekurangnya satu atribut.</span><span class="sxs-lookup"><span data-stu-id="92568-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="92568-144">Jika Anda mendefinisikan atribut ukuran, atribut ukuran hanya akan mencakup satu atribut secara default.</span><span class="sxs-lookup"><span data-stu-id="92568-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="92568-145">Pilihan ini adalah tentang memilih entitas yang mencakup atribut tersebut.</span><span class="sxs-lookup"><span data-stu-id="92568-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="92568-146">**Bidang**: Pilih atribut khusus yang akan disertakan baik di entitas atau atribut ukuran Anda.</span><span class="sxs-lookup"><span data-stu-id="92568-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="92568-147">**wadah**: memilih apakah akan menggabungkan data secara harian, bulanan, atau tahunan.</span><span class="sxs-lookup"><span data-stu-id="92568-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="92568-148">Ini adalah pilihan yang diperlukan hanya jika Anda telah memilih jenis tanggal dari atribut.</span><span class="sxs-lookup"><span data-stu-id="92568-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="92568-149">**Sebagai**: menentukan nama bidang baru Anda.</span><span class="sxs-lookup"><span data-stu-id="92568-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="92568-150">**nama tampilan**: menentukan nama tampilan bidang anda.</span><span class="sxs-lookup"><span data-stu-id="92568-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="92568-151">Ukuran bisnis Anda akan disimpan sebagai entitas nomor tunggal dan akan muncul di halaman **Beranda**, kecuali Anda menambahkan dimensi lainnya ke ukuran Anda.</span><span class="sxs-lookup"><span data-stu-id="92568-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="92568-152">Setelah menambahkan dimensi lainnya , ukuran *tidak* akan muncul di halaman **Beranda**.</span><span class="sxs-lookup"><span data-stu-id="92568-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="92568-153">Atau, tambahkan fungsi agregat.</span><span class="sxs-lookup"><span data-stu-id="92568-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="92568-154">Agregasi apa pun yang Anda buat menghasilkan nilai baru dalam entitas atau atribut Ukuran Anda.</span><span class="sxs-lookup"><span data-stu-id="92568-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="92568-155">Fungsi agregasi yang didukung adalah **:** min **,** Max **,** Average **,** median **,** Sum **, Count Unique**, **First** (mengambil record pertama dari nilai dimensi), dan **Last** (mengambil record terakhir yang ditambahkan ke nilai dimensi).</span><span class="sxs-lookup"><span data-stu-id="92568-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="92568-156">Pilih **Simpan** untuk menerapkan perubahan ke ukuran.</span><span class="sxs-lookup"><span data-stu-id="92568-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="92568-157">Kelola ukuran Anda</span><span class="sxs-lookup"><span data-stu-id="92568-157">Manage your measures</span></span>

<span data-ttu-id="92568-158">Setelah membuat minimal satu pengukuran, Anda akan melihat daftar ukuran pada halaman **Ukuran**.</span><span class="sxs-lookup"><span data-stu-id="92568-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="92568-159">Anda akan menemukan informasi tentang jenis ukuran, pembuat, tanggal pembuatan dan waktu, terakhir mengedit tanggal dan waktu, status (Apakah ukuran aktif, tidak aktif, atau gagal), dan refresh tanggal dan waktu terakhir.</span><span class="sxs-lookup"><span data-stu-id="92568-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="92568-160">Bila Anda memilih ukuran dari daftar, Anda dapat melihat pratinjau outputnya.</span><span class="sxs-lookup"><span data-stu-id="92568-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="92568-161">Untuk me-refresh semua ukuran Anda pada waktu yang sama, pilih **Segarkan semua** tanpa memilih ukuran tertentu.</span><span class="sxs-lookup"><span data-stu-id="92568-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="92568-162">![Tindakan untuk mengelola ukuran tunggal](media/measure-actions.png "Tindakan untuk mengelola langkah tunggal")</span><span class="sxs-lookup"><span data-stu-id="92568-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="92568-163">Atau, Pilih ukuran dari daftar dan lakukan salah satu tindakan berikut:</span><span class="sxs-lookup"><span data-stu-id="92568-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="92568-164">Pilih nama ukuran untuk melihat rinciannya.</span><span class="sxs-lookup"><span data-stu-id="92568-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="92568-165">**Edit** konfigurasi ukuran.</span><span class="sxs-lookup"><span data-stu-id="92568-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="92568-166">**Ubah nama** ukuran.</span><span class="sxs-lookup"><span data-stu-id="92568-166">**Rename** the measure.</span></span>
- <span data-ttu-id="92568-167">**Hapus** ukuran.</span><span class="sxs-lookup"><span data-stu-id="92568-167">**Delete** the measure.</span></span>
- <span data-ttu-id="92568-168">Pilih elipsis (...) dan kemudian **refresh** untuk memulai proses refresh untuk ukuran.</span><span class="sxs-lookup"><span data-stu-id="92568-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="92568-169">Pilih elipsis (...) dan kemudian **Unduh** untuk mendapatkan File .CSV ukuran.</span><span class="sxs-lookup"><span data-stu-id="92568-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="92568-170">Ada [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="92568-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="92568-171">Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="92568-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="92568-172">Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan.</span><span class="sxs-lookup"><span data-stu-id="92568-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="92568-173">Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="92568-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="92568-174">Langkah selanjutnya</span><span class="sxs-lookup"><span data-stu-id="92568-174">Next step</span></span>

<span data-ttu-id="92568-175">Anda dapat menggunakan langkah yang ada untuk membuat segmen pelanggan pertama pada halaman **segmen**.</span><span class="sxs-lookup"><span data-stu-id="92568-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="92568-176">Untuk informasi lebih lanjut, lihat [Segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="92568-176">For more information, see [Segments](segments.md).</span></span>
