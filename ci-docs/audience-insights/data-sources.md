---
title: Gunakan sumber data untuk menyerap data
description: Pelajari cara mengimpor data dari berbagai sumber.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304700"
---
# <a name="data-sources-overview"></a><span data-ttu-id="0e6ce-103">Ikhtisar sumber data</span><span class="sxs-lookup"><span data-stu-id="0e6ce-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0e6ce-104">Kemampuan wawasan audiens di Dynamics 365 Customer Insights terhubung ke data dari sekumpulan sumber yang luas.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="0e6ce-105">Menghubungkan ke sumber data sering disebut sebagai proses *penyerapan data*.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="0e6ce-106">Setelah menyerap data, Anda dapat [menyatukan](data-unification.md), dan melakukan tindakan padanya.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="0e6ce-107">Tambahkan sumber data</span><span class="sxs-lookup"><span data-stu-id="0e6ce-107">Add a data source</span></span>

<span data-ttu-id="0e6ce-108">Lihat artikel rinci tentang cara menambahkan sumber data, tergantung pada pilihan yang anda pilih.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="0e6ce-109">Anda dapat menambahkan sumber data dengan tiga cara utama:</span><span class="sxs-lookup"><span data-stu-id="0e6ce-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="0e6ce-110">melalui lusinan Power Query connectors</span><span class="sxs-lookup"><span data-stu-id="0e6ce-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="0e6ce-111">Dari folder Common Data Model</span><span class="sxs-lookup"><span data-stu-id="0e6ce-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="0e6ce-112">Dari Danau Microsoft Dataverse Anda sendiri</span><span class="sxs-lookup"><span data-stu-id="0e6ce-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="0e6ce-113">Menambahkan data dari sumber data lokal</span><span class="sxs-lookup"><span data-stu-id="0e6ce-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="0e6ce-114">Menyerap data dari sumber data lokal di Wawasan Audiens didukung berdasarkan aliran data Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="0e6ce-115">Aliran data dapat diaktifkan di Customer Insights dengan [menyediakan URL lingkungan Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) saat menyiapkan lingkungan.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="0e6ce-116">Sumber data yang dibuat setelah mengaitkan lingkungan Dataverse dengan Customer Insights akan menggunakan [aliran data Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) secara default.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="0e6ce-117">Aliran data mendukung konektivitas lokal menggunakan gateway data.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="0e6ce-118">Hapus dan buat ulang sumber data yang ada sebelum lingkungan Dataverse dikaitkan untuk [menggunakan gateway data lokal](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="0e6ce-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="0e6ce-119">Gateway data dari lingkungan Power BI atau Power Apps yang ada akan terlihat dan Anda dapat menggunakan kembali di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="0e6ce-120">Halaman sumber data menampilkan tautan untuk membuka lingkungan Microsoft Power Platform tempat Anda dapat melihat dan mengkonfigurasi gateway data lokal.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="0e6ce-121">Meninjau data yang diserap</span><span class="sxs-lookup"><span data-stu-id="0e6ce-121">Review ingested data</span></span>

<span data-ttu-id="0e6ce-122">Anda akan melihat nama dari setiap sumber data yang diserap, statusnya, serta waktu terakhir data disegarkan untuk sumber itu.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="0e6ce-123">Anda dapat mengurutkan daftar sumber data menurut setiap kolom.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0e6ce-124">![Sumber Data ditambahkan](media/configure-data-datasource-added.png "Sumber Data ditambahkan")</span><span class="sxs-lookup"><span data-stu-id="0e6ce-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="0e6ce-125">Status</span><span class="sxs-lookup"><span data-stu-id="0e6ce-125">Status</span></span>  |<span data-ttu-id="0e6ce-126">KETERANGAN</span><span class="sxs-lookup"><span data-stu-id="0e6ce-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="0e6ce-127">Berhasil</span><span class="sxs-lookup"><span data-stu-id="0e6ce-127">Successful</span></span>   |<span data-ttu-id="0e6ce-128">Sumber data berhasil diserap jika waktu disebutkan di bidang **Disegarkan**.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="0e6ce-129">Belum dimulai</span><span class="sxs-lookup"><span data-stu-id="0e6ce-129">Not started</span></span>   |<span data-ttu-id="0e6ce-130">Sumber data belum diserap datanya atau masih dalam mode draf.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="0e6ce-131">Me-refresh</span><span class="sxs-lookup"><span data-stu-id="0e6ce-131">Refreshing</span></span>    |<span data-ttu-id="0e6ce-132">Penyerapan data sedang berlangsung.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-132">Data ingestion is in progress.</span></span> <span data-ttu-id="0e6ce-133">Anda dapat membatalkan operasi ini dengan memilih **berhenti menyegarkan** di kolom **tindakan**.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="0e6ce-134">Menghentikan refresh sumber data akan mengembalikannya ke status refresh terakhir.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="0e6ce-135">Gagal</span><span class="sxs-lookup"><span data-stu-id="0e6ce-135">Failed</span></span>     |<span data-ttu-id="0e6ce-136">Penyerapan data mengalami kesalahan.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="0e6ce-137">Pilih nilai di kolom **Status** dari daftar sumber data untuk meninjau rincian lainnya.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="0e6ce-138">Di panel **Rincian progres**, perluas **sumber Data**.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="0e6ce-139">Pilih **Lihat rincian** untuk informasi lebih lanjut tentang status penyegaran, termasuk rincian kesalahan dan pembaruan proses hilir.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="0e6ce-140">Memuat data dapat memakan waktu.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-140">Loading data can take time.</span></span> <span data-ttu-id="0e6ce-141">Setelah penyegaran berhasil, data yang terserap dapat ditinjau dari halaman **entitas**.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="0e6ce-142">Untuk informasi lebih lanjut, [Entitas](entities.md).</span><span class="sxs-lookup"><span data-stu-id="0e6ce-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="0e6ce-143">Segarkan sumber data</span><span class="sxs-lookup"><span data-stu-id="0e6ce-143">Refresh a data source</span></span>

<span data-ttu-id="0e6ce-144">Sumber data dapat disegarkan dengan jadwal otomatis atau diperbarui secara manual sesuai permintaan.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="0e6ce-145">Buka **admin** > **sistem** > [**jadwal**](system.md#schedule-tab) untuk mengkonfigurasi penyegaran terjadwal dari semua sumber data Anda yang diserap.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="0e6ce-146">Untuk me-refresh sumber data sesuai permintaan, ikuti langkah berikut:</span><span class="sxs-lookup"><span data-stu-id="0e6ce-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="0e6ce-147">Di wawasan audiens, buka **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="0e6ce-148">Pilih elipsis vertikal di sebelah sumber data yang ingin Anda segarkan, lalu pilih **Segarkan** dari daftar dropdown.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="0e6ce-149">Sumber data sekarang dipicu untuk penyegaran manual.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="0e6ce-150">Merefresh sumber data akan memperbarui skema entitas dan data untuk semua entitas yang ditentukan dalam sumber data.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="0e6ce-151">Pilih **Hentikan penyegaran** jika Anda ingin membatalkan refresh yang ada dan sumber data akan kembali ke status refresh terakhirnya.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="0e6ce-152">Hapus sumber data</span><span class="sxs-lookup"><span data-stu-id="0e6ce-152">Delete a data source</span></span>

1. <span data-ttu-id="0e6ce-153">Di wawasan audiens, buka **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="0e6ce-154">Pilih elipsis vertikal di sebelah sumber data yang ingin Anda hapus, lalu pilih **Hapus** dari menu dropdown.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="0e6ce-155">Konfirmasikan penghapusan.</span><span class="sxs-lookup"><span data-stu-id="0e6ce-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
