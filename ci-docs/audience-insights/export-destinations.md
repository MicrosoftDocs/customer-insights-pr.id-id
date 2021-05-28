---
title: Mengekspor data dari Customer Insights
description: Kelola ekspor untuk berbagi data.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016618"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="dc53f-103">Gambaran umum Ekspor (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="dc53f-103">Exports (preview) overview</span></span>

<span data-ttu-id="dc53f-104">Halaman **Ekspor** memperlihatkan kepada Anda semua ekspor yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="dc53f-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="dc53f-105">Ekspor berbagi data tertentu dengan berbagai aplikasi.</span><span class="sxs-lookup"><span data-stu-id="dc53f-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="dc53f-106">Mereka dapat menyertakan profil pelanggan atau entitas, skema, dan detail pemetaan.</span><span class="sxs-lookup"><span data-stu-id="dc53f-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="dc53f-107">Setiap ekspor memerlukan [koneksi, yang disiapkan oleh administrator, untuk mengelola autentikasi dan akses](connections.md).</span><span class="sxs-lookup"><span data-stu-id="dc53f-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="dc53f-108">Buka **Data** > **Ekspor** untuk menampilkan halaman ekspor.</span><span class="sxs-lookup"><span data-stu-id="dc53f-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="dc53f-109">Semua peran pengguna memiliki akses untuk melihat ekspor yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="dc53f-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="dc53f-110">Gunakan bidang pencarian di bilah perintah untuk menemukan ekspor menurut nama, nama koneksi, atau tipe koneksinya.</span><span class="sxs-lookup"><span data-stu-id="dc53f-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="dc53f-111">Konfigurasikan ekspor baru</span><span class="sxs-lookup"><span data-stu-id="dc53f-111">Set up a new export</span></span>

<span data-ttu-id="dc53f-112">Untuk menyiapkan atau mengedit ekspor, Anda harus memiliki koneksi yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="dc53f-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="dc53f-113">Koneksi bergantung pada [peran pengguna](permissions.md) Anda:</span><span class="sxs-lookup"><span data-stu-id="dc53f-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="dc53f-114">Administrator memiliki akses ke semua koneksi.</span><span class="sxs-lookup"><span data-stu-id="dc53f-114">Administrators have access to all connections.</span></span> <span data-ttu-id="dc53f-115">Mereka juga dapat membuat koneksi baru saat menyiapkan ekspor.</span><span class="sxs-lookup"><span data-stu-id="dc53f-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="dc53f-116">Kontributor dapat memiliki akses ke koneksi tertentu.</span><span class="sxs-lookup"><span data-stu-id="dc53f-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="dc53f-117">Mereka bergantung pada administrator untuk mengonfigurasi dan berbagi koneksi.</span><span class="sxs-lookup"><span data-stu-id="dc53f-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="dc53f-118">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="dc53f-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="dc53f-119">Pemirsa hanya dapat melihat ekspor yang ada tetapi tidak membuatnya.</span><span class="sxs-lookup"><span data-stu-id="dc53f-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="dc53f-120">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="dc53f-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dc53f-121">Pilih **Tambahkan ekspor** untuk membuat tujuan ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="dc53f-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="dc53f-122">Di panel **Konfigurasikan ekspor**, pilih koneksi mana yang akan digunakan.</span><span class="sxs-lookup"><span data-stu-id="dc53f-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="dc53f-123">[Koneksi](connections.md) dikelola oleh administrator.</span><span class="sxs-lookup"><span data-stu-id="dc53f-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="dc53f-124">Berikan detail yang diperlukan dan pilih **Simpan** untuk membuat ekspor.</span><span class="sxs-lookup"><span data-stu-id="dc53f-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="dc53f-125">Edit ekspor</span><span class="sxs-lookup"><span data-stu-id="dc53f-125">Edit an export</span></span>

1. <span data-ttu-id="dc53f-126">Pilih elipsis vertikal untuk tujuan ekspor yang akan diedit.</span><span class="sxs-lookup"><span data-stu-id="dc53f-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="dc53f-127">Dari menu tarik-turun, pilih **Edit**.</span><span class="sxs-lookup"><span data-stu-id="dc53f-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="dc53f-128">Ubah nilai yang ingin Anda perbarui dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="dc53f-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="dc53f-129">Melihat ekspor dan mengekspor detail</span><span class="sxs-lookup"><span data-stu-id="dc53f-129">View Exports and export details</span></span>

<span data-ttu-id="dc53f-130">Setelah membuat tujuan ekspor, mereka tercantum pada **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="dc53f-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="dc53f-131">Semua pengguna dapat melihat data mana yang dibagikan dan status terbarunya.</span><span class="sxs-lookup"><span data-stu-id="dc53f-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="dc53f-132">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="dc53f-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dc53f-133">Pengguna tanpa izin edit memilih **Lihat**, bukan **Edit** untuk melihat detail ekspor.</span><span class="sxs-lookup"><span data-stu-id="dc53f-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="dc53f-134">Panel samping ini memperlihatkan pengaturan ekspor ini.</span><span class="sxs-lookup"><span data-stu-id="dc53f-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="dc53f-135">Tanpa izin edit, Anda tidak bisa mengubah nilai.</span><span class="sxs-lookup"><span data-stu-id="dc53f-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="dc53f-136">Pilih **Tutup** untuk kembali ke halaman ekspor.</span><span class="sxs-lookup"><span data-stu-id="dc53f-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="dc53f-137">Menjalankan ekspor Atas Permintaan</span><span class="sxs-lookup"><span data-stu-id="dc53f-137">Run exports on demand</span></span>

<span data-ttu-id="dc53f-138">Setelah mengonfigurasi ekspor, ekspor akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab) selama memiliki koneksi yang berfungsi.</span><span class="sxs-lookup"><span data-stu-id="dc53f-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="dc53f-139">Untuk mengekspor data tanpa menunggu refresh terjadwal, buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="dc53f-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="dc53f-140">Anda memiliki dua pilihan:</span><span class="sxs-lookup"><span data-stu-id="dc53f-140">You have two options:</span></span>

- <span data-ttu-id="dc53f-141">Untuk menjalankan semua ekspor, pilih **Jalankan semua** di bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="dc53f-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="dc53f-142">Untuk menjalankan ekspor tunggal, pilih elipsis (...) pada item daftar lalu pilih **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="dc53f-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="dc53f-143">Menghapus ekspor</span><span class="sxs-lookup"><span data-stu-id="dc53f-143">Remove an Export</span></span>

1. <span data-ttu-id="dc53f-144">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="dc53f-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dc53f-145">Pilih elipsis vertikal untuk ekspor yang akan dihilangkan.</span><span class="sxs-lookup"><span data-stu-id="dc53f-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="dc53f-146">Dari menu dropdown, pilih **hilangkan**.</span><span class="sxs-lookup"><span data-stu-id="dc53f-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="dc53f-147">Konfirmasikan penghapusan dengan memilih **Hapus** di layar konfirmasi.</span><span class="sxs-lookup"><span data-stu-id="dc53f-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
