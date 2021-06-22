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
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253044"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="1dba3-103">Gambaran umum Ekspor (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="1dba3-103">Exports (preview) overview</span></span>

<span data-ttu-id="1dba3-104">Halaman **Ekspor** memperlihatkan kepada Anda semua ekspor yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="1dba3-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="1dba3-105">Ekspor berbagi data tertentu dengan berbagai aplikasi.</span><span class="sxs-lookup"><span data-stu-id="1dba3-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="1dba3-106">Mereka dapat menyertakan profil pelanggan atau entitas, skema, dan detail pemetaan.</span><span class="sxs-lookup"><span data-stu-id="1dba3-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="1dba3-107">Setiap ekspor memerlukan [koneksi, yang disiapkan oleh administrator, untuk mengelola autentikasi dan akses](connections.md).</span><span class="sxs-lookup"><span data-stu-id="1dba3-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="1dba3-108">Buka **Data** > **Ekspor** untuk menampilkan halaman ekspor.</span><span class="sxs-lookup"><span data-stu-id="1dba3-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="1dba3-109">Semua peran pengguna memiliki akses untuk melihat ekspor yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="1dba3-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="1dba3-110">Gunakan bidang pencarian di bilah perintah untuk menemukan ekspor menurut nama, nama koneksi, atau tipe koneksinya.</span><span class="sxs-lookup"><span data-stu-id="1dba3-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="1dba3-111">Konfigurasikan ekspor baru</span><span class="sxs-lookup"><span data-stu-id="1dba3-111">Set up a new export</span></span>

<span data-ttu-id="1dba3-112">Untuk menyiapkan atau mengedit ekspor, Anda harus memiliki koneksi yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="1dba3-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="1dba3-113">Koneksi bergantung pada [peran pengguna](permissions.md) Anda:</span><span class="sxs-lookup"><span data-stu-id="1dba3-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="1dba3-114">Administrator memiliki akses ke semua koneksi.</span><span class="sxs-lookup"><span data-stu-id="1dba3-114">Administrators have access to all connections.</span></span> <span data-ttu-id="1dba3-115">Mereka juga dapat membuat koneksi baru saat menyiapkan ekspor.</span><span class="sxs-lookup"><span data-stu-id="1dba3-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="1dba3-116">Kontributor dapat memiliki akses ke koneksi tertentu.</span><span class="sxs-lookup"><span data-stu-id="1dba3-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="1dba3-117">Mereka bergantung pada administrator untuk mengonfigurasi dan berbagi koneksi.</span><span class="sxs-lookup"><span data-stu-id="1dba3-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="1dba3-118">Daftar ekspor akan menampilkan kontributor apakah mereka dapat mengedit atau hanya melihat ekspor di kolom **izin Anda**.</span><span class="sxs-lookup"><span data-stu-id="1dba3-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="1dba3-119">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1dba3-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="1dba3-120">Pemirsa hanya dapat melihat ekspor yang ada tetapi tidak membuatnya.</span><span class="sxs-lookup"><span data-stu-id="1dba3-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="1dba3-121">Menentukan ekspor baru</span><span class="sxs-lookup"><span data-stu-id="1dba3-121">Define a new export</span></span>

1. <span data-ttu-id="1dba3-122">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="1dba3-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1dba3-123">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="1dba3-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="1dba3-124">Di panel **Konfigurasikan ekspor**, pilih koneksi mana yang akan digunakan.</span><span class="sxs-lookup"><span data-stu-id="1dba3-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="1dba3-125">[Koneksi](connections.md) dikelola oleh administrator.</span><span class="sxs-lookup"><span data-stu-id="1dba3-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="1dba3-126">Berikan detail yang diperlukan dan pilih **Simpan** untuk membuat ekspor.</span><span class="sxs-lookup"><span data-stu-id="1dba3-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="1dba3-127">Menentukan ekspor baru berdasarkan ekspor yang ada</span><span class="sxs-lookup"><span data-stu-id="1dba3-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="1dba3-128">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="1dba3-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1dba3-129">Dalam daftar ekspor, pilih ekspor yang ingin Anda duplikasi.</span><span class="sxs-lookup"><span data-stu-id="1dba3-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="1dba3-130">Pilih **Buat duplikat** di bilah perintah untuk membuka panel **Atur ekspor** dengan rincian ekspor yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="1dba3-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="1dba3-131">Baca dan sesuaikan ekspor, lalu pilih **Simpan** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="1dba3-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="1dba3-132">Edit ekspor</span><span class="sxs-lookup"><span data-stu-id="1dba3-132">Edit an export</span></span>

1. <span data-ttu-id="1dba3-133">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="1dba3-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1dba3-134">Dalam daftar ekspor, pilih ekspor yang ingin Anda edit.</span><span class="sxs-lookup"><span data-stu-id="1dba3-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="1dba3-135">Di bilah perintah, pilih **Edit**.</span><span class="sxs-lookup"><span data-stu-id="1dba3-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="1dba3-136">Ubah nilai yang ingin Anda perbarui dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="1dba3-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="1dba3-137">Melihat ekspor dan mengekspor detail</span><span class="sxs-lookup"><span data-stu-id="1dba3-137">View exports and export details</span></span>

<span data-ttu-id="1dba3-138">Setelah membuat tujuan ekspor, mereka tercantum pada **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="1dba3-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="1dba3-139">Semua pengguna dapat melihat data mana yang dibagikan dan status terbarunya.</span><span class="sxs-lookup"><span data-stu-id="1dba3-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="1dba3-140">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="1dba3-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1dba3-141">Pengguna tanpa izin edit memilih **Lihat**, bukan **Edit** untuk melihat detail ekspor.</span><span class="sxs-lookup"><span data-stu-id="1dba3-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="1dba3-142">Panel sisi menampilkan konfigurasi ekspor.</span><span class="sxs-lookup"><span data-stu-id="1dba3-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="1dba3-143">Tanpa izin edit, Anda tidak bisa mengubah nilai.</span><span class="sxs-lookup"><span data-stu-id="1dba3-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="1dba3-144">Pilih **Tutup** untuk kembali ke halaman ekspor.</span><span class="sxs-lookup"><span data-stu-id="1dba3-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="1dba3-145">Jadwalkan dan jalankan ekspor</span><span class="sxs-lookup"><span data-stu-id="1dba3-145">Schedule and run exports</span></span>

<span data-ttu-id="1dba3-146">Setiap ekspor yang Anda konfigurasikan memiliki jadwal refresh.</span><span class="sxs-lookup"><span data-stu-id="1dba3-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="1dba3-147">Selama pembaruan, sistem mencari data baru atau yang diperbarui untuk disertakan dalam ekspor.</span><span class="sxs-lookup"><span data-stu-id="1dba3-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="1dba3-148">Secara default, ekspor dijalankan sebagai bagian dari setiap [pembaruan sistem terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1dba3-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1dba3-149">Anda dapat menyesuaikan jadwal refresh atau menonaktifkannya untuk menjalankan ekspor secara manual.</span><span class="sxs-lookup"><span data-stu-id="1dba3-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="1dba3-150">Jadwal ekspor tergantung pada status lingkungan Anda.</span><span class="sxs-lookup"><span data-stu-id="1dba3-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="1dba3-151">Jika ada pembaruan pada [dependensi](system.md#refresh-policies) yang sedang berlangsung ketika ekspor terjadwal harus dimulai, sistem akan terlebih dulu menyelesaikan dependensi, lalu menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="1dba3-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="1dba3-152">Anda dapat melihat kapan ekspor terakhir kali di-refresh di kolom **Disegarkan**.</span><span class="sxs-lookup"><span data-stu-id="1dba3-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="1dba3-153">Jadwalkan ekspor</span><span class="sxs-lookup"><span data-stu-id="1dba3-153">Schedule exports</span></span>

<span data-ttu-id="1dba3-154">Anda dapat menentukan jadwal refresh kustom untuk ekspor individual atau beberapa ekspor sekaligus.</span><span class="sxs-lookup"><span data-stu-id="1dba3-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="1dba3-155">Jadwal yang ditentukan saat ini tercantum di kolom **Jadwal** dari daftar ekspor.</span><span class="sxs-lookup"><span data-stu-id="1dba3-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="1dba3-156">Izin untuk mengubah jadwal sama seperti [pengeditan dan penentuan ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1dba3-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="1dba3-157">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="1dba3-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1dba3-158">Pilih ekspor yang ingin dijadwalkan.</span><span class="sxs-lookup"><span data-stu-id="1dba3-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="1dba3-159">Pilih **Jadwal** di bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="1dba3-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="1dba3-160">Di panel **Jadwalkan ekspor**, atur **Jadwal berjalan** ke **Aktif** untuk menjalankan ekspor secara otomatis.</span><span class="sxs-lookup"><span data-stu-id="1dba3-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="1dba3-161">Atur ke **Nonaktif** untuk me-refresh secara manual.</span><span class="sxs-lookup"><span data-stu-id="1dba3-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="1dba3-162">Untuk ekspor yang di-refresh secara otomatis, pilih nilai **Pengulangan** dan tentukan rincian untuknya.</span><span class="sxs-lookup"><span data-stu-id="1dba3-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="1dba3-163">Waktu yang ditentukan berlaku untuk semua instans pengulangan.</span><span class="sxs-lookup"><span data-stu-id="1dba3-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="1dba3-164">Ini adalah waktu ketika ekspor harus mulai me-refresh.</span><span class="sxs-lookup"><span data-stu-id="1dba3-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="1dba3-165">Terapkan dan aktifkan perubahan Anda dengan memilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="1dba3-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="1dba3-166">Saat mengedit jadwal untuk beberapa ekspor, Anda harus membuat pilihan di dalam **Pertahankan atau timpa jadwal**:</span><span class="sxs-lookup"><span data-stu-id="1dba3-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="1dba3-167">**Pertahankan jadwal individual**: Pertahankan jadwal yang ditentukan sebelumnya untuk ekspor yang dipilih dan cukup nonaktifkan atau aktifkan.</span><span class="sxs-lookup"><span data-stu-id="1dba3-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="1dba3-168">**Menentukan jadwal baru untuk semua ekspor yang dipilih**: Menimpa jadwal yang ada dari ekspor yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="1dba3-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="1dba3-169">Menjalankan ekspor Atas Permintaan</span><span class="sxs-lookup"><span data-stu-id="1dba3-169">Run exports on demand</span></span>

<span data-ttu-id="1dba3-170">Untuk mengekspor data tanpa menunggu refresh terjadwal, buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="1dba3-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="1dba3-171">Untuk menjalankan semua ekspor, pilih **Jalankan semua** di bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="1dba3-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="1dba3-172">Tindakan ini hanya akan menjalankan ekspor yang memiliki jadwal aktif.</span><span class="sxs-lookup"><span data-stu-id="1dba3-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="1dba3-173">Untuk menjalankan satu ekspor, pilih ekspor dalam daftar, lalu pilih **Jalankan** di bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="1dba3-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="1dba3-174">Itulah cara Anda menjalankan ekspor tanpa jadwal aktif.</span><span class="sxs-lookup"><span data-stu-id="1dba3-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="1dba3-175">Menghapus ekspor</span><span class="sxs-lookup"><span data-stu-id="1dba3-175">Remove an Export</span></span>

1. <span data-ttu-id="1dba3-176">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="1dba3-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1dba3-177">Pilih ekspor yang ingin Anda hilangkan.</span><span class="sxs-lookup"><span data-stu-id="1dba3-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="1dba3-178">Di bilah perintah, pilih **Hapus**.</span><span class="sxs-lookup"><span data-stu-id="1dba3-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="1dba3-179">Konfirmasikan penghapusan dengan memilih **Hapus** di layar konfirmasi.</span><span class="sxs-lookup"><span data-stu-id="1dba3-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
