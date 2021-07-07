---
title: Mengekspor data dari Customer Insights
description: Kelola ekspor untuk berbagi data.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305482"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="f974c-103">Gambaran umum Ekspor (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="f974c-103">Exports (preview) overview</span></span>

<span data-ttu-id="f974c-104">Halaman **Ekspor** memperlihatkan kepada Anda semua ekspor yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="f974c-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="f974c-105">Ekspor berbagi data tertentu dengan berbagai aplikasi.</span><span class="sxs-lookup"><span data-stu-id="f974c-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="f974c-106">Mereka dapat menyertakan profil pelanggan atau entitas, skema, dan detail pemetaan.</span><span class="sxs-lookup"><span data-stu-id="f974c-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="f974c-107">Setiap ekspor memerlukan [koneksi, yang disiapkan oleh administrator, untuk mengelola autentikasi dan akses](connections.md).</span><span class="sxs-lookup"><span data-stu-id="f974c-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="f974c-108">Buka **Data** > **Ekspor** untuk menampilkan halaman ekspor.</span><span class="sxs-lookup"><span data-stu-id="f974c-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="f974c-109">Semua peran pengguna dapat melihat ekspor yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="f974c-109">All user roles can view configured exports.</span></span> <span data-ttu-id="f974c-110">Gunakan bidang pencarian di bilah perintah untuk menemukan ekspor berdasarkan nama, nama koneksi, atau jenis koneksi.</span><span class="sxs-lookup"><span data-stu-id="f974c-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="f974c-111">Konfigurasikan ekspor baru</span><span class="sxs-lookup"><span data-stu-id="f974c-111">Set up a new export</span></span>

<span data-ttu-id="f974c-112">Untuk menyiapkan atau mengedit ekspor, Anda harus memiliki koneksi yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="f974c-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="f974c-113">Koneksi bergantung pada [peran pengguna](permissions.md) Anda:</span><span class="sxs-lookup"><span data-stu-id="f974c-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="f974c-114">Administrator memiliki akses ke semua koneksi.</span><span class="sxs-lookup"><span data-stu-id="f974c-114">Administrators have access to all connections.</span></span> <span data-ttu-id="f974c-115">Mereka juga dapat membuat koneksi baru saat menyiapkan ekspor.</span><span class="sxs-lookup"><span data-stu-id="f974c-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="f974c-116">Kontributor dapat memiliki akses ke koneksi tertentu.</span><span class="sxs-lookup"><span data-stu-id="f974c-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="f974c-117">Mereka bergantung pada administrator untuk mengonfigurasi dan berbagi koneksi.</span><span class="sxs-lookup"><span data-stu-id="f974c-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="f974c-118">Daftar ekspor akan menampilkan kontributor apakah mereka dapat mengedit atau hanya melihat ekspor di kolom **izin Anda**.</span><span class="sxs-lookup"><span data-stu-id="f974c-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="f974c-119">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f974c-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="f974c-120">Pemirsa hanya dapat melihat ekspor yang ada tetapi tidak membuatnya.</span><span class="sxs-lookup"><span data-stu-id="f974c-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="f974c-121">Menentukan ekspor baru</span><span class="sxs-lookup"><span data-stu-id="f974c-121">Define a new export</span></span>

1. <span data-ttu-id="f974c-122">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="f974c-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f974c-123">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="f974c-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="f974c-124">Di panel **Konfigurasikan ekspor**, pilih koneksi mana yang akan digunakan.</span><span class="sxs-lookup"><span data-stu-id="f974c-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="f974c-125">[Koneksi](connections.md) dikelola oleh administrator.</span><span class="sxs-lookup"><span data-stu-id="f974c-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="f974c-126">Berikan detail yang diperlukan dan pilih **Simpan** untuk membuat ekspor.</span><span class="sxs-lookup"><span data-stu-id="f974c-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="f974c-127">Menentukan ekspor baru berdasarkan ekspor yang ada</span><span class="sxs-lookup"><span data-stu-id="f974c-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="f974c-128">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="f974c-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f974c-129">Dalam daftar ekspor, pilih ekspor yang ingin Anda duplikasi.</span><span class="sxs-lookup"><span data-stu-id="f974c-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="f974c-130">Pilih **Buat duplikat** di bilah perintah untuk membuka panel **Atur ekspor** dengan rincian ekspor yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="f974c-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="f974c-131">Baca dan sesuaikan ekspor, lalu pilih **Simpan** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="f974c-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="f974c-132">Edit ekspor</span><span class="sxs-lookup"><span data-stu-id="f974c-132">Edit an export</span></span>

1. <span data-ttu-id="f974c-133">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="f974c-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f974c-134">Dalam daftar ekspor, pilih ekspor yang ingin Anda edit.</span><span class="sxs-lookup"><span data-stu-id="f974c-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="f974c-135">Di bilah perintah, pilih **Edit**.</span><span class="sxs-lookup"><span data-stu-id="f974c-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="f974c-136">Ubah nilai yang ingin Anda perbarui dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="f974c-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="f974c-137">Melihat ekspor dan mengekspor detail</span><span class="sxs-lookup"><span data-stu-id="f974c-137">View exports and export details</span></span>

<span data-ttu-id="f974c-138">Setelah membuat tujuan ekspor, mereka tercantum pada **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="f974c-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="f974c-139">Semua pengguna dapat melihat data mana yang dibagikan dan status terbarunya.</span><span class="sxs-lookup"><span data-stu-id="f974c-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="f974c-140">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="f974c-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f974c-141">Pengguna tanpa izin mengedit, pilih **Tampilan**, bukan **Edit** untuk melihat rincian ekspor.</span><span class="sxs-lookup"><span data-stu-id="f974c-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="f974c-142">Panel sisi menampilkan konfigurasi ekspor.</span><span class="sxs-lookup"><span data-stu-id="f974c-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="f974c-143">Tanpa izin edit, Anda tidak bisa mengubah nilai.</span><span class="sxs-lookup"><span data-stu-id="f974c-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="f974c-144">Pilih **Tutup** untuk kembali ke halaman ekspor.</span><span class="sxs-lookup"><span data-stu-id="f974c-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="f974c-145">Jadwalkan dan jalankan ekspor</span><span class="sxs-lookup"><span data-stu-id="f974c-145">Schedule and run exports</span></span>

<span data-ttu-id="f974c-146">Setiap ekspor yang Anda konfigurasikan memiliki jadwal refresh.</span><span class="sxs-lookup"><span data-stu-id="f974c-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="f974c-147">Selama pembaruan, sistem mencari data baru atau yang diperbarui untuk disertakan dalam ekspor.</span><span class="sxs-lookup"><span data-stu-id="f974c-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="f974c-148">Secara default, ekspor dijalankan sebagai bagian dari setiap [pembaruan sistem terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f974c-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f974c-149">Anda dapat menyesuaikan jadwal refresh atau menonaktifkannya untuk menjalankan ekspor secara manual.</span><span class="sxs-lookup"><span data-stu-id="f974c-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="f974c-150">Jadwal ekspor tergantung pada status lingkungan Anda.</span><span class="sxs-lookup"><span data-stu-id="f974c-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="f974c-151">Jika ada pembaruan yang sedang berlangsung pada [dependensi](system.md#refresh-policies) ketika ekspor terjadwal harus dimulai, sistem akan terlebih dulu menyelesaikan pembaruan dan kemudian menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="f974c-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="f974c-152">Anda dapat melihat kapan ekspor terakhir kali di-refresh di kolom **Disegarkan**.</span><span class="sxs-lookup"><span data-stu-id="f974c-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="f974c-153">Jadwalkan ekspor</span><span class="sxs-lookup"><span data-stu-id="f974c-153">Schedule exports</span></span>

<span data-ttu-id="f974c-154">Anda dapat menentukan jadwal refresh kustom untuk ekspor individual atau beberapa ekspor sekaligus.</span><span class="sxs-lookup"><span data-stu-id="f974c-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="f974c-155">Jadwal yang ditentukan saat ini tercantum di kolom **Jadwal** dari daftar ekspor.</span><span class="sxs-lookup"><span data-stu-id="f974c-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="f974c-156">Izin untuk mengubah jadwal sama seperti [pengeditan dan penentuan ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f974c-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="f974c-157">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="f974c-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f974c-158">Pilih ekspor yang ingin dijadwalkan.</span><span class="sxs-lookup"><span data-stu-id="f974c-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="f974c-159">Pilih **Jadwal** di bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="f974c-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="f974c-160">Di panel **Jadwalkan ekspor**, atur **Jadwal berjalan** ke **Aktif** untuk menjalankan ekspor secara otomatis.</span><span class="sxs-lookup"><span data-stu-id="f974c-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="f974c-161">Atur ke **Nonaktif** untuk me-refresh secara manual.</span><span class="sxs-lookup"><span data-stu-id="f974c-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="f974c-162">Untuk ekspor yang di-refresh secara otomatis, pilih nilai **Pengulangan** dan tentukan rincian untuknya.</span><span class="sxs-lookup"><span data-stu-id="f974c-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="f974c-163">Waktu yang ditentukan berlaku untuk semua instans pengulangan.</span><span class="sxs-lookup"><span data-stu-id="f974c-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="f974c-164">Ini adalah waktu ketika ekspor harus mulai me-refresh.</span><span class="sxs-lookup"><span data-stu-id="f974c-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="f974c-165">Terapkan dan aktifkan perubahan Anda dengan memilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="f974c-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="f974c-166">Saat mengedit jadwal untuk beberapa ekspor, Anda harus membuat pilihan di dalam **Pertahankan atau timpa jadwal**:</span><span class="sxs-lookup"><span data-stu-id="f974c-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="f974c-167">**Pertahankan jadwal individual**: Pertahankan jadwal yang ditentukan sebelumnya untuk ekspor yang dipilih dan cukup nonaktifkan atau aktifkan.</span><span class="sxs-lookup"><span data-stu-id="f974c-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="f974c-168">**Menentukan jadwal baru untuk semua ekspor yang dipilih**: Menimpa jadwal yang ada dari ekspor yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="f974c-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="f974c-169">Menjalankan ekspor Atas Permintaan</span><span class="sxs-lookup"><span data-stu-id="f974c-169">Run exports on demand</span></span>

<span data-ttu-id="f974c-170">Untuk mengekspor data tanpa menunggu refresh terjadwal, buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="f974c-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="f974c-171">Untuk menjalankan semua ekspor, pilih **Jalankan semua** di bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="f974c-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="f974c-172">Tindakan ini hanya akan menjalankan ekspor yang memiliki jadwal aktif.</span><span class="sxs-lookup"><span data-stu-id="f974c-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="f974c-173">Untuk menjalankan satu ekspor, pilih ekspor dalam daftar, lalu pilih **Jalankan** di bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="f974c-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="f974c-174">Itulah cara Anda menjalankan ekspor tanpa jadwal aktif.</span><span class="sxs-lookup"><span data-stu-id="f974c-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="f974c-175">Menghapus ekspor</span><span class="sxs-lookup"><span data-stu-id="f974c-175">Remove an Export</span></span>

1. <span data-ttu-id="f974c-176">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="f974c-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f974c-177">Pilih ekspor yang ingin Anda hilangkan.</span><span class="sxs-lookup"><span data-stu-id="f974c-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="f974c-178">Di bilah perintah, pilih **Hapus**.</span><span class="sxs-lookup"><span data-stu-id="f974c-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="f974c-179">Konfirmasikan penghapusan dengan memilih **Hapus** di layar konfirmasi.</span><span class="sxs-lookup"><span data-stu-id="f974c-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
