---
title: Membuat dan mengelola segmen
description: Buat segmen pelanggan untuk mengelompokkan mereka berdasarkan berbagai atribut.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270360"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="a82f0-103">Membuat dan mengelola segmen</span><span class="sxs-lookup"><span data-stu-id="a82f0-103">Create and manage segments</span></span>

<span data-ttu-id="a82f0-104">Segmen memungkinkan Anda mengelompokkan pelanggan berdasarkan atribut demografi, transaksional, atau perilaku.</span><span class="sxs-lookup"><span data-stu-id="a82f0-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="a82f0-105">Anda dapat menggunakan segmen untuk menargetkan kampanye promosi, aktivitas penjualan, dan tindakan dukungan pelanggan untuk mencapai sasaran bisnis Anda.</span><span class="sxs-lookup"><span data-stu-id="a82f0-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="a82f0-106">Anda dapat menentukan filter kompleks di sekitar entitas profil pelanggan dan entitas terkait.</span><span class="sxs-lookup"><span data-stu-id="a82f0-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="a82f0-107">Setiap segmen, setelah pemrosesan, membuat kumpulan rekaman pelanggan yang dapat Anda ekspor dan lakukan tindakan padanya.</span><span class="sxs-lookup"><span data-stu-id="a82f0-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="a82f0-108">Beberapa [batas Layanan](service-limits.md) berlaku.</span><span class="sxs-lookup"><span data-stu-id="a82f0-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="a82f0-109">Kecuali jika dinyatakan lain, semua segmen adalah **segmen dinamis**, yang diperbarui pada jadwal berulang.</span><span class="sxs-lookup"><span data-stu-id="a82f0-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="a82f0-110">Contoh berikut menjelaskan kemampuan segmentasi.</span><span class="sxs-lookup"><span data-stu-id="a82f0-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="a82f0-111">Kami telah mendefinisikan segmen untuk pelanggan yang memesan setidaknya $500 barang di 90 hari terakhir *dan* yang terlibat dalam panggilan layanan pelanggan yang dieskalasi.</span><span class="sxs-lookup"><span data-stu-id="a82f0-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a82f0-112">![Beberapa grup](media/segmentation-group1-2.png "Beberapa grup")</span><span class="sxs-lookup"><span data-stu-id="a82f0-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="a82f0-113">Buat segmen baru</span><span class="sxs-lookup"><span data-stu-id="a82f0-113">Create a new segment</span></span>

<span data-ttu-id="a82f0-114">Segmen dikelola pada halaman **segmen**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="a82f0-115">Di wawasan audiens, buka halaman **segmen**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="a82f0-116">Pilih **Baru** > **segmen kosong**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="a82f0-117">Di panel **segmen baru**, pilih jenis segmen dan berikan **nama**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="a82f0-118">Atau, berikan nama tampilan, dan deskripsi yang membantu mengidentifikasi segmen.</span><span class="sxs-lookup"><span data-stu-id="a82f0-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="a82f0-119">Pilih **berikutnya** untuk mengakses halaman **pembuat segmen** dengan menentukan grup.</span><span class="sxs-lookup"><span data-stu-id="a82f0-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="a82f0-120">Grup adalah satu set pelanggan.</span><span class="sxs-lookup"><span data-stu-id="a82f0-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="a82f0-121">Pilih entitas yang mencakup atribut yang ingin Anda segmentasikan.</span><span class="sxs-lookup"><span data-stu-id="a82f0-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="a82f0-122">Pilih atribut untuk segmentasi.</span><span class="sxs-lookup"><span data-stu-id="a82f0-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="a82f0-123">Atribut ini dapat memiliki salah satu dari empat jenis nilai: numerik, string, tanggal, atau Boolean.</span><span class="sxs-lookup"><span data-stu-id="a82f0-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="a82f0-124">Pilih operator dan nilai untuk atribut dipilih.</span><span class="sxs-lookup"><span data-stu-id="a82f0-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a82f0-125">![Filter grup kustom](media/customer-group-numbers.png "Filter grup pelanggan")</span><span class="sxs-lookup"><span data-stu-id="a82f0-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="a82f0-126">Nomor</span><span class="sxs-lookup"><span data-stu-id="a82f0-126">Number</span></span> |<span data-ttu-id="a82f0-127">Definisi</span><span class="sxs-lookup"><span data-stu-id="a82f0-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="a82f0-128">1</span><span class="sxs-lookup"><span data-stu-id="a82f0-128">1</span></span>     |<span data-ttu-id="a82f0-129">Entity</span><span class="sxs-lookup"><span data-stu-id="a82f0-129">Entity</span></span>          |
   |<span data-ttu-id="a82f0-130">2</span><span class="sxs-lookup"><span data-stu-id="a82f0-130">2</span></span>     |<span data-ttu-id="a82f0-131">Atribut</span><span class="sxs-lookup"><span data-stu-id="a82f0-131">Attribute</span></span>          |
   |<span data-ttu-id="a82f0-132">3</span><span class="sxs-lookup"><span data-stu-id="a82f0-132">3</span></span>    |<span data-ttu-id="a82f0-133">Operator</span><span class="sxs-lookup"><span data-stu-id="a82f0-133">Operator</span></span>         |
   |<span data-ttu-id="a82f0-134">4</span><span class="sxs-lookup"><span data-stu-id="a82f0-134">4</span></span>    |<span data-ttu-id="a82f0-135">Nilai</span><span class="sxs-lookup"><span data-stu-id="a82f0-135">Value</span></span>         |

8. <span data-ttu-id="a82f0-136">Jika entitas terhubung ke entitas pelanggan terpadu melalui [Relasi](relationships.md), Anda harus menentukan jalur relasi untuk membuat segmen valid.</span><span class="sxs-lookup"><span data-stu-id="a82f0-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="a82f0-137">Tambahkan entitas dari jalur relasi hingga Anda dapat memilih entitas **pelanggan: CustomerInsights** dari dropdown.</span><span class="sxs-lookup"><span data-stu-id="a82f0-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="a82f0-138">Selanjutnya, pilih **semua rekaman** untuk setiap kondisi.</span><span class="sxs-lookup"><span data-stu-id="a82f0-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a82f0-139">![Jalur relasi selama pembuatan segmen](media/segments-multiple-relationships.png "Jalur relasi selama pembuatan segmen")</span><span class="sxs-lookup"><span data-stu-id="a82f0-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="a82f0-140">Pilih **Simpan** untuk menyimpan segmen Anda.</span><span class="sxs-lookup"><span data-stu-id="a82f0-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="a82f0-141">Segmen Anda akan disimpan dan diproses jika semua persyaratan divalidasi.</span><span class="sxs-lookup"><span data-stu-id="a82f0-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="a82f0-142">Jika tidak, maka akan disimpan sebagai draf.</span><span class="sxs-lookup"><span data-stu-id="a82f0-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="a82f0-143">Untuk kembali ke halaman **Segmen**, pilih **kembali ke segmen**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="a82f0-144">Mengelola segmen yang ada</span><span class="sxs-lookup"><span data-stu-id="a82f0-144">Manage existing segments</span></span>

<span data-ttu-id="a82f0-145">Di halaman **segmen**, Anda dapat melihat semua segmen tersimpan dan mengelolanya.</span><span class="sxs-lookup"><span data-stu-id="a82f0-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="a82f0-146">Setiap segmen diwakili oleh baris yang berisi informasi tambahan tentang segmen.</span><span class="sxs-lookup"><span data-stu-id="a82f0-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="a82f0-147">Anda dapat mengurutkan segmen di kolom dengan memilih heading kolom.</span><span class="sxs-lookup"><span data-stu-id="a82f0-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="a82f0-148">Gunakan kotak **Cari** di sudut kanan atas untuk memfilter segmen.</span><span class="sxs-lookup"><span data-stu-id="a82f0-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a82f0-149">![Pilihan untuk mengelola segmen yang ada](media/segments-selected-segment.png "Pilihan untuk mengelola segmen yang ada")</span><span class="sxs-lookup"><span data-stu-id="a82f0-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="a82f0-150">Tindakan berikut tersedia bila Anda memilih segmen:</span><span class="sxs-lookup"><span data-stu-id="a82f0-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="a82f0-151">**Lihat** rincian segmen, termasuk tren jumlah anggota yang menampilkan pratinjau anggota segmen.</span><span class="sxs-lookup"><span data-stu-id="a82f0-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="a82f0-152">**Edit** segmen untuk mengubah properti.</span><span class="sxs-lookup"><span data-stu-id="a82f0-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="a82f0-153">**Refresh** segmen untuk menyertakan data terbaru.</span><span class="sxs-lookup"><span data-stu-id="a82f0-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="a82f0-154">**Aktifkan** atau **Nonaktifkan** segmen.</span><span class="sxs-lookup"><span data-stu-id="a82f0-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="a82f0-155">Segmen memiliki dua kemungkinan status - aktif atau tidak aktif.</span><span class="sxs-lookup"><span data-stu-id="a82f0-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="a82f0-156">Status ini berguna saat mengedit segmen.</span><span class="sxs-lookup"><span data-stu-id="a82f0-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="a82f0-157">Untuk segmen yang tidak aktif, definisi segmen ada, namun tidak berisi pelanggan.</span><span class="sxs-lookup"><span data-stu-id="a82f0-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="a82f0-158">Bila Anda mengaktifkan segmen, status akan berubah dari ' tidak aktif ' menjadi ' aktif ' dan mulai mencari Pelanggan yang cocok dengan definisi segmen.</span><span class="sxs-lookup"><span data-stu-id="a82f0-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="a82f0-159">Jika [penyegaran terjadwal](system.md#schedule-tab) dikonfigurasi, segmen yang tidak aktif memiliki **status** yang didaftarkan sebagai **dilewati**, yang menunjukkan bahwa penyegaran bahkan tidak dicoba.</span><span class="sxs-lookup"><span data-stu-id="a82f0-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="a82f0-160">Bila segmen aktif diaktifkan, segmen akan diperbarui dan akan disertakan dalam penyegaran terjadwal.</span><span class="sxs-lookup"><span data-stu-id="a82f0-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="a82f0-161">Atau, Anda dapat menggunakan fungsi **jadwalkan nanti** dalam menu menurun **Aktifkan/Nonaktifkan** untuk menentukan tanggal dan waktu di masa mendatang untuk pengaktifan dan penonaktifan segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="a82f0-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="a82f0-162">**Ganti nama** segmen.</span><span class="sxs-lookup"><span data-stu-id="a82f0-162">**Rename** the segment.</span></span>
- <span data-ttu-id="a82f0-163">**Unduh** Daftar anggota sebagai File .CSV.</span><span class="sxs-lookup"><span data-stu-id="a82f0-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="a82f0-164">Pilihan **Tambahkan ke** akan mengirimkan daftar id pelanggan di segmen untuk diproses di aplikasi lain.</span><span class="sxs-lookup"><span data-stu-id="a82f0-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="a82f0-165">**Hapus** segmen.</span><span class="sxs-lookup"><span data-stu-id="a82f0-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="a82f0-166">Refresh Segmen</span><span class="sxs-lookup"><span data-stu-id="a82f0-166">Refresh segments</span></span>

<span data-ttu-id="a82f0-167">Anda dapat menyegarkan semua segmen sekaligus dengan memilih **Segarkan semua** pada halaman **segmen** atau Anda dapat menyegarkan satu atau beberapa segmen saat memilih dan memilih **Segarkan** dari pilihan.</span><span class="sxs-lookup"><span data-stu-id="a82f0-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="a82f0-168">Atau, Anda dapat mengkonfigurasi refresh berulang pada **Admin** > **sistem** > **jadwal**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="a82f0-169">Ada [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="a82f0-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="a82f0-170">Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="a82f0-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="a82f0-171">Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan.</span><span class="sxs-lookup"><span data-stu-id="a82f0-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="a82f0-172">Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="a82f0-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="a82f0-173">Unduh dan ekspor Segmen</span><span class="sxs-lookup"><span data-stu-id="a82f0-173">Download and export segments</span></span>

<span data-ttu-id="a82f0-174">Anda dapat mengunduh segmen ke file CSV atau mengekspornya ke Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a82f0-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="a82f0-175">Mengunduh segmen ke file CSV</span><span class="sxs-lookup"><span data-stu-id="a82f0-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="a82f0-176">Di wawasan audiens, buka halaman **segmen**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="a82f0-177">Pilih elipsis (...) dalam ubin segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="a82f0-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="a82f0-178">Pilih **Unduh sebagai CSV** dari daftar tarik-turun tindakan.</span><span class="sxs-lookup"><span data-stu-id="a82f0-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="a82f0-179">Ekspor segmen ke Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="a82f0-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="a82f0-180">Sebelum mengekspor segmen ke Dynamics 365 Sales, admin harus [membuat tujuan ekspor](export-destinations.md) untuk Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a82f0-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="a82f0-181">Di wawasan audiens, buka halaman **segmen**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="a82f0-182">Pilih elipsis (...) dalam ubin segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="a82f0-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="a82f0-183">Pilih **Tambah ke** dari daftar drop-down tindakan, lalu pilih tujuan ekspor yang akan Anda kirimi data.</span><span class="sxs-lookup"><span data-stu-id="a82f0-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="a82f0-184">Mode draf untuk segmen</span><span class="sxs-lookup"><span data-stu-id="a82f0-184">Draft mode for segments</span></span>

<span data-ttu-id="a82f0-185">Jika tidak semua persyaratan untuk memproses segmen terpenuhi, Anda dapat menyimpan segmen sebagai draf dan mengaksesnya dari halaman **segmen**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="a82f0-186">Ini akan disimpan sebagai segmen yang tidak aktif, dan tidak dapat diaktifkan hingga berlaku.</span><span class="sxs-lookup"><span data-stu-id="a82f0-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="a82f0-187">Menambah kondisi lainnya ke grup</span><span class="sxs-lookup"><span data-stu-id="a82f0-187">Add more conditions to a group</span></span>

<span data-ttu-id="a82f0-188">Untuk menambahkan kondisi ke grup, Anda dapat menggunakan dua operator logika:</span><span class="sxs-lookup"><span data-stu-id="a82f0-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="a82f0-189">Operator **AND**: kedua kondisi harus dipenuhi sebagai bagian dari proses segmentasi.</span><span class="sxs-lookup"><span data-stu-id="a82f0-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="a82f0-190">Pilihan ini paling berguna saat Anda menentukan kondisi di seluruh entitas yang berbeda.</span><span class="sxs-lookup"><span data-stu-id="a82f0-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="a82f0-191">Operator **OR**: Salah satu dari kondisi harus dipenuhi sebagai bagian dari proses segmentasi.</span><span class="sxs-lookup"><span data-stu-id="a82f0-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="a82f0-192">Pilihan ini paling berguna saat Anda menentukan beberapa kondisi untuk entitas yang sama.</span><span class="sxs-lookup"><span data-stu-id="a82f0-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a82f0-193">![Operator OR bila kedua kondisi harus dipenuhi](media/segmentation-either-condition.png "Operator OR bila kedua kondisi harus dipenuhi")</span><span class="sxs-lookup"><span data-stu-id="a82f0-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="a82f0-194">Saat ini mungkin untuk mengurung operator **OR** di bawah operator **AND**, namun tidak sebaliknya.</span><span class="sxs-lookup"><span data-stu-id="a82f0-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="a82f0-195">Menggabungkan beberapa grup</span><span class="sxs-lookup"><span data-stu-id="a82f0-195">Combine multiple groups</span></span>

<span data-ttu-id="a82f0-196">Setiap grup menghasilkan himpunan pelanggan tertentu.</span><span class="sxs-lookup"><span data-stu-id="a82f0-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="a82f0-197">Anda dapat menggabungkan grup ini untuk menyertakan Pelanggan yang diperlukan untuk kasus bisnis Anda.</span><span class="sxs-lookup"><span data-stu-id="a82f0-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="a82f0-198">Di wawasan audiens, buka halaman **segmen**, lalu pilih segmen.</span><span class="sxs-lookup"><span data-stu-id="a82f0-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="a82f0-199">Pilih **Tambah Grup**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a82f0-200">![Grup pelanggan Tambah grup](media/customer-group-add-group.png "Grup pelanggan Tambah grup")</span><span class="sxs-lookup"><span data-stu-id="a82f0-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="a82f0-201">Pilih salah satu operator rangkaian yang berikut: **Himpunan**, **Berpotongan**, atau **Kecuali**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a82f0-202">![Grup pelanggan Tambah penyatuan](media/customer-group-union.png "Grup pelanggan Tambah penyatuan")</span><span class="sxs-lookup"><span data-stu-id="a82f0-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="a82f0-203">Pilih himpunan operator untuk menentukan grup baru.</span><span class="sxs-lookup"><span data-stu-id="a82f0-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="a82f0-204">Simpan grup berbeda untuk menentukan data apa yang akan dipertahankan:</span><span class="sxs-lookup"><span data-stu-id="a82f0-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="a82f0-205">**Semesta** menyatukan dua kelompok.</span><span class="sxs-lookup"><span data-stu-id="a82f0-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="a82f0-206">**Berpotongan** tumpang-tindih kedua grup.</span><span class="sxs-lookup"><span data-stu-id="a82f0-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="a82f0-207">Hanya data yang *umum* untuk kedua grup yang dipertahankan dalam Grup Terpadu.</span><span class="sxs-lookup"><span data-stu-id="a82f0-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="a82f0-208">**Kecuali** menggabungkan dua grup.</span><span class="sxs-lookup"><span data-stu-id="a82f0-208">**Except** combines the two groups.</span></span> <span data-ttu-id="a82f0-209">Hanya data dalam grup A yang *tidak umum* untuk data di Grup B yang dipertahankan.</span><span class="sxs-lookup"><span data-stu-id="a82f0-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="a82f0-210">Melihat riwayat pemrosesan dan anggota segmen</span><span class="sxs-lookup"><span data-stu-id="a82f0-210">View processing history and segment members</span></span>

<span data-ttu-id="a82f0-211">Anda dapat melihat data gabungan tentang segmen dengan meninjau detailnya.</span><span class="sxs-lookup"><span data-stu-id="a82f0-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="a82f0-212">Pada halaman **segmen**, pilih segmen yang ingin Anda tinjau.</span><span class="sxs-lookup"><span data-stu-id="a82f0-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="a82f0-213">Bagian atas halaman mencakup diagram tren yang memvisualkan perubahan dalam jumlah anggota.</span><span class="sxs-lookup"><span data-stu-id="a82f0-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="a82f0-214">Arahkan kursor ke poin data untuk melihat jumlah anggota pada tanggal tertentu.</span><span class="sxs-lookup"><span data-stu-id="a82f0-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="a82f0-215">Anda dapat memperbarui jangka waktu visualisasi.</span><span class="sxs-lookup"><span data-stu-id="a82f0-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a82f0-216">![Rentang Waktu segmen](media/segment-time-range.png "Rentang Waktu segmen")</span><span class="sxs-lookup"><span data-stu-id="a82f0-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="a82f0-217">Bagian bawah berisi daftar anggota segmen.</span><span class="sxs-lookup"><span data-stu-id="a82f0-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="a82f0-218">Bidang yang muncul di daftar ini didasarkan pada atribut entitas segmen.</span><span class="sxs-lookup"><span data-stu-id="a82f0-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="a82f0-219">Daftar ini adalah pratinjau anggota segmen yang cocok dan menampilkan rekaman 100 pertama segmen Anda sehingga Anda dapat dengan cepat mengevaluasinya dan meninjau definisinya jika diperlukan.</span><span class="sxs-lookup"><span data-stu-id="a82f0-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="a82f0-220">Untuk melihat semua rekaman yang cocok, Anda harus [mengekspor segmen](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a82f0-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="a82f0-221">Segmen ringkas</span><span class="sxs-lookup"><span data-stu-id="a82f0-221">Quick segments</span></span>

<span data-ttu-id="a82f0-222">Selain pembuat segmen, ada jalur lain untuk membuat segmen.</span><span class="sxs-lookup"><span data-stu-id="a82f0-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="a82f0-223">Segmen ringkas memungkinkan Anda membuat segmen sederhana dengan satu operator dengan cepat dan dengan wawasan instan.</span><span class="sxs-lookup"><span data-stu-id="a82f0-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="a82f0-224">Pada halaman **segmen**, pilih **baru** > **Buat cepat dari**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="a82f0-225">Pilih pilihan **profil** untuk membuat segmen yang didasarkan pada entitas pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="a82f0-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="a82f0-226">Pilih pilihan **tindakan** untuk membuat segmen di sekitar masing-masing jenis atribut Pelanggan yang sebelumnya Anda buat di halaman **Ukuran**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="a82f0-227">Pilih **pilihan intelijen** untuk membuat segmen di sekitar salah satu entitas output yang dihasilkan menggunakan **prediksi** maupun kemampuan **model kustom**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="a82f0-228">Di kotak dialog **segmen ringkas baru**, pilih atribut dari dropdown **bidang**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="a82f0-229">Sistem akan memberikan beberapa wawasan tambahan yang membantu Anda membuat segmen pelanggan yang lebih baik.</span><span class="sxs-lookup"><span data-stu-id="a82f0-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="a82f0-230">Untuk bidang kategoris, kami akan menampilkan 10 hitungan pelanggan teratas.</span><span class="sxs-lookup"><span data-stu-id="a82f0-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="a82f0-231">Pilih **nilai** dan pilih **tinjau**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="a82f0-232">Untuk atribut numerik, sistem akan menampilkan nilai atribut yang berada di dalam persentil masing-masing pelanggan.</span><span class="sxs-lookup"><span data-stu-id="a82f0-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="a82f0-233">Pilih **operator** dan **nilai**, lalu pilih **tinjau**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="a82f0-234">Sistem akan memberi Anda **perkiraan ukuran segmen**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="a82f0-235">Anda dapat memilih apakah akan menghasilkan segmen yang telah Anda tetapkan, atau pertama-tama, mengunjungi kembali untuk mendapatkan ukuran segmen yang berbeda.</span><span class="sxs-lookup"><span data-stu-id="a82f0-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a82f0-236">![Nama dan estimasi untuk segmen cepat](media/quick-segment-name.png "Nama dan estimasi untuk segmen cepat")</span><span class="sxs-lookup"><span data-stu-id="a82f0-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="a82f0-237">Beri **nama** segmen Anda.</span><span class="sxs-lookup"><span data-stu-id="a82f0-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="a82f0-238">Atau, berikan **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="a82f0-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="a82f0-239">Klik **Simpan** untuk membuat segmen Anda.</span><span class="sxs-lookup"><span data-stu-id="a82f0-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="a82f0-240">Setelah segmen selesai diproses, Anda dapat melihatnya seperti segmen lain yang Anda buat.</span><span class="sxs-lookup"><span data-stu-id="a82f0-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="a82f0-241">Untuk skenario berikut, kami menyarankan menggunakan pembuat segmen daripada kemampuan segmen yang direkomendasikan:</span><span class="sxs-lookup"><span data-stu-id="a82f0-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="a82f0-242">Membuat segmen dengan filter pada bidang kategoris di mana operator berbeda dengan operator **Is**</span><span class="sxs-lookup"><span data-stu-id="a82f0-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="a82f0-243">Membuat segmen dengan filter pada bidang numerik di mana operator berbeda daripada operator **antara**, **lebih besar dari**, dan **kurang dari**</span><span class="sxs-lookup"><span data-stu-id="a82f0-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="a82f0-244">Membuat segmen dengan filter pada bidang jenis tanggal</span><span class="sxs-lookup"><span data-stu-id="a82f0-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="a82f0-245">Langkah-langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="a82f0-245">Next steps</span></span>

<span data-ttu-id="a82f0-246">[Ekspor segmen](export-destinations.md) dan jelajahi bagian [kartu pelanggan](customer-card-add-in.md) dan [konektor](export-power-bi.md) untuk mendapatkan wawasan tentang tingkat pelanggan.</span><span class="sxs-lookup"><span data-stu-id="a82f0-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]