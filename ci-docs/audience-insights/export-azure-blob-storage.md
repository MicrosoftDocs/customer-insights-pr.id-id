---
title: Mengekspor data Customer Insights ke Penyimpanan Azure Blob
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke penyimpanan Blob.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976185"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="38a22-103">Mengekspor daftar segmen dan data lainnya ke Penyimpanan Blob Azure (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="38a22-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="38a22-104">Simpan data Customer Insights Anda di penyimpanan Blob atau gunakan untuk mentransfer data ke aplikasi lainnya.</span><span class="sxs-lookup"><span data-stu-id="38a22-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="38a22-105">Siapkan sambungan ke penyimpanan Blob</span><span class="sxs-lookup"><span data-stu-id="38a22-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="38a22-106">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="38a22-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="38a22-107">Pilih **Tambahkan koneksi** dan pilih **penyimpanan Blob Azure** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="38a22-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="38a22-108">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="38a22-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="38a22-109">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="38a22-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="38a22-110">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="38a22-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="38a22-111">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="38a22-111">Choose who can use this connection.</span></span> <span data-ttu-id="38a22-112">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="38a22-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="38a22-113">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="38a22-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="38a22-114">Masukkan **Nama akun**, **Kunci akun**, dan **Wadah** untuk akun penyimpanan Blob Anda.</span><span class="sxs-lookup"><span data-stu-id="38a22-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="38a22-115">Untuk mempelajari selengkapnya tentang cara menemukan nama akun penyimpanan Blob dan kunci akun, lihat [Mengelola pengaturan akun penyimpanan di portal Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="38a22-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="38a22-116">Untuk mempelajari cara membuat penampung, lihat [membuat penampung](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="38a22-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="38a22-117">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="38a22-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="38a22-118">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="38a22-118">Configure an export</span></span>

<span data-ttu-id="38a22-119">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="38a22-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="38a22-120">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="38a22-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="38a22-121">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="38a22-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="38a22-122">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="38a22-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="38a22-123">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Penyimpanan Blob Azure.</span><span class="sxs-lookup"><span data-stu-id="38a22-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="38a22-124">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="38a22-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="38a22-125">Centang kotak di samping masing-masing entitas yang akan diekspor ke tujuan ini.</span><span class="sxs-lookup"><span data-stu-id="38a22-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="38a22-126">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="38a22-126">Select **Save**.</span></span>

<span data-ttu-id="38a22-127">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="38a22-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="38a22-128">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="38a22-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="38a22-129">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="38a22-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="38a22-130">Data yang diekspor disimpan dalam wadah penyimpanan Blob yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="38a22-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="38a22-131">Jalur folder berikut dibuat secara otomatis dalam penampung:</span><span class="sxs-lookup"><span data-stu-id="38a22-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="38a22-132">Untuk entitas sumber dan entitas yang dihasilkan oleh sistem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="38a22-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="38a22-133">Contoh: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="38a22-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="38a22-134">Model.json untuk entitas yang diekspor akan berada di tingkat %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="38a22-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="38a22-135">Contoh: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="38a22-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
