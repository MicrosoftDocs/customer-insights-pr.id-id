---
title: Panduan sampel prediksi kehilangan pelanggan transaksional
description: Gunakan contoh panduan ini untuk mencoba model prediksi kehilangan pelanggan transaksional bawaan.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 81540ad2f490cf566f031233543b3cb6aa838033
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269794"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="6b691-103">Panduan sampel prediksi kehilangan pelanggan transaksional (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="6b691-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="6b691-104">Panduan ini akan memandu Anda tentang contoh komprehensif prediksi kehilangan pelanggan transaksional di Customer Insights menggunakan data sampel yang diberikan di bawah ini.</span><span class="sxs-lookup"><span data-stu-id="6b691-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="6b691-105">Semua data yang digunakan dalam panduan ini bukan data pelanggan nyata dan merupakan bagian dari himpunan data Aswono yang ditemukan dalam lingkungan *demo* dalam langganan customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="6b691-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="6b691-106">Skenario</span><span class="sxs-lookup"><span data-stu-id="6b691-106">Scenario</span></span>

<span data-ttu-id="6b691-107">Aswono adalah perusahaan yang memproduksi mesin kopi dan kopi berkualitas tinggi, yang dijual melalui situs web Kopi Aswono.</span><span class="sxs-lookup"><span data-stu-id="6b691-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="6b691-108">Tujuan mereka adalah untuk mengetahui Pelanggan mana yang biasanya membeli produk mereka secara teratur, yang akan berhenti menjadi pelanggan aktif dalam 60 hari berikutnya.</span><span class="sxs-lookup"><span data-stu-id="6b691-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="6b691-109">Mengetahui pelanggan mana yang **cenderung pergi**, dapat membantu mereka menyelamatkan upaya pemasaran dengan berfokus pada menjaganya.</span><span class="sxs-lookup"><span data-stu-id="6b691-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6b691-110">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="6b691-110">Prerequisites</span></span>

- <span data-ttu-id="6b691-111">Sekurangnya [izin kontributor](permissions.md) di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6b691-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="6b691-112">Sebaiknya Anda menerapkan langkah-langkah berikut [di lingkungan baru](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="6b691-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="6b691-113">Tugas 1- Serap Data</span><span class="sxs-lookup"><span data-stu-id="6b691-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="6b691-114">Tinjau artikel [tentang konsumsi data](data-sources.md) dan [mengimpor sumber data menggunakan konektor connector](connect-power-query.md) secara khusus.</span><span class="sxs-lookup"><span data-stu-id="6b691-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="6b691-115">Informasi berikut ini mengasumsikan bahwa Anda telah mengenal dan menyerap data secara umum.</span><span class="sxs-lookup"><span data-stu-id="6b691-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="6b691-116">Menyerap data pelanggan dari platform eCommerce</span><span class="sxs-lookup"><span data-stu-id="6b691-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="6b691-117">Buat sumber data bernama **eCommerce**, pilih pilihan impor, dan pilih konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="6b691-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="6b691-118">Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="6b691-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="6b691-119">Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.</span><span class="sxs-lookup"><span data-stu-id="6b691-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="6b691-120">Perbarui DataType untuk kolom yang tercantum di bawah ini:</span><span class="sxs-lookup"><span data-stu-id="6b691-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="6b691-121">**DateOfBirth**: tanggal</span><span class="sxs-lookup"><span data-stu-id="6b691-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="6b691-122">**CreatedOn**: Tanggal/Waktu/Zona</span><span class="sxs-lookup"><span data-stu-id="6b691-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="6b691-123">![Mengubah DoB ke Tanggal](media/ecommerce-dob-date.PNG "Ubah tanggal lahir sampai saat ini")</span><span class="sxs-lookup"><span data-stu-id="6b691-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="6b691-124">Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="6b691-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="6b691-125">Simpan Sumber Data.</span><span class="sxs-lookup"><span data-stu-id="6b691-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="6b691-126">Menyerap Data pembelian online</span><span class="sxs-lookup"><span data-stu-id="6b691-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="6b691-127">Tambahkan himpunan data lain ke sumber data **eCommerce** yang sama.</span><span class="sxs-lookup"><span data-stu-id="6b691-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="6b691-128">Pilih konektor **teks/CSV** lagi.</span><span class="sxs-lookup"><span data-stu-id="6b691-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="6b691-129">Masukkan URL untuk data **pembelian online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="6b691-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="6b691-130">Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.</span><span class="sxs-lookup"><span data-stu-id="6b691-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="6b691-131">Perbarui DataType untuk kolom yang tercantum di bawah ini:</span><span class="sxs-lookup"><span data-stu-id="6b691-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="6b691-132">**PurchasedOn**: tanggal/waktu</span><span class="sxs-lookup"><span data-stu-id="6b691-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="6b691-133">**TotalPrice**: mata uang</span><span class="sxs-lookup"><span data-stu-id="6b691-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="6b691-134">Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="6b691-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="6b691-135">Simpan Sumber Data.</span><span class="sxs-lookup"><span data-stu-id="6b691-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="6b691-136">Menyerap data pelanggan dari skema kesetiaan</span><span class="sxs-lookup"><span data-stu-id="6b691-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="6b691-137">Buat sumber data bernama **LoyaltyScheme**, pilih pilihan impor, dan pilih konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="6b691-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="6b691-138">Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="6b691-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="6b691-139">Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.</span><span class="sxs-lookup"><span data-stu-id="6b691-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="6b691-140">Perbarui DataType untuk kolom yang tercantum di bawah ini:</span><span class="sxs-lookup"><span data-stu-id="6b691-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="6b691-141">**DateOfBirth**: tanggal</span><span class="sxs-lookup"><span data-stu-id="6b691-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="6b691-142">**RewardsPoints**: Bilangan Cacah</span><span class="sxs-lookup"><span data-stu-id="6b691-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="6b691-143">**CreatedOn**: Waktu/Tanggal</span><span class="sxs-lookup"><span data-stu-id="6b691-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="6b691-144">Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="6b691-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="6b691-145">Simpan Sumber Data.</span><span class="sxs-lookup"><span data-stu-id="6b691-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="6b691-146">Tugas 2-penyatuan data</span><span class="sxs-lookup"><span data-stu-id="6b691-146">Task 2 - Data unification</span></span>

<span data-ttu-id="6b691-147">Setelah menyerap data, kita sekarang memulai proses **Memetakan, Mencocokkan, menggabungkan** untuk membuat profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="6b691-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="6b691-148">Untuk informasi selengkapnya, lihat [Penyatuan data](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="6b691-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="6b691-149">Peta</span><span class="sxs-lookup"><span data-stu-id="6b691-149">Map</span></span>

1. <span data-ttu-id="6b691-150">Setelah menyerap data, Petakan kontak dari eCommerce dan data kesetiaan ke jenis data umum.</span><span class="sxs-lookup"><span data-stu-id="6b691-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="6b691-151">Buka **Data** > **Satukan** > **Petakan**.</span><span class="sxs-lookup"><span data-stu-id="6b691-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="6b691-152">Pilih entitas yang menunjukkan profil pelanggan- **ecommercecontacts** dan **loycustomer**.</span><span class="sxs-lookup"><span data-stu-id="6b691-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="menyatukan sumber data eCommerce dan kesetiaan.":::

1. <span data-ttu-id="6b691-154">Pilih **contactid** sebagai kunci primer untuk **ecommercecontacts** dan **loyaltyid** sebagai kunci primer untuk **loycustomer**.</span><span class="sxs-lookup"><span data-stu-id="6b691-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Menyatukan LoyaltyId sebagai kunci primer.":::

### <a name="match"></a><span data-ttu-id="6b691-156">Cocokkan</span><span class="sxs-lookup"><span data-stu-id="6b691-156">Match</span></span>

1. <span data-ttu-id="6b691-157">Pergi ke tab **Cocokkan** dan pilih **Atur Urutan**.</span><span class="sxs-lookup"><span data-stu-id="6b691-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="6b691-158">Di daftar drop-down **utama**, pilih **ecommercecontacts: eCommerce** sebagai sumber utama dan mencakup semua rekaman.</span><span class="sxs-lookup"><span data-stu-id="6b691-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="6b691-159">Pada daftar drop-down **entitas 2**, pilih **Loycustomer: LoyaltyScheme** dan sertakan semua rekaman.</span><span class="sxs-lookup"><span data-stu-id="6b691-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Satukan dan cocokkan eCommerce dan Loyalty.":::

1. <span data-ttu-id="6b691-161">Pilih **Buat aturan baru**</span><span class="sxs-lookup"><span data-stu-id="6b691-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="6b691-162">Tambahkan kondisi pertama Anda menggunakan FullName.</span><span class="sxs-lookup"><span data-stu-id="6b691-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="6b691-163">Untuk eCommerceContacts, pilih **fullname** di drop-down.</span><span class="sxs-lookup"><span data-stu-id="6b691-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="6b691-164">Untuk loyCustomers, pilih **fullname** di drop-down.</span><span class="sxs-lookup"><span data-stu-id="6b691-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="6b691-165">Pilih drop-down **normalkan** dan pilih **jenis (telepon, nama, alamat,...)**.</span><span class="sxs-lookup"><span data-stu-id="6b691-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="6b691-166">Atur **tingkat presisi**: **dasar** dan **nilai**: **tinggi**.</span><span class="sxs-lookup"><span data-stu-id="6b691-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="6b691-167">Masukkan nama **fullname, email** untuk aturan baru.</span><span class="sxs-lookup"><span data-stu-id="6b691-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="6b691-168">Tambahkan kondisi kedua untuk alamat email dengan memilih **Tambah kondisi**</span><span class="sxs-lookup"><span data-stu-id="6b691-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="6b691-169">Untuk eCommerceContacts entitas, pilih **email** di drop-down.</span><span class="sxs-lookup"><span data-stu-id="6b691-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="6b691-170">Untuk loyCustomers entitas, pilih **email** di drop-down.</span><span class="sxs-lookup"><span data-stu-id="6b691-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="6b691-171">Biarkan Normalkan kosong.</span><span class="sxs-lookup"><span data-stu-id="6b691-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="6b691-172">Atur **tingkat presisi**: **dasar** dan **nilai**: **tinggi**.</span><span class="sxs-lookup"><span data-stu-id="6b691-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Satukan aturan kecocokan untuk nama dan email.":::

7. <span data-ttu-id="6b691-174">Pilih **Simpan** dan **Tutup**.</span><span class="sxs-lookup"><span data-stu-id="6b691-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="6b691-175">Penggabungan</span><span class="sxs-lookup"><span data-stu-id="6b691-175">Merge</span></span>

1. <span data-ttu-id="6b691-176">Buka tab **Gabungkan**.</span><span class="sxs-lookup"><span data-stu-id="6b691-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="6b691-177">Pada entitas **contactid** untuk **loycustomer**, ubah nama tampilan ke **contactidloyalty** untuk membedakannya dari id lain yang diserap.</span><span class="sxs-lookup"><span data-stu-id="6b691-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Ubah nama contactid dari Loyalty id.":::

1. <span data-ttu-id="6b691-179">Pilih **Simpan** dan **Jalankan** untuk memulai proses penggabungan.</span><span class="sxs-lookup"><span data-stu-id="6b691-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="6b691-180">Tugas 3-konfigurasi prediksi kehilangan pelanggan transaksi</span><span class="sxs-lookup"><span data-stu-id="6b691-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="6b691-181">Dengan profil pelanggan terpadu di tempatnya, kini kita dapat menjalankan prediksi kehilangan pelanggan langganan.</span><span class="sxs-lookup"><span data-stu-id="6b691-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="6b691-182">Untuk langkah rinci, lihat artikel [prediksi kehilangan pelanggan langganan](predict-subscription-churn.md) (pratinjau).</span><span class="sxs-lookup"><span data-stu-id="6b691-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="6b691-183">Buka **intelijen** > **Temukan** dan pilih untuk menggunakan **model kehilangan pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="6b691-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="6b691-184">Pilih pilihan **Transaksional** dan pilih **Mulai**.</span><span class="sxs-lookup"><span data-stu-id="6b691-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="6b691-185">Namai model **prediksi kehilangan pelanggan transaksi eCommerce OOB** dan entitas output **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="6b691-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="6b691-186">Tentukan dua kondisi untuk model kehilangan pelanggan:</span><span class="sxs-lookup"><span data-stu-id="6b691-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="6b691-187">**Jendela prediksi**: minimal **60** hari.</span><span class="sxs-lookup"><span data-stu-id="6b691-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="6b691-188">Pengaturan ini menentukan seberapa jauh ke masa depan kita ingin memprediksi kehilangan pelanggan.</span><span class="sxs-lookup"><span data-stu-id="6b691-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="6b691-189">**Definisi kehilangan pelanggan**: **minimal 60** hari.</span><span class="sxs-lookup"><span data-stu-id="6b691-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="6b691-190">Durasi tanpa pembelian yang mana setelah itu pelanggan dianggap hilang.</span><span class="sxs-lookup"><span data-stu-id="6b691-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="pilih jendela prediksi pengungkit model dan definisi kehilangan pelanggan.":::

1. <span data-ttu-id="6b691-192">Pilih **Riwayat Pembelian (diperlukan)** dan pilih **Tambah data** untuk Riwayat pembelian.</span><span class="sxs-lookup"><span data-stu-id="6b691-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="6b691-193">Tambahkan entitas **eCommercePurchases : eCommerce** dan Petakan bidang dari eCommerce ke bidang terkait yang diperlukan oleh model.</span><span class="sxs-lookup"><span data-stu-id="6b691-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="6b691-194">Gabungkan entitas **ecommercepurchases: eCommerce** dengan **ecommercecontacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="6b691-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Bergabung dengan entitas e-commerce.":::

1. <span data-ttu-id="6b691-196">Pilih **berikutnya** untuk mengatur jadwal model.</span><span class="sxs-lookup"><span data-stu-id="6b691-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="6b691-197">Model harus dilatih secara teratur untuk mempelajari pola baru bila ada data baru yang terserap.</span><span class="sxs-lookup"><span data-stu-id="6b691-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="6b691-198">Untuk contoh ini, pilih **bulanan**.</span><span class="sxs-lookup"><span data-stu-id="6b691-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="6b691-199">Setelah meninjau semua rincian, pilih **Simpan dan jalankan**.</span><span class="sxs-lookup"><span data-stu-id="6b691-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="6b691-200">Tugas 4-TInjau hasil dan penjelasan model</span><span class="sxs-lookup"><span data-stu-id="6b691-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="6b691-201">Biarkan model menyelesaikan pelatihan dan penilaian data.</span><span class="sxs-lookup"><span data-stu-id="6b691-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="6b691-202">Anda sekarang dapat meninjau penjelasan model kehilangan pelanggan langganan.</span><span class="sxs-lookup"><span data-stu-id="6b691-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="6b691-203">Untuk informasi lebih lanjut, lihat [meninjau status dan hasil prediksi](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="6b691-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="6b691-204">Tugas 5-membuat segmen pelanggan berisiko kehilangan tinggi</span><span class="sxs-lookup"><span data-stu-id="6b691-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="6b691-205">Menjalankan model produksi membuat entitas baru yang dapat Anda lihat di **data** > **entitas**.</span><span class="sxs-lookup"><span data-stu-id="6b691-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="6b691-206">Anda dapat membuat segmen baru berdasarkan entitas yang dibuat oleh model.</span><span class="sxs-lookup"><span data-stu-id="6b691-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="6b691-207">Buka **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="6b691-207">Go to **Segments**.</span></span> <span data-ttu-id="6b691-208">Pilih **baru** lalu pilih **buat dari** > **intelijen**.</span><span class="sxs-lookup"><span data-stu-id="6b691-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Membuat segmen dengan output model.":::

1. <span data-ttu-id="6b691-210">Pilih titik akhir **OOBSubscriptionChurnPrediction** dan tentukan segmen:</span><span class="sxs-lookup"><span data-stu-id="6b691-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="6b691-211">Bidang: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="6b691-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="6b691-212">Operator: Lebih besar dari</span><span class="sxs-lookup"><span data-stu-id="6b691-212">Operator: greater than</span></span>
   - <span data-ttu-id="6b691-213">Nilai: 0,6</span><span class="sxs-lookup"><span data-stu-id="6b691-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Siapkan segmen kehilangan pelangganlangganan.":::

<span data-ttu-id="6b691-215">Anda sekarang memiliki segmen yang diperbarui secara dinamis yang mengidentifikasi pelanggan berisiko kehilangan pelanggantinggi untuk bisnis langganan ini.</span><span class="sxs-lookup"><span data-stu-id="6b691-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="6b691-216">Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6b691-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]