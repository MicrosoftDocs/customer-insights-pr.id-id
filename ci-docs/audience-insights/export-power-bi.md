---
title: Konektor Power BI
description: Pelajari cara menggunakan konektor Dynamics 365 Customer Insights di Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406040"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="059ec-103">Konektor untuk Power BI (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="059ec-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="059ec-104">Buat visualisasi untuk data Anda dengan Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="059ec-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="059ec-105">Buat wawasan tambahan dan Buat laporan dengan data pelanggan terpadu Anda.</span><span class="sxs-lookup"><span data-stu-id="059ec-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="059ec-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="059ec-106">Prerequisites</span></span>

- <span data-ttu-id="059ec-107">Anda memiliki profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="059ec-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="059ec-108">Versi terbaru [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) terinstal di komputer Anda.</span><span class="sxs-lookup"><span data-stu-id="059ec-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="059ec-109">[Pelajari lebih lanjut tentang Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="059ec-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="059ec-110">Konfigurasikan konektor untuk Power BI</span><span class="sxs-lookup"><span data-stu-id="059ec-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="059ec-111">Di Power BI Desktop, pilih **file** > **Dapatkan data**.</span><span class="sxs-lookup"><span data-stu-id="059ec-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="059ec-112">Pilih **Lihat lainnya** dan Cari **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="059ec-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="059ec-113">Pilih hasil, lalu pilih **Sambungkan**.</span><span class="sxs-lookup"><span data-stu-id="059ec-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="059ec-114">**masuk** dengan akun organisasi yang sama yang Anda gunakan untuk Customer Insights dan pilih **Sambungkan**.</span><span class="sxs-lookup"><span data-stu-id="059ec-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="059ec-115">Akun yang Anda tunjukkan dalam langkah ini digunakan untuk mengambil data dari Customer Insights dan tidak perlu sama dengan yang Anda gunakan untuk masuk ke Power BI.</span><span class="sxs-lookup"><span data-stu-id="059ec-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="059ec-116">Untuk mengatur ulang akun yang digunakan untuk pengambilan data, buka Power BI dan buka **File** > **pilihan** > **pengaturan** > **pengaturan sumber data**.</span><span class="sxs-lookup"><span data-stu-id="059ec-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="059ec-117">Di daftar sumber data, pilih **Login Dynamics 365 Customer Insights** dan pilih **izin yang jelas**.</span><span class="sxs-lookup"><span data-stu-id="059ec-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="059ec-118">Di kotak dialog **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="059ec-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="059ec-119">Anda akan melihat daftar semua lingkungan yang dapat Anda akses.</span><span class="sxs-lookup"><span data-stu-id="059ec-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="059ec-120">Perluas lingkungan dan buka folder apa pun (entitas, langkah-langkah, segmen, pengayaan).</span><span class="sxs-lookup"><span data-stu-id="059ec-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="059ec-121">Misalnya, buka folder **entitas**, untuk melihat semua entitas yang dapat diimpor.</span><span class="sxs-lookup"><span data-stu-id="059ec-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="059ec-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span><span class="sxs-lookup"><span data-stu-id="059ec-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="059ec-123">Pilih kotak centang di samping entitas untuk mencakup dan **memuat**.</span><span class="sxs-lookup"><span data-stu-id="059ec-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="059ec-124">Anda dapat memilih beberapa entitas dari beberapa lingkungan.</span><span class="sxs-lookup"><span data-stu-id="059ec-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="059ec-125">Anda akan melihat kotak dialog pemuatan saat entitas Anda dimuat.</span><span class="sxs-lookup"><span data-stu-id="059ec-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="059ec-126">Setelah semua entitas yang dipilih telah dimuat, Anda dapat menggunakan kemampuan Power BI untuk memvisualisasikan data.</span><span class="sxs-lookup"><span data-stu-id="059ec-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="059ec-127">himpunan data besar</span><span class="sxs-lookup"><span data-stu-id="059ec-127">Large data sets</span></span>

<span data-ttu-id="059ec-128">Customer Insights connector untuk Power BI dirancang untuk berfungsi untuk himpunan data yang berisi 1 juta profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="059ec-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="059ec-129">Mengimpor kumpulan data yang lebih besar mungkin berfungsi, namun memerlukan waktu lama.</span><span class="sxs-lookup"><span data-stu-id="059ec-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="059ec-130">Selain itu, proses dapat berjalan ke batas waktu karena keterbatasan Power BI.</span><span class="sxs-lookup"><span data-stu-id="059ec-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="059ec-131">Untuk informasi lebih lanjut, lihat [Power BI : rekomendasi untuk himpunan data besar](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="059ec-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="059ec-132">Bekerja dengan subset data</span><span class="sxs-lookup"><span data-stu-id="059ec-132">Work with a subset of data</span></span>

<span data-ttu-id="059ec-133">Pertimbangkan untuk bekerja dengan subset data Anda.</span><span class="sxs-lookup"><span data-stu-id="059ec-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="059ec-134">Misalnya, Anda dapat membuat [segmen](segments.md) dan bukan mengekspor semua rekaman pelanggan ke Power BI.</span><span class="sxs-lookup"><span data-stu-id="059ec-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
