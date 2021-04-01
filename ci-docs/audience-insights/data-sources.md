---
title: Gunakan sumber data untuk menyerap data
description: Pelajari cara mengimpor data dari berbagai sumber.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 780dc61a82d6ed9856a37dc8f164fa946d982bbe
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595951"
---
# <a name="data-sources-overview"></a><span data-ttu-id="ade34-103">Ikhtisar sumber data</span><span class="sxs-lookup"><span data-stu-id="ade34-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ade34-104">Kemampuan wawasan audiens di Dynamics 365 Customer Insights terhubung ke data dari sekumpulan sumber yang luas.</span><span class="sxs-lookup"><span data-stu-id="ade34-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="ade34-105">Menghubungkan ke sumber data sering disebut sebagai proses *penyerapan data*.</span><span class="sxs-lookup"><span data-stu-id="ade34-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="ade34-106">Setelah menyerap data, Anda dapat [menyatukan](data-unification.md), dan melakukan tindakan padanya.</span><span class="sxs-lookup"><span data-stu-id="ade34-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="ade34-107">Tambahkan sumber data</span><span class="sxs-lookup"><span data-stu-id="ade34-107">Add a data source</span></span>

<span data-ttu-id="ade34-108">Lihat artikel rinci tentang cara menambahkan sumber data, tergantung pada pilihan yang anda pilih.</span><span class="sxs-lookup"><span data-stu-id="ade34-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="ade34-109">Anda dapat menambahkan sumber data dengan tiga cara utama:</span><span class="sxs-lookup"><span data-stu-id="ade34-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="ade34-110">melalui lusinan Power Query connectors</span><span class="sxs-lookup"><span data-stu-id="ade34-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="ade34-111">Dari folder Common Data Model</span><span class="sxs-lookup"><span data-stu-id="ade34-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="ade34-112">Dari Danau Common Data Service Anda sendiri</span><span class="sxs-lookup"><span data-stu-id="ade34-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="ade34-113">Anda tidak dapat menambahkan data dari sumber data lokal.</span><span class="sxs-lookup"><span data-stu-id="ade34-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="ade34-114">Meninjau data yang diserap</span><span class="sxs-lookup"><span data-stu-id="ade34-114">Review ingested data</span></span>

<span data-ttu-id="ade34-115">Anda akan melihat nama dari setiap sumber data yang diserap, statusnya, serta waktu terakhir data disegarkan untuk sumber itu.</span><span class="sxs-lookup"><span data-stu-id="ade34-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="ade34-116">Anda dapat mengurutkan daftar sumber data menurut setiap kolom.</span><span class="sxs-lookup"><span data-stu-id="ade34-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ade34-117">![Sumber Data ditambahkan](media/configure-data-datasource-added.png "Sumber Data ditambahkan")</span><span class="sxs-lookup"><span data-stu-id="ade34-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="ade34-118">Status</span><span class="sxs-lookup"><span data-stu-id="ade34-118">Status</span></span>  |<span data-ttu-id="ade34-119">KETERANGAN</span><span class="sxs-lookup"><span data-stu-id="ade34-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="ade34-120">Berhasil</span><span class="sxs-lookup"><span data-stu-id="ade34-120">Successful</span></span>   |<span data-ttu-id="ade34-121">Sumber data berhasil diserap jika waktu disebutkan di bidang **Disegarkan**.</span><span class="sxs-lookup"><span data-stu-id="ade34-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="ade34-122">Belum dimulai</span><span class="sxs-lookup"><span data-stu-id="ade34-122">Not started</span></span>   |<span data-ttu-id="ade34-123">Sumber data belum diserap datanya atau masih dalam mode draf.</span><span class="sxs-lookup"><span data-stu-id="ade34-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="ade34-124">Me-refresh</span><span class="sxs-lookup"><span data-stu-id="ade34-124">Refreshing</span></span>    |<span data-ttu-id="ade34-125">Penyerapan data sedang berlangsung.</span><span class="sxs-lookup"><span data-stu-id="ade34-125">Data ingestion is in progress.</span></span> <span data-ttu-id="ade34-126">Anda dapat membatalkan operasi ini dengan memilih **berhenti menyegarkan** di kolom **tindakan**.</span><span class="sxs-lookup"><span data-stu-id="ade34-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="ade34-127">Menghentikan refresh sumber data akan mengembalikannya ke status refresh terakhir.</span><span class="sxs-lookup"><span data-stu-id="ade34-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="ade34-128">Gagal</span><span class="sxs-lookup"><span data-stu-id="ade34-128">Failed</span></span>     |<span data-ttu-id="ade34-129">Penyerapan data mengalami kesalahan.</span><span class="sxs-lookup"><span data-stu-id="ade34-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="ade34-130">Pilih nilai di kolom **Status** dari daftar sumber data untuk meninjau rincian lainnya.</span><span class="sxs-lookup"><span data-stu-id="ade34-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="ade34-131">Di panel **Rincian progres**, perluas **sumber Data**.</span><span class="sxs-lookup"><span data-stu-id="ade34-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="ade34-132">Pilih **Lihat rincian** untuk informasi lebih lanjut tentang status penyegaran, termasuk rincian kesalahan dan pembaruan proses hilir.</span><span class="sxs-lookup"><span data-stu-id="ade34-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="ade34-133">Pemuatan data dapat memerlukan waktu.</span><span class="sxs-lookup"><span data-stu-id="ade34-133">Loading data can take some time.</span></span> <span data-ttu-id="ade34-134">Setelah penyegaran berhasil, data yang terserap dapat ditinjau dari halaman **entitas**.</span><span class="sxs-lookup"><span data-stu-id="ade34-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="ade34-135">Untuk informasi lebih lanjut, [Entitas](entities.md).</span><span class="sxs-lookup"><span data-stu-id="ade34-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="ade34-136">Segarkan sumber data</span><span class="sxs-lookup"><span data-stu-id="ade34-136">Refresh a data source</span></span>

<span data-ttu-id="ade34-137">Sumber data dapat disegarkan dengan jadwal otomatis atau diperbarui secara manual sesuai permintaan.</span><span class="sxs-lookup"><span data-stu-id="ade34-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="ade34-138">Buka **admin** > **sistem** > [**jadwal**](system.md#schedule-tab) untuk mengkonfigurasi penyegaran terjadwal dari semua sumber data Anda yang diserap.</span><span class="sxs-lookup"><span data-stu-id="ade34-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="ade34-139">Untuk me-refresh sumber data sesuai permintaan, ikuti langkah berikut:</span><span class="sxs-lookup"><span data-stu-id="ade34-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="ade34-140">Di wawasan audiens, buka **Data** > **Sumber data**</span><span class="sxs-lookup"><span data-stu-id="ade34-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="ade34-141">Pilih elipsis vertikal di sebelah sumber data ingin anda refresh dan pilih **Segarkan** dari daftar drop-down.</span><span class="sxs-lookup"><span data-stu-id="ade34-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="ade34-142">Sumber data sekarang dipicu untuk penyegaran manual.</span><span class="sxs-lookup"><span data-stu-id="ade34-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="ade34-143">Menyegarkan sumber data akan memperbarui skema entitas serta data untuk semua entitas yang ditentukan dalam sumber data.</span><span class="sxs-lookup"><span data-stu-id="ade34-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="ade34-144">Pilih **Hentikan penyegaran** jika Anda ingin membatalkan refresh yang ada dan sumber data akan kembali ke status refresh terakhirnya.</span><span class="sxs-lookup"><span data-stu-id="ade34-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="ade34-145">Hapus sumber data</span><span class="sxs-lookup"><span data-stu-id="ade34-145">Delete a data source</span></span>

1. <span data-ttu-id="ade34-146">Di wawasan audiens, buka **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="ade34-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="ade34-147">Pilih elipsis vertikal di sebelah sumber data yang akan dihapus dan pilih **Hapus** dari menu drop-down.</span><span class="sxs-lookup"><span data-stu-id="ade34-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="ade34-148">Konfirmasikan penghapusan.</span><span class="sxs-lookup"><span data-stu-id="ade34-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]