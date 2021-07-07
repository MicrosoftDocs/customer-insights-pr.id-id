---
title: Lihat Profil pelanggan
description: Dapatkan gabungan tampilan data pelanggan terpadu Anda.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: c9adb4d7db74573d0512ae7a68a0e7ab51c994a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304608"
---
# <a name="customer-profiles"></a><span data-ttu-id="e452c-103">Profil pelanggan</span><span class="sxs-lookup"><span data-stu-id="e452c-103">Customer profiles</span></span>

<span data-ttu-id="e452c-104">Halaman **pelanggan** menampilkan tampilan gabungan pelanggan Anda, berdasarkan data profil yang Anda kumpulkan dari [semua sumber data](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="e452c-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="e452c-105">Profil pelanggan tersedia setelah Anda [membuat entitas pelanggan terpadu](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="e452c-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="e452c-106">Pastikan Anda menyelesaikan proses penyatuan data untuk mendapatkan tampilan Pelanggan yang lebih kaya.</span><span class="sxs-lookup"><span data-stu-id="e452c-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="e452c-107">Halaman ini juga memungkinkan Anda mencari pelanggan.</span><span class="sxs-lookup"><span data-stu-id="e452c-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="e452c-108">Pelanggan dapat berupa individu atau organisasi (pratinjau).</span><span class="sxs-lookup"><span data-stu-id="e452c-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="e452c-109">Setiap profil pelanggan atau organisasi diwakili oleh ubin.</span><span class="sxs-lookup"><span data-stu-id="e452c-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="e452c-110">Pilih ubin untuk melihat informasi tambahan tentang pelanggan atau organisasi tertentu.</span><span class="sxs-lookup"><span data-stu-id="e452c-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="e452c-111">Gunakan kontrol paginasi di bagian bawah halaman untuk melihat rekaman tambahan.</span><span class="sxs-lookup"><span data-stu-id="e452c-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="e452c-112">![Profil pelanggan B2C](media/profiles-customers.png "Profil pelanggan B2C")</span><span class="sxs-lookup"><span data-stu-id="e452c-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="e452c-113">Organisasi (Pratinjau)</span><span class="sxs-lookup"><span data-stu-id="e452c-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="e452c-114">![Profil pelanggan B2B](media/profile-customers-b2b.png "Profil pelanggan B2B")</span><span class="sxs-lookup"><span data-stu-id="e452c-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="e452c-115">Jika Anda tidak dapat melihat ubin ketika Anda memilih **pelanggan** di navigasi, administrator harus [menentukan sekurangnya satu atribut](search-filter-index.md) yang dapat dicari di layar **indeks Pencarian & Filter**.</span><span class="sxs-lookup"><span data-stu-id="e452c-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="e452c-116">Cari pelanggan</span><span class="sxs-lookup"><span data-stu-id="e452c-116">Search for customers</span></span>

<span data-ttu-id="e452c-117">Cari pelanggan dengan memasukkan nama atau suatu atribut lain di kotak pencarian.</span><span class="sxs-lookup"><span data-stu-id="e452c-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="e452c-118">Pencarian hanya berfungsi dalam entitas profil pelanggan yang dibuat selama proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="e452c-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="e452c-119">Sebagai admin, Anda dapat mengkonfigurasi atribut yang dapat dicari menggunakan halaman **indeks pencarian & filter**.</span><span class="sxs-lookup"><span data-stu-id="e452c-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="e452c-120">Untuk informasi lebih lanjut, Lihat [mengelola indeks pencarian & Filter](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="e452c-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="e452c-121">Filter pelanggan</span><span class="sxs-lookup"><span data-stu-id="e452c-121">Filter customers</span></span>

<span data-ttu-id="e452c-122">Anda dapat memfilter pelanggan berdasarkan bidang entitas profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="e452c-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="e452c-123">Mirip dengan pencarian, admin harus terlebih dulu menentukan bidang tersebut sebagai dapat disaring menggunakan halaman **indeks pencarian & filter**.</span><span class="sxs-lookup"><span data-stu-id="e452c-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="e452c-124">Pilih **filter** pada halaman **pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="e452c-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="e452c-125">Centang kotak di samping atribut untuk memfilter pelanggan.</span><span class="sxs-lookup"><span data-stu-id="e452c-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="e452c-126">![Profil pelanggan](media/profiles-customers3.png "Profil pelanggan")</span><span class="sxs-lookup"><span data-stu-id="e452c-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="e452c-127">Hapus Filter dengan memilih **Hapus Filter** pada halaman **pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="e452c-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="e452c-128">Halaman Rincian pelanggan</span><span class="sxs-lookup"><span data-stu-id="e452c-128">Customer details page</span></span>

<span data-ttu-id="e452c-129">Pilih salah satu ubin pelanggan untuk membuka **halaman rincian pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="e452c-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="e452c-130">Tampilan ini berisi informasi terpadu untuk pelanggan yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="e452c-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="e452c-131">Rincian pelanggan mencakup:</span><span class="sxs-lookup"><span data-stu-id="e452c-131">Customer details include:</span></span>

-   <span data-ttu-id="e452c-132">**Ubin profil pelanggan**: ubin ini menampilkan nilai yang berbeda dari entitas profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="e452c-132">**Customer profile tile**: This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="e452c-133">Rincian ini dapat mencakup alamat email, nama, kota, dan sebagainya.</span><span class="sxs-lookup"><span data-stu-id="e452c-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="e452c-134">**Minat potensial, merek potensial**: ditampilkan jika Anda mengonfigurasi pengayaan pihak pertama.</span><span class="sxs-lookup"><span data-stu-id="e452c-134">**Potential interests, potential brands**: Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="e452c-135">Ini menunjukkan potensi minat dan afinitas untuk merek yang memiliki profil pelanggan yang serupa dengan yang mungkin dimiliki pelanggan ini.</span><span class="sxs-lookup"><span data-stu-id="e452c-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="e452c-136">Untuk informasi lebih lanjut, lihat [memperkaya profil pelanggan dengan afinitas merek dan minat](enrichment-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="e452c-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md).</span></span>

-   <span data-ttu-id="e452c-137">**Tindakan**: menunjukkan jika Anda mengonfigurasi satu atau beberapa ukuran dari jenis tertentu: ukuran atribut pelanggan.</span><span class="sxs-lookup"><span data-stu-id="e452c-137">**Measures**: Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="e452c-138">Mereka mencakup KPI yang dihitung di sekitar pelanggan Anda di tingkat pelanggan individual.</span><span class="sxs-lookup"><span data-stu-id="e452c-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="e452c-139">Untuk informasi lebih lanjut, lihat [menentukan dan mengelola langkah](measures.md).</span><span class="sxs-lookup"><span data-stu-id="e452c-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="e452c-140">**Timeline aktivitas**: menunjukkan apakah Anda telah mengonfigurasi aktivitas.</span><span class="sxs-lookup"><span data-stu-id="e452c-140">**Activity timeline**: Shows if you have configured activities.</span></span> <span data-ttu-id="e452c-141">Tampilan Timeline berisi aktivitas yang diurutkan secara kronologis dari pelanggan ini, dimulai dengan aktivitas terbaru.</span><span class="sxs-lookup"><span data-stu-id="e452c-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="e452c-142">Untuk informasi lebih lanjut, lihat [Aktivitas pelanggan](activities.md).</span><span class="sxs-lookup"><span data-stu-id="e452c-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="e452c-143">pilih **kembali ke pelanggan** untuk kembali ke halaman pencarian pelanggan.</span><span class="sxs-lookup"><span data-stu-id="e452c-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e452c-144">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="e452c-144">Next steps</span></span>

<span data-ttu-id="e452c-145">[Tambahkan sumber data lainnya](data-sources.md) atau [Buat segmen pelanggan](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e452c-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
