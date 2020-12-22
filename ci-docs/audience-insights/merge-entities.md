---
title: Gabungkan entitas dalam penyatuan data
description: Gabungkan entitas untuk membuat profil pelanggan terpadu.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406075"
---
# <a name="merge-entities"></a><span data-ttu-id="62529-103">Gabungkan Entitas</span><span class="sxs-lookup"><span data-stu-id="62529-103">Merge entities</span></span>

<span data-ttu-id="62529-104">Fase gabungkan adalah fase terakhir dalam proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="62529-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="62529-105">Tujuannya adalah merekonsiliasi data yang berkonflik.</span><span class="sxs-lookup"><span data-stu-id="62529-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="62529-106">Contoh data yang berkonflik dapat mencakup nama pelanggan yang berada di dua dataset, namun ditampilkan sedikit berbeda di masing-masing ("Grant Marshall" versus "Grant"), atau format nomor telepon yang berbeda format (617-803-091X versus 617803091X).</span><span class="sxs-lookup"><span data-stu-id="62529-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="62529-107">Penggabungan titik data yang berkonflik dilakukan pada basis atribut demi atribut.</span><span class="sxs-lookup"><span data-stu-id="62529-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="62529-108">Setelah menyelesaikan [fase kecocokan](match-entities.md), Anda memulai fase penggabungan dengan memilih ubin **gabungkan** pada halaman **satukan**.</span><span class="sxs-lookup"><span data-stu-id="62529-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="62529-109">Tinjau rekomendasi sistem</span><span class="sxs-lookup"><span data-stu-id="62529-109">Review system recommendations</span></span>

<span data-ttu-id="62529-110">Di halaman **Gabungkan**, Anda dapat memilih dan mengecualikan atribut yang harus digabungkan dalam entitas profil pelanggan terpadu (hasil dari proses konfigurasi).</span><span class="sxs-lookup"><span data-stu-id="62529-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="62529-111">Beberapa atribut secara otomatis digabungkan oleh sistem.</span><span class="sxs-lookup"><span data-stu-id="62529-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="62529-112">Lihat atribut yang digabungkan</span><span class="sxs-lookup"><span data-stu-id="62529-112">View merged attributes</span></span>

<span data-ttu-id="62529-113">Untuk melihat atribut yang disertakan dalam salah satu dari atribut yang digabungkan secara otomatis, pilih atribut gabungan tersebut.</span><span class="sxs-lookup"><span data-stu-id="62529-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="62529-114">Dua atribut yang membentuk atribut gabungan akan muncul di dua baris baru di bawah atribut gabungan.</span><span class="sxs-lookup"><span data-stu-id="62529-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="62529-115">![pilih atribut gabungan](media/configure-data-merge-profile-attributes.png "pilih atribut gabungan")</span><span class="sxs-lookup"><span data-stu-id="62529-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="62529-116">Pisahkan atribut yang digabungkan</span><span class="sxs-lookup"><span data-stu-id="62529-116">Separate merged attributes</span></span>

<span data-ttu-id="62529-117">Untuk memisahkan atau batal menggabungkan atribut yang digabungkan secara otomatis, temukan atribut di tabel **atribut profil**.</span><span class="sxs-lookup"><span data-stu-id="62529-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="62529-118">Pilih tombol elipsis (...).</span><span class="sxs-lookup"><span data-stu-id="62529-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="62529-119">Di daftar drop-down , pilih **Bidang terpisah**.</span><span class="sxs-lookup"><span data-stu-id="62529-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="62529-120">Hapus atribut yang digabungkan</span><span class="sxs-lookup"><span data-stu-id="62529-120">Remove merged attributes</span></span>

<span data-ttu-id="62529-121">Untuk mengecualikan atribut dari entitas profil pelanggan akhir, temukan di tabel **atribut profil**.</span><span class="sxs-lookup"><span data-stu-id="62529-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="62529-122">Pilih tombol elipsis (...).</span><span class="sxs-lookup"><span data-stu-id="62529-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="62529-123">Di daftar drop-down , pilih **Jangan gabungkan**.</span><span class="sxs-lookup"><span data-stu-id="62529-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="62529-124">Atribut dipindahkan ke bagian **dihapus dari rekaman pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="62529-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="62529-125">Tambahkan atribut gabungan secara manual</span><span class="sxs-lookup"><span data-stu-id="62529-125">Manually add a merged attribute</span></span>

<span data-ttu-id="62529-126">Untuk menambahkan atribut gabungan, buka halaman **gabungkan**.</span><span class="sxs-lookup"><span data-stu-id="62529-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="62529-127">Pilih **Tambah atribut gabungan**.</span><span class="sxs-lookup"><span data-stu-id="62529-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="62529-128">Berikan **nama** untuk mengidentifikasinya di halaman **gabungkan** nanti.</span><span class="sxs-lookup"><span data-stu-id="62529-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="62529-129">Atau, berikan **nama tampilan** untuk ditampilkan di entitas profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="62529-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="62529-130">Konfigurasi **Pilih atribut duplikat** untuk memilih atribut yang ingin Anda gabungkan dari entitas yang cocok.</span><span class="sxs-lookup"><span data-stu-id="62529-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="62529-131">Anda juga dapat mencari atribut.</span><span class="sxs-lookup"><span data-stu-id="62529-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="62529-132">Tetapkan **peringkat menurut nilai penting** untuk memprioritaskan satu atribut di atas yang lain.</span><span class="sxs-lookup"><span data-stu-id="62529-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="62529-133">Misalnya, jika entitas *WebAccountCSV* mencakup data yang paling akurat tentang atribut *nama lengkap*, Anda dapat memprioritaskan entitas ini melalui *ContactCSV* dengan memilih *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="62529-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="62529-134">Akibatnya, *WebAccountCSV* bergerak ke prioritas pertama, sementara *ContactCSV* bergerak ke prioritas kedua ketika menarik nilai untuk atribut *nama lengkap*.</span><span class="sxs-lookup"><span data-stu-id="62529-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="62529-135">Jalankan gabungan</span><span class="sxs-lookup"><span data-stu-id="62529-135">Run your merge</span></span>

<span data-ttu-id="62529-136">Apakah Anda menggabungkan atribut secara manual atau membiarkan sistem menggabungkannya, Anda dapat menjalankan gabungan.</span><span class="sxs-lookup"><span data-stu-id="62529-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="62529-137">Pada halaman **Gabungkan**, pilih **Jalankan** untuk memulai proses.</span><span class="sxs-lookup"><span data-stu-id="62529-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="62529-138">![menyimpan dan menjalankan Gabungan data](media/configure-data-merge-save-run.png "menyimpan dan menjalankan Gabungan data")</span><span class="sxs-lookup"><span data-stu-id="62529-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="62529-139">Untuk membuat perubahan tambahan dan menjalankan ulang langkah tersebut, Anda dapat membatalkan penggabungan yang sedang berlangsung.</span><span class="sxs-lookup"><span data-stu-id="62529-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="62529-140">Pilih teks **menyegarkan...** dan pilih **Batalkan pekerjaan**  di panel sisi yang muncul.</span><span class="sxs-lookup"><span data-stu-id="62529-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="62529-141">Setelah teks **Menyegarkan...** berubah menjadi **sukses**, penggabungan telah diselesaikan dan mengatasi kontradiksi dalam data Anda sesuai dengan kebijakan yang ditentukan.</span><span class="sxs-lookup"><span data-stu-id="62529-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="62529-142">Atribut yang digabung dan tidak digabung disertakan dalam entitas profil terpadu.</span><span class="sxs-lookup"><span data-stu-id="62529-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="62529-143">Atribut yang dikeluarkan tidak disertakan dalam entitas profil terpadu.</span><span class="sxs-lookup"><span data-stu-id="62529-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="62529-144">Jika ini bukan pertama kali Anda menjalankan penggabungan dengan berhasil, semua proses hilir, termasuk pengayaan, segmentasi, dan langkah akan berjalan ulang secara otomatis.</span><span class="sxs-lookup"><span data-stu-id="62529-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="62529-145">Setelah semua proses hilir telah jalankan kembali, profil pelanggan mencerminkan perubahan yang Anda buat.</span><span class="sxs-lookup"><span data-stu-id="62529-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="62529-146">Ada [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="62529-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="62529-147">Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="62529-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="62529-148">Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan.</span><span class="sxs-lookup"><span data-stu-id="62529-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="62529-149">Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="62529-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="62529-150">Langkah Berikutnya</span><span class="sxs-lookup"><span data-stu-id="62529-150">Next Step</span></span>

<span data-ttu-id="62529-151">Konfigurasikan [aktivitas](activities.md), [pengayaan](enrichment-microsoft-graph.md), atau [Relasi](relationships.md) untuk mendapatkan wawasan lebih tentang pelanggan anda.</span><span class="sxs-lookup"><span data-stu-id="62529-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="62529-152">Jika anda telah mengonfigurasi aktivitas, pengayaan, atau Relasi, atau jika anda telah menentukan segmen, maka akan diproses secara otomatis untuk menggunakan data pelanggan terkini.</span><span class="sxs-lookup"><span data-stu-id="62529-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>


