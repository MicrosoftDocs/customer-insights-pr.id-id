---
title: Penyegaran tambahan untuk sumber data berbasis kueri daya
description: Refresh data baru dan yang diperbarui untuk sumber data besar berdasarkan Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268552"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="e661c-103">Penyegaran inkremental untuk sumber daya berbasis Power Query</span><span class="sxs-lookup"><span data-stu-id="e661c-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="e661c-104">Peningkatan refresh secara bertahap untuk sumber data memberikan keuntungan berikut:</span><span class="sxs-lookup"><span data-stu-id="e661c-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="e661c-105">**Refresh lebih cepat** -hanya data yang telah diubah akan disegarkan.</span><span class="sxs-lookup"><span data-stu-id="e661c-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="e661c-106">Misalnya, Anda mungkin hanya me-refresh lima hari terakhir dari kumpulan data historis.</span><span class="sxs-lookup"><span data-stu-id="e661c-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="e661c-107">**Peningkatan keandalan** -dengan penyegaran lebih kecil, Anda tidak perlu memelihara koneksi ke sistem sumber volatil begitu lama, sehingga mengurangi risiko masalah koneksi.</span><span class="sxs-lookup"><span data-stu-id="e661c-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="e661c-108">**Pengurangan konsumsi sumber daya** -menyegarkan hanya subset dari total data Anda yang menyebabkan penggunaan sumber daya komputasi lebih efisien dan mengurangi emisi lingkungan.</span><span class="sxs-lookup"><span data-stu-id="e661c-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="e661c-109">Konfigurasikan refresh bertahap</span><span class="sxs-lookup"><span data-stu-id="e661c-109">Configure incremental refresh</span></span>

<span data-ttu-id="e661c-110">Wawasan audiens memungkinkan refresh tambahan untuk sumber data yang diimpor melalui Power Query yang mendukung konsumsi inkremental.</span><span class="sxs-lookup"><span data-stu-id="e661c-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="e661c-111">Misalnya, database Azure SQL dengan bidang tanggal dan waktu, yang menunjukkan Kapan rekaman data terakhir diperbarui.</span><span class="sxs-lookup"><span data-stu-id="e661c-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="e661c-112">[buat sumber data baru berdasarkan Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="e661c-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="e661c-113">Berikan nama untuk sumber data.</span><span class="sxs-lookup"><span data-stu-id="e661c-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="e661c-114">Pilih sumber data yang mendukung penyegaran tambahan, seperti database Azure SQL.</span><span class="sxs-lookup"><span data-stu-id="e661c-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="e661c-115">Pilih entitas atau tabel untuk diserap.</span><span class="sxs-lookup"><span data-stu-id="e661c-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="e661c-116">Selesaikan langkah transformasi dan pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="e661c-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="e661c-117">Di kotak dialog **Atur penyegaran tambahan**, pilih **konfigurasi** untuk membuka **pengaturan penyegaran tambahan**.</span><span class="sxs-lookup"><span data-stu-id="e661c-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="e661c-118">Jika anda memilih **lewati**, sumber data akan me-refresh seluruh himpunan data.</span><span class="sxs-lookup"><span data-stu-id="e661c-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="e661c-119">Anda juga dapat menerapkan penyegaran tambahan nanti dengan mengedit sumber data yang ada.</span><span class="sxs-lookup"><span data-stu-id="e661c-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="e661c-120">Pada **pengaturanpenyegaran tambahan**, anda akan mengkonfigurasikan refresh tambahan untuk semua entitas yang anda pilih saat membuat sumber data.</span><span class="sxs-lookup"><span data-stu-id="e661c-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e661c-121">![konfigurasikan entitas di sumber data untuk penyegaran tambahan](media/incremental-refresh-settings.png "konfigurasikan entitas di sumber data untuk penyegaran tambahan")</span><span class="sxs-lookup"><span data-stu-id="e661c-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="e661c-122">Pilih entitas, dan berikan rincian berikut:</span><span class="sxs-lookup"><span data-stu-id="e661c-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="e661c-123">**Tentukan primary key**: Pilih primary key untuk entitas atau tabel.</span><span class="sxs-lookup"><span data-stu-id="e661c-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="e661c-124">**Tentukan bidang"terakhir diperbarui"**: bidang ini hanya akan menampilkan atribut jenis tanggal atau waktu.</span><span class="sxs-lookup"><span data-stu-id="e661c-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="e661c-125">Pilih atribut yang menunjukkan Kapan rekaman terakhir diperbarui.</span><span class="sxs-lookup"><span data-stu-id="e661c-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="e661c-126">Ini akan digunakan untuk mengidentifikasi rekaman yang berada dalam jangka waktu refresh tambahan.</span><span class="sxs-lookup"><span data-stu-id="e661c-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="e661c-127">**periksa pembaruan setiap**: tentukan berapa lama anda ingin jangka waktu refresh inkremental.</span><span class="sxs-lookup"><span data-stu-id="e661c-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="e661c-128">Pilih **simpan** untuk menyelesaikan pembuatan sumber data.</span><span class="sxs-lookup"><span data-stu-id="e661c-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="e661c-129">Penyegaran data awal akan menjadi penyegaran penuh.</span><span class="sxs-lookup"><span data-stu-id="e661c-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="e661c-130">Setelah itu, penyegaran data tambahan terjadi sebagaimana dikonfigurasi di langkah sebelumnya.</span><span class="sxs-lookup"><span data-stu-id="e661c-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]