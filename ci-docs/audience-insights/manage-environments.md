---
title: Membuat dan mengelola lingkungan
description: Pelajari cara mendaftar ke layanan dan cara mengelola lingkungan.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 744f0bcbf5d2700363180f44e38d6dee9bf5df63
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270116"
---
# <a name="manage-environments"></a><span data-ttu-id="d67dc-103">Kelola lingkungan</span><span class="sxs-lookup"><span data-stu-id="d67dc-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d67dc-104">Artikel ini menjelaskan cara membuat organisasi baru dan cara menyediakan lingkungan.</span><span class="sxs-lookup"><span data-stu-id="d67dc-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="d67dc-105">Mendaftar dan membuat organisasi</span><span class="sxs-lookup"><span data-stu-id="d67dc-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="d67dc-106">Kunjungi situs web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="d67dc-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="d67dc-107">Pilih **Mulai**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="d67dc-108">Pilih skenario daftar pilihan Anda dan pilih tautan yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="d67dc-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="d67dc-109">Setujui persyaratan dan ketentuan, lalu pilih **Lanjutkan** untuk mulai membuat organisasi.</span><span class="sxs-lookup"><span data-stu-id="d67dc-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="d67dc-110">Setelah lingkungan dibuat, Anda akan diarahkan ke [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="d67dc-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="d67dc-111">Gunakan lingkungan demo untuk menjelajahi aplikasi, atau membuat lingkungan baru dengan mengikuti langkah di bagian berikutnya.</span><span class="sxs-lookup"><span data-stu-id="d67dc-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="d67dc-112">Setelah menentukan pengaturan lingkungan, pilih **buat**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="d67dc-113">Anda akan masuk setelah lingkungan berhasil dibuat.</span><span class="sxs-lookup"><span data-stu-id="d67dc-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="d67dc-114">Membuat lingkungan di organisasi yang ada</span><span class="sxs-lookup"><span data-stu-id="d67dc-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="d67dc-115">Terdapat dua cara untuk membuat lingkungan baru.</span><span class="sxs-lookup"><span data-stu-id="d67dc-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="d67dc-116">Anda dapat menentukan konfigurasi yang sama sekali baru atau Anda dapat menyalin beberapa pengaturan konfigurasi dari lingkungan yang ada.</span><span class="sxs-lookup"><span data-stu-id="d67dc-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="d67dc-117">Untuk membuat lingkungan:</span><span class="sxs-lookup"><span data-stu-id="d67dc-117">To create an environment:</span></span>

1. <span data-ttu-id="d67dc-118">Pilih pemilih **Lingkungan** di header aplikasi.</span><span class="sxs-lookup"><span data-stu-id="d67dc-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="d67dc-119">Pilih **baru**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d67dc-120">![Pengaturan Lingkungan](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="d67dc-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="d67dc-121">Di dialog **buat lingkungan baru**, pilih **lingkungan baru**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="d67dc-122">Jika Anda ingin [menyalin data dari lingkungan saat ini](#additional-considerations-for-copy-configuration-preview), pilih **salinan dari lingkungan yang ada**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="d67dc-123">Anda akan melihat daftar semua lingkungan yang tersedia di organisasi tempat Anda dapat menyalin data.</span><span class="sxs-lookup"><span data-stu-id="d67dc-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="d67dc-124">Sediakan rincian berikut:</span><span class="sxs-lookup"><span data-stu-id="d67dc-124">Provide the following details:</span></span>
   - <span data-ttu-id="d67dc-125">**Nama**: Ketik nama untuk lingkungan ini.</span><span class="sxs-lookup"><span data-stu-id="d67dc-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="d67dc-126">Bidang ini telah diisi jika Anda telah menyalin dari lingkungan yang ada, namun Anda dapat mengubahnya.</span><span class="sxs-lookup"><span data-stu-id="d67dc-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="d67dc-127">**Kawasan**: kawasan tempat layanan disebarkan dan dihosting.</span><span class="sxs-lookup"><span data-stu-id="d67dc-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="d67dc-128">**Jenis**: Pilih Apakah Anda ingin membuat lingkungan produksi atau Sandbox.</span><span class="sxs-lookup"><span data-stu-id="d67dc-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="d67dc-129">Atau, Anda dapat memilih **pengaturan tingkat lanjut**:</span><span class="sxs-lookup"><span data-stu-id="d67dc-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="d67dc-130">**Simpan semua data ke**: menentukan lokasi penyimpanan data output yang dihasilkan dari Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d67dc-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="d67dc-131">Anda akan memiliki dua pilihan: **penyimpanan Customer Insights** (Azure Data Lake yang dikelola oleh tim Customer Insights) dan **Azure Data Lake Storage Gen2** (Azure Data Lake Storage milik Anda).</span><span class="sxs-lookup"><span data-stu-id="d67dc-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="d67dc-132">Secara default, pilihan penyimpanan Customer Insights dipilih.</span><span class="sxs-lookup"><span data-stu-id="d67dc-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d67dc-133">Dengan menyimpan data ke Azure Data Lake Storage, Anda setuju bahwa data akan ditransfer ke dan disimpan di lokasi geografis yang sesuai untuk akun Azure Storage, yang mungkin berbeda dari lokasi penyimpanan data di Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d67dc-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="d67dc-134">Pelajari lebih lanjut di pusat kepercayaan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d67dc-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="d67dc-135">Saat ini, entitas yang diserap akan selalu tersimpan di data Lake yang dikelola oleh customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d67dc-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="d67dc-136">Kami hanya mendukung akun penyimpanan Azure data Lake Gen2 dari wilayah Azure yang sama yang Anda pilih saat membuat lingkungan.</span><span class="sxs-lookup"><span data-stu-id="d67dc-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="d67dc-137">Kami hanya mendukung akun penyimpanan yang diaktifkan Azure Data Lake Gen2 Hierarchical Name Space (HNS).</span><span class="sxs-lookup"><span data-stu-id="d67dc-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="d67dc-138">Untuk opsi Azure Data Lake Storage Gen2, Anda dapat memilih antara menggunakan pilihan berbasis sumber daya dan pilihan berbasis langganan untuk autentikasi.</span><span class="sxs-lookup"><span data-stu-id="d67dc-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="d67dc-139">Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="d67dc-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="d67dc-140">Nama **penampung** tidak dapat diubah dan akan menjadi "customerinsights".</span><span class="sxs-lookup"><span data-stu-id="d67dc-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="d67dc-141">Jika Anda ingin menggunakan [prediksi](predictions.md) atau mengkonfigurasikan berbagi data dengan aplikasi dan solusi berdasarkan Microsoft Dataverse, berikan URL lingkungan Microsoft Dataverse dalam **Konfigurasikan berbagi data dengan Microsoft Dataverse dan aktifkan kemampuan tambahan**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="d67dc-142">Pilih **Aktifkan berbagi data** untuk berbagi data output Customer Insights dengan Data Lake terkelola Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d67dc-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="d67dc-143">Berbagi data dengan Data Lake terkelola Microsoft Dataverse saat ini tidak didukung bila Anda menyimpan semua data untuk Azure Data Lake Storage Anda sendiri.</span><span class="sxs-lookup"><span data-stu-id="d67dc-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="d67dc-144">[Prediksi nilai yang tidak ada pada entitas](predictions.md) saat ini tidak didukung bila Anda mengaktifkan berbagi data dengan Data Lake terkelola Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d67dc-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="d67dc-145">![Pilihan konfigurasi untuk mengaktifkan berbagi data dengan Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="d67dc-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="d67dc-146">Bila Anda menjalankan proses, seperti konsumsi data atau pembuatan segmen, folder yang sesuai akan dibuat di akun penyimpanan yang Anda tentukan di atas.</span><span class="sxs-lookup"><span data-stu-id="d67dc-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="d67dc-147">File data dan file model .json akan dibuat dan ditambahkan ke subfolder masing-masing berdasarkan proses yang Anda jalankan.</span><span class="sxs-lookup"><span data-stu-id="d67dc-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="d67dc-148">Jika Anda membuat beberapa lingkungan dari Customer Insights dan memilih untuk menyimpan entitas output dari lingkungan tersebut di akun penyimpanan, folder terpisah akan dibuat untuk setiap lingkungan dengan ci_<environmentid> dalam penampung.</span><span class="sxs-lookup"><span data-stu-id="d67dc-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="d67dc-149">Pertimbangan tambahan untuk konfigurasi salinan (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="d67dc-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="d67dc-150">Pengaturan konfigurasi berikut disalin:</span><span class="sxs-lookup"><span data-stu-id="d67dc-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="d67dc-151">Konfigurasi fitur</span><span class="sxs-lookup"><span data-stu-id="d67dc-151">Feature configurations</span></span>
- <span data-ttu-id="d67dc-152">Sumber data yang diserap/diimpor</span><span class="sxs-lookup"><span data-stu-id="d67dc-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="d67dc-153">Konfigurasi penyatuan data (petakan, cocokkan, gabungkan)</span><span class="sxs-lookup"><span data-stu-id="d67dc-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="d67dc-154">Segmen</span><span class="sxs-lookup"><span data-stu-id="d67dc-154">Segments</span></span>
- <span data-ttu-id="d67dc-155">Tindakan</span><span class="sxs-lookup"><span data-stu-id="d67dc-155">Measures</span></span>
- <span data-ttu-id="d67dc-156">Relasi</span><span class="sxs-lookup"><span data-stu-id="d67dc-156">Relationships</span></span>
- <span data-ttu-id="d67dc-157">Aktivitas</span><span class="sxs-lookup"><span data-stu-id="d67dc-157">Activities</span></span>
- <span data-ttu-id="d67dc-158">Indeks Pencarian & filter</span><span class="sxs-lookup"><span data-stu-id="d67dc-158">Search & filter Index</span></span>
- <span data-ttu-id="d67dc-159">Tujuan ekspor</span><span class="sxs-lookup"><span data-stu-id="d67dc-159">Export destinations</span></span>
- <span data-ttu-id="d67dc-160">Refresh terjadwal</span><span class="sxs-lookup"><span data-stu-id="d67dc-160">Scheduled refresh</span></span>
- <span data-ttu-id="d67dc-161">Pengayaan</span><span class="sxs-lookup"><span data-stu-id="d67dc-161">Enrichments</span></span>
- <span data-ttu-id="d67dc-162">Manajemen model</span><span class="sxs-lookup"><span data-stu-id="d67dc-162">Model management</span></span>
- <span data-ttu-id="d67dc-163">Penetapan peran</span><span class="sxs-lookup"><span data-stu-id="d67dc-163">Role assignments</span></span>

<span data-ttu-id="d67dc-164">Pengaturan berikut *tidak* disalin:</span><span class="sxs-lookup"><span data-stu-id="d67dc-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="d67dc-165">Profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="d67dc-165">Customer profiles.</span></span>
- <span data-ttu-id="d67dc-166">Kredensial sumber data.</span><span class="sxs-lookup"><span data-stu-id="d67dc-166">Data source credentials.</span></span> <span data-ttu-id="d67dc-167">Anda harus memberikan kredensial untuk setiap sumber data dan menyegarkan sumber data secara manual.</span><span class="sxs-lookup"><span data-stu-id="d67dc-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="d67dc-168">Sumber data dari folder Common Data Model dan danau terkelola Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d67dc-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="d67dc-169">Anda harus membuat sumber data secara manual dengan nama yang sama seperti di lingkungan sumber.</span><span class="sxs-lookup"><span data-stu-id="d67dc-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="d67dc-170">Bila Anda menyalin lingkungan, Anda akan melihat pesan konfirmasi bahwa lingkungan baru telah dibuat.</span><span class="sxs-lookup"><span data-stu-id="d67dc-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="d67dc-171">Pilih **buka sumber data** untuk melihat daftar sumber data.</span><span class="sxs-lookup"><span data-stu-id="d67dc-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="d67dc-172">Semua sumber data akan menampilkan status **kredensial yang diperlukan**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="d67dc-173">Edit sumber data dan masukkan kredensial untuk me-refresh mereka.</span><span class="sxs-lookup"><span data-stu-id="d67dc-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d67dc-174">![Sumber data disalin](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="d67dc-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="d67dc-175">Setelah menyegarkan sumber data, buka **data** > **Satukan**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="d67dc-176">Di sini Anda akan menemukan pengaturan dari lingkungan sumber.</span><span class="sxs-lookup"><span data-stu-id="d67dc-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="d67dc-177">Edit sesuai kebutuhan atau pilih **Jalankan** untuk memulai proses penyatuan data dan buat entitas pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="d67dc-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="d67dc-178">Bila penyatuan data selesai, buka **langkah** dan **segmen** untuk me-refresh juga.</span><span class="sxs-lookup"><span data-stu-id="d67dc-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="d67dc-179">Edit lingkungan yang ada</span><span class="sxs-lookup"><span data-stu-id="d67dc-179">Edit an existing environment</span></span>

<span data-ttu-id="d67dc-180">Anda dapat mengedit beberapa rincian lingkungan yang ada.</span><span class="sxs-lookup"><span data-stu-id="d67dc-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="d67dc-181">Pilih pemilih **Lingkungan** di header aplikasi.</span><span class="sxs-lookup"><span data-stu-id="d67dc-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="d67dc-182">Pilih ikon **Edit**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="d67dc-183">Di kotak **Edit lingkungan**, Anda dapat memperbarui **nama tampilan** lingkungan, tetapi Anda tidak dapat mengubah **Kawasan** atau **Jenis**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="d67dc-184">Jika lingkungan dikonfigurasi untuk menyimpan data di Azure Data Lake Storage Gen2, Anda dapat memperbarui **kunci akun**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="d67dc-185">Namun, Anda tidak dapat mengubah **nama akun** atau nama **penampung**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="d67dc-186">Atau, Anda dapat memperbarui dari sambungan berbasis kunci akun ke sambungan berbasis sumber daya atau berbasis langganan.</span><span class="sxs-lookup"><span data-stu-id="d67dc-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="d67dc-187">Setelah ditingkatkan, Anda tidak dapat kembali ke kunci akun setelah pembaruan.</span><span class="sxs-lookup"><span data-stu-id="d67dc-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="d67dc-188">Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="d67dc-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="d67dc-189">Anda tidak dapat **mengubah** informasi penampung saat memperbarui sambungan.</span><span class="sxs-lookup"><span data-stu-id="d67dc-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="d67dc-190">Mengatur ulang lingkungan yang ada</span><span class="sxs-lookup"><span data-stu-id="d67dc-190">Reset an existing environment</span></span>

<span data-ttu-id="d67dc-191">Sebagai administrator, Anda dapat mengatur ulang lingkungan ke status kosong jika Anda ingin menghapus semua konfigurasi dan menghapus data yang diserap.</span><span class="sxs-lookup"><span data-stu-id="d67dc-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="d67dc-192">Pilih pemilih **Lingkungan** di header aplikasi.</span><span class="sxs-lookup"><span data-stu-id="d67dc-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="d67dc-193">Pilih lingkungan yang ingin Anda atur ulang dan pilih elipsis **...**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="d67dc-194">Pilih opsi **Atur ulang**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="d67dc-195">Untuk mengkonfirmasi penghapusan, masukkan nama lingkungan dan pilih **Atur ulang**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="d67dc-196">Menghapus lingkungan yang ada (hanya tersedia untuk admin)</span><span class="sxs-lookup"><span data-stu-id="d67dc-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="d67dc-197">Sebagai administrator, Anda dapat menghapus lingkungan yang dikelola.</span><span class="sxs-lookup"><span data-stu-id="d67dc-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="d67dc-198">Pilih pemilih **Lingkungan** di header aplikasi.</span><span class="sxs-lookup"><span data-stu-id="d67dc-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="d67dc-199">Pilih lingkungan yang ingin Anda atur ulang dan pilih elipsis **...**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="d67dc-200">Pilih opsi **Hapus**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="d67dc-201">Untuk mengonfirmasikan penghapusan, masukkan nama lingkungan dan pilih **Hapus**.</span><span class="sxs-lookup"><span data-stu-id="d67dc-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]