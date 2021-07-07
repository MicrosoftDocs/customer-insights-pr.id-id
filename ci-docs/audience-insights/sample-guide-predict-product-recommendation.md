---
title: Panduan sampel prediksi Rekomendasi produk
description: Gunakan contoh panduan ini untuk mencoba model prediksi rekomendasi produk siap pakai.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: a85ee598ec747d0594755314e83a127ce0f2af95
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306170"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="2fe78-103">Panduan sampel prediksi Rekomendasi produk (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="2fe78-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="2fe78-104">Kami akan menjelaskan kepada Anda contoh akhir dari prediksi rekomendasi produk menggunakan data sampel yang diberikan di bawah ini.</span><span class="sxs-lookup"><span data-stu-id="2fe78-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="2fe78-105">Skenario</span><span class="sxs-lookup"><span data-stu-id="2fe78-105">Scenario</span></span>

<span data-ttu-id="2fe78-106">Contoso adalah perusahaan yang memproduksi mesin kopi dan kopi berkualitas tinggi, yang mereka jual melalui situs web Kopi Contoso mereka.</span><span class="sxs-lookup"><span data-stu-id="2fe78-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="2fe78-107">Tujuan mereka adalah untuk memahami produk yang harus mereka rekomendasikan kepada pelanggan berulang mereka.</span><span class="sxs-lookup"><span data-stu-id="2fe78-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="2fe78-108">Mengetahui pelanggan **lebih cenderung membeli** dapat membantu mereka menghemat upaya pemasaran dengan berfokus pada item tertentu.</span><span class="sxs-lookup"><span data-stu-id="2fe78-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2fe78-109">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="2fe78-109">Prerequisites</span></span>

- <span data-ttu-id="2fe78-110">Sekurangnya [izin kontributor](permissions.md) di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2fe78-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="2fe78-111">Sebaiknya Anda menerapkan langkah-langkah berikut [di lingkungan baru](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="2fe78-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="2fe78-112">Tugas 1- Serap Data</span><span class="sxs-lookup"><span data-stu-id="2fe78-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="2fe78-113">Tinjau artikel [tentang konsumsi data](data-sources.md) dan [mengimpor sumber data menggunakan konektor connector](connect-power-query.md) secara khusus.</span><span class="sxs-lookup"><span data-stu-id="2fe78-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="2fe78-114">Informasi berikut ini mengasumsikan bahwa Anda telah mengenal dan menyerap data secara umum.</span><span class="sxs-lookup"><span data-stu-id="2fe78-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="2fe78-115">Menyerap data pelanggan dari platform eCommerce</span><span class="sxs-lookup"><span data-stu-id="2fe78-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="2fe78-116">Buat sumber data bernama **eCommerce**, pilih pilihan impor, dan pilih konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="2fe78-117">Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="2fe78-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="2fe78-118">Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="2fe78-119">Perbarui DataType untuk kolom yang tercantum di bawah ini:</span><span class="sxs-lookup"><span data-stu-id="2fe78-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="2fe78-120">**DateOfBirth**: tanggal</span><span class="sxs-lookup"><span data-stu-id="2fe78-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="2fe78-121">**CreatedOn**: Tanggal/Waktu/Zona</span><span class="sxs-lookup"><span data-stu-id="2fe78-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tanggal lahir sampai saat ini.":::

5. <span data-ttu-id="2fe78-123">Di bidang ' nama ' pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="2fe78-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="2fe78-124">**Simpan** Sumber Data.</span><span class="sxs-lookup"><span data-stu-id="2fe78-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="2fe78-125">Menyerap Data pembelian online</span><span class="sxs-lookup"><span data-stu-id="2fe78-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="2fe78-126">Tambahkan himpunan data lain ke sumber data **eCommerce** yang sama.</span><span class="sxs-lookup"><span data-stu-id="2fe78-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="2fe78-127">Pilih konektor **teks/CSV** lagi.</span><span class="sxs-lookup"><span data-stu-id="2fe78-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="2fe78-128">Masukkan URL untuk data **pembelian online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="2fe78-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="2fe78-129">Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="2fe78-130">Perbarui DataType untuk kolom yang tercantum di bawah ini:</span><span class="sxs-lookup"><span data-stu-id="2fe78-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="2fe78-131">**PurchasedOn**: tanggal/waktu</span><span class="sxs-lookup"><span data-stu-id="2fe78-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="2fe78-132">**TotalPrice**: mata uang</span><span class="sxs-lookup"><span data-stu-id="2fe78-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="2fe78-133">Di bidang **nama** pada panel sisi, ganti nama sumber data dari **kueri** menjadi **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="2fe78-134">**Simpan** Sumber Data.</span><span class="sxs-lookup"><span data-stu-id="2fe78-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="2fe78-135">Menyerap data pelanggan dari skema kesetiaan</span><span class="sxs-lookup"><span data-stu-id="2fe78-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="2fe78-136">Buat sumber data bernama **LoyaltyScheme**, pilih pilihan impor, dan pilih konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="2fe78-137">Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="2fe78-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="2fe78-138">Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="2fe78-139">Perbarui DataType untuk kolom yang tercantum di bawah ini:</span><span class="sxs-lookup"><span data-stu-id="2fe78-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="2fe78-140">**DateOfBirth**: tanggal</span><span class="sxs-lookup"><span data-stu-id="2fe78-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="2fe78-141">**RewardsPoints**: Bilangan Cacah</span><span class="sxs-lookup"><span data-stu-id="2fe78-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="2fe78-142">**CreatedOn**: Waktu/Tanggal</span><span class="sxs-lookup"><span data-stu-id="2fe78-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="2fe78-143">Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="2fe78-144">**Simpan** Sumber Data.</span><span class="sxs-lookup"><span data-stu-id="2fe78-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="2fe78-145">Tugas 2-penyatuan data</span><span class="sxs-lookup"><span data-stu-id="2fe78-145">Task 2 - Data unification</span></span>

<span data-ttu-id="2fe78-146">Setelah menyerap data, kami sekarang memulai proses penyatuan data untuk membuat profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="2fe78-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="2fe78-147">Untuk informasi selengkapnya, lihat [Penyatuan data](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="2fe78-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="2fe78-148">Peta</span><span class="sxs-lookup"><span data-stu-id="2fe78-148">Map</span></span>

1. <span data-ttu-id="2fe78-149">Setelah menyerap data, Petakan kontak dari eCommerce dan data kesetiaan ke jenis data umum.</span><span class="sxs-lookup"><span data-stu-id="2fe78-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="2fe78-150">Buka **Data** > **Satukan** > **Petakan**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="2fe78-151">Pilih entitas yang menunjukkan profil pelanggan- **ecommercecontacts** dan **loycustomer**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![menyatukan sumber data eCommerce dan kesetiaan.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="2fe78-153">Pilih **contactid** sebagai kunci primer untuk **ecommercecontacts** dan **loyaltyid** sebagai kunci primer untuk **loycustomer**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Menyatukan LoyaltyId sebagai kunci primer.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="2fe78-155">Cocokkan</span><span class="sxs-lookup"><span data-stu-id="2fe78-155">Match</span></span>

1. <span data-ttu-id="2fe78-156">Pergi ke tab **Cocokkan** dan pilih **Atur Urutan**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="2fe78-157">Dalam daftar dropdown **Utama**, pilih **eCommerceContacts: e Commerce** sebagai sumber utama dan sertakan semua rekaman.</span><span class="sxs-lookup"><span data-stu-id="2fe78-157">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="2fe78-158">Dalam daftar dropdown **Entitas 2**, pilih **loyCustomers: LoyaltyScheme** dan sertakan semua rekaman.</span><span class="sxs-lookup"><span data-stu-id="2fe78-158">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Satukan dan cocokkan eCommerce dan Loyalty.](media/unify-match-order.png)

4. <span data-ttu-id="2fe78-160">Pilih **Buat aturan baru**</span><span class="sxs-lookup"><span data-stu-id="2fe78-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="2fe78-161">Tambahkan kondisi pertama Anda menggunakan FullName.</span><span class="sxs-lookup"><span data-stu-id="2fe78-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="2fe78-162">Untuk eCommerceContacts, pilih **FullName** di dropdown.</span><span class="sxs-lookup"><span data-stu-id="2fe78-162">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="2fe78-163">Untuk loyCustomers, pilih **FullName** di dropdown.</span><span class="sxs-lookup"><span data-stu-id="2fe78-163">For loyCustomers select **FullName** in the dropdown.</span></span>
   - <span data-ttu-id="2fe78-164">Pilih drop-down **normalkan** dan pilih **jenis (telepon, nama, alamat,...)**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="2fe78-165">Atur **tingkat presisi**: **dasar** dan **nilai**: **tinggi**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="2fe78-166">Masukkan nama **fullname, email** untuk aturan baru.</span><span class="sxs-lookup"><span data-stu-id="2fe78-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="2fe78-167">Tambahkan kondisi kedua untuk alamat email dengan memilih **Tambah kondisi**</span><span class="sxs-lookup"><span data-stu-id="2fe78-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="2fe78-168">Untuk entitas eCommerceContacts, pilih **EMail** di dropdown.</span><span class="sxs-lookup"><span data-stu-id="2fe78-168">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   - <span data-ttu-id="2fe78-169">Untuk entitas loyCustomers, pilih **EMail** di dropdown.</span><span class="sxs-lookup"><span data-stu-id="2fe78-169">For entity loyCustomers, choose **EMail** in the dropdown.</span></span>
   - <span data-ttu-id="2fe78-170">Biarkan Normalkan kosong.</span><span class="sxs-lookup"><span data-stu-id="2fe78-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="2fe78-171">Atur **tingkat presisi**: **dasar** dan **nilai**: **tinggi**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Satukan aturan kecocokan untuk nama dan email.](media/unify-match-rule.png)

7. <span data-ttu-id="2fe78-173">Pilih **Simpan** dan **Tutup**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="2fe78-174">Penggabungan</span><span class="sxs-lookup"><span data-stu-id="2fe78-174">Merge</span></span>

1. <span data-ttu-id="2fe78-175">Buka tab **Gabungkan**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="2fe78-176">Pada entitas **contactid** untuk **loycustomer**, ubah nama tampilan ke **contactidloyalty** untuk membedakannya dari id lain yang diserap.</span><span class="sxs-lookup"><span data-stu-id="2fe78-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Ubah nama contactid dari Loyalty id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="2fe78-178">Pilih **Simpan** dan **Jalankan** untuk memulai proses penggabungan.</span><span class="sxs-lookup"><span data-stu-id="2fe78-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="2fe78-179">Tugas 3 - Mengkonfigurasi prediksi rekomendasi produk</span><span class="sxs-lookup"><span data-stu-id="2fe78-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="2fe78-180">Dengan profil pelanggan terpadu di tempatnya, kini kita dapat menjalankan prediksi kehilangan pelanggan langganan.</span><span class="sxs-lookup"><span data-stu-id="2fe78-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="2fe78-181">Buka **Inteligensi** > **prediksi** pilih **Rekomendasi produk**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="2fe78-182">Pilih **Mulai**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-182">Select **Get started**.</span></span>

1. <span data-ttu-id="2fe78-183">Namai **Prediksi model rekomendasi produk OOB** dan entitas output **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="2fe78-184">Tentukan tiga kondisi untuk model:</span><span class="sxs-lookup"><span data-stu-id="2fe78-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="2fe78-185">**Jumlah produk**: Atur nilai ini ke **5**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="2fe78-186">Pengaturan ini menentukan seberapa banyak produk yang ingin Anda rekomendasikan kepada pelanggan.</span><span class="sxs-lookup"><span data-stu-id="2fe78-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="2fe78-187">**Ulangi pembelian yang diharapkan**: Pilih **Ya** untuk menunjukkan bahwa Anda ingin menyertakan produk dalam rekomendasi yang telah dibeli pelanggan Anda sebelumnya.</span><span class="sxs-lookup"><span data-stu-id="2fe78-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="2fe78-188">**Periode lihat kembali:** Pilih sekurangnya **365 hari**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="2fe78-189">Pengaturan ini menentukan berapa lama model akan melihat kembali aktivitas pelanggan untuk menggunakannya sebagai input untuk rekomendasi mereka.</span><span class="sxs-lookup"><span data-stu-id="2fe78-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferensi model untuk model rekomendasi produk.":::

1. <span data-ttu-id="2fe78-191">Pilih **Data yang diperlukan** dan pilih **Tambah data** untuk Riwayat pembelian.</span><span class="sxs-lookup"><span data-stu-id="2fe78-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="2fe78-192">Tambahkan entitas **eCommercePurchases : eCommerce** dan Petakan bidang dari eCommerce ke bidang terkait yang diperlukan oleh model.</span><span class="sxs-lookup"><span data-stu-id="2fe78-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="2fe78-193">Gabungkan entitas **ecommercepurchases: eCommerce** dengan **ecommercecontacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Bergabung dengan entitas e-commerce.](media/model-purchase-join.png)

1. <span data-ttu-id="2fe78-195">Pilih **berikutnya** untuk mengatur jadwal model.</span><span class="sxs-lookup"><span data-stu-id="2fe78-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="2fe78-196">Model harus dilatih secara teratur untuk mempelajari pola baru bila ada data baru yang terserap.</span><span class="sxs-lookup"><span data-stu-id="2fe78-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="2fe78-197">Untuk contoh ini, pilih **bulanan**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="2fe78-198">Setelah meninjau semua rincian, pilih **Simpan dan jalankan**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="2fe78-199">Tugas 4-TInjau hasil dan penjelasan model</span><span class="sxs-lookup"><span data-stu-id="2fe78-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="2fe78-200">Biarkan model menyelesaikan pelatihan dan penilaian data.</span><span class="sxs-lookup"><span data-stu-id="2fe78-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="2fe78-201">Anda sekarang dapat meninjau penjelasan model rekomendasi produk.</span><span class="sxs-lookup"><span data-stu-id="2fe78-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="2fe78-202">Untuk informasi lebih lanjut, lihat [meninjau status dan hasil prediksi](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="2fe78-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="2fe78-203">Tugas 5 - Membuat segmen produk dengan pembelian tinggi</span><span class="sxs-lookup"><span data-stu-id="2fe78-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="2fe78-204">Menjalankan model produksi membuat entitas baru yang dapat Anda lihat di **data** > **entitas**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="2fe78-205">Anda dapat membuat segmen baru berdasarkan entitas yang dibuat oleh model.</span><span class="sxs-lookup"><span data-stu-id="2fe78-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="2fe78-206">Buka **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-206">Go to **Segments**.</span></span> <span data-ttu-id="2fe78-207">Pilih **baru** lalu pilih **buat dari** > **intelijen**.</span><span class="sxs-lookup"><span data-stu-id="2fe78-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Membuat segmen dengan output model.](media/segment-intelligence.png)

1. <span data-ttu-id="2fe78-209">Pilih titik akhir **OOBProductRecommendationModelPrediction** dan tentukan segmen:</span><span class="sxs-lookup"><span data-stu-id="2fe78-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="2fe78-210">Bidang: ProductID</span><span class="sxs-lookup"><span data-stu-id="2fe78-210">Field: ProductID</span></span>
   - <span data-ttu-id="2fe78-211">Operator: Nilai</span><span class="sxs-lookup"><span data-stu-id="2fe78-211">Operator: Value</span></span>
   - <span data-ttu-id="2fe78-212">Nilai: Pilih tiga ID produk teratas</span><span class="sxs-lookup"><span data-stu-id="2fe78-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Membuat segmen dari hasil model.":::

<span data-ttu-id="2fe78-214">Anda sekarang memiliki segmen yang secara dinamis diperbarui dan mengidentifikasi pelanggan yang lebih ingin membeli tiga produk yang paling direkomendasikan</span><span class="sxs-lookup"><span data-stu-id="2fe78-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="2fe78-215">Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="2fe78-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]