---
title: Sambungkan data Common Data Model ke akun Azure Data Lake
description: Bekerja dengan Common Data Model menggunakan Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596549"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="1ec36-103">Sambungkan ke folder Common Data Model dengan akun Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="1ec36-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="1ec36-104">Artikel ini memberikan informasi tentang cara menyerap data dari folder Common Data Model menggunakan akun Azure Data Lake Storage Gen2 Anda.</span><span class="sxs-lookup"><span data-stu-id="1ec36-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="1ec36-105">Pertimbangan penting</span><span class="sxs-lookup"><span data-stu-id="1ec36-105">Important considerations</span></span>

- <span data-ttu-id="1ec36-106">Data di Azure Data Lake data harus mengikuti standar Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="1ec36-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="1ec36-107">Format lain tidak didukung saat ini.</span><span class="sxs-lookup"><span data-stu-id="1ec36-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="1ec36-108">Konsumsi data mendukung akun penyimpanan Azure data Lake *Gen2* secara eksklusif.</span><span class="sxs-lookup"><span data-stu-id="1ec36-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="1ec36-109">Anda tidak dapat menggunakan akun penyimpanan Azure Data Lake Gen1 untuk menyerap data.</span><span class="sxs-lookup"><span data-stu-id="1ec36-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="1ec36-110">Untuk mengautentikasi dengan prinsipal Layanan Azure, pastikan perangkat dikonfigurasi di penyewa Anda.</span><span class="sxs-lookup"><span data-stu-id="1ec36-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="1ec36-111">Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="1ec36-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="1ec36-112">Azure Data Lake yang akan disambungkan dan diserap datanya harus berada di kawasan Azure yang sama dengan lingkungan Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1ec36-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="1ec36-113">Koneksi ke folder Common Data Model dari Data Lake di kawasan Azure berbeda tidak didukung.</span><span class="sxs-lookup"><span data-stu-id="1ec36-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="1ec36-114">Untuk mengetahui kawasan Azure lingkungan, buka **Admin** > **sistem** > **tentang** di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="1ec36-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="1ec36-115">Data yang tersimpan di layanan online, dapat disimpan di lokasi yang berbeda dengan data yang diproses atau disimpan di Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1ec36-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="1ec36-116">Dengan mengimpor atau menyambung ke data yang tersimpan di layanan online, Anda setuju bahwa data dapat ditransfer ke dan disimpan dengan Dynamics 365 Customer Insights. [Pelajari lebih lanjut di pusat kepercayaan Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="1ec36-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="1ec36-117">Sambungkan ke folder Model Data Umum</span><span class="sxs-lookup"><span data-stu-id="1ec36-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="1ec36-118">Di wawasan audiens, buka **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="1ec36-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="1ec36-119">Pilih **Tambahkan sumber data**.</span><span class="sxs-lookup"><span data-stu-id="1ec36-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="1ec36-120">Pilih **sambungkan ke folder Common Data Model**, masukkan **nama** untuk sumber data, lalu pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="1ec36-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="1ec36-121">Panduan nama:</span><span class="sxs-lookup"><span data-stu-id="1ec36-121">Name guidelines:</span></span> 
   - <span data-ttu-id="1ec36-122">Diawali dengan huruf.</span><span class="sxs-lookup"><span data-stu-id="1ec36-122">Start with a letter.</span></span>
   - <span data-ttu-id="1ec36-123">Gunakan huruf dan angka saja.</span><span class="sxs-lookup"><span data-stu-id="1ec36-123">Use letters and numbers only.</span></span> <span data-ttu-id="1ec36-124">Spasi atau karakter khusus tidak dibolehkan.</span><span class="sxs-lookup"><span data-stu-id="1ec36-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="1ec36-125">Gunakan antara 3 hingga 64 karakter.</span><span class="sxs-lookup"><span data-stu-id="1ec36-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="1ec36-126">Anda dapat memilih antara menggunakan pilihan berbasis sumber daya dan pilihan berbasis langganan untuk autentikasi.</span><span class="sxs-lookup"><span data-stu-id="1ec36-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="1ec36-127">Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="1ec36-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="1ec36-128">Masukkan informasi **penampung** dan pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="1ec36-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ec36-129">![Kotak dialog untuk memasukkan rincian sambungan baru untuk Azure Data Lake](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="1ec36-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="1ec36-130">Anda memerlukan salah satu peran berikut, baik untuk wadah atau akun penyimpanan yang dirujuk di atas agar dapat terhubung dan membuat sumber data:</span><span class="sxs-lookup"><span data-stu-id="1ec36-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="1ec36-131">Pembaca Data Blob Penyimpanan</span><span class="sxs-lookup"><span data-stu-id="1ec36-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="1ec36-132">pemilik Data Blob Penyimpanan</span><span class="sxs-lookup"><span data-stu-id="1ec36-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="1ec36-133">Kontributor data Blob penyimpanan</span><span class="sxs-lookup"><span data-stu-id="1ec36-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="1ec36-134">Di dialog **Pilih folder Common Data Model**, pilih file model.JSON atau manifest.json untuk diimpor datanya, lalu pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="1ec36-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="1ec36-135">File model.json atau manifest.json yang terkait dengan sumber data lain di lingkungan tidak akan ditampilkan dalam daftar.</span><span class="sxs-lookup"><span data-stu-id="1ec36-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="1ec36-136">Anda akan mendapatkan daftar entitas yang tersedia dalam file model.json atau manifest.json yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="1ec36-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="1ec36-137">Anda dapat meninjau dan memilih dari daftar entitas yang tersedia dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="1ec36-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="1ec36-138">Semua entitas yang dipilih akan diserap dari sumber data baru.</span><span class="sxs-lookup"><span data-stu-id="1ec36-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ec36-139">![Kotak dialog menampilkan daftar entitas dari file model.JSON](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="1ec36-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="1ec36-140">Tunjukkan entitas data mana yang Anda inginkan untuk mengaktifkan pembuatan profil data dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="1ec36-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="1ec36-141">Pembuatan profil data memungkinkan kemampuan analitik dan kemampuan lainnya.</span><span class="sxs-lookup"><span data-stu-id="1ec36-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="1ec36-142">Anda dapat memilih seluruh entitas, yang memilih semua atribut dari entitas, atau memilih atribut tertentu pilihan Anda.</span><span class="sxs-lookup"><span data-stu-id="1ec36-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="1ec36-143">Secara default, entitas tidak diaktifkan untuk pembuatan profil data.</span><span class="sxs-lookup"><span data-stu-id="1ec36-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1ec36-144">![Kotak dialog menampilkan profil data](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="1ec36-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="1ec36-145">Setelah menyimpan pilihan, halaman **sumber data** akan terbuka.</span><span class="sxs-lookup"><span data-stu-id="1ec36-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="1ec36-146">Anda seharusnya sekarang melihat koneksi folder Common Data Model sebagai sumber data.</span><span class="sxs-lookup"><span data-stu-id="1ec36-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec36-147">File model.json atau manifest.json hanya dapat dikaitkan dengan satu sumber data di lingkungan yang sama.</span><span class="sxs-lookup"><span data-stu-id="1ec36-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="1ec36-148">Namun, file model.json atau manifest.json yang sama dapat digunakan untuk sumber data di beberapa lingkungan.</span><span class="sxs-lookup"><span data-stu-id="1ec36-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="1ec36-149">Mengedit sumber data folder Common Data Model</span><span class="sxs-lookup"><span data-stu-id="1ec36-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="1ec36-150">Anda dapat memperbarui kunci akses untuk akun penyimpanan yang berisi folder Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="1ec36-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="1ec36-151">Anda juga dapat mengubah file model.json atau manifest.json.</span><span class="sxs-lookup"><span data-stu-id="1ec36-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="1ec36-152">Untuk menyambung ke kontainer lain dari akun penyimpanan, atau mengubah nama akun, buat [sambungan sumber data baru](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="1ec36-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="1ec36-153">Di wawasan audiens, buka **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="1ec36-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="1ec36-154">Di samping sumber data yang ingin anda perbarui, pilih elipsis.</span><span class="sxs-lookup"><span data-stu-id="1ec36-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="1ec36-155">Pilih opsi **Edit** dari daftar.</span><span class="sxs-lookup"><span data-stu-id="1ec36-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="1ec36-156">Atau, perbarui **tombol akses** dan pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="1ec36-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialog untuk mengedit dan memperbarui kunci akses untuk sumber data yang ada](media/edit-access-key.png)

5. <span data-ttu-id="1ec36-158">Atau, Anda dapat memperbarui dari sambungan kunci akun ke sambungan berbasis sumber daya atau berbasis langganan.</span><span class="sxs-lookup"><span data-stu-id="1ec36-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="1ec36-159">Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="1ec36-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="1ec36-160">Anda tidak dapat **mengubah** informasi penampung saat memperbarui sambungan.</span><span class="sxs-lookup"><span data-stu-id="1ec36-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![Kotak dialog untuk memasukkan rincian sambungan untuk Azure Data Lake ke akun penyimpanan yang ada](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="1ec36-162">Anda memerlukan salah satu peran berikut, baik untuk wadah atau akun penyimpanan yang dirujuk di atas agar dapat terhubung dan membuat sumber data:</span><span class="sxs-lookup"><span data-stu-id="1ec36-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="1ec36-163">Pembaca Data Blob Penyimpanan</span><span class="sxs-lookup"><span data-stu-id="1ec36-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="1ec36-164">pemilik Data Blob Penyimpanan</span><span class="sxs-lookup"><span data-stu-id="1ec36-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="1ec36-165">Kontributor data Blob penyimpanan</span><span class="sxs-lookup"><span data-stu-id="1ec36-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="1ec36-166">Atau, pilih file model.json atau manifest.json dengan rangkaian entitas yang berbeda dari wadah.</span><span class="sxs-lookup"><span data-stu-id="1ec36-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="1ec36-167">Atau, Anda dapat memilih entitas tambahan untuk diserap.</span><span class="sxs-lookup"><span data-stu-id="1ec36-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="1ec36-168">Anda juga dapat menghapus entitas yang telah dipilih jika tidak ada dependensi.</span><span class="sxs-lookup"><span data-stu-id="1ec36-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="1ec36-169">Jika ada dependensi pada file model.json atau manifest.json yang ada dan rangkaian entitas, Anda akan melihat pesan kesalahan dan tidak dapat memilih file model.json atau json yang berbeda.</span><span class="sxs-lookup"><span data-stu-id="1ec36-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="1ec36-170">Hilangkan dependensi tersebut sebelum mengubah file model.json atau manifest.json atau buat sumber data baru dengan file model.json atau manifest.json yang ingin Anda gunakan untuk menghindari dependensi dihapus.</span><span class="sxs-lookup"><span data-stu-id="1ec36-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="1ec36-171">Atau, Anda dapat memilih atribut atau entitas tambahan untuk mengaktifkan pemrofilan data atau menonaktifkan yang telah dipilih.</span><span class="sxs-lookup"><span data-stu-id="1ec36-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]