---
title: Mengekspor data Customer Insights ke Azure Synapse Analytics
description: Pelajari lebih lanjut cara mengkonfigurasi sambungan ke Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977381"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="b72c9-103">Ekspor data ke Azure Synapse Analytics (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="b72c9-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="b72c9-104">Azure Synapse adalah layanan analitik yang mempercepat waktu untuk wawasan di seluruh gudang data dan sistem data besar.</span><span class="sxs-lookup"><span data-stu-id="b72c9-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="b72c9-105">Anda data menyerap dan menggunakan data Customer Insights dalam [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="b72c9-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b72c9-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="b72c9-106">Prerequisites</span></span>

<span data-ttu-id="b72c9-107">Prasyarat berikut harus dipenuhi untuk mengkonfigurasi sambungan dari Customer Insights ke Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="b72c9-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="b72c9-108">Pastikan untuk menetapkan semua **penugasan peran** seperti dijelaskan.</span><span class="sxs-lookup"><span data-stu-id="b72c9-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="b72c9-109">Prasyarat di Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b72c9-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="b72c9-110">Anda memiliki peran **Administrator** di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="b72c9-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="b72c9-111">Selengkapnya tentang [menetapkan izin pengguna di audiens wawasan](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="b72c9-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="b72c9-112">Di Azure:</span><span class="sxs-lookup"><span data-stu-id="b72c9-112">In Azure:</span></span> 

- <span data-ttu-id="b72c9-113">Langganan Azure aktif.</span><span class="sxs-lookup"><span data-stu-id="b72c9-113">An active Azure subscription.</span></span>

- <span data-ttu-id="b72c9-114">Jika menggunakan akun Azure Data Lake Storage Gen2 baru, *prinsipal layanan untuk wawasan audiens* memerlukan izin **kontributor Data Blob penyimpanan**.</span><span class="sxs-lookup"><span data-stu-id="b72c9-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="b72c9-115">Selengkapnya tentang [menyambung ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure untuk wawasan audiens](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="b72c9-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="b72c9-116">Data Lake Storage Gen2 **harus mengaktifkan** [ruang nama hierarkis](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="b72c9-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="b72c9-117">Pada grup sumber daya, tempat ruang kerja Azure Synapse terletak, *prinsipal layanan* dan *pengguna wawasan audiens* harus ditetapkan sekurangnya izin **Pembaca**.</span><span class="sxs-lookup"><span data-stu-id="b72c9-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="b72c9-118">Untuk informasi lebih lanjut, lihat [Menetapkan peran Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="b72c9-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="b72c9-119">*Pengguna* memerlukan izin **kontributor Data Blob Penyimpanan** di akun Azure Data Lake Storage Gen2 dengan data berada dan ditautkan ke ruang kerja Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="b72c9-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="b72c9-120">Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="b72c9-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="b72c9-121">*[Identitas yang dikelola Ruang kerja Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* memerlukan memerlukan izin **kontributor Data Blob Penyimpanan** di akun Azure Data Lake Storage Gen2 dengan data berada dan ditautkan ke ruang kerja Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="b72c9-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="b72c9-122">Pelajari lebih lanjut tentang [menggunakan portal Azure untuk menetapkan peran Azure untuk akses ke data blob dan antrean](/azure/storage/common/storage-auth-aad-rbac-portal) serta [izin kontributor Data Blob Penyimpanan](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="b72c9-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="b72c9-123">Di ruang kerja Azure Synapse, *prinsipal layanan untuk wawasan audiens* memerlukan **penetapan peran Administrator Synapse**.</span><span class="sxs-lookup"><span data-stu-id="b72c9-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="b72c9-124">Untuk informasi lebih lanjut, lihat [Cara mengkonfigurasi kontrol akses untuk ruang kerja Synapse Anda](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="b72c9-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="b72c9-125">Siapkan sambungan ke dan ekspor ke Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="b72c9-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="b72c9-126">Mengonfigurasi koneksi</span><span class="sxs-lookup"><span data-stu-id="b72c9-126">Configure a connection</span></span>

1. <span data-ttu-id="b72c9-127">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="b72c9-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b72c9-128">Pilih **Tambah koneksi** dan pilih **Azure Synapse Analytics** atau pilih **Konfigurasi** dalam petak **Azure Synapse Analytics** untuk mengonfigurasikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="b72c9-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="b72c9-129">Beri koneksi Anda nama yang dikenali di bidang nama tampilan.</span><span class="sxs-lookup"><span data-stu-id="b72c9-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="b72c9-130">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="b72c9-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="b72c9-131">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="b72c9-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b72c9-132">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="b72c9-132">Choose who can use this connection.</span></span> <span data-ttu-id="b72c9-133">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="b72c9-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b72c9-134">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b72c9-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b72c9-135">Pilih atau cari langganan yang akan digunakan untuk data Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b72c9-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="b72c9-136">Segera setelah langganan dipilih, Anda juga dapat memilih **Ruang Kerja**, **Akun Penyimpanan**, dan **Wadah**.</span><span class="sxs-lookup"><span data-stu-id="b72c9-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="b72c9-137">Pilih **Simpan** untuk menyimpan koneksi.</span><span class="sxs-lookup"><span data-stu-id="b72c9-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="b72c9-138">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="b72c9-138">Configure an export</span></span>

<span data-ttu-id="b72c9-139">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="b72c9-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b72c9-140">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b72c9-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b72c9-141">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="b72c9-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b72c9-142">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="b72c9-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="b72c9-143">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="b72c9-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="b72c9-144">Jika Anda tidak melihat nama bagian ini, tidak ada [koneksi](connections.md) tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="b72c9-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="b72c9-145">Berikan daftar **nama tampilan** yang dapat dikenali untuk ekspor Anda dan **nama Database**.</span><span class="sxs-lookup"><span data-stu-id="b72c9-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="b72c9-146">Pilih entitas yang akan diekspor ke Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="b72c9-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="b72c9-147">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="b72c9-147">Select **Save**.</span></span>

<span data-ttu-id="b72c9-148">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="b72c9-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b72c9-149">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b72c9-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b72c9-150">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b72c9-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="b72c9-151">Memperbarui ekspor</span><span class="sxs-lookup"><span data-stu-id="b72c9-151">Update an export</span></span>

1. <span data-ttu-id="b72c9-152">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="b72c9-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b72c9-153">Pilih **Edit** di ekspor yang ingin Anda perbarui.</span><span class="sxs-lookup"><span data-stu-id="b72c9-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="b72c9-154">**Tambah** atau **Hilangkan** entitas dari pilihan.</span><span class="sxs-lookup"><span data-stu-id="b72c9-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="b72c9-155">Jika entitas dihapus dari pilihan, entitas tersebut tidak akan dihapus dari database Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="b72c9-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="b72c9-156">Namun, pembaruan data mendatang tidak akan memperbarui entitas yang dihapus di database tersebut.</span><span class="sxs-lookup"><span data-stu-id="b72c9-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="b72c9-157">**Mengubah Nama Database** akan membuat database Synapse Analytics baru.</span><span class="sxs-lookup"><span data-stu-id="b72c9-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="b72c9-158">Database dengan nama yang dikonfigurasi sebelum tidak akan menerima pembaruan apa pun di pembaruan mendatang.</span><span class="sxs-lookup"><span data-stu-id="b72c9-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
