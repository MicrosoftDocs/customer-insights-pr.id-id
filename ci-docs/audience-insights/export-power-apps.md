---
title: Konektor Power Apps
description: Hubungkan Power Apps dengan Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598159"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="628b5-103">Microsoft Power Apps connector (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="628b5-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="628b5-104">Bawa profil pelanggan terpadu ke aplikasi Anda yang disesuaikan dengan Power Apps.</span><span class="sxs-lookup"><span data-stu-id="628b5-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="628b5-105">Hubungkan Power Apps dan Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="628b5-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="628b5-106">Customer Insights adalah salah satu dari banyak [sumber yang tersedia untuk data di Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="628b5-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="628b5-107">Lihat dokumentasi Power Apps untuk mempelajari cara [menambahkan sambungan data ke aplikasi](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="628b5-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="628b5-108">Sebaiknya Anda juga meninjau [cara Power Apps menggunakan delegasi untuk menangani kumpulan data besar di aplikasi Canvas](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="628b5-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="628b5-109">Entitas yang tersedia</span><span class="sxs-lookup"><span data-stu-id="628b5-109">Available entities</span></span>

<span data-ttu-id="628b5-110">Setelah menambahkan Customer Insights sebagai sambungan data, Anda dapat memilih entitas berikut di Power Apps:</span><span class="sxs-lookup"><span data-stu-id="628b5-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="628b5-111">Pelanggan: untuk menggunakan data dari [profil pelanggan terpadu](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="628b5-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="628b5-112">UnifiedActivity: untuk menampilkan [Timeline aktivitas](activities.md) pada aplikasi.</span><span class="sxs-lookup"><span data-stu-id="628b5-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="628b5-113">Pembatasan</span><span class="sxs-lookup"><span data-stu-id="628b5-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="628b5-114">Entitas yang dapat diambil</span><span class="sxs-lookup"><span data-stu-id="628b5-114">Retrievable entities</span></span>

<span data-ttu-id="628b5-115">Anda hanya dapat mengambil entitas **pelanggan**, **unifiedactivity**, dan **segmen** melalui Power Apps connector.</span><span class="sxs-lookup"><span data-stu-id="628b5-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="628b5-116">Entitas lain ditampilkan karena konektor yang mendasari mendukung mereka melalui pemicu di Power Automate.</span><span class="sxs-lookup"><span data-stu-id="628b5-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="628b5-117">Delegasi</span><span class="sxs-lookup"><span data-stu-id="628b5-117">Delegation</span></span>

<span data-ttu-id="628b5-118">Delegasi bekerja untuk entitas pelanggan dan entitas UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="628b5-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="628b5-119">Delegasi untuk entitas **pelanggan**: untuk menggunakan delegasi untuk entitas ini, bidang harus diindeks dalam [index pencarian & Filter](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="628b5-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="628b5-120">Delegasi untuk **unifiedactivity** : delegasi untuk entitas ini hanya berfungsi untuk bidang **activityid** dan **customerid**.</span><span class="sxs-lookup"><span data-stu-id="628b5-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="628b5-121">Untuk informasi lebih lanjut tentang delegasi, lihat [fungsi dan operasi Power Apps yang dapat didelegasikan](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="628b5-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="628b5-122">Kontrol galeri contoh</span><span class="sxs-lookup"><span data-stu-id="628b5-122">Example gallery control</span></span>

<span data-ttu-id="628b5-123">Misalnya, Anda menambahkan profil pelanggan ke [kontrol Galeri](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="628b5-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="628b5-124">Tambahkan **kontrol galeri** ke aplikasi yang sedang Anda bangun.</span><span class="sxs-lookup"><span data-stu-id="628b5-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="628b5-125">![Menambahkan elemen galeri](media/connector-powerapps9.png "Menambahkan elemen galeri")</span><span class="sxs-lookup"><span data-stu-id="628b5-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="628b5-126">Pilih **pelanggan** sebagai sumber data item.</span><span class="sxs-lookup"><span data-stu-id="628b5-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="628b5-127">![Pilih sumber data](media/choose-datasource-powerapps.png "Pilih sumber data")</span><span class="sxs-lookup"><span data-stu-id="628b5-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="628b5-128">Anda dapat mengubah panel data di sebelah kanan untuk memilih bidang untuk entitas Pelanggan yang akan ditampilkan di galeri.</span><span class="sxs-lookup"><span data-stu-id="628b5-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="628b5-129">Jika Anda ingin menampilkan bidang apa pun dari pelanggan yang dipilih di Galeri, isi properti teks label:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="628b5-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="628b5-130">Contoh: Gallery1. Selected. address1_city</span><span class="sxs-lookup"><span data-stu-id="628b5-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="628b5-131">Untuk menampilkan Timeline terpadu untuk pelanggan, tambahkan elemen Galeri, dan tambahkan properti item: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="628b5-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="628b5-132">Contoh: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="628b5-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]