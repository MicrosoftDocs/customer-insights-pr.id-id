---
title: Mencari dan memfilter Profil Pelanggan
description: Temukan informasi tentang profil pelanggan terpadu dan filter untuk atribut tertentu dengan cepat.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406082"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="38714-103">Profil pelanggan: Indeks Cari & Filter</span><span class="sxs-lookup"><span data-stu-id="38714-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="38714-104">Hasil mempersatukan data pelanggan adalah entitas profil pelanggan yang memberikan tampilan terpadu ke basis pelanggan Total Anda.</span><span class="sxs-lookup"><span data-stu-id="38714-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="38714-105">Untuk dengan cepat [mencari informasi tentang pelanggan atau grup pelanggan tertentu](customer-profiles.md), Anda dapat mengkonfigurasi kemampuan **pencarian** dan **filter** pada halaman **pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="38714-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="38714-106">Baca terus untuk mempelajari cara admin dapat mengedit atribut pada halaman **indeks pencarian & Filter**, yang tersedia bagi pengguna untuk mencari dan memfilter.</span><span class="sxs-lookup"><span data-stu-id="38714-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="38714-107">![Cari filter](media/search-filter.png "Cari filter")</span><span class="sxs-lookup"><span data-stu-id="38714-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="38714-108">Tambahkan bidang dan tentukan atribut</span><span class="sxs-lookup"><span data-stu-id="38714-108">Add fields and specify attributes</span></span>

<span data-ttu-id="38714-109">Jika ini adalah pertama kali Anda menentukan atribut yang dapat dicari sebagai administrator, Anda harus menentukan bidang terindeks terlebih dulu.</span><span class="sxs-lookup"><span data-stu-id="38714-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="38714-110">Sebaiknya Anda memilih semua atribut yang bisa digunakan pengguna untuk mencari dan memfilter pelanggan pada halaman **pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="38714-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="38714-111">Anda hanya dapat menentukan atribut yang ada di entitas profil pelanggan yang Anda buat selama proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="38714-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="38714-112">Buka halaman **pelanggan** dan pilih **index pencarian & filter**.</span><span class="sxs-lookup"><span data-stu-id="38714-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="38714-113">Kami membuat konfigurasi indeks pencarian default pada atribut yang tersedia dalam entitas pelanggan dari jenis semantik berikut sebagaimana ditentukan pada halaman peta.</span><span class="sxs-lookup"><span data-stu-id="38714-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="38714-114">Nama Depan, Nama Belakang, nama tengah, nama lengkap orang</span><span class="sxs-lookup"><span data-stu-id="38714-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="38714-115">Nama Organisasi</span><span class="sxs-lookup"><span data-stu-id="38714-115">Organization Name</span></span>
> - <span data-ttu-id="38714-116">Alamat email</span><span class="sxs-lookup"><span data-stu-id="38714-116">Email address</span></span>
> - <span data-ttu-id="38714-117">Nomor telepon</span><span class="sxs-lookup"><span data-stu-id="38714-117">Phone number</span></span>
> - <span data-ttu-id="38714-118">Informasi lokasi</span><span class="sxs-lookup"><span data-stu-id="38714-118">Location information</span></span>

2. <span data-ttu-id="38714-119">Pilih **+Tambah** untuk menentukan bidang yang diindeks.</span><span class="sxs-lookup"><span data-stu-id="38714-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="38714-120">Pilih atribut dalam daftar yang ingin ditambahkan sebagai bidang terindeks.</span><span class="sxs-lookup"><span data-stu-id="38714-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="38714-121">Anda selalu dapat menambahkan atribut lainnya dengan memilih **Tambah**.</span><span class="sxs-lookup"><span data-stu-id="38714-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="38714-122">Anda juga dapat menghapus setiap atribut yang dipilih dengan memilih simbol **Hapus**.</span><span class="sxs-lookup"><span data-stu-id="38714-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="38714-123">Jelajahi tabel bidang pelanggan terindeks</span><span class="sxs-lookup"><span data-stu-id="38714-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="38714-124">Informasi berikut disajikan dalam tabel.</span><span class="sxs-lookup"><span data-stu-id="38714-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="38714-125">**Nama**: Mewakili nama atribut sebagaimana ditampilkan di entitas profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="38714-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="38714-126">**Jenis data**: menentukan apakah jenis data adalah string, angka, atau tanggal.</span><span class="sxs-lookup"><span data-stu-id="38714-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="38714-127">**Tercakup dalam pencarian**: menentukan apakah atribut ini dapat digunakan untuk mencari pelanggan pada halaman **pelanggan** menggunakan bidang **pencarian**.</span><span class="sxs-lookup"><span data-stu-id="38714-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="38714-128">**Tambahkan filter**: Kontrol untuk menentukan bagaimana atribut ini dapat digunakan untuk pemfilteran pada halaman **pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="38714-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="38714-129">Mengedit pilihan filter untuk atribut tertentu</span><span class="sxs-lookup"><span data-stu-id="38714-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="38714-130">Menu **filter** pada halaman **pelanggan** dapat mencakup berbagai tingkat atribut (misalnya, kelompok usia berbeda untuk memfilter pelanggan berdasarkannya).</span><span class="sxs-lookup"><span data-stu-id="38714-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="38714-131">Pilih **Tambah filter** untuk atribut tertentu pada halaman **indeks pencarian & filter**.</span><span class="sxs-lookup"><span data-stu-id="38714-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="38714-132">Anda dapat menentukan jumlah hasil dan urutan pengaturannya.</span><span class="sxs-lookup"><span data-stu-id="38714-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="38714-133">Tergantung pada jenis data atribut, salah satu panel berikut ditampilkan.</span><span class="sxs-lookup"><span data-stu-id="38714-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="38714-134">Atribut jenis string: Tentukan jumlah hasil yang diinginkan pada panel **Opsi filter string**, serta kebijakan pesanan untuk mengaturnya.</span><span class="sxs-lookup"><span data-stu-id="38714-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="38714-135">Atribut jenis numerik: Tentukan interval yang disertakan di panel **Opsi filter Angka**, serta kebijakan pesanan untuk mengaturnya.</span><span class="sxs-lookup"><span data-stu-id="38714-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="38714-136">Atribut jenis tanggal: Tentukan interval yang disertakan di panel **Opsi filter Tanggal**, serta kebijakan pesanan untuk mengaturnya.</span><span class="sxs-lookup"><span data-stu-id="38714-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="38714-137">Pilih **Simpan** untuk menerapkan perubahan.</span><span class="sxs-lookup"><span data-stu-id="38714-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="38714-138">Pilih **Jalankan** setelah Anda siap menerapkan pengaturan Anda.</span><span class="sxs-lookup"><span data-stu-id="38714-138">Select **Run** once you're ready to apply your settings.</span></span>
