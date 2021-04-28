---
title: Ekspor data Customer Insights ke Azure Data Lake Storage Gen2
description: Pelajari cara mengkonfigurasi sambungan ke Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760055"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="c8612-103">Siapkan sambungan ke Azure Data Lake Storage Gen2 (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="c8612-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="c8612-104">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="c8612-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="c8612-105">Pilih **Tambahkan koneksi** dan pilih **Azure Data Lake Gen 2** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="c8612-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="c8612-106">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="c8612-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="c8612-107">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="c8612-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="c8612-108">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="c8612-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="c8612-109">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="c8612-109">Choose who can use this connection.</span></span> <span data-ttu-id="c8612-110">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="c8612-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="c8612-111">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c8612-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="c8612-112">Masukkan **Nama akun**, **Kunci akun**, dan **Wadah** untuk Azure Data Lake Storage Gen2 Anda.</span><span class="sxs-lookup"><span data-stu-id="c8612-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="c8612-113">Untuk mempelajari cara membuat akun penyimpanan yang akan digunakan dengan Azure Data Lake Storage Gen2, lihat [Membuat akun penyimpanan](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="c8612-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="c8612-114">Untuk mempelajari selengkapnya tentang nama akun Azure Data Lake Gen 2 dan kunci akun, lihat [Mengelola pengaturan akun penyimpanan di portal Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="c8612-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="c8612-115">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="c8612-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="c8612-116">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="c8612-116">Configure an export</span></span>

<span data-ttu-id="c8612-117">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="c8612-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="c8612-118">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c8612-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="c8612-119">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="c8612-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c8612-120">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="c8612-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="c8612-121">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="c8612-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="c8612-122">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="c8612-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="c8612-123">Centang kotak di samping masing-masing entitas yang akan diekspor ke tujuan ini.</span><span class="sxs-lookup"><span data-stu-id="c8612-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="c8612-124">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="c8612-124">Select **Save**.</span></span>

<span data-ttu-id="c8612-125">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="c8612-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="c8612-126">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c8612-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c8612-127">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c8612-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="c8612-128">Data yang diekspor disimpan dalam wadah penyimpanan Azure Data Lake Gen 2 yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="c8612-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
