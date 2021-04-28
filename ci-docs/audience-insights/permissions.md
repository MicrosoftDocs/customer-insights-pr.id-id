---
title: Kelola izin pengguna
description: Pelajari tentang izin dan peran pengguna.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760377"
---
# <a name="user-permissions"></a><span data-ttu-id="823b7-103">Izin pengguna</span><span class="sxs-lookup"><span data-stu-id="823b7-103">User permissions</span></span>

<span data-ttu-id="823b7-104">Halaman **izin** adalah tempat Anda akan mengkonfigurasi peran dan izin untuk menggunakan wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="823b7-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="823b7-105">Anda harus memiliki izin administrator untuk melihat halaman.</span><span class="sxs-lookup"><span data-stu-id="823b7-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="823b7-106">Untuk mengakses halaman izin di wawasan audiens, buka **Admin** > **izin**.</span><span class="sxs-lookup"><span data-stu-id="823b7-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="823b7-107">Ada tiga jenis peran:</span><span class="sxs-lookup"><span data-stu-id="823b7-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="823b7-108">Penampil</span><span class="sxs-lookup"><span data-stu-id="823b7-108">Viewer</span></span>

- <span data-ttu-id="823b7-109">Jelajahi wawasan dan segmen di halaman **Beranda** dan **segmen**.</span><span class="sxs-lookup"><span data-stu-id="823b7-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="823b7-110">Cari dan filter profil pelanggan menggunakan halaman **pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="823b7-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="823b7-111">Bidang harus dapat dicari.</span><span class="sxs-lookup"><span data-stu-id="823b7-111">Fields must be searchable.</span></span>
- <span data-ttu-id="823b7-112">Lihat dan Jelajahi halaman **pengayaan**.</span><span class="sxs-lookup"><span data-stu-id="823b7-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="823b7-113">Jelajahi serta ekspor entitas menggunakan halaman **entitas**.</span><span class="sxs-lookup"><span data-stu-id="823b7-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="823b7-114">Lihat status proses sistem menggunakan halaman **sistem**.</span><span class="sxs-lookup"><span data-stu-id="823b7-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="823b7-115">Lihat ekspor dalam halaman **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="823b7-115">View exports in **Exports** page.</span></span>
- <span data-ttu-id="823b7-116">Menginstal dan menggunakan dasbor **Power BI Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="823b7-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="823b7-117">Kontributor</span><span class="sxs-lookup"><span data-stu-id="823b7-117">Contributor</span></span>

- <span data-ttu-id="823b7-118">Semua izin yang tersedia untuk pemirsa.</span><span class="sxs-lookup"><span data-stu-id="823b7-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="823b7-119">Muat dan Ubah data menggunakan halaman **sumber data**.</span><span class="sxs-lookup"><span data-stu-id="823b7-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="823b7-120">Lengkapi bagian *penyatuan data* (**memetakan**, **mencocokkan**, dan **menggabungkan**) yang menghasilkan entitas profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="823b7-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="823b7-121">Tentukan **Relasi** dan **aktivitas**.</span><span class="sxs-lookup"><span data-stu-id="823b7-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="823b7-122">Buat segmen menggunakan halaman **segmen**.</span><span class="sxs-lookup"><span data-stu-id="823b7-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="823b7-123">Buat ukuran menggunakan halaman **ukuran**.</span><span class="sxs-lookup"><span data-stu-id="823b7-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="823b7-124">Kelola konfigurasi dan Perkaya profil pelanggan dari halaman **pengayaan** (hanya untuk pengayaan pihak pertama).</span><span class="sxs-lookup"><span data-stu-id="823b7-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>
- <span data-ttu-id="823b7-125">Kelola dan buat ekspor berdasarkan koneksi yang dibagikan dengan kontributor.</span><span class="sxs-lookup"><span data-stu-id="823b7-125">Manage and create exports based on connections shared with contributors.</span></span> <span data-ttu-id="823b7-126">[Selengkapnya tentang cara administrator mengizinkan kontributor menggunakan sambungan untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="823b7-126">[Learn more about how administrators allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

## <a name="administrator"></a><span data-ttu-id="823b7-127">Administrator</span><span class="sxs-lookup"><span data-stu-id="823b7-127">Administrator</span></span>

- <span data-ttu-id="823b7-128">Semua izin yang tersedia untuk Kontributor.</span><span class="sxs-lookup"><span data-stu-id="823b7-128">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="823b7-129">Ubah pengaturan pada halaman **sistem**, termasuk bahasa kerja dan refresh jadwal untuk proses sistem Anda.</span><span class="sxs-lookup"><span data-stu-id="823b7-129">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="823b7-130">Lihat dan tambahkan izin menggunakan halaman **izin**.</span><span class="sxs-lookup"><span data-stu-id="823b7-130">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="823b7-131">Atur definisi pencarian dan filter untuk halaman pelanggan menggunakan halaman **indeks pencarian & Filter** (dapat diakses melalui halaman **pelanggan**).</span><span class="sxs-lookup"><span data-stu-id="823b7-131">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="823b7-132">Kelola koneksi dan izinkan mereka untuk peran pengguna lain di halaman **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="823b7-132">Manage connections and allow them for other user roles on **Connections** page.</span></span>
- <span data-ttu-id="823b7-133">Kelola konfigurasi dan Perkaya profil pelanggan dari halaman **pengayaan** (untuk semua pengayaan).</span><span class="sxs-lookup"><span data-stu-id="823b7-133">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="823b7-134">Mengelola dan membuat ekspor di halaman **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="823b7-134">Manage and create exports on **Exports** page.</span></span>
- <span data-ttu-id="823b7-135">Instal dan gunakan **Add -in kartu pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="823b7-135">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="823b7-136">Tambahkan dan gunakan **Power Apps connector**.</span><span class="sxs-lookup"><span data-stu-id="823b7-136">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="823b7-137">Aktifkan penggunaan [API Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="823b7-137">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="823b7-138">Menetapkan izin dan peran</span><span class="sxs-lookup"><span data-stu-id="823b7-138">Assign roles and permissions</span></span>

1. <span data-ttu-id="823b7-139">Di wawasan audiens, buka **Admin** > **Izin**.</span><span class="sxs-lookup"><span data-stu-id="823b7-139">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="823b7-140">Pilih **Tambah Pengguna** untuk membuka panel **Tambah/Edit izin**.</span><span class="sxs-lookup"><span data-stu-id="823b7-140">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="823b7-141">Gunakan bidang **pencarian** untuk menemukan pengguna Azure Active Directory atau grup yang izinnya ingin Anda Sesuaikan.</span><span class="sxs-lookup"><span data-stu-id="823b7-141">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="823b7-142">Pilih **peran** yang akan ditetapkan ke pengguna atau grup tersebut.</span><span class="sxs-lookup"><span data-stu-id="823b7-142">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="823b7-143">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="823b7-143">Select **Save**.</span></span> <span data-ttu-id="823b7-144">Lingkungan saat ini akan secara otomatis dibagikan dengan pengguna atau anggota grup yang izinnya telah Anda ubah.</span><span class="sxs-lookup"><span data-stu-id="823b7-144">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="823b7-145">Pengguna dapat mengakses aplikasi customer Insights dan bekerja sesuai dengan peran mereka.</span><span class="sxs-lookup"><span data-stu-id="823b7-145">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="823b7-146">Lihat izin saat ini</span><span class="sxs-lookup"><span data-stu-id="823b7-146">View current permissions</span></span>

<span data-ttu-id="823b7-147">Di audiens wawasan, buka **Admin** > **izin** untuk melihat tugas peran apa yang saat ini aktif.</span><span class="sxs-lookup"><span data-stu-id="823b7-147">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="823b7-148">Kolom **jenis** menentukan pengguna, grup, atau aplikasi tunggal.</span><span class="sxs-lookup"><span data-stu-id="823b7-148">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="823b7-149">Sistem ini mendukung setiap pengguna dan grup.</span><span class="sxs-lookup"><span data-stu-id="823b7-149">The system supports individual users and groups.</span></span>
- <span data-ttu-id="823b7-150">Peran ditentukan dalam kolom **peran**.</span><span class="sxs-lookup"><span data-stu-id="823b7-150">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="823b7-151">Pilih judul kolom untuk mengurutkan hasil berdasarkan nilai kolom tersebut.</span><span class="sxs-lookup"><span data-stu-id="823b7-151">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="823b7-152">Gunakan bidang **pencarian** di bagian atas halaman untuk mencari pengguna tertentu.</span><span class="sxs-lookup"><span data-stu-id="823b7-152">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
