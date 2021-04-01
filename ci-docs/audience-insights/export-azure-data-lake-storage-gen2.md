---
title: Ekspor data Customer Insights ke Azure Data Lake Storage Gen2
description: Pelajari cara mengkonfigurasi sambungan ke Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596641"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="91caf-103">Konektor untuk Azure Data Lake Storage Gen2 (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="91caf-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="91caf-104">Simpan data Customer Insights Anda di Azure Data Lake Storage Gen2 atau gunakan untuk mentransfer data ke aplikasi lainnya.</span><span class="sxs-lookup"><span data-stu-id="91caf-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="91caf-105">Mengkonfigurasi konektor untuk Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="91caf-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="91caf-106">Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="91caf-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="91caf-107">Dalam **Azure Data Lake Storage Gen2**, pilih **Konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="91caf-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="91caf-108">Beri nama yang dikenali di bidang **nama tampilan** tujuan anda.</span><span class="sxs-lookup"><span data-stu-id="91caf-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="91caf-109">Masukkan **Nama akun**, **Kunci akun**, dan **Wadah** untuk Azure Data Lake Storage Gen2 Anda.</span><span class="sxs-lookup"><span data-stu-id="91caf-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="91caf-110">Untuk mempelajari cara membuat akun penyimpanan yang akan digunakan dengan Azure Data Lake Storage Gen2, lihat [Membuat akun penyimpanan](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="91caf-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="91caf-111">Untuk mempelajari lebih lanjut tentang cara menemukan nama akun dan kunci akun penyimpanan Azure Data Lake Gen2, lihat [Mengelola pengaturan akun penyimpanan di portal Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="91caf-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="91caf-112">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="91caf-112">Select **Next**.</span></span>

1. <span data-ttu-id="91caf-113">Centang kotak di samping masing-masing entitas yang akan diekspor ke tujuan ini.</span><span class="sxs-lookup"><span data-stu-id="91caf-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="91caf-114">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="91caf-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="91caf-115">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="91caf-115">Export the data</span></span>

<span data-ttu-id="91caf-116">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="91caf-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="91caf-117">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="91caf-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>