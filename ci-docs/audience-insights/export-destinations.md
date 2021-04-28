---
title: Mengekspor data dari Customer Insights
description: Kelola ekspor untuk berbagi data.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896147"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="48a00-103">Gambaran umum Ekspor (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="48a00-103">Exports (preview) overview</span></span>

<span data-ttu-id="48a00-104">Halaman **Ekspor** memperlihatkan kepada Anda semua ekspor yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="48a00-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="48a00-105">Ekspor berbagi data tertentu dengan berbagai aplikasi.</span><span class="sxs-lookup"><span data-stu-id="48a00-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="48a00-106">Mereka dapat menyertakan profil pelanggan atau entitas, skema, dan detail pemetaan.</span><span class="sxs-lookup"><span data-stu-id="48a00-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="48a00-107">Setiap ekspor memerlukan [koneksi, yang disiapkan oleh administrator, untuk mengelola autentikasi dan akses](connections.md).</span><span class="sxs-lookup"><span data-stu-id="48a00-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="48a00-108">Hingga Maret 2021, ekspor membuat koneksi ke layanan yang sesuai secara otomatis.</span><span class="sxs-lookup"><span data-stu-id="48a00-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="48a00-109">Ekspor sekarang memerlukan [koneksi, yang dibuat dan dibagikan oleh administrator](connections.md) sebelum Anda bisa membuatnya.</span><span class="sxs-lookup"><span data-stu-id="48a00-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="48a00-110">Buka **Data** > **Ekspor** untuk menampilkan halaman ekspor.</span><span class="sxs-lookup"><span data-stu-id="48a00-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="48a00-111">Semua peran pengguna memiliki akses untuk melihat ekspor yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="48a00-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="48a00-112">Gunakan bidang pencarian di bilah perintah untuk menemukan ekspor menurut nama, nama koneksi, atau tipe koneksinya.</span><span class="sxs-lookup"><span data-stu-id="48a00-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="48a00-113">Konfigurasikan ekspor baru</span><span class="sxs-lookup"><span data-stu-id="48a00-113">Set up a new export</span></span>

<span data-ttu-id="48a00-114">Untuk menyiapkan atau mengedit ekspor, Anda harus memiliki koneksi yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="48a00-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="48a00-115">Koneksi bergantung pada [peran pengguna](permissions.md) Anda:</span><span class="sxs-lookup"><span data-stu-id="48a00-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="48a00-116">Administrator memiliki akses ke semua koneksi.</span><span class="sxs-lookup"><span data-stu-id="48a00-116">Administrators have access to all connections.</span></span> <span data-ttu-id="48a00-117">Mereka juga dapat membuat koneksi baru saat menyiapkan ekspor.</span><span class="sxs-lookup"><span data-stu-id="48a00-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="48a00-118">Kontributor dapat memiliki akses ke koneksi tertentu.</span><span class="sxs-lookup"><span data-stu-id="48a00-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="48a00-119">Mereka bergantung pada administrator untuk mengonfigurasi dan berbagi koneksi.</span><span class="sxs-lookup"><span data-stu-id="48a00-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="48a00-120">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="48a00-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="48a00-121">Pemirsa hanya dapat melihat ekspor yang ada tetapi tidak membuatnya.</span><span class="sxs-lookup"><span data-stu-id="48a00-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="48a00-122">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="48a00-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="48a00-123">Pilih **Tambahkan ekspor** untuk membuat tujuan ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="48a00-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="48a00-124">Di panel **Konfigurasikan ekspor**, pilih koneksi mana yang akan digunakan.</span><span class="sxs-lookup"><span data-stu-id="48a00-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="48a00-125">[Koneksi](connections.md) dikelola oleh administrator.</span><span class="sxs-lookup"><span data-stu-id="48a00-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="48a00-126">Berikan detail yang diperlukan dan pilih **Simpan** untuk membuat ekspor.</span><span class="sxs-lookup"><span data-stu-id="48a00-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="48a00-127">Edit ekspor</span><span class="sxs-lookup"><span data-stu-id="48a00-127">Edit an export</span></span>

1. <span data-ttu-id="48a00-128">Pilih elipsis vertikal untuk tujuan ekspor yang akan diedit.</span><span class="sxs-lookup"><span data-stu-id="48a00-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="48a00-129">Dari menu tarik-turun, pilih **Edit**.</span><span class="sxs-lookup"><span data-stu-id="48a00-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="48a00-130">Ubah nilai yang ingin Anda perbarui dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="48a00-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="48a00-131">Melihat ekspor dan mengekspor detail</span><span class="sxs-lookup"><span data-stu-id="48a00-131">View Exports and export details</span></span>

<span data-ttu-id="48a00-132">Setelah membuat tujuan ekspor, mereka tercantum pada **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="48a00-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="48a00-133">Semua pengguna dapat melihat data mana yang dibagikan dan status terbarunya.</span><span class="sxs-lookup"><span data-stu-id="48a00-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="48a00-134">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="48a00-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="48a00-135">Pengguna tanpa izin edit memilih **Lihat**, bukan **Edit** untuk melihat detail ekspor.</span><span class="sxs-lookup"><span data-stu-id="48a00-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="48a00-136">Panel samping ini memperlihatkan pengaturan ekspor ini.</span><span class="sxs-lookup"><span data-stu-id="48a00-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="48a00-137">Tanpa izin edit, Anda tidak bisa mengubah nilai.</span><span class="sxs-lookup"><span data-stu-id="48a00-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="48a00-138">Pilih **Tutup** untuk kembali ke halaman ekspor.</span><span class="sxs-lookup"><span data-stu-id="48a00-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="48a00-139">Menjalankan ekspor Atas Permintaan</span><span class="sxs-lookup"><span data-stu-id="48a00-139">Run exports on demand</span></span>

<span data-ttu-id="48a00-140">Setelah mengonfigurasi ekspor, ekspor akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab) selama memiliki koneksi yang berfungsi.</span><span class="sxs-lookup"><span data-stu-id="48a00-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="48a00-141">Untuk mengekspor data tanpa menunggu refresh terjadwal, buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="48a00-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="48a00-142">Anda memiliki dua pilihan:</span><span class="sxs-lookup"><span data-stu-id="48a00-142">You have two options:</span></span>

- <span data-ttu-id="48a00-143">Untuk menjalankan semua ekspor, pilih **Jalankan semua** di bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="48a00-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="48a00-144">Untuk menjalankan ekspor tunggal, pilih elipsis (...) pada item daftar lalu pilih **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="48a00-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="48a00-145">Menghapus ekspor</span><span class="sxs-lookup"><span data-stu-id="48a00-145">Remove an Export</span></span>

1. <span data-ttu-id="48a00-146">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="48a00-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="48a00-147">Pilih elipsis vertikal untuk ekspor yang akan dihilangkan.</span><span class="sxs-lookup"><span data-stu-id="48a00-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="48a00-148">Dari menu dropdown, pilih **hilangkan**.</span><span class="sxs-lookup"><span data-stu-id="48a00-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="48a00-149">Konfirmasikan penghapusan dengan memilih **Hapus** di layar konfirmasi.</span><span class="sxs-lookup"><span data-stu-id="48a00-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
