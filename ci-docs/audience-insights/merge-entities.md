---
title: Gabungkan entitas dalam penyatuan data
description: Gabungkan entitas untuk membuat profil pelanggan terpadu.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305645"
---
# <a name="merge-entities"></a><span data-ttu-id="af0f7-103">Gabungkan Entitas</span><span class="sxs-lookup"><span data-stu-id="af0f7-103">Merge entities</span></span>

<span data-ttu-id="af0f7-104">Fase gabungkan adalah fase terakhir dalam proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="af0f7-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="af0f7-105">Tujuannya adalah merekonsiliasi data yang berkonflik.</span><span class="sxs-lookup"><span data-stu-id="af0f7-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="af0f7-106">Contoh data yang berkonflik dapat mencakup nama pelanggan yang berada di dua dataset, namun ditampilkan sedikit berbeda di masing-masing ("Grant Marshall" versus "Grant"), atau format nomor telepon yang berbeda format (617-803-091X versus 617803091X).</span><span class="sxs-lookup"><span data-stu-id="af0f7-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="af0f7-107">Penggabungan titik data yang berkonflik dilakukan pada basis atribut demi atribut.</span><span class="sxs-lookup"><span data-stu-id="af0f7-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Halaman gabungan dalam proses penyatuan data yang menampilkan tabel dengan bidang gabungan yang mendefinisikan profil pelanggan terpadu.":::

<span data-ttu-id="af0f7-109">Setelah menyelesaikan [fase kecocokan](match-entities.md), Anda memulai fase penggabungan dengan memilih ubin **gabungkan** pada halaman **satukan**.</span><span class="sxs-lookup"><span data-stu-id="af0f7-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="af0f7-110">Tinjau rekomendasi sistem</span><span class="sxs-lookup"><span data-stu-id="af0f7-110">Review system recommendations</span></span>

<span data-ttu-id="af0f7-111">Pada **Data** > **Satukan** > **Gabungkan**, Anda memilih dan mengecualikan atribut untuk digabungkan dalam entitas profil pelanggan terpadu Anda.</span><span class="sxs-lookup"><span data-stu-id="af0f7-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="af0f7-112">Profil pelanggan terpadu adalah hasil dari proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="af0f7-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="af0f7-113">Beberapa atribut secara otomatis digabungkan oleh sistem.</span><span class="sxs-lookup"><span data-stu-id="af0f7-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="af0f7-114">Untuk melihat atribut yang tercakup di salah satu atribut gabungan otomatis Anda, pilih atribut gabungan tersebut di tab **Bidang pelanggan** pada tabel.</span><span class="sxs-lookup"><span data-stu-id="af0f7-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="af0f7-115">Atribut yang membentuk atribut gabungan ditampilkan dalam dua baris baru di bawah atribut gabungan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="af0f7-116">Memisahkan, mengganti nama, mengecualikan, dan mengedit bidang gabungan</span><span class="sxs-lookup"><span data-stu-id="af0f7-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="af0f7-117">Anda dapat mengubah cara sistem memproses atribut gabungan untuk menghasilkan profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="af0f7-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="af0f7-118">Pilih **Tampilkan lainnya**, lalu pilih yang akan diubah.</span><span class="sxs-lookup"><span data-stu-id="af0f7-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Pilihan di menu dropdown Tampilkan lainnya untuk mengelola atribut gabungan.":::

<span data-ttu-id="af0f7-120">Untuk informasi lebih lanjut, lihat bagian berikut.</span><span class="sxs-lookup"><span data-stu-id="af0f7-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="af0f7-121">Pisahkan bidang gabungan</span><span class="sxs-lookup"><span data-stu-id="af0f7-121">Separate merged fields</span></span>

<span data-ttu-id="af0f7-122">Untuk memisahkan bidang gabungan, cari atribut di tabel.</span><span class="sxs-lookup"><span data-stu-id="af0f7-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="af0f7-123">Bidang terpisah ditampilkan sebagai poin data individual di profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="af0f7-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="af0f7-124">Pilih bidang gabungan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="af0f7-125">Pilih **Tampilkan lainnya** dan pilih **Bidang terpisah**.</span><span class="sxs-lookup"><span data-stu-id="af0f7-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="af0f7-126">Konfirmasikan pemisahan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-126">Confirm the separation.</span></span>

1. <span data-ttu-id="af0f7-127">Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="af0f7-128">Ganti nama bidang yang digabungkan</span><span class="sxs-lookup"><span data-stu-id="af0f7-128">Rename merged fields</span></span>

<span data-ttu-id="af0f7-129">Ubah nama tampilan atribut gabungan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="af0f7-130">Anda tidak dapat mengubah nama entitas output.</span><span class="sxs-lookup"><span data-stu-id="af0f7-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="af0f7-131">Pilih bidang gabungan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="af0f7-132">Pilih **Tampilkan lainnya** dan pilih **Ganti nama**.</span><span class="sxs-lookup"><span data-stu-id="af0f7-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="af0f7-133">Konfirmasikan perubahan nama tampilan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="af0f7-134">Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="af0f7-135">Pisahkan bidang gabungan</span><span class="sxs-lookup"><span data-stu-id="af0f7-135">Exclude merged fields</span></span>

<span data-ttu-id="af0f7-136">Pisahkan atribut dari profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="af0f7-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="af0f7-137">Jika bidang digunakan dalam proses lain, misalnya dalam segmen, hilangkan dari proses ini sebelum mengecualikannya dari profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="af0f7-138">Pilih bidang gabungan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="af0f7-139">Pilih **Tampilkan lainnya** dan pilih **Pisahkan**.</span><span class="sxs-lookup"><span data-stu-id="af0f7-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="af0f7-140">Konfirmasikan pengecualian.</span><span class="sxs-lookup"><span data-stu-id="af0f7-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="af0f7-141">Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="af0f7-142">Pada halaman **Gabung**, pilih **Bidang yang dikecualikan** untuk melihat daftar semua bidang yang dipisahkan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="af0f7-143">Panel ini memungkinkan Anda menambahkan kembali bidang yang dipisahkan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="af0f7-144">Gabungkan bidang secara manual</span><span class="sxs-lookup"><span data-stu-id="af0f7-144">Manually combine fields</span></span>

<span data-ttu-id="af0f7-145">Tentukan atribut gabungan secara manual.</span><span class="sxs-lookup"><span data-stu-id="af0f7-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="af0f7-146">Pada halaman **Gabung**, pilih **Gabungkan bidang**.</span><span class="sxs-lookup"><span data-stu-id="af0f7-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="af0f7-147">Berikan **Nama** dan **nama bidang Output**.</span><span class="sxs-lookup"><span data-stu-id="af0f7-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="af0f7-148">Pilih bidang untuk ditambahkan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-148">Choose a field to add.</span></span> <span data-ttu-id="af0f7-149">pilih **Tambahkan bidang** untuk mengombinasikan bidang lainnya.</span><span class="sxs-lookup"><span data-stu-id="af0f7-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="af0f7-150">Konfirmasikan pengecualian.</span><span class="sxs-lookup"><span data-stu-id="af0f7-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="af0f7-151">Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="af0f7-152">Ubah urutan bidang</span><span class="sxs-lookup"><span data-stu-id="af0f7-152">Change the order of fields</span></span>

<span data-ttu-id="af0f7-153">Beberapa entitas berisi rincian lebih banyak daripada entitas lain.</span><span class="sxs-lookup"><span data-stu-id="af0f7-153">Some entities contain more details than others.</span></span> <span data-ttu-id="af0f7-154">Jika entitas mencakup data terbaru tentang bidang, Anda dapat memprioritaskan entitas lain saat menggabungkan nilai.</span><span class="sxs-lookup"><span data-stu-id="af0f7-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="af0f7-155">Pilih bidang gabungan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="af0f7-156">Pilih **Tampilkan lainnya** dan pilih **Edit**.</span><span class="sxs-lookup"><span data-stu-id="af0f7-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="af0f7-157">Di panel **Gabungkan bidang**, pilih **Pindahkan ke atas/bawah** untuk mengatur urutan atau menarik dan melepasnya dalam posisi yang diinginkan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="af0f7-158">Konfirmasikan perubahan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-158">Confirm the change.</span></span>

1. <span data-ttu-id="af0f7-159">Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="af0f7-160">Jalankan gabungan</span><span class="sxs-lookup"><span data-stu-id="af0f7-160">Run your merge</span></span>

<span data-ttu-id="af0f7-161">Apakah Anda menggabungkan atribut secara manual atau membiarkan sistem menggabungkannya, Anda dapat menjalankan gabungan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="af0f7-162">Pada halaman **Gabungkan**, pilih **Jalankan** untuk memulai proses.</span><span class="sxs-lookup"><span data-stu-id="af0f7-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="af0f7-163">![menyimpan dan menjalankan Gabungan data](media/configure-data-merge-save-run.png "menyimpan dan menjalankan Gabungan data")</span><span class="sxs-lookup"><span data-stu-id="af0f7-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="af0f7-164">Pilih **Jalankan hanya penggabungan** jika Anda hanya ingin melihat output yang tercermin di entitas pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="af0f7-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="af0f7-165">Proses hilir akan di-refresh sebagaimana [ditentukan dalam jadwal refresh](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="af0f7-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="af0f7-166">Pilih **Jalankan Proses Penggabungan dan hilir** untuk me-refresh sistem dengan perubahan Anda.</span><span class="sxs-lookup"><span data-stu-id="af0f7-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="af0f7-167">Semua proses, termasuk pengayaan, segmen, dan langkah-langkah akan berjalan secara otomatis.</span><span class="sxs-lookup"><span data-stu-id="af0f7-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="af0f7-168">Setelah semua proses hilir selesai, profil pelanggan mencerminkan perubahan yang Anda buat.</span><span class="sxs-lookup"><span data-stu-id="af0f7-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="af0f7-169">Untuk membuat perubahan lebih banyak dan menjalankan ulang langkah, Anda dapat membatalkan penggabungan yang sedang berlangsung.</span><span class="sxs-lookup"><span data-stu-id="af0f7-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="af0f7-170">Pilih teks **menyegarkan...** dan pilih **Batalkan pekerjaan**  di panel sisi yang muncul.</span><span class="sxs-lookup"><span data-stu-id="af0f7-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="af0f7-171">Ada [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="af0f7-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="af0f7-172">Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="af0f7-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="af0f7-173">Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan.</span><span class="sxs-lookup"><span data-stu-id="af0f7-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="af0f7-174">Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="af0f7-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="af0f7-175">Langkah Berikutnya</span><span class="sxs-lookup"><span data-stu-id="af0f7-175">Next Step</span></span>

<span data-ttu-id="af0f7-176">Konfigurasikan [aktivitas](activities.md), [pengayaan](enrichment-hub.md), atau [Relasi](relationships.md) untuk mendapatkan wawasan lebih tentang pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="af0f7-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="af0f7-177">Jika Anda telah mengkonfigurasi aktivitas, pengayaan, atau segmen, maka aktivitas akan diproses secara otomatis untuk menggunakan data pelanggan terbaru.</span><span class="sxs-lookup"><span data-stu-id="af0f7-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
