---
title: Sambungkan data Common Data Model ke akun Azure Data Lake
description: Bekerja dengan Common Data Model menggunakan Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643462"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="424fa-103">Sambungkan ke folder Common Data Model dengan akun Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="424fa-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="424fa-104">Artikel ini memberikan informasi tentang cara menyerap data dari folder Common Data Model menggunakan akun Azure Data Lake Storage Gen2 Anda.</span><span class="sxs-lookup"><span data-stu-id="424fa-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="424fa-105">Pertimbangan penting</span><span class="sxs-lookup"><span data-stu-id="424fa-105">Important considerations</span></span>

- <span data-ttu-id="424fa-106">Data di Azure Data Lake data harus mengikuti standar Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="424fa-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="424fa-107">Format lain tidak didukung saat ini.</span><span class="sxs-lookup"><span data-stu-id="424fa-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="424fa-108">Konsumsi data mendukung akun penyimpanan Azure data Lake *Gen2* secara eksklusif.</span><span class="sxs-lookup"><span data-stu-id="424fa-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="424fa-109">Anda tidak dapat menggunakan akun penyimpanan Azure Data Lake Gen1 untuk menyerap data.</span><span class="sxs-lookup"><span data-stu-id="424fa-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="424fa-110">Untuk mengautentikasi dengan prinsipal Layanan Azure, pastikan perangkat dikonfigurasi di penyewa Anda.</span><span class="sxs-lookup"><span data-stu-id="424fa-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="424fa-111">Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="424fa-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="424fa-112">Azure Data Lake yang akan disambungkan dan diserap datanya harus berada di kawasan Azure yang sama dengan lingkungan Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="424fa-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="424fa-113">Koneksi ke folder Common Data Model dari Data Lake di kawasan Azure berbeda tidak didukung.</span><span class="sxs-lookup"><span data-stu-id="424fa-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="424fa-114">Untuk mengetahui kawasan Azure lingkungan, buka **Admin** > **sistem** > **tentang** di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="424fa-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="424fa-115">Data yang tersimpan di layanan online, dapat disimpan di lokasi yang berbeda dengan data yang diproses atau disimpan di Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="424fa-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="424fa-116">Dengan mengimpor atau menyambung ke data yang tersimpan di layanan online, Anda setuju bahwa data dapat ditransfer ke dan disimpan dengan Dynamics 365 Customer Insights. [Pelajari lebih lanjut di pusat kepercayaan Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="424fa-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="424fa-117">Sambungkan ke folder Model Data Umum</span><span class="sxs-lookup"><span data-stu-id="424fa-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="424fa-118">Di wawasan audiens, buka **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="424fa-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="424fa-119">Pilih **Tambahkan sumber data**.</span><span class="sxs-lookup"><span data-stu-id="424fa-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="424fa-120">Pilih **sambungkan ke folder Common Data Model**, masukkan **nama** untuk sumber data, lalu pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="424fa-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="424fa-121">Anda dapat memilih antara menggunakan pilihan berbasis sumber daya dan pilihan berbasis langganan untuk autentikasi.</span><span class="sxs-lookup"><span data-stu-id="424fa-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="424fa-122">Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="424fa-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="424fa-123">Masukkan informasi **penampung** dan pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="424fa-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="424fa-124">![Kotak dialog untuk memasukkan rincian sambungan untuk Azure Data Lake](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="424fa-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="424fa-125">Di dialog **Pilih folder Common Data Model**, pilih file model.JSON untuk diimpor datanya, lalu pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="424fa-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="424fa-126">File model.JSON apa pun yang terkait dengan sumber data lain di lingkungan tidak akan ditampilkan dalam daftar.</span><span class="sxs-lookup"><span data-stu-id="424fa-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="424fa-127">Anda akan mendapatkan daftar entitas yang tersedia dalam file model.JSON yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="424fa-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="424fa-128">Anda dapat meninjau dan memilih dari daftar entitas yang tersedia dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="424fa-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="424fa-129">Semua entitas yang dipilih akan diserap dari sumber data baru.</span><span class="sxs-lookup"><span data-stu-id="424fa-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="424fa-130">![Kotak dialog menampilkan daftar entitas dari file model.JSON](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="424fa-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="424fa-131">Tunjukkan entitas data mana yang Anda inginkan untuk mengaktifkan pembuatan profil data dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="424fa-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="424fa-132">Pembuatan profil data memungkinkan kemampuan analitik dan kemampuan lainnya.</span><span class="sxs-lookup"><span data-stu-id="424fa-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="424fa-133">Anda dapat memilih seluruh entitas, yang memilih semua atribut dari entitas, atau memilih atribut tertentu pilihan Anda.</span><span class="sxs-lookup"><span data-stu-id="424fa-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="424fa-134">Secara default, entitas tidak diaktifkan untuk pembuatan profil data.</span><span class="sxs-lookup"><span data-stu-id="424fa-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="424fa-135">![Kotak dialog menampilkan profil data](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="424fa-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="424fa-136">Setelah menyimpan pilihan, halaman **sumber data** akan terbuka.</span><span class="sxs-lookup"><span data-stu-id="424fa-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="424fa-137">Anda seharusnya sekarang melihat koneksi folder Common Data Model sebagai sumber data.</span><span class="sxs-lookup"><span data-stu-id="424fa-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="424fa-138">File model.json hanya dapat dikaitkan dengan satu sumber data di lingkungan yang sama.</span><span class="sxs-lookup"><span data-stu-id="424fa-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="424fa-139">Namun, file model.JSON yang sama dapat digunakan untuk sumber data di beberapa lingkungan.</span><span class="sxs-lookup"><span data-stu-id="424fa-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="424fa-140">Mengedit sumber data folder Common Data Model</span><span class="sxs-lookup"><span data-stu-id="424fa-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="424fa-141">Anda dapat memperbarui kunci akses untuk akun penyimpanan yang berisi folder Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="424fa-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="424fa-142">Anda juga dapat mengubah file model.JSON.</span><span class="sxs-lookup"><span data-stu-id="424fa-142">You may also change the model.json file.</span></span> <span data-ttu-id="424fa-143">Untuk menyambung ke kontainer lain dari akun penyimpanan, atau mengubah nama akun, buat [sambungan sumber data baru](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="424fa-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="424fa-144">Di wawasan audiens, buka **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="424fa-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="424fa-145">Di samping sumber data yang ingin anda perbarui, pilih elipsis.</span><span class="sxs-lookup"><span data-stu-id="424fa-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="424fa-146">Pilih opsi **Edit** dari daftar.</span><span class="sxs-lookup"><span data-stu-id="424fa-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="424fa-147">Atau, perbarui **tombol akses** dan pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="424fa-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Dialog untuk mengedit dan memperbarui kunci akses untuk sumber data yang ada](media/edit-access-key.png)

5. <span data-ttu-id="424fa-149">Atau, Anda dapat memperbarui dari sambungan kunci akun ke sambungan berbasis sumber daya atau berbasis langganan.</span><span class="sxs-lookup"><span data-stu-id="424fa-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="424fa-150">Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="424fa-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="424fa-151">Anda tidak dapat **mengubah** informasi penampung saat memperbarui sambungan.</span><span class="sxs-lookup"><span data-stu-id="424fa-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="424fa-152">![Kotak dialog untuk memasukkan rincian sambungan untuk Azure Data Lake](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="424fa-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="424fa-153">Atau, pilih file model.JSON yang berbeda dengan kumpulan entitas yang berbeda dari kontainer.</span><span class="sxs-lookup"><span data-stu-id="424fa-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="424fa-154">Atau, Anda dapat memilih entitas tambahan untuk diserap.</span><span class="sxs-lookup"><span data-stu-id="424fa-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="424fa-155">Anda juga dapat menghapus entitas yang telah dipilih jika tidak ada dependensi.</span><span class="sxs-lookup"><span data-stu-id="424fa-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="424fa-156">Jika ada ketergantungan pada file model.JSON yang ada dan kumpulan entitas, Anda akan melihat pesan kesalahan dan tidak dapat memilih file model.JSON yang berbeda.</span><span class="sxs-lookup"><span data-stu-id="424fa-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="424fa-157">Hapus dependensi tersebut sebelum mengubah file model.json atau buat sumber data baru dengan file model.json yang ingin anda gunakan untuk menghindari penghapusan dependensi.</span><span class="sxs-lookup"><span data-stu-id="424fa-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="424fa-158">Atau, Anda dapat memilih atribut atau entitas tambahan untuk mengaktifkan pemrofilan data atau menonaktifkan yang telah dipilih.</span><span class="sxs-lookup"><span data-stu-id="424fa-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
