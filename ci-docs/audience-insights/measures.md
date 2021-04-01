---
title: Membuat dan mengelola ukuran
description: Menentukan ukuran untuk menganalisis dan mencerminkan kinerja bisnis Anda.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654736"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="fc68b-103">Menentukan dan mengelola ukuran</span><span class="sxs-lookup"><span data-stu-id="fc68b-103">Define and manage measures</span></span>

<span data-ttu-id="fc68b-104">Ukuran membantu Anda memahami lebih baik perilaku pelanggan dan kinerja bisnis dengan mengambil nilai yang relevan dari [profil terpadu](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="fc68b-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="fc68b-105">Misalnya, bisnis ingin melihat *total pengeluaran per pelanggan* untuk memahami riwayat pembelian pelanggan individual.</span><span class="sxs-lookup"><span data-stu-id="fc68b-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="fc68b-106">Atau ukur *total penjualan perusahaan* untuk memahami pendapatan tingkat agregat dalam seluruh bisnis.</span><span class="sxs-lookup"><span data-stu-id="fc68b-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="fc68b-107">Ukuran dibuat menggunakan pembuat ukuran, platform kueri data dengan berbagai operator, dan pilihan pemetaan sederhana.</span><span class="sxs-lookup"><span data-stu-id="fc68b-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="fc68b-108">Alat ini memungkinkan Anda memfilter data, mengelompokkan hasil, mendeteksi [jalur relasi entitas](relationships.md), dan mempratinjau output.</span><span class="sxs-lookup"><span data-stu-id="fc68b-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="fc68b-109">Gunakan pembuat ukuran untuk merencanakan aktivitas bisnis dengan mengkueri data pelanggan dan mengekstrak wawasan.</span><span class="sxs-lookup"><span data-stu-id="fc68b-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="fc68b-110">Contohnya, membuat ukuran *total pengeluaran per pelanggan* dan *penghasilan total per pelanggan* membantu mengidentifikasi grup pelanggan dengan pengeluaran tinggi namun penghasilan yang tinggi.</span><span class="sxs-lookup"><span data-stu-id="fc68b-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="fc68b-111">Anda dapat [membuat segmen](segments.md) untuk mendorong tindakan terbaik berikutnya.</span><span class="sxs-lookup"><span data-stu-id="fc68b-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="fc68b-112">Membuat ukuran</span><span class="sxs-lookup"><span data-stu-id="fc68b-112">Create a measure</span></span>

<span data-ttu-id="fc68b-113">Bagian ini akan memandu Anda membuat pengukuran baru dari awal.</span><span class="sxs-lookup"><span data-stu-id="fc68b-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="fc68b-114">Anda dapat membuat pengukuran dengan atribut data dari entitas data yang telah diatur relasinya untuk terhubung dengan entitas Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="fc68b-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="fc68b-115">Di wawasan audiens, buka **Ukuran**.</span><span class="sxs-lookup"><span data-stu-id="fc68b-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="fc68b-116">Pilih **baru**.</span><span class="sxs-lookup"><span data-stu-id="fc68b-116">Select **New**.</span></span>

1. <span data-ttu-id="fc68b-117">Pilih **Edit nama** dan berikan **Nama** untuk ukurannya.</span><span class="sxs-lookup"><span data-stu-id="fc68b-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="fc68b-118">Jika konfigurasi pengukuran baru Anda hanya memiliki dua bidang, misalnya CustomerID dan satu perhitungan, output akan ditambahkan sebagai kolom baru ke entitas yang dihasilkan sistem yang disebut Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="fc68b-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="fc68b-119">Anda akan dapat melihat nilai pengukuran di profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="fc68b-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="fc68b-120">Ukuran lain akan menghasilkan entitas mereka sendiri.</span><span class="sxs-lookup"><span data-stu-id="fc68b-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="fc68b-121">Di area konfigurasi, pilih fungsi agresi dari menu drop-down **Pilih Fungsi**.</span><span class="sxs-lookup"><span data-stu-id="fc68b-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="fc68b-122">Fungsi agresi mencakup:</span><span class="sxs-lookup"><span data-stu-id="fc68b-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="fc68b-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="fc68b-123">**Sum**</span></span>
   - <span data-ttu-id="fc68b-124">**Rata-rata**</span><span class="sxs-lookup"><span data-stu-id="fc68b-124">**Average**</span></span>
   - <span data-ttu-id="fc68b-125">**Count**</span><span class="sxs-lookup"><span data-stu-id="fc68b-125">**Count**</span></span>
   - <span data-ttu-id="fc68b-126">**Jumlah Unik**</span><span class="sxs-lookup"><span data-stu-id="fc68b-126">**Count Unique**</span></span>
   - <span data-ttu-id="fc68b-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="fc68b-127">**Max**</span></span>
   - <span data-ttu-id="fc68b-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="fc68b-128">**Min**</span></span>
   - <span data-ttu-id="fc68b-129">**Pertama**: mengambil nilai pertama rekaman data</span><span class="sxs-lookup"><span data-stu-id="fc68b-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="fc68b-130">**Terakhir**: mengambil nilai terakhir yang ditambahkan ke rekaman data</span><span class="sxs-lookup"><span data-stu-id="fc68b-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operator untuk menghitung pengukuran.":::

1. <span data-ttu-id="fc68b-132">Pilih **Tambah atribut** untuk memilih data yang diperlukan untuk membuat pengukuran ini.</span><span class="sxs-lookup"><span data-stu-id="fc68b-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="fc68b-133">Pilih tab **atribut**.</span><span class="sxs-lookup"><span data-stu-id="fc68b-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="fc68b-134">Entitas data: Pilih entitas yang mencakup atribut yang ingin Anda ukur.</span><span class="sxs-lookup"><span data-stu-id="fc68b-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="fc68b-135">Atribut data: Pilih atribut yang ingin Anda gunakan di fungsi agresi untuk menghitung ukuran.</span><span class="sxs-lookup"><span data-stu-id="fc68b-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="fc68b-136">Anda hanya dapat memilih satu atribut setiap kali.</span><span class="sxs-lookup"><span data-stu-id="fc68b-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="fc68b-137">Anda juga dapat memilih atribut data dari ukuran yang ada dengan memilih tab **Ukuran**. Atau, Anda dapat mencari entitas atau nama ukuran.</span><span class="sxs-lookup"><span data-stu-id="fc68b-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="fc68b-138">Pilih **Tambah** untuk menambahkan atribut yang dipilih ke ukuran.</span><span class="sxs-lookup"><span data-stu-id="fc68b-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Pilih atribut untuk digunakan dalam penghitungan.":::

1. <span data-ttu-id="fc68b-140">Untuk membuat ukuran yang lebih kompleks, Anda dapat menambahkan lebih banyak atribut atau menggunakan operator hitung pada fungsi pengukuran Anda.</span><span class="sxs-lookup"><span data-stu-id="fc68b-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Buat pengukuran yang kompleks dengan operator hitung.":::

1. <span data-ttu-id="fc68b-142">Untuk menambahkan filter, pilih **Filter** pada area konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="fc68b-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="fc68b-143">Di bagian **Tambah atribut** pada panel **Filter**, pilih atribut yang akan digunakan untuk membuat filter.</span><span class="sxs-lookup"><span data-stu-id="fc68b-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="fc68b-144">Atur operator filter untuk menentukan filter untuk setiap atribut yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="fc68b-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="fc68b-145">Pilih **Terapkan** untuk menambahkan filter ke ukuran.</span><span class="sxs-lookup"><span data-stu-id="fc68b-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="fc68b-146">Untuk menambahkan dimensi, pilih **Dimensi** pada area konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="fc68b-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="fc68b-147">Dimensi akan ditampilkan sebagai kolom dalam entitas output pengukuran.</span><span class="sxs-lookup"><span data-stu-id="fc68b-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="fc68b-148">Pilih **Edit dimensi** untuk menambahkan atribut data untuk mengelompokkan nilai ukuran.</span><span class="sxs-lookup"><span data-stu-id="fc68b-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="fc68b-149">Misalnya, kota atau jenis kelamin.</span><span class="sxs-lookup"><span data-stu-id="fc68b-149">For example, city or gender.</span></span> <span data-ttu-id="fc68b-150">Secara default, dimensi *CustomerID* dipilih untuk membuat *ukuran tingkat pelanggan*.</span><span class="sxs-lookup"><span data-stu-id="fc68b-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="fc68b-151">Anda dapat menghilangkan dimensi default jika ingin membuat *ukuran tingkat bisnis*.</span><span class="sxs-lookup"><span data-stu-id="fc68b-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="fc68b-152">Pilih **Selesai** untuk menambahkan dimensi ke ukuran.</span><span class="sxs-lookup"><span data-stu-id="fc68b-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="fc68b-153">Jika ada beberapa jalur antara entitas data yang Anda petakan dan entitas *Pelanggan*, Anda harus memilih salah satu jalur relasi [entitas yang diidentifikasi](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="fc68b-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="fc68b-154">Hasil ukuran dapat bervariasi, tergantung pada jalur yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="fc68b-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="fc68b-155">Pilih **preferensi Data** dan pilih jalur entitas yang harus digunakan untuk mengidentifikasi ukuran Anda.</span><span class="sxs-lookup"><span data-stu-id="fc68b-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="fc68b-156">Jika hanya ada satu jalur ke entitas *Pelanggan*, kontrol ini tidak akan ditampilkan.</span><span class="sxs-lookup"><span data-stu-id="fc68b-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="fc68b-157">Pilih **Selesai** untuk menerapkan pilihan Anda.</span><span class="sxs-lookup"><span data-stu-id="fc68b-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Pilih jalur entitas untuk ukuran.":::

1. <span data-ttu-id="fc68b-159">Untuk menambahkan perhitungan lainnya untuk pengukuran, pilih **Penghitungan baru**.</span><span class="sxs-lookup"><span data-stu-id="fc68b-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="fc68b-160">Anda hanya dapat menggunakan entitas pada jalur entitas yang sama untuk perhitungan baru.</span><span class="sxs-lookup"><span data-stu-id="fc68b-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="fc68b-161">Perhitungan lainnya akan ditampilkan sebagai kolom baru dalam entitas output pengukuran.</span><span class="sxs-lookup"><span data-stu-id="fc68b-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="fc68b-162">Pilih **...** pada penghitungan untuk **membuat duplikat**, **Mengganti Nama**, atau **Menghapus perhitungan** dari pengukuran.</span><span class="sxs-lookup"><span data-stu-id="fc68b-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="fc68b-163">Di area **Pratinjau**, Anda akan melihat skema data dari entitas output pengukuran, termasuk filter dan dimensi.</span><span class="sxs-lookup"><span data-stu-id="fc68b-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="fc68b-164">Pratinjau merespons secara dinamis terhadap perubahan dalam konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="fc68b-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="fc68b-165">Pilih **Jalankan** untuk menghitung hasil pengukuran yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="fc68b-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="fc68b-166">Pilih **Simpan dan tutup** jika Anda ingin menyimpan konfigurasi saat ini dan menjalankan pengukuran nanti.</span><span class="sxs-lookup"><span data-stu-id="fc68b-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="fc68b-167">Buka **Ukuran** untuk melihat ukuran yang baru dibuat dalam daftar.</span><span class="sxs-lookup"><span data-stu-id="fc68b-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="fc68b-168">Kelola ukuran Anda</span><span class="sxs-lookup"><span data-stu-id="fc68b-168">Manage your measures</span></span>

<span data-ttu-id="fc68b-169">Setelah [membuat pengukuran](#create-a-measure), Anda akan melihat daftar ukuran pada halaman **Ukuran**.</span><span class="sxs-lookup"><span data-stu-id="fc68b-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="fc68b-170">Anda akan menemukan informasi tentang jenis pengukuran, pembuat, tanggal pembuatan, status, dan status.</span><span class="sxs-lookup"><span data-stu-id="fc68b-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="fc68b-171">Bila Anda memilih ukuran dari daftar, Anda dapat mempratinjau output dan mengunduh file .CSV.</span><span class="sxs-lookup"><span data-stu-id="fc68b-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="fc68b-172">Untuk me-refresh semua ukuran Anda pada waktu yang sama, pilih **Segarkan semua** tanpa memilih ukuran tertentu.</span><span class="sxs-lookup"><span data-stu-id="fc68b-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fc68b-173">![Tindakan untuk mengelola ukuran tunggal](media/measure-actions.png "Tindakan untuk mengelola langkah tunggal")</span><span class="sxs-lookup"><span data-stu-id="fc68b-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="fc68b-174">Pilih ukuran dari daftar untuk pilihan berikut:</span><span class="sxs-lookup"><span data-stu-id="fc68b-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="fc68b-175">Pilih nama ukuran untuk melihat rinciannya.</span><span class="sxs-lookup"><span data-stu-id="fc68b-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="fc68b-176">**Edit** konfigurasi ukuran.</span><span class="sxs-lookup"><span data-stu-id="fc68b-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="fc68b-177">**segarkan** pengukuran berdasarkan data terbaru.</span><span class="sxs-lookup"><span data-stu-id="fc68b-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="fc68b-178">**Ubah nama** ukuran.</span><span class="sxs-lookup"><span data-stu-id="fc68b-178">**Rename** the measure.</span></span>
- <span data-ttu-id="fc68b-179">**Hapus** ukuran.</span><span class="sxs-lookup"><span data-stu-id="fc68b-179">**Delete** the measure.</span></span>
- <span data-ttu-id="fc68b-180">**Aktifkan** atau **Nonaktifkan**.</span><span class="sxs-lookup"><span data-stu-id="fc68b-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="fc68b-181">Ukuran yang tidak aktif tidak akan di-refresh selama [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fc68b-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="fc68b-182">Ada [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="fc68b-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="fc68b-183">Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="fc68b-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="fc68b-184">Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan.</span><span class="sxs-lookup"><span data-stu-id="fc68b-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="fc68b-185">Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="fc68b-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="fc68b-186">Langkah selanjutnya</span><span class="sxs-lookup"><span data-stu-id="fc68b-186">Next step</span></span>

<span data-ttu-id="fc68b-187">Anda dapat menggunakan ukuran yang ada untuk membuat [segmen pelanggan](segments.md).</span><span class="sxs-lookup"><span data-stu-id="fc68b-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]