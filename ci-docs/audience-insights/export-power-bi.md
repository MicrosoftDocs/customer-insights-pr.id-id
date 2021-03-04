---
title: Konektor Power BI
description: Pelajari cara menggunakan konektor Dynamics 365 Customer Insights di Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0607a4644ac7d7beb19e4faecf012efcd197d48c
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477092"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="bf993-103">Konektor untuk Power BI (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="bf993-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="bf993-104">Buat visualisasi untuk data Anda dengan Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="bf993-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="bf993-105">Buat wawasan tambahan dan Buat laporan dengan data pelanggan terpadu Anda.</span><span class="sxs-lookup"><span data-stu-id="bf993-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bf993-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="bf993-106">Prerequisites</span></span>

- <span data-ttu-id="bf993-107">Anda memiliki profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="bf993-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="bf993-108">Versi terbaru [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) terinstal di komputer Anda.</span><span class="sxs-lookup"><span data-stu-id="bf993-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="bf993-109">[Pelajari lebih lanjut tentang Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="bf993-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="bf993-110">Konfigurasikan konektor untuk Power BI</span><span class="sxs-lookup"><span data-stu-id="bf993-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="bf993-111">Di Power BI Desktop, pilih **file** > **Dapatkan data**.</span><span class="sxs-lookup"><span data-stu-id="bf993-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="bf993-112">Pilih **Lihat lainnya** dan Cari **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="bf993-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="bf993-113">Pilih **Sambungkan**.</span><span class="sxs-lookup"><span data-stu-id="bf993-113">Select **Connect**.</span></span>

1. <span data-ttu-id="bf993-114">**masuk** dengan akun organisasi yang sama yang Anda gunakan untuk Customer Insights dan pilih **Sambungkan**.</span><span class="sxs-lookup"><span data-stu-id="bf993-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="bf993-115">Akun yang Anda tunjukkan dalam langkah ini digunakan untuk mengambil data dari Customer Insights dan tidak perlu sama dengan yang Anda gunakan untuk masuk ke Power BI.</span><span class="sxs-lookup"><span data-stu-id="bf993-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="bf993-116">Untuk mengatur ulang akun yang digunakan untuk pengambilan data, buka Power BI dan buka **File** > **pilihan** > **pengaturan** > **pengaturan sumber data**.</span><span class="sxs-lookup"><span data-stu-id="bf993-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="bf993-117">Di daftar sumber data, pilih **Login Dynamics 365 Customer Insights** dan pilih **izin yang jelas**.</span><span class="sxs-lookup"><span data-stu-id="bf993-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="bf993-118">Di kotak dialog **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="bf993-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="bf993-119">Anda akan melihat daftar semua lingkungan yang dapat Anda akses.</span><span class="sxs-lookup"><span data-stu-id="bf993-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="bf993-120">Perluas lingkungan dan buka folder apa pun (entitas, langkah-langkah, segmen, pengayaan).</span><span class="sxs-lookup"><span data-stu-id="bf993-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="bf993-121">Misalnya, buka folder **entitas**, untuk melihat semua entitas yang dapat diimpor.</span><span class="sxs-lookup"><span data-stu-id="bf993-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="bf993-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span><span class="sxs-lookup"><span data-stu-id="bf993-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="bf993-123">Pilih kotak centang di samping entitas untuk mencakup dan **memuat**.</span><span class="sxs-lookup"><span data-stu-id="bf993-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="bf993-124">Anda dapat memilih beberapa entitas dari beberapa lingkungan.</span><span class="sxs-lookup"><span data-stu-id="bf993-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="bf993-125">Anda akan melihat kotak dialog pemuatan saat entitas Anda dimuat.</span><span class="sxs-lookup"><span data-stu-id="bf993-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="bf993-126">Setelah semua entitas yang dipilih telah dimuat, Anda dapat menggunakan kemampuan Power BI untuk memvisualisasikan data.</span><span class="sxs-lookup"><span data-stu-id="bf993-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="bf993-127">himpunan data besar</span><span class="sxs-lookup"><span data-stu-id="bf993-127">Large data sets</span></span>

<span data-ttu-id="bf993-128">Customer Insights connector untuk Power BI dirancang untuk berfungsi untuk himpunan data yang berisi 1 juta profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="bf993-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="bf993-129">Mengimpor kumpulan data yang lebih besar mungkin berfungsi, namun memerlukan waktu lama.</span><span class="sxs-lookup"><span data-stu-id="bf993-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="bf993-130">Selain itu, proses dapat berjalan ke batas waktu karena keterbatasan Power BI.</span><span class="sxs-lookup"><span data-stu-id="bf993-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="bf993-131">Untuk informasi lebih lanjut, lihat [Power BI : rekomendasi untuk himpunan data besar](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="bf993-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="bf993-132">Bekerja dengan subset data</span><span class="sxs-lookup"><span data-stu-id="bf993-132">Work with a subset of data</span></span>

<span data-ttu-id="bf993-133">Pertimbangkan untuk bekerja dengan subset data Anda.</span><span class="sxs-lookup"><span data-stu-id="bf993-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="bf993-134">Misalnya, Anda dapat membuat [segmen](segments.md) dan bukan mengekspor semua rekaman pelanggan ke Power BI.</span><span class="sxs-lookup"><span data-stu-id="bf993-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="bf993-135">Mengatasi Masalah</span><span class="sxs-lookup"><span data-stu-id="bf993-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="bf993-136">Lingkungan Customer Insights tidak ditampilkan di Power BI</span><span class="sxs-lookup"><span data-stu-id="bf993-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="bf993-137">Lingkungan yang memiliki lebih dari satu [relasi](relationships.md) yang didefinisikan antara dua entitas yang sama di wawasan audiens tidak akan tersedia di Power BI connector.</span><span class="sxs-lookup"><span data-stu-id="bf993-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="bf993-138">Anda dapat mengidentifikasi dan menghilangkan duplikat Relasi.</span><span class="sxs-lookup"><span data-stu-id="bf993-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="bf993-139">Secara audiens, buka **Data** > **Relasi** tentang lingkungan yang Anda lewatkan di Power BI.</span><span class="sxs-lookup"><span data-stu-id="bf993-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="bf993-140">Identifikasikan duplikat Relasi:</span><span class="sxs-lookup"><span data-stu-id="bf993-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="bf993-141">Periksa apakah ada lebih dari satu relasi yang didefinisikan antara dua entitas yang sama.</span><span class="sxs-lookup"><span data-stu-id="bf993-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="bf993-142">Periksa apakah ada relasi yang dibuat antara dua entitas yang tercakup dalam proses penyatuan.</span><span class="sxs-lookup"><span data-stu-id="bf993-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="bf993-143">Terdapat relasi implisit yang didefinisikan antara semua entitas yang tercakup dalam proses penyatuan.</span><span class="sxs-lookup"><span data-stu-id="bf993-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="bf993-144">Hilangkan duplikat Relasi yang diidentifikasi.</span><span class="sxs-lookup"><span data-stu-id="bf993-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="bf993-145">Setelah penghapusan duplikat Relasi, coba untuk mengkonfigurasi Power BI connector lagi.</span><span class="sxs-lookup"><span data-stu-id="bf993-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="bf993-146">Lingkungan seharusnya tersedia sekarang.</span><span class="sxs-lookup"><span data-stu-id="bf993-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]

