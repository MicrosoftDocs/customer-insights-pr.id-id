---
title: Panduan sampel prediksi kehilangan pelanggan langganan
description: Gunakan contoh panduan ini untuk mencoba model prediksi kehilangan pelanggan langganan bawaan.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 324e5c19778230dd978b2f4e9156a2dd82b3d2bd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595522"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="d433f-103">Panduan sampel prediksi kehilangan pelanggan langganan (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="d433f-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="d433f-104">Kami akan menjelaskan kepada Anda contoh akhir dari prediksi kehilangan pelanggan langganan menggunakan data sampel yang diberikan di bawah ini.</span><span class="sxs-lookup"><span data-stu-id="d433f-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="d433f-105">Skenario</span><span class="sxs-lookup"><span data-stu-id="d433f-105">Scenario</span></span>

<span data-ttu-id="d433f-106">Aswono adalah perusahaan yang memproduksi mesin kopi dan kopi berkualitas tinggi, yang dijual melalui situs web Kopi Aswono.</span><span class="sxs-lookup"><span data-stu-id="d433f-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="d433f-107">Mereka baru saja memulai bisnis langganan untuk pelanggan mereka agar mendapatkan kopi secara teratur.</span><span class="sxs-lookup"><span data-stu-id="d433f-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="d433f-108">Tujuannya adalah untuk memahami, pelanggan langganan mana yang dapat membatalkan langganan dalam beberapa bulan ke depan.</span><span class="sxs-lookup"><span data-stu-id="d433f-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="d433f-109">Mengetahui pelanggan mana yang **cenderung pergi**, dapat membantu mereka menyelamatkan upaya pemasaran dengan berfokus pada menjaganya.</span><span class="sxs-lookup"><span data-stu-id="d433f-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d433f-110">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="d433f-110">Prerequisites</span></span>

- <span data-ttu-id="d433f-111">Sekurangnya [izin kontributor](permissions.md) di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d433f-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="d433f-112">Sebaiknya Anda menerapkan langkah-langkah berikut [di lingkungan baru](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="d433f-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="d433f-113">Tugas 1- Serap Data</span><span class="sxs-lookup"><span data-stu-id="d433f-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="d433f-114">Tinjau artikel [tentang konsumsi data](data-sources.md) dan [mengimpor sumber data menggunakan konektor connector](connect-power-query.md) secara khusus.</span><span class="sxs-lookup"><span data-stu-id="d433f-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="d433f-115">Informasi berikut ini mengasumsikan bahwa Anda telah mengenal dan menyerap data secara umum.</span><span class="sxs-lookup"><span data-stu-id="d433f-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="d433f-116">Menyerap data pelanggan dari platform eCommerce</span><span class="sxs-lookup"><span data-stu-id="d433f-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="d433f-117">Buat sumber data bernama **eCommerce**, pilih pilihan impor, dan pilih konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d433f-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d433f-118">Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="d433f-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="d433f-119">Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.</span><span class="sxs-lookup"><span data-stu-id="d433f-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d433f-120">Perbarui DataType untuk kolom yang tercantum di bawah ini:</span><span class="sxs-lookup"><span data-stu-id="d433f-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="d433f-121">**DateOfBirth**: tanggal</span><span class="sxs-lookup"><span data-stu-id="d433f-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="d433f-122">**CreatedOn**: Tanggal/Waktu/Zona</span><span class="sxs-lookup"><span data-stu-id="d433f-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Ubah tanggal lahir sampai saat ini.":::

1. <span data-ttu-id="d433f-124">Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="d433f-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="d433f-125">Simpan Sumber Data.</span><span class="sxs-lookup"><span data-stu-id="d433f-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="d433f-126">Menyerap data pelanggan dari skema kesetiaan</span><span class="sxs-lookup"><span data-stu-id="d433f-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="d433f-127">Buat sumber data bernama **LoyaltyScheme**, pilih pilihan impor, dan pilih konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d433f-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d433f-128">Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="d433f-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="d433f-129">Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.</span><span class="sxs-lookup"><span data-stu-id="d433f-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d433f-130">Perbarui DataType untuk kolom yang tercantum di bawah ini:</span><span class="sxs-lookup"><span data-stu-id="d433f-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="d433f-131">**DateOfBirth**: tanggal</span><span class="sxs-lookup"><span data-stu-id="d433f-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="d433f-132">**RewardsPoints**: Bilangan Cacah</span><span class="sxs-lookup"><span data-stu-id="d433f-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="d433f-133">**CreatedOn**: Waktu/Tanggal</span><span class="sxs-lookup"><span data-stu-id="d433f-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="d433f-134">Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d433f-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="d433f-135">Simpan Sumber Data.</span><span class="sxs-lookup"><span data-stu-id="d433f-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="d433f-136">Serap Informasi Langganan</span><span class="sxs-lookup"><span data-stu-id="d433f-136">Ingest subscription information</span></span>

1. <span data-ttu-id="d433f-137">Buat sumber data bernama **subscriptionhistory**, pilih pilihan impor, dan pilih konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d433f-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d433f-138">Masukkan URL untuk kontak eCommerce https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="d433f-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="d433f-139">Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.</span><span class="sxs-lookup"><span data-stu-id="d433f-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d433f-140">Perbarui DataType untuk kolom yang tercantum di bawah ini:</span><span class="sxs-lookup"><span data-stu-id="d433f-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="d433f-141">**SubscriptioID**: Bilangan Cacah</span><span class="sxs-lookup"><span data-stu-id="d433f-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="d433f-142">**SubscriptionAmount**: Mata uang</span><span class="sxs-lookup"><span data-stu-id="d433f-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="d433f-143">**SubscriptionEndDate**: tanggal waktu</span><span class="sxs-lookup"><span data-stu-id="d433f-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="d433f-144">**SubscriptionStartDate**: Date/Time</span><span class="sxs-lookup"><span data-stu-id="d433f-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="d433f-145">**TransactionDate**: Date/Time</span><span class="sxs-lookup"><span data-stu-id="d433f-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="d433f-146">**IsRecurring**: Benar/salah</span><span class="sxs-lookup"><span data-stu-id="d433f-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="d433f-147">**Is_auto_renew**: Benar/Salah</span><span class="sxs-lookup"><span data-stu-id="d433f-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="d433f-148">**RecurringFrequencyInMonths**: Bilangan Cacah</span><span class="sxs-lookup"><span data-stu-id="d433f-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="d433f-149">Di bidang **nama** pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **subscriptionhistory**.</span><span class="sxs-lookup"><span data-stu-id="d433f-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="d433f-150">Simpan Sumber Data.</span><span class="sxs-lookup"><span data-stu-id="d433f-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="d433f-151">Serap data pelanggan dari ulasan situs</span><span class="sxs-lookup"><span data-stu-id="d433f-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="d433f-152">Buat sumber data bernama **Situs web**, pilih pilihan impor, dan pilih konektor **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="d433f-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="d433f-153">Masukkan URL untuk kontak eCommerce https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="d433f-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="d433f-154">Saat mengedit data, pilih **Ubah** dan kemudian **gunakan baris pertama sebagai header**.</span><span class="sxs-lookup"><span data-stu-id="d433f-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="d433f-155">Perbarui DataType untuk kolom yang tercantum di bawah ini:</span><span class="sxs-lookup"><span data-stu-id="d433f-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="d433f-156">**Bilangan Bulat**: Bilangan Cacah</span><span class="sxs-lookup"><span data-stu-id="d433f-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="d433f-157">**ReviewDate**: tanggal</span><span class="sxs-lookup"><span data-stu-id="d433f-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="d433f-158">Di bidang ' nama ' pada panel sisi kanan, ganti nama sumber data dari **kueri** menjadi **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="d433f-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="d433f-159">Tugas 2-penyatuan data</span><span class="sxs-lookup"><span data-stu-id="d433f-159">Task 2 - Data unification</span></span>

<span data-ttu-id="d433f-160">Setelah menyerap data, kita sekarang memulai proses **Memetakan, Mencocokkan, menggabungkan** untuk membuat profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="d433f-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="d433f-161">Untuk informasi selengkapnya, lihat [Penyatuan data](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="d433f-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="d433f-162">Peta</span><span class="sxs-lookup"><span data-stu-id="d433f-162">Map</span></span>

1. <span data-ttu-id="d433f-163">Setelah menyerap data, Petakan kontak dari eCommerce dan data kesetiaan ke jenis data umum.</span><span class="sxs-lookup"><span data-stu-id="d433f-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="d433f-164">Buka **Data** > **Satukan** > **Petakan**.</span><span class="sxs-lookup"><span data-stu-id="d433f-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="d433f-165">Pilih entitas yang menunjukkan profil pelanggan- **ecommercecontacts** dan **loycustomer**.</span><span class="sxs-lookup"><span data-stu-id="d433f-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="menyatukan sumber data eCommerce dan kesetiaan.":::

1. <span data-ttu-id="d433f-167">Pilih **contactid** sebagai kunci primer untuk **ecommercecontacts** dan **loyaltyid** sebagai kunci primer untuk **loycustomer**.</span><span class="sxs-lookup"><span data-stu-id="d433f-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Menyatukan LoyaltyId sebagai kunci primer.":::

### <a name="match"></a><span data-ttu-id="d433f-169">Cocokkan</span><span class="sxs-lookup"><span data-stu-id="d433f-169">Match</span></span>

1. <span data-ttu-id="d433f-170">Pergi ke tab **Cocokkan** dan pilih **Atur Urutan**.</span><span class="sxs-lookup"><span data-stu-id="d433f-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="d433f-171">Di daftar drop-down **utama**, pilih **ecommercecontacts: eCommerce** sebagai sumber utama dan mencakup semua rekaman.</span><span class="sxs-lookup"><span data-stu-id="d433f-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="d433f-172">Pada daftar drop-down **entitas 2**, pilih **Loycustomer: LoyaltyScheme** dan sertakan semua rekaman.</span><span class="sxs-lookup"><span data-stu-id="d433f-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Satukan dan cocokkan eCommerce dan Loyalty.":::

1. <span data-ttu-id="d433f-174">Pilih **Buat aturan baru**</span><span class="sxs-lookup"><span data-stu-id="d433f-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="d433f-175">Tambahkan kondisi pertama Anda menggunakan FullName.</span><span class="sxs-lookup"><span data-stu-id="d433f-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="d433f-176">Untuk eCommerceContacts, pilih **fullname** di drop-down.</span><span class="sxs-lookup"><span data-stu-id="d433f-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="d433f-177">Untuk loyCustomers, pilih **fullname** di drop-down.</span><span class="sxs-lookup"><span data-stu-id="d433f-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="d433f-178">Pilih drop-down **normalkan** dan pilih **jenis (telepon, nama, alamat,...)**.</span><span class="sxs-lookup"><span data-stu-id="d433f-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="d433f-179">Atur **tingkat presisi**: **dasar** dan **nilai**: **tinggi**.</span><span class="sxs-lookup"><span data-stu-id="d433f-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="d433f-180">Masukkan nama **fullname, email** untuk aturan baru.</span><span class="sxs-lookup"><span data-stu-id="d433f-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="d433f-181">Tambahkan kondisi kedua untuk alamat email dengan memilih **Tambah kondisi**</span><span class="sxs-lookup"><span data-stu-id="d433f-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="d433f-182">Untuk eCommerceContacts entitas, pilih **email** di drop-down.</span><span class="sxs-lookup"><span data-stu-id="d433f-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="d433f-183">Untuk loyCustomers entitas, pilih **email** di drop-down.</span><span class="sxs-lookup"><span data-stu-id="d433f-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="d433f-184">Biarkan Normalkan kosong.</span><span class="sxs-lookup"><span data-stu-id="d433f-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="d433f-185">Atur **tingkat presisi**: **dasar** dan **nilai**: **tinggi**.</span><span class="sxs-lookup"><span data-stu-id="d433f-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Satukan aturan kecocokan untuk nama dan email.":::

7. <span data-ttu-id="d433f-187">Pilih **Simpan** dan **Tutup**.</span><span class="sxs-lookup"><span data-stu-id="d433f-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="d433f-188">Penggabungan</span><span class="sxs-lookup"><span data-stu-id="d433f-188">Merge</span></span>

1. <span data-ttu-id="d433f-189">Buka tab **Gabungkan**.</span><span class="sxs-lookup"><span data-stu-id="d433f-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="d433f-190">Pada entitas **contactid** untuk **loycustomer**, ubah nama tampilan ke **contactidloyalty** untuk membedakannya dari id lain yang diserap.</span><span class="sxs-lookup"><span data-stu-id="d433f-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="Ubah nama contactid dari Loyalty id.":::

1. <span data-ttu-id="d433f-192">Pilih **Simpan** dan **Jalankan** untuk memulai proses penggabungan.</span><span class="sxs-lookup"><span data-stu-id="d433f-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="d433f-193">Tugas 3-konfigurasi prediksi kehilangan pelanggan langganan</span><span class="sxs-lookup"><span data-stu-id="d433f-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="d433f-194">Dengan profil pelanggan terpadu di tempatnya, kini kita dapat menjalankan prediksi kehilangan pelanggan langganan.</span><span class="sxs-lookup"><span data-stu-id="d433f-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="d433f-195">Untuk langkah rinci, lihat artikel [prediksi kehilangan pelanggan langganan](predict-subscription-churn.md) (pratinjau).</span><span class="sxs-lookup"><span data-stu-id="d433f-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="d433f-196">Buka **intelijen** > **Temukan** dan pilih untuk menggunakan **model kehilangan pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="d433f-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="d433f-197">Pilih pilihan **langganan** dan pilih **Mulai**.</span><span class="sxs-lookup"><span data-stu-id="d433f-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="d433f-198">Namai model **prediksi kehilangan pelanggan langganan oob** dan entitas output **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="d433f-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="d433f-199">Tentukan dua kondisi untuk model kehilangan pelanggan:</span><span class="sxs-lookup"><span data-stu-id="d433f-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="d433f-200">**Hari sejak langganan berakhir**: **minimal 60** hari.</span><span class="sxs-lookup"><span data-stu-id="d433f-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="d433f-201">Jika pelanggan tidak memperpanjang langganan dalam periode setelah langganan berakhir, mereka dianggap telah pergi.</span><span class="sxs-lookup"><span data-stu-id="d433f-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="d433f-202">**Definisi kehilangan pelanggan**: **minimal 93** hari.</span><span class="sxs-lookup"><span data-stu-id="d433f-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="d433f-203">Durasi yang diprediksi model tentang pelanggan mana yang mungkin pergi.</span><span class="sxs-lookup"><span data-stu-id="d433f-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="d433f-204">Semakin jauh di masa depan Anda melihat, semakin kurang tepat hasilnya.</span><span class="sxs-lookup"><span data-stu-id="d433f-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="pilih jendela prediksi pengungkit model dan definisi kehilangan pelanggan.":::

1. <span data-ttu-id="d433f-206">Pilih **Tambah data yang diperlukan** dan pilih **Tambah data** untuk Riwayat langganan.</span><span class="sxs-lookup"><span data-stu-id="d433f-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="d433f-207">Tambahkan entitas **langganan: SubscriptionHistory** dan Petakan bidang dari eCommerce ke bidang terkait yang diperlukan oleh model.</span><span class="sxs-lookup"><span data-stu-id="d433f-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="d433f-208">Bergabung dengan entitas **langganan: SubscriptionHistory** dengan **ecommercecontacts: eCommerce**, namai relasi **ecommercesubscription**.</span><span class="sxs-lookup"><span data-stu-id="d433f-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Bergabung dengan entitas e-commerce.":::

1. <span data-ttu-id="d433f-210">Dalam aktivitas pelanggan, tambahkan entitas **webreview: situs web** dan petakan bidang dari webreview ke bidang terkait yang diperlukan oleh model.</span><span class="sxs-lookup"><span data-stu-id="d433f-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="d433f-211">Kunci utama: ReviewId</span><span class="sxs-lookup"><span data-stu-id="d433f-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="d433f-212">Tanda Waktu: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="d433f-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="d433f-213">aktivitas: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="d433f-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="d433f-214">Konfigurasikan aktivitas untuk ulasan situs.</span><span class="sxs-lookup"><span data-stu-id="d433f-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="d433f-215">Pilih aktivitas **peninjauan** dan gabung dengan entitas **Webreview: website** dengan **Ecommercecontacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="d433f-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="d433f-216">Pilih **berikutnya** untuk mengatur jadwal model.</span><span class="sxs-lookup"><span data-stu-id="d433f-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="d433f-217">Model harus dilatih secara teratur untuk mempelajari pola baru bila ada data baru yang terserap.</span><span class="sxs-lookup"><span data-stu-id="d433f-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="d433f-218">Untuk contoh ini, pilih **bulanan**.</span><span class="sxs-lookup"><span data-stu-id="d433f-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="d433f-219">Setelah meninjau semua rincian, pilih **Simpan dan jalankan**.</span><span class="sxs-lookup"><span data-stu-id="d433f-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="d433f-220">Tugas 4-TInjau hasil dan penjelasan model</span><span class="sxs-lookup"><span data-stu-id="d433f-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="d433f-221">Biarkan model menyelesaikan pelatihan dan penilaian data.</span><span class="sxs-lookup"><span data-stu-id="d433f-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="d433f-222">Anda sekarang dapat meninjau penjelasan model kehilangan pelanggan langganan.</span><span class="sxs-lookup"><span data-stu-id="d433f-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="d433f-223">Untuk informasi lebih lanjut, lihat [meninjau status dan hasil prediksi](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="d433f-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="d433f-224">Tugas 5-membuat segmen pelanggan berisiko kehilangan tinggi</span><span class="sxs-lookup"><span data-stu-id="d433f-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="d433f-225">Menjalankan model produksi membuat entitas baru yang dapat Anda lihat di **data** > **entitas**.</span><span class="sxs-lookup"><span data-stu-id="d433f-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="d433f-226">Anda dapat membuat segmen baru berdasarkan entitas yang dibuat oleh model.</span><span class="sxs-lookup"><span data-stu-id="d433f-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="d433f-227">Buka **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="d433f-227">Go to **Segments**.</span></span> <span data-ttu-id="d433f-228">Pilih **baru** lalu pilih **buat dari** > **intelijen**.</span><span class="sxs-lookup"><span data-stu-id="d433f-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Membuat segmen dengan output model.":::

1. <span data-ttu-id="d433f-230">Pilih titik akhir **OOBSubscriptionChurnPrediction** dan tentukan segmen:</span><span class="sxs-lookup"><span data-stu-id="d433f-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="d433f-231">Bidang: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="d433f-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="d433f-232">Operator: Lebih besar dari</span><span class="sxs-lookup"><span data-stu-id="d433f-232">Operator: greater than</span></span>
   - <span data-ttu-id="d433f-233">Nilai: 0,6</span><span class="sxs-lookup"><span data-stu-id="d433f-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Siapkan segmen kehilangan pelangganlangganan.":::

<span data-ttu-id="d433f-235">Anda sekarang memiliki segmen yang diperbarui secara dinamis yang mengidentifikasi pelanggan berisiko kehilangan pelanggantinggi untuk bisnis langganan ini.</span><span class="sxs-lookup"><span data-stu-id="d433f-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="d433f-236">Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="d433f-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]