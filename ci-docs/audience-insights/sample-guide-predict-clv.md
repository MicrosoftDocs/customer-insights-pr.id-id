---
title: Contoh panduan prediksi nilai seumur hidup pelanggan
description: Gunakan panduan sampel ini untuk mencoba model prediksi pelanggan nilai seumur hidup.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129949"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="9ef2a-103">Contoh panduan prediksi nilai seumur hidup pelanggan (CLV)</span><span class="sxs-lookup"><span data-stu-id="9ef2a-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="9ef2a-104">Panduan ini akan menjelaskan kepada Anda contoh komprehensif dari nilai seumur hidup pelanggan (CLV) dalam Customer Insights dengan menggunakan data sampel.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="9ef2a-105">Skenario</span><span class="sxs-lookup"><span data-stu-id="9ef2a-105">Scenario</span></span>

<span data-ttu-id="9ef2a-106">Contoso adalah perusahaan yang memproduksi mesin kopi dan kopi berkualitas tinggi.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="9ef2a-107">Mereka menjual produk melalui situs web Kopi Contoso mereka.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="9ef2a-108">Perusahaan ingin memahami nilai (pendapatan) yang dapat dihasilkan pelanggan mereka dalam 12 bulan ke depan.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="9ef2a-109">Mengetahui nilai yang diharapkan dari pelanggan mereka dalam 12 bulan ke depan akan membantu mereka mengarahkan upaya pemasaran mereka pada pelanggan bernilai tinggi.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9ef2a-110">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="9ef2a-110">Prerequisites</span></span>

- <span data-ttu-id="9ef2a-111">Setidaknya [izin kontributor](permissions.md) dalam wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="9ef2a-112">Sebaiknya Anda menerapkan langkah-langkah berikut [di lingkungan baru](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="9ef2a-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="9ef2a-113">Tugas 1- Serap Data</span><span class="sxs-lookup"><span data-stu-id="9ef2a-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="9ef2a-114">Tinjau artikel tentang [penyerapan data](data-sources.md) dan [mengimpor sumber data menggunakan Power Query connector](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9ef2a-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="9ef2a-115">Informasi berikut ini mengasumsikan bahwa Anda telah mengenal dan menyerap data secara umum.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="9ef2a-116">Menyerap data pelanggan dari platform eCommerce</span><span class="sxs-lookup"><span data-stu-id="9ef2a-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="9ef2a-117">Buat sumber data bernama  **eCommerce** , pilih pilihan impor, dan pilih konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9ef2a-118">Masukkan URL untuk kontak eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="9ef2a-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="9ef2a-119">Saat mengedit data, pilih  **Ubah**  dan kemudian  **gunakan baris pertama sebagai header**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9ef2a-120">Perbarui DataType untuk kolom yang tercantum di bawah ini:</span><span class="sxs-lookup"><span data-stu-id="9ef2a-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9ef2a-121">**DateOfBirth**: tanggal</span><span class="sxs-lookup"><span data-stu-id="9ef2a-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="9ef2a-122">**CreatedOn**: Tanggal/Waktu/Zona</span><span class="sxs-lookup"><span data-stu-id="9ef2a-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tanggal lahir sampai saat ini.":::

1. <span data-ttu-id="9ef2a-124">Di bidang ' nama ' pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="9ef2a-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="9ef2a-125">**Simpan** Sumber Data.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="9ef2a-126">Menyerap Data pembelian online</span><span class="sxs-lookup"><span data-stu-id="9ef2a-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="9ef2a-127">Tambahkan himpunan data lain ke sumber data **eCommerce** yang sama.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="9ef2a-128">Pilih konektor **teks/CSV** lagi.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="9ef2a-129">Masukkan URL untuk data **pembelian online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="9ef2a-130">Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9ef2a-131">Perbarui DataType untuk kolom yang tercantum di bawah ini:</span><span class="sxs-lookup"><span data-stu-id="9ef2a-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9ef2a-132">**PurchasedOn**: tanggal/waktu</span><span class="sxs-lookup"><span data-stu-id="9ef2a-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="9ef2a-133">**TotalPrice**: mata uang</span><span class="sxs-lookup"><span data-stu-id="9ef2a-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="9ef2a-134">Di bidang **nama** pada panel sisi, ganti nama sumber data dari **kueri** menjadi **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="9ef2a-135">**Simpan** Sumber Data.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="9ef2a-136">Menyerap data pelanggan dari skema kesetiaan</span><span class="sxs-lookup"><span data-stu-id="9ef2a-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="9ef2a-137">Buat sumber data bernama **LoyaltyScheme**, pilih pilihan impor, dan pilih konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9ef2a-138">Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="9ef2a-139">Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9ef2a-140">Perbarui DataType untuk kolom yang tercantum di bawah ini:</span><span class="sxs-lookup"><span data-stu-id="9ef2a-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="9ef2a-141">**DateOfBirth**: tanggal</span><span class="sxs-lookup"><span data-stu-id="9ef2a-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="9ef2a-142">**RewardsPoints**: Bilangan Cacah</span><span class="sxs-lookup"><span data-stu-id="9ef2a-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="9ef2a-143">**CreatedOn**: Waktu/Tanggal</span><span class="sxs-lookup"><span data-stu-id="9ef2a-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="9ef2a-144">Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="9ef2a-145">**Simpan** Sumber Data.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="9ef2a-146">Serap data pelanggan dari ulasan situs</span><span class="sxs-lookup"><span data-stu-id="9ef2a-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="9ef2a-147">Buat sumber data bernama **Situs web**, pilih pilihan impor, dan pilih konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="9ef2a-148">Masukkan URL untuk kontak eCommerce https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="9ef2a-149">Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="9ef2a-150">Perbarui DataType untuk kolom yang tercantum di bawah ini:</span><span class="sxs-lookup"><span data-stu-id="9ef2a-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="9ef2a-151">**ReviewRating**: Angka Desimal</span><span class="sxs-lookup"><span data-stu-id="9ef2a-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="9ef2a-152">**ReviewDate**: tanggal</span><span class="sxs-lookup"><span data-stu-id="9ef2a-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="9ef2a-153">Di bidang 'Nama' di panel sebelah kanan, ganti nama sumber data Anda dari **Kueri** menjadi **Ulasan**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="9ef2a-154">**Simpan** Sumber Data.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="9ef2a-155">Tugas 2-penyatuan data</span><span class="sxs-lookup"><span data-stu-id="9ef2a-155">Task 2 - Data unification</span></span>

<span data-ttu-id="9ef2a-156">Setelah menyerap data, kami sekarang memulai proses penyatuan data untuk membuat profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="9ef2a-157">Untuk informasi selengkapnya, lihat [Penyatuan data](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="9ef2a-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="9ef2a-158">Peta</span><span class="sxs-lookup"><span data-stu-id="9ef2a-158">Map</span></span>

1. <span data-ttu-id="9ef2a-159">Setelah menyerap data, Petakan kontak dari eCommerce dan data kesetiaan ke jenis data umum.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="9ef2a-160">Buka **Data** > **Satukan** > **Petakan**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="9ef2a-161">Pilih entitas yang menunjukkan profil pelanggan- **ecommercecontacts** dan **loycustomer**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="9ef2a-162">Lalu, pilih **Terapkan**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-162">Then, select **Apply**.</span></span>

   ![menyatukan sumber data eCommerce dan kesetiaan.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="9ef2a-164">Pilih **contactid** sebagai kunci primer untuk **ecommercecontacts** dan **loyaltyid** sebagai kunci primer untuk **loycustomer**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Menyatukan LoyaltyId sebagai kunci primer.](media/unify-loyaltyid.png)

1. <span data-ttu-id="9ef2a-166">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="9ef2a-167">Cocokkan</span><span class="sxs-lookup"><span data-stu-id="9ef2a-167">Match</span></span>

1. <span data-ttu-id="9ef2a-168">Pergi ke tab **Cocokkan** dan pilih **Atur Urutan**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="9ef2a-169">Di daftar drop-down **utama**, pilih **ecommercecontacts: eCommerce** sebagai sumber utama dan mencakup semua rekaman.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="9ef2a-170">Pada daftar drop-down **entitas 2**, pilih **Loycustomer: LoyaltyScheme** dan sertakan semua rekaman.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Satukan dan cocokkan eCommerce dan Loyalty.](media/unify-match-order.png)

1. <span data-ttu-id="9ef2a-172">Pilih **Tambah aturan**</span><span class="sxs-lookup"><span data-stu-id="9ef2a-172">Select **Add rule**</span></span>

1. <span data-ttu-id="9ef2a-173">Tambahkan kondisi pertama Anda menggunakan FullName.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="9ef2a-174">Untuk eCommerceContacts, pilih **fullname** di drop-down.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="9ef2a-175">Untuk loyCustomers, pilih **fullname** di drop-down.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="9ef2a-176">Pilih drop-down **normalkan** dan pilih **jenis (telepon, nama, alamat,...)**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="9ef2a-177">Atur **tingkat presisi**: **dasar** dan **nilai**: **tinggi**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="9ef2a-178">Masukkan nama **fullname, email** untuk aturan baru.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="9ef2a-179">Tambahkan kondisi kedua untuk alamat email dengan memilih **Tambah kondisi**</span><span class="sxs-lookup"><span data-stu-id="9ef2a-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="9ef2a-180">Untuk eCommerceContacts entitas, pilih **email** di drop-down.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="9ef2a-181">Untuk loyCustomers entitas, pilih **email** di drop-down.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="9ef2a-182">Biarkan Normalkan kosong.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="9ef2a-183">Atur **tingkat presisi**: **dasar** dan **nilai**: **tinggi**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Satukan aturan kecocokan untuk nama dan email.](media/unify-match-rule.png)

1. <span data-ttu-id="9ef2a-185">Pilih **Selesai**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-185">Select **Done**.</span></span>

1. <span data-ttu-id="9ef2a-186">Pilih **Simpan** dan **Tutup**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="9ef2a-187">Penggabungan</span><span class="sxs-lookup"><span data-stu-id="9ef2a-187">Merge</span></span>

1. <span data-ttu-id="9ef2a-188">Buka tab **Gabungkan**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="9ef2a-189">Pada entitas **contactid** untuk **loycustomer**, ubah nama tampilan ke **contactidloyalty** untuk membedakannya dari id lain yang diserap.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![Ubah nama contactid dari Loyalty id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="9ef2a-191">Pilih **Simpan** dan **Jalankan proses penggunaan dan hilir**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="9ef2a-192">Tugas 3 - Mengonfigurasi prediksi nilai seumur hidup pelanggan</span><span class="sxs-lookup"><span data-stu-id="9ef2a-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="9ef2a-193">Dengan adanya profil pelanggan terpadu, kita sekarang dapat menjalankan prediksi nilai seumur hidup pelanggan.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="9ef2a-194">Untuk langkah-langkah mendetail, [lihat Prediksi Nilai Seumur Pelanggan (pratinjau)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="9ef2a-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="9ef2a-195">Buka  **Kecerdasan**  > **Prediksi**  dan pilih **model nilai seumur hidup Pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="9ef2a-196">Telusuri informasi di panel samping dan pilih **Mulai**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="9ef2a-197">Beri nama model **Prediksi CLV eCommerce OOB** dan entitas output  **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="9ef2a-198">Tentukan preferensi model untuk model CLV:</span><span class="sxs-lookup"><span data-stu-id="9ef2a-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="9ef2a-199">**Periode waktu prediksi**: **12 bulan atau 1 tahun**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="9ef2a-200">Pengaturan ini menentukan seberapa jauh ke masa depan untuk memprediksi nilai seumur hidup pelanggan.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="9ef2a-201">**Pelanggan aktif**: Tentukan apa artinya pelanggan aktif untuk bisnis Anda.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="9ef2a-202">Tetapkan jangka waktu historis di mana pelanggan harus memiliki setidaknya satu transaksi untuk dianggap aktif.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="9ef2a-203">Model tersebut hanya akan memperkirakan CLV untuk pelanggan aktif.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="9ef2a-204">Pilih antara mengizinkan model menghitung periode waktu berdasarkan data transaksi historis atau memberikan informasi jangka waktu.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="9ef2a-205">Dalam contoh panduan ini, kami **membiarkan model menghitung interval pembelian**, yang merupakan opsi default.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="9ef2a-206">**Pelanggan bernilai tinggi**: Tentukan pelanggan bernilai tinggi sebagai persentil pelanggan membayar teratas.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="9ef2a-207">Model ini menggunakan input ini untuk memberikan hasil yang sesuai dengan definisi bisnis Anda tentang pelanggan bernilai tinggi.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="9ef2a-208">Anda dapat memilih untuk membiarkan model menentukan pelanggan bernilai tinggi.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="9ef2a-209">Ini menggunakan aturan heuristik yang memperoleh persentil.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="9ef2a-210">Anda juga dapat mendefinisikan pelanggan bernilai tinggi sebagai persentil pelanggan membayar di masa mendatang.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="9ef2a-211">Dalam panduan sampel ini, kami secara manual mendefinisikan pelanggan bernilai tinggi sebagai **30% pelanggan bayar aktif teratas** dan memilih **Berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Langkah preferensi dalam pengalaman terpandu untuk model CLV.":::

1. <span data-ttu-id="9ef2a-213">Di langkah **Data yang Diperlukan**, pilih **Tambahkan data** untuk menyediakan data riwayat transaksi.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="9ef2a-214">Tambahkan entitas **eCommercePurchases: eCommerce** dan petakan atribut yang diperlukan oleh model:</span><span class="sxs-lookup"><span data-stu-id="9ef2a-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="9ef2a-215">ID Transaksi: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="9ef2a-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="9ef2a-216">Tanggal Transaksi: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="9ef2a-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="9ef2a-217">Jumlah transaksi: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="9ef2a-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="9ef2a-218">ID Produk: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="9ef2a-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="9ef2a-219">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-219">Select **Next**.</span></span>

1. <span data-ttu-id="9ef2a-220">Mengatur hubungan antara entitas **eCommercePurchases: entitas eCommerce** dan  **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="9ef2a-221">Langkah **Data tambahan (opsional)** memungkinkan Anda menambahkan lebih banyak data aktivitas pelanggan.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="9ef2a-222">Data ini dapat membantu mendapatkan lebih banyak wawasan untuk interaksi pelanggan dengan bisnis Anda, yang dapat berkontribusi pada CLV.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="9ef2a-223">Menambahkan interaksi pelanggan utama seperti log web, log layanan pelanggan, atau riwayat program hadiah dapat meningkatkan akurasi prediksi.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="9ef2a-224">Pilih **Tambahkan data** untuk menyertakan lebih banyak data aktivitas pelanggan.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="9ef2a-225">Tambahkan entitas aktivitas pelanggan dan petakan nama bidangnya ke bidang terkait yang diperlukan oleh model:</span><span class="sxs-lookup"><span data-stu-id="9ef2a-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="9ef2a-226">Entitas aktivitas pelanggan: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="9ef2a-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="9ef2a-227">Kunci utama: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="9ef2a-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="9ef2a-228">Cap waktu: website.reviews.reviewDate</span><span class="sxs-lookup"><span data-stu-id="9ef2a-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="9ef2a-229">Kejadian (nama aktivitas): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="9ef2a-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="9ef2a-230">Detail (jumlah atau nilai): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="9ef2a-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="9ef2a-231">Pilih **Berikutnya** dan konfigurasikan aktivitas dan hubungan antara data transaksi dan data pelanggan:</span><span class="sxs-lookup"><span data-stu-id="9ef2a-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="9ef2a-232">Jenis aktivitas: Pilih yang ada</span><span class="sxs-lookup"><span data-stu-id="9ef2a-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="9ef2a-233">Label aktivitas: Review</span><span class="sxs-lookup"><span data-stu-id="9ef2a-233">Activity label: Review</span></span>
   - <span data-ttu-id="9ef2a-234">Label terkait: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="9ef2a-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="9ef2a-235">Entitas pelanggan: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="9ef2a-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="9ef2a-236">Relasi: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="9ef2a-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="9ef2a-237">Pilih **berikutnya** untuk mengatur jadwal model.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="9ef2a-238">Model perlu berlatih secara teratur untuk mempelajari pola baru ketika ada data baru yang diserap.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="9ef2a-239">Untuk contoh ini, pilih **Bulanan**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="9ef2a-240">Setelah meninjau semua rincian, pilih  **Simpan dan jalankan**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="9ef2a-241">Tugas 4-TInjau hasil dan penjelasan model</span><span class="sxs-lookup"><span data-stu-id="9ef2a-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="9ef2a-242">Biarkan model menyelesaikan pelatihan dan penilaian data.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="9ef2a-243">Selanjutnya, Anda dapat meninjau hasil dan penjelasan model CLV.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="9ef2a-244">Untuk informasi lebih lanjut, lihat [meninjau status dan hasil prediksi](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="9ef2a-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="9ef2a-245">Tugas 5 - Buat segmen pelanggan bernilai tinggi</span><span class="sxs-lookup"><span data-stu-id="9ef2a-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="9ef2a-246">Menjalankan model membuat entitas baru, yang tercantum di **Data** > **Entitas**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="9ef2a-247">Anda dapat membuat segmen pelanggan baru berdasarkan entitas yang dibuat oleh model.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="9ef2a-248">Buka **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="9ef2a-249">Pilih  **baru** lalu pilih **buat dari** > **intelijen**.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Membuat segmen dengan output model.](media/segment-intelligence.png)

1. <span data-ttu-id="9ef2a-251">Pilih entitas  **OOBeCommerceCLVPrediction** dan tentukan segmen:</span><span class="sxs-lookup"><span data-stu-id="9ef2a-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="9ef2a-252">Bidang: CLVScore</span><span class="sxs-lookup"><span data-stu-id="9ef2a-252">Field: CLVScore</span></span>
  - <span data-ttu-id="9ef2a-253">Operator: Lebih besar dari</span><span class="sxs-lookup"><span data-stu-id="9ef2a-253">Operator: greater than</span></span>
  - <span data-ttu-id="9ef2a-254">Nilai: 1500</span><span class="sxs-lookup"><span data-stu-id="9ef2a-254">Value: 1500</span></span>

1. <span data-ttu-id="9ef2a-255">Pilih **Tinjau** dan **Simpan** segmen.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="9ef2a-256">Anda sekarang memiliki segmen yang mengidentifikasi pelanggan yang diprediksi akan menghasilkan pendapatan lebih dari $1500 dalam 12 bulan ke depan.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="9ef2a-257">Segmen ini diperbarui secara dinamis jika lebih banyak data yang diserap.</span><span class="sxs-lookup"><span data-stu-id="9ef2a-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="9ef2a-258">Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9ef2a-258">For more information, see [Create and manage segments](segments.md).</span></span>
