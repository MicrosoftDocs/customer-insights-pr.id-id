---
title: Membuat dan mengelola ukuran
description: Menentukan ukuran untuk menganalisis dan mencerminkan kinerja bisnis Anda.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049254"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="ac971-103">Menentukan dan mengelola ukuran</span><span class="sxs-lookup"><span data-stu-id="ac971-103">Define and manage measures</span></span>

<span data-ttu-id="ac971-104">Ukuran membantu Anda untuk lebih memahami perilaku pelanggan dan kinerja bisnis.</span><span class="sxs-lookup"><span data-stu-id="ac971-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="ac971-105">Mereka melihat nilai-nilai yang relevan dari [profil terpadu](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="ac971-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="ac971-106">Misalnya, bisnis ingin melihat *total pengeluaran per pelanggan* untuk memahami riwayat pembelian pelanggan individual atau mengukur *total penjualan perusahaan* untuk memahami pendapatan tingkat agregat dalam seluruh bisnis.</span><span class="sxs-lookup"><span data-stu-id="ac971-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="ac971-107">Ukuran dibuat menggunakan pembuat ukuran, platform kueri data dengan berbagai operator, dan pilihan pemetaan sederhana.</span><span class="sxs-lookup"><span data-stu-id="ac971-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="ac971-108">Alat ini memungkinkan Anda memfilter data, mengelompokkan hasil, mendeteksi [jalur relasi entitas](relationships.md), dan mempratinjau output.</span><span class="sxs-lookup"><span data-stu-id="ac971-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="ac971-109">Gunakan pembuat ukuran untuk merencanakan aktivitas bisnis dengan mengkueri data pelanggan dan mengekstrak wawasan.</span><span class="sxs-lookup"><span data-stu-id="ac971-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="ac971-110">Contohnya, membuat ukuran *total pengeluaran per pelanggan* dan *penghasilan total per pelanggan* membantu mengidentifikasi grup pelanggan dengan pengeluaran tinggi namun penghasilan yang tinggi.</span><span class="sxs-lookup"><span data-stu-id="ac971-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="ac971-111">Anda dapat [membuat segmen](segments.md) untuk mendorong tindakan terbaik berikutnya.</span><span class="sxs-lookup"><span data-stu-id="ac971-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="ac971-112">Buat ukuran sendiri dari awal</span><span class="sxs-lookup"><span data-stu-id="ac971-112">Build your own measure from scratch</span></span>

<span data-ttu-id="ac971-113">Bagian ini akan memandu Anda membuat pengukuran baru dari awal.</span><span class="sxs-lookup"><span data-stu-id="ac971-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="ac971-114">Anda dapat membuat pengukuran dengan atribut data dari entitas data yang telah diatur relasinya untuk terhubung dengan entitas Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="ac971-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="ac971-115">Di wawasan audiens, buka **Ukuran**.</span><span class="sxs-lookup"><span data-stu-id="ac971-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="ac971-116">Pilih **Baru** dan pilih **Bangun milik Anda sendiri**.</span><span class="sxs-lookup"><span data-stu-id="ac971-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="ac971-117">Pilih **Edit nama** dan berikan **Nama** untuk ukurannya.</span><span class="sxs-lookup"><span data-stu-id="ac971-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="ac971-118">Jika konfigurasi pengukuran baru Anda hanya memiliki dua bidang, misalnya CustomerID dan satu perhitungan, output akan ditambahkan sebagai kolom baru ke entitas yang dihasilkan sistem yang disebut Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="ac971-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="ac971-119">Anda akan dapat melihat nilai pengukuran di profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="ac971-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="ac971-120">Ukuran lain akan menghasilkan entitas mereka sendiri.</span><span class="sxs-lookup"><span data-stu-id="ac971-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="ac971-121">Di area konfigurasi, pilih fungsi agresi dari menu drop-down **Pilih Fungsi**.</span><span class="sxs-lookup"><span data-stu-id="ac971-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="ac971-122">Fungsi agresi mencakup:</span><span class="sxs-lookup"><span data-stu-id="ac971-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="ac971-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="ac971-123">**Sum**</span></span>
   - <span data-ttu-id="ac971-124">**Rata-rata**</span><span class="sxs-lookup"><span data-stu-id="ac971-124">**Average**</span></span>
   - <span data-ttu-id="ac971-125">**Count**</span><span class="sxs-lookup"><span data-stu-id="ac971-125">**Count**</span></span>
   - <span data-ttu-id="ac971-126">**Jumlah Unik**</span><span class="sxs-lookup"><span data-stu-id="ac971-126">**Count Unique**</span></span>
   - <span data-ttu-id="ac971-127">**Max**</span><span class="sxs-lookup"><span data-stu-id="ac971-127">**Max**</span></span>
   - <span data-ttu-id="ac971-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="ac971-128">**Min**</span></span>
   - <span data-ttu-id="ac971-129">**Pertama**: mengambil nilai pertama rekaman data</span><span class="sxs-lookup"><span data-stu-id="ac971-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="ac971-130">**Terakhir**: mengambil nilai terakhir yang ditambahkan ke rekaman data</span><span class="sxs-lookup"><span data-stu-id="ac971-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operator untuk menghitung pengukuran.":::

1. <span data-ttu-id="ac971-132">Pilih **Tambah atribut** untuk memilih data yang diperlukan untuk membuat pengukuran ini.</span><span class="sxs-lookup"><span data-stu-id="ac971-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="ac971-133">Pilih tab **atribut**.</span><span class="sxs-lookup"><span data-stu-id="ac971-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="ac971-134">Entitas data: Pilih entitas yang mencakup atribut yang ingin Anda ukur.</span><span class="sxs-lookup"><span data-stu-id="ac971-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="ac971-135">Atribut data: Pilih atribut yang ingin Anda gunakan di fungsi agresi untuk menghitung ukuran.</span><span class="sxs-lookup"><span data-stu-id="ac971-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="ac971-136">Anda hanya dapat memilih satu atribut setiap kali.</span><span class="sxs-lookup"><span data-stu-id="ac971-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="ac971-137">Anda juga dapat memilih atribut data dari ukuran yang ada dengan memilih tab **Ukuran**. Atau, Anda dapat mencari entitas atau nama ukuran.</span><span class="sxs-lookup"><span data-stu-id="ac971-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="ac971-138">Pilih **Tambah** untuk menambahkan atribut yang dipilih ke ukuran.</span><span class="sxs-lookup"><span data-stu-id="ac971-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Pilih atribut untuk digunakan dalam penghitungan.":::

1. <span data-ttu-id="ac971-140">Untuk membuat ukuran yang lebih kompleks, Anda dapat menambahkan lebih banyak atribut atau menggunakan operator hitung pada fungsi pengukuran Anda.</span><span class="sxs-lookup"><span data-stu-id="ac971-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Buat pengukuran yang kompleks dengan operator hitung.":::

1. <span data-ttu-id="ac971-142">Untuk menambahkan filter, pilih **Filter** pada area konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="ac971-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="ac971-143">Di bagian **Tambah atribut** pada panel **Filter**, pilih atribut yang akan digunakan untuk membuat filter.</span><span class="sxs-lookup"><span data-stu-id="ac971-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="ac971-144">Atur operator filter untuk menentukan filter untuk setiap atribut yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="ac971-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="ac971-145">Pilih **Terapkan** untuk menambahkan filter ke ukuran.</span><span class="sxs-lookup"><span data-stu-id="ac971-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="ac971-146">Untuk menambahkan dimensi, pilih **Dimensi** pada area konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="ac971-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="ac971-147">Dimensi akan ditampilkan sebagai kolom dalam entitas output pengukuran.</span><span class="sxs-lookup"><span data-stu-id="ac971-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="ac971-148">Pilih **Edit dimensi** untuk menambahkan atribut data untuk mengelompokkan nilai ukuran.</span><span class="sxs-lookup"><span data-stu-id="ac971-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="ac971-149">Misalnya, kota atau jenis kelamin.</span><span class="sxs-lookup"><span data-stu-id="ac971-149">For example, city or gender.</span></span> <span data-ttu-id="ac971-150">Secara default, dimensi *CustomerID* dipilih untuk membuat *ukuran tingkat pelanggan*.</span><span class="sxs-lookup"><span data-stu-id="ac971-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="ac971-151">Anda dapat menghilangkan dimensi default jika ingin membuat *ukuran tingkat bisnis*.</span><span class="sxs-lookup"><span data-stu-id="ac971-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="ac971-152">Pilih **Selesai** untuk menambahkan dimensi ke ukuran.</span><span class="sxs-lookup"><span data-stu-id="ac971-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="ac971-153">Jika ada nilai dalam data Anda yang perlu Anda ganti dengan bilangan bulat, misalnya, ganti *null* dengan *0*, pilih **Aturan**.</span><span class="sxs-lookup"><span data-stu-id="ac971-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="ac971-154">Konfigurasikan aturan dan pastikan Anda hanya memilih bilangan cacah sebagai pengganti.</span><span class="sxs-lookup"><span data-stu-id="ac971-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="ac971-155">Jika ada beberapa jalur antara entitas data yang Anda petakan dan entitas *Pelanggan*, Anda harus memilih salah satu jalur relasi [entitas yang diidentifikasi](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="ac971-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="ac971-156">Hasil ukuran dapat bervariasi, tergantung pada jalur yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="ac971-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="ac971-157">Pilih **preferensi Data** dan pilih jalur entitas yang harus digunakan untuk mengidentifikasi ukuran Anda.</span><span class="sxs-lookup"><span data-stu-id="ac971-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="ac971-158">Jika hanya ada satu jalur ke entitas *Pelanggan*, kontrol ini tidak akan ditampilkan.</span><span class="sxs-lookup"><span data-stu-id="ac971-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="ac971-159">Pilih **Selesai** untuk menerapkan pilihan Anda.</span><span class="sxs-lookup"><span data-stu-id="ac971-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Pilih jalur entitas untuk ukuran.":::

1. <span data-ttu-id="ac971-161">Untuk menambahkan perhitungan lainnya untuk pengukuran, pilih **Penghitungan baru**.</span><span class="sxs-lookup"><span data-stu-id="ac971-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="ac971-162">Anda hanya dapat menggunakan entitas pada jalur entitas yang sama untuk perhitungan baru.</span><span class="sxs-lookup"><span data-stu-id="ac971-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="ac971-163">Perhitungan lainnya akan ditampilkan sebagai kolom baru dalam entitas output pengukuran.</span><span class="sxs-lookup"><span data-stu-id="ac971-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="ac971-164">Pilih **...** pada penghitungan untuk **membuat duplikat**, **Mengganti Nama**, atau **Menghapus perhitungan** dari pengukuran.</span><span class="sxs-lookup"><span data-stu-id="ac971-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="ac971-165">Di area **Pratinjau**, Anda akan melihat skema data dari entitas output pengukuran, termasuk filter dan dimensi.</span><span class="sxs-lookup"><span data-stu-id="ac971-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="ac971-166">Pratinjau merespons secara dinamis terhadap perubahan dalam konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="ac971-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="ac971-167">Pilih **Jalankan** untuk menghitung hasil pengukuran yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="ac971-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="ac971-168">Pilih **Simpan dan tutup** jika Anda ingin menyimpan konfigurasi saat ini dan menjalankan pengukuran nanti.</span><span class="sxs-lookup"><span data-stu-id="ac971-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="ac971-169">Buka **Ukuran** untuk melihat ukuran yang baru dibuat dalam daftar.</span><span class="sxs-lookup"><span data-stu-id="ac971-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="ac971-170">Gunakan templat untuk menyusun pengukuran</span><span class="sxs-lookup"><span data-stu-id="ac971-170">Use a template to build a measure</span></span>

<span data-ttu-id="ac971-171">Anda dapat menggunakan templat yang sudah ditentukan sebelumnya dari langkah-langkah yang umum digunakan untuk membuatnya.</span><span class="sxs-lookup"><span data-stu-id="ac971-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="ac971-172">Deskripsi terperinci tentang templat dan pengalaman terpandu membantu Anda mengukur pembuatan yang efisien.</span><span class="sxs-lookup"><span data-stu-id="ac971-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="ac971-173">Templat dibuat berdasarkan data yang dipetakan dari entitas *Aktivitas Terpadu*.</span><span class="sxs-lookup"><span data-stu-id="ac971-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="ac971-174">Jadi pastikan Anda telah mengonfigurasi [aktivitas pelanggan](activities.md) sebelum membuat ukuran dari templat.</span><span class="sxs-lookup"><span data-stu-id="ac971-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="ac971-175">Template ukuran yang tersedia:</span><span class="sxs-lookup"><span data-stu-id="ac971-175">Available measure templates:</span></span> 
- <span data-ttu-id="ac971-176">Nilai transaksi rata-rata (ATV)</span><span class="sxs-lookup"><span data-stu-id="ac971-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="ac971-177">Nilai transaksi total</span><span class="sxs-lookup"><span data-stu-id="ac971-177">Total transaction value</span></span>
- <span data-ttu-id="ac971-178">Pendapatan rata-rata harian</span><span class="sxs-lookup"><span data-stu-id="ac971-178">Average daily revenue</span></span>
- <span data-ttu-id="ac971-179">Pendapatan rata-rata tahunan</span><span class="sxs-lookup"><span data-stu-id="ac971-179">Average yearly revenue</span></span>
- <span data-ttu-id="ac971-180">Jumlah transaksi</span><span class="sxs-lookup"><span data-stu-id="ac971-180">Transaction count</span></span>
- <span data-ttu-id="ac971-181">Poin loyalitas yang diperoleh</span><span class="sxs-lookup"><span data-stu-id="ac971-181">Loyalty points earned</span></span>
- <span data-ttu-id="ac971-182">Poin loyalitas yang ditukarkan</span><span class="sxs-lookup"><span data-stu-id="ac971-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="ac971-183">Saldo poin loyalitas</span><span class="sxs-lookup"><span data-stu-id="ac971-183">Loyalty points balance</span></span>
- <span data-ttu-id="ac971-184">Rentang periode aktif pelanggan aktif</span><span class="sxs-lookup"><span data-stu-id="ac971-184">Active customer lifespan</span></span>
- <span data-ttu-id="ac971-185">Durasi keanggotaan loyalitas</span><span class="sxs-lookup"><span data-stu-id="ac971-185">Loyalty membership duration</span></span>
- <span data-ttu-id="ac971-186">Waktu sejak pembelian terakhir</span><span class="sxs-lookup"><span data-stu-id="ac971-186">Time since last purchase</span></span>

<span data-ttu-id="ac971-187">Prosedur berikut ini menguraikan langkah-langkah untuk menyusun ukuran baru menggunakan templat.</span><span class="sxs-lookup"><span data-stu-id="ac971-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="ac971-188">Di wawasan audiens, buka **Ukuran**.</span><span class="sxs-lookup"><span data-stu-id="ac971-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="ac971-189">Pilih **Baru** dan pilih **pilih template**.</span><span class="sxs-lookup"><span data-stu-id="ac971-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Cuplikan layar menu tarik-turun saat membuat pengukuran baru dengan sorotan pada templat.":::

1. <span data-ttu-id="ac971-191">Temukan templat yang sesuai dengan kebutuhan Anda dan pilih **Pilih templat**.</span><span class="sxs-lookup"><span data-stu-id="ac971-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="ac971-192">Tinjau data yang diperlukan dan pilih **Mulai** jika Anda memiliki semua data yang ada.</span><span class="sxs-lookup"><span data-stu-id="ac971-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="ac971-193">Di panel **Edit nama**, atur nama untuk ukuran Anda dan entitas output.</span><span class="sxs-lookup"><span data-stu-id="ac971-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="ac971-194">Pilih **Selesai**.</span><span class="sxs-lookup"><span data-stu-id="ac971-194">Select **Done**.</span></span>

1. <span data-ttu-id="ac971-195">Di bagian **Atur periode waktu**, tentukan jangka waktu data yang akan digunakan.</span><span class="sxs-lookup"><span data-stu-id="ac971-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="ac971-196">Pilih jika Anda ingin pengukuran baru untuk mencakup seluruh himpunan data dengan memilih **Sepanjang waktu**.</span><span class="sxs-lookup"><span data-stu-id="ac971-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="ac971-197">Atau jika Anda ingin mengukur untuk fokus pada **periode waktu tertentu**.</span><span class="sxs-lookup"><span data-stu-id="ac971-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Cuplikan layar memperlihatkan bagian periode waktu saat mengonfigurasi ukuran dari templat.":::

1. <span data-ttu-id="ac971-199">Di bagian berikutnya, pilih **Tambahkan data** untuk memilih aktivitas dan memetakan data terkait dari entitas *Aktivitas Terpadu* Anda.</span><span class="sxs-lookup"><span data-stu-id="ac971-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="ac971-200">Langkah 1 dari 2: Di bawah **Tipe aktivitas**, pilih tipe entitas yang ingin Anda gunakan.</span><span class="sxs-lookup"><span data-stu-id="ac971-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="ac971-201">Untuk **Aktivitas**, pilih entitas yang ingin Anda petakan.</span><span class="sxs-lookup"><span data-stu-id="ac971-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="ac971-202">Langkah 2 dari 2: Pilih atribut dari entitas *Aktivitas Terpadu* untuk komponen yang diperlukan oleh rumus.</span><span class="sxs-lookup"><span data-stu-id="ac971-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="ac971-203">Misalnya, untuk nilai transaksi rata-rata, itu adalah atribut yang mewakili nilai Transaksi.</span><span class="sxs-lookup"><span data-stu-id="ac971-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="ac971-204">Untuk **Cap waktu Aktivitas**, pilih atribut dari entitas Aktivitas Terpadu yang menunjukkan tanggal dan waktu aktivitas.</span><span class="sxs-lookup"><span data-stu-id="ac971-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="ac971-205">Setelah pemetaan data berhasil, Anda dapat melihat status sebagai **Selesai** dan nama aktivitas dan atribut yang dipetakan.</span><span class="sxs-lookup"><span data-stu-id="ac971-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Cuplikan layar konfigurasi templat ukuran yang selesai.":::

1. <span data-ttu-id="ac971-207">Sekarang Anda dapat memilih **Jalankan** untuk menghitung hasil pengukuran.</span><span class="sxs-lookup"><span data-stu-id="ac971-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="ac971-208">Untuk memperbaikinya nanti, pilih **Simpan draf**.</span><span class="sxs-lookup"><span data-stu-id="ac971-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="ac971-209">Kelola ukuran Anda</span><span class="sxs-lookup"><span data-stu-id="ac971-209">Manage your measures</span></span>

<span data-ttu-id="ac971-210">Anda dapat menemukan daftar ukuran di halaman **Ukuran**.</span><span class="sxs-lookup"><span data-stu-id="ac971-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="ac971-211">Anda akan menemukan informasi tentang jenis pengukuran, pembuat, tanggal pembuatan, status, dan status.</span><span class="sxs-lookup"><span data-stu-id="ac971-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="ac971-212">Bila Anda memilih ukuran dari daftar, Anda dapat mempratinjau output dan mengunduh file .CSV.</span><span class="sxs-lookup"><span data-stu-id="ac971-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="ac971-213">Untuk me-refresh semua ukuran Anda pada waktu yang sama, pilih **Segarkan semua** tanpa memilih ukuran tertentu.</span><span class="sxs-lookup"><span data-stu-id="ac971-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ac971-214">![Tindakan untuk mengelola ukuran tunggal](media/measure-actions.png "Tindakan untuk mengelola langkah tunggal")</span><span class="sxs-lookup"><span data-stu-id="ac971-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="ac971-215">Pilih ukuran dari daftar untuk pilihan berikut:</span><span class="sxs-lookup"><span data-stu-id="ac971-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="ac971-216">Pilih nama ukuran untuk melihat rinciannya.</span><span class="sxs-lookup"><span data-stu-id="ac971-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="ac971-217">**Edit** konfigurasi ukuran.</span><span class="sxs-lookup"><span data-stu-id="ac971-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="ac971-218">**segarkan** pengukuran berdasarkan data terbaru.</span><span class="sxs-lookup"><span data-stu-id="ac971-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="ac971-219">**Ubah nama** ukuran.</span><span class="sxs-lookup"><span data-stu-id="ac971-219">**Rename** the measure.</span></span>
- <span data-ttu-id="ac971-220">**Hapus** ukuran.</span><span class="sxs-lookup"><span data-stu-id="ac971-220">**Delete** the measure.</span></span>
- <span data-ttu-id="ac971-221">**Aktifkan** atau **Nonaktifkan**.</span><span class="sxs-lookup"><span data-stu-id="ac971-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="ac971-222">Ukuran yang tidak aktif tidak akan di-refresh selama [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ac971-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="ac971-223">Ada [enam jenis status](system.md#status-types) untuk tugas/proses.</span><span class="sxs-lookup"><span data-stu-id="ac971-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="ac971-224">Selain itu, sebagian besar proses [tergantung pada proses hilir lainnya](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="ac971-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="ac971-225">Anda dapat memilih status proses untuk melihat rincian kemajuan seluruh pekerjaan.</span><span class="sxs-lookup"><span data-stu-id="ac971-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="ac971-226">Setelah memilih **Lihat rincian** untuk salah satu tugas pekerjaan, Anda menemukan informasi tambahan: waktu pemrosesan, tanggal pemrosesan terakhir, dan semua kesalahan serta peringatan yang terkait dengan tugas.</span><span class="sxs-lookup"><span data-stu-id="ac971-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="ac971-227">Langkah selanjutnya</span><span class="sxs-lookup"><span data-stu-id="ac971-227">Next step</span></span>

<span data-ttu-id="ac971-228">Anda dapat menggunakan ukuran yang ada untuk membuat [segmen pelanggan](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ac971-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
