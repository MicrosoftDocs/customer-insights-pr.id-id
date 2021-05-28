---
title: Membuat dan mengelola segmen
description: Buat segmen pelanggan untuk mengelompokkan mereka berdasarkan berbagai atribut.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064941"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="833e6-103">Membuat dan mengelola segmen</span><span class="sxs-lookup"><span data-stu-id="833e6-103">Create and manage segments</span></span>

<span data-ttu-id="833e6-104">Tentukan filter kompleks di sekitar entitas pelanggan terpadu dan entitas terkaitnya.</span><span class="sxs-lookup"><span data-stu-id="833e6-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="833e6-105">Setiap segmen, setelah pemrosesan, membuat kumpulan rekaman pelanggan yang dapat Anda ekspor dan lakukan tindakan padanya.</span><span class="sxs-lookup"><span data-stu-id="833e6-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="833e6-106">Segmen dikelola pada halaman **segmen**.</span><span class="sxs-lookup"><span data-stu-id="833e6-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="833e6-107">Contoh berikut menjelaskan kemampuan segmentasi.</span><span class="sxs-lookup"><span data-stu-id="833e6-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="833e6-108">Kami telah mendefinisikan segmen untuk pelanggan yang memesan setidaknya $500 barang di 90 hari terakhir *dan* yang terlibat dalam panggilan layanan pelanggan yang dieskalasi.</span><span class="sxs-lookup"><span data-stu-id="833e6-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Cuplikan layar antarmuka pembuat segmen dengan dua grup yang menentukan segmen pelanggan.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="833e6-110">Buat segmen baru</span><span class="sxs-lookup"><span data-stu-id="833e6-110">Create a new segment</span></span>

<span data-ttu-id="833e6-111">Tersedia beberapa cara untuk membuat segmen baru.</span><span class="sxs-lookup"><span data-stu-id="833e6-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="833e6-112">Bagian ini menjelaskan cara membuat *segmen kosong* dari awal.</span><span class="sxs-lookup"><span data-stu-id="833e6-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="833e6-113">Anda juga dapat membuat *segmen cepat* berdasarkan entitas yang ada atau menggunakan model Pembelajaran Mesin untuk mendapatkan *segmen yang disarankan*.</span><span class="sxs-lookup"><span data-stu-id="833e6-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="833e6-114">Informasi selengkapnya: [Ikhtisar segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="833e6-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="833e6-115">Saat membuat segmen, Anda dapat menyimpan draf.</span><span class="sxs-lookup"><span data-stu-id="833e6-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="833e6-116">Fitur tersebut akan disimpan sebagai segmen dan tidak dapat diaktifkan jika diselesaikan dengan konfigurasi yang valid.</span><span class="sxs-lookup"><span data-stu-id="833e6-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="833e6-117">Buka halaman **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="833e6-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="833e6-118">Pilih **Baru** > **segmen kosong**.</span><span class="sxs-lookup"><span data-stu-id="833e6-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="833e6-119">Di panel **Segmen baru**, pilih jenis segmen:</span><span class="sxs-lookup"><span data-stu-id="833e6-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="833e6-120">**Segmen dinamis** [di-refresh](segments.md#refresh-segments) pada jadwal berulang.</span><span class="sxs-lookup"><span data-stu-id="833e6-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="833e6-121">**Segmen statis** berjalan sekali saat Anda membuatnya.</span><span class="sxs-lookup"><span data-stu-id="833e6-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="833e6-122">Berikan **nama entitas Output** untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="833e6-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="833e6-123">Atau, berikan nama tampilan, dan deskripsi yang membantu mengidentifikasi segmen.</span><span class="sxs-lookup"><span data-stu-id="833e6-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="833e6-124">Pilih **berikutnya** untuk mengakses halaman **pembuat segmen** dengan menentukan grup.</span><span class="sxs-lookup"><span data-stu-id="833e6-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="833e6-125">Grup adalah satu set pelanggan.</span><span class="sxs-lookup"><span data-stu-id="833e6-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="833e6-126">Pilih entitas yang mencakup atribut yang ingin Anda segmentasikan.</span><span class="sxs-lookup"><span data-stu-id="833e6-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="833e6-127">Pilih atribut untuk segmentasi.</span><span class="sxs-lookup"><span data-stu-id="833e6-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="833e6-128">Atribut ini dapat memiliki salah satu dari empat jenis nilai: numerik, string, tanggal, atau Boolean.</span><span class="sxs-lookup"><span data-stu-id="833e6-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="833e6-129">Pilih operator dan nilai untuk atribut dipilih.</span><span class="sxs-lookup"><span data-stu-id="833e6-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="833e6-130">![Filter grup kustom](media/customer-group-numbers.png "Filter grup pelanggan")</span><span class="sxs-lookup"><span data-stu-id="833e6-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="833e6-131">Angka</span><span class="sxs-lookup"><span data-stu-id="833e6-131">Number</span></span> |<span data-ttu-id="833e6-132">Definisi</span><span class="sxs-lookup"><span data-stu-id="833e6-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="833e6-133">1</span><span class="sxs-lookup"><span data-stu-id="833e6-133">1</span></span>     |<span data-ttu-id="833e6-134">Entity</span><span class="sxs-lookup"><span data-stu-id="833e6-134">Entity</span></span>          |
   |<span data-ttu-id="833e6-135">2</span><span class="sxs-lookup"><span data-stu-id="833e6-135">2</span></span>     |<span data-ttu-id="833e6-136">Atribut</span><span class="sxs-lookup"><span data-stu-id="833e6-136">Attribute</span></span>          |
   |<span data-ttu-id="833e6-137">3</span><span class="sxs-lookup"><span data-stu-id="833e6-137">3</span></span>    |<span data-ttu-id="833e6-138">Operator</span><span class="sxs-lookup"><span data-stu-id="833e6-138">Operator</span></span>         |
   |<span data-ttu-id="833e6-139">4</span><span class="sxs-lookup"><span data-stu-id="833e6-139">4</span></span>    |<span data-ttu-id="833e6-140">Nilai</span><span class="sxs-lookup"><span data-stu-id="833e6-140">Value</span></span>         |

   1. <span data-ttu-id="833e6-141">Untuk menambahkan kondisi ke grup, Anda dapat menggunakan dua operator logika:</span><span class="sxs-lookup"><span data-stu-id="833e6-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="833e6-142">Operator **AND**: kedua kondisi harus dipenuhi sebagai bagian dari proses segmentasi.</span><span class="sxs-lookup"><span data-stu-id="833e6-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="833e6-143">Pilihan ini paling berguna saat Anda menentukan kondisi di seluruh entitas yang berbeda.</span><span class="sxs-lookup"><span data-stu-id="833e6-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="833e6-144">Operator **OR**: Salah satu dari kondisi harus dipenuhi sebagai bagian dari proses segmentasi.</span><span class="sxs-lookup"><span data-stu-id="833e6-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="833e6-145">Pilihan ini paling berguna saat Anda menentukan beberapa kondisi untuk entitas yang sama.</span><span class="sxs-lookup"><span data-stu-id="833e6-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="833e6-146">![Operator OR bila kedua kondisi harus dipenuhi](media/segmentation-either-condition.png "Operator OR bila kedua kondisi harus dipenuhi")</span><span class="sxs-lookup"><span data-stu-id="833e6-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="833e6-147">Saat ini mungkin untuk mengurung operator **OR** di bawah operator **AND**, namun tidak sebaliknya.</span><span class="sxs-lookup"><span data-stu-id="833e6-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="833e6-148">Setiap grup cocok dengan rangkaian pelanggan.</span><span class="sxs-lookup"><span data-stu-id="833e6-148">Each group matches set of customers.</span></span> <span data-ttu-id="833e6-149">Anda dapat menggabungkan grup untuk menyertakan pelanggan yang diperlukan untuk kasus bisnis Anda.</span><span class="sxs-lookup"><span data-stu-id="833e6-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="833e6-150">Pilih **Tambah Grup**.</span><span class="sxs-lookup"><span data-stu-id="833e6-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="833e6-151">![Grup pelanggan Tambah grup](media/customer-group-add-group.png "Grup pelanggan Tambah grup")</span><span class="sxs-lookup"><span data-stu-id="833e6-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="833e6-152">Pilih salah satu operator rangkaian: **Gabungan**, **Irisan**, atau **Lepas**.</span><span class="sxs-lookup"><span data-stu-id="833e6-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="833e6-153">![Grup pelanggan Tambah penyatuan](media/customer-group-union.png "Grup pelanggan Tambah penyatuan")</span><span class="sxs-lookup"><span data-stu-id="833e6-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="833e6-154">**Semesta** menyatukan dua kelompok.</span><span class="sxs-lookup"><span data-stu-id="833e6-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="833e6-155">**Berpotongan** tumpang-tindih kedua grup.</span><span class="sxs-lookup"><span data-stu-id="833e6-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="833e6-156">Hanya data yang *umum* untuk kedua grup yang dipertahankan dalam Grup Terpadu.</span><span class="sxs-lookup"><span data-stu-id="833e6-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="833e6-157">**Kecuali** menggabungkan dua grup.</span><span class="sxs-lookup"><span data-stu-id="833e6-157">**Except** combines the two groups.</span></span> <span data-ttu-id="833e6-158">Hanya data dalam grup A yang *tidak umum* untuk data di Grup B yang dipertahankan.</span><span class="sxs-lookup"><span data-stu-id="833e6-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="833e6-159">Jika entitas terhubung ke entitas pelanggan terpadu melalui [Relasi](relationships.md), Anda harus menentukan jalur relasi untuk membuat segmen valid.</span><span class="sxs-lookup"><span data-stu-id="833e6-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="833e6-160">Tambahkan entitas dari jalur relasi hingga Anda dapat memilih entitas **pelanggan: CustomerInsights** dari dropdown.</span><span class="sxs-lookup"><span data-stu-id="833e6-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="833e6-161">Selanjutnya, pilih **Semua rekaman** untuk setiap langkah.</span><span class="sxs-lookup"><span data-stu-id="833e6-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="833e6-162">![Jalur relasi selama pembuatan segmen](media/segments-multiple-relationships.png "Jalur relasi selama pembuatan segmen")</span><span class="sxs-lookup"><span data-stu-id="833e6-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="833e6-163">Secara default, segmen akan menghasilkan entitas output yang berisi semua atribut profil pelanggan yang cocok dengan filter yang ditentukan.</span><span class="sxs-lookup"><span data-stu-id="833e6-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="833e6-164">Jika segmen didasarkan pada entitas lain dari entitas *Pelanggan*, Anda dapat menambahkan lebih banyak atribut dari entitas ini ke entitas output.</span><span class="sxs-lookup"><span data-stu-id="833e6-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="833e6-165">Pilih **atribut Proyek** untuk memilih atribut yang akan ditambahkan ke entitas output.</span><span class="sxs-lookup"><span data-stu-id="833e6-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="833e6-166">Contoh: Segmen didasarkan pada entitas yang berisi data aktivitas pelanggan yang terkait dengan entitas *Pelanggan*.</span><span class="sxs-lookup"><span data-stu-id="833e6-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="833e6-167">Segmen tersebut mencari semua pelanggan yang menelepon pusat bantuan dalam 60 hari terakhir.</span><span class="sxs-lookup"><span data-stu-id="833e6-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="833e6-168">Anda dapat memilih untuk menambahkan durasi panggilan dan jumlah panggilan ke semua rekaman pelanggan yang cocok di entitas output.</span><span class="sxs-lookup"><span data-stu-id="833e6-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="833e6-169">Informasi ini mungkin berguna untuk mengirim email dengan tautan bermanfaat ke artikel bantuan online dan Tanya Jawab kepada pelanggan yang sering menelepon.</span><span class="sxs-lookup"><span data-stu-id="833e6-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="833e6-170">Atribut yang diproyeksikan hanya berfungsi untuk entitas yang memiliki relasi satu ke banyak dengan entitas pelanggan.</span><span class="sxs-lookup"><span data-stu-id="833e6-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="833e6-171">Misalnya, satu pelanggan dapat memiliki beberapa langganan.</span><span class="sxs-lookup"><span data-stu-id="833e6-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="833e6-172">Anda hanya dapat memproyeksikan atribut dari entitas yang digunakan di setiap grup kueri segmen yang Anda bentuk.</span><span class="sxs-lookup"><span data-stu-id="833e6-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="833e6-173">Atribut yang diproyeksikan digunakan saat menggunakan operator yang ditentukan.</span><span class="sxs-lookup"><span data-stu-id="833e6-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="833e6-174">Pilih **Simpan** untuk menyimpan segmen Anda.</span><span class="sxs-lookup"><span data-stu-id="833e6-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="833e6-175">Segmen Anda akan disimpan dan diproses jika semua persyaratan divalidasi.</span><span class="sxs-lookup"><span data-stu-id="833e6-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="833e6-176">Jika tidak, maka akan disimpan sebagai draf.</span><span class="sxs-lookup"><span data-stu-id="833e6-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="833e6-177">Untuk kembali ke halaman **Segmen**, pilih **kembali ke segmen**.</span><span class="sxs-lookup"><span data-stu-id="833e6-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="833e6-178">Segmen ringkas</span><span class="sxs-lookup"><span data-stu-id="833e6-178">Quick segments</span></span>

<span data-ttu-id="833e6-179">Segmen singkat memungkinkan Anda membuat segmen sederhana dengan satu operator secara cepat untuk wawasan yang lebih cepat.</span><span class="sxs-lookup"><span data-stu-id="833e6-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="833e6-180">Pada halaman **Segmen**, pilih **Baru** > **Buat dari**.</span><span class="sxs-lookup"><span data-stu-id="833e6-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="833e6-181">Pilih pilihan **profil** untuk membuat segmen yang didasarkan pada entitas *pelanggan terpadu*.</span><span class="sxs-lookup"><span data-stu-id="833e6-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="833e6-182">Pilih pilihan **Ukuran** untuk membuat segmen di sekitar ukuran yang telah Anda buat sebelumnya.</span><span class="sxs-lookup"><span data-stu-id="833e6-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="833e6-183">Pilih **pilihan intelijen** untuk membuat segmen di sekitar salah satu entitas output yang dihasilkan menggunakan **prediksi** maupun kemampuan **model kustom**.</span><span class="sxs-lookup"><span data-stu-id="833e6-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="833e6-184">Di kotak dialog **segmen ringkas baru**, pilih atribut dari dropdown **bidang**.</span><span class="sxs-lookup"><span data-stu-id="833e6-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="833e6-185">Sistem akan memberikan beberapa wawasan tambahan yang membantu Anda membuat segmen pelanggan yang lebih baik.</span><span class="sxs-lookup"><span data-stu-id="833e6-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="833e6-186">Untuk bidang kategoris, kami akan menampilkan 10 hitungan pelanggan teratas.</span><span class="sxs-lookup"><span data-stu-id="833e6-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="833e6-187">Pilih **nilai** dan pilih **tinjau**.</span><span class="sxs-lookup"><span data-stu-id="833e6-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="833e6-188">Untuk atribut numerik, sistem akan menampilkan nilai atribut yang berada di dalam persentil masing-masing pelanggan.</span><span class="sxs-lookup"><span data-stu-id="833e6-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="833e6-189">Pilih **operator** dan **nilai**, lalu pilih **tinjau**.</span><span class="sxs-lookup"><span data-stu-id="833e6-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="833e6-190">Sistem akan memberi Anda **perkiraan ukuran segmen**.</span><span class="sxs-lookup"><span data-stu-id="833e6-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="833e6-191">Anda dapat memilih apakah akan menghasilkan segmen yang telah Anda tetapkan, atau pertama-tama, mengunjungi kembali untuk mendapatkan ukuran segmen yang berbeda.</span><span class="sxs-lookup"><span data-stu-id="833e6-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="833e6-192">![Nama dan estimasi untuk segmen cepat](media/quick-segment-name.png "Nama dan estimasi untuk segmen cepat")</span><span class="sxs-lookup"><span data-stu-id="833e6-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="833e6-193">Beri **nama** segmen Anda.</span><span class="sxs-lookup"><span data-stu-id="833e6-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="833e6-194">Atau, berikan **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="833e6-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="833e6-195">Klik **Simpan** untuk membuat segmen Anda.</span><span class="sxs-lookup"><span data-stu-id="833e6-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="833e6-196">Setelah segmen selesai diproses, Anda dapat melihatnya seperti segmen lain yang Anda buat.</span><span class="sxs-lookup"><span data-stu-id="833e6-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="833e6-197">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="833e6-197">Next steps</span></span>

<span data-ttu-id="833e6-198">[Ekspor segmen](export-destinations.md) dan jelajahi bagian [kartu pelanggan](customer-card-add-in.md) dan [konektor](export-power-bi.md) untuk mendapatkan wawasan tentang tingkat pelanggan.</span><span class="sxs-lookup"><span data-stu-id="833e6-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
