---
title: Destinasi ekspor
description: Ekspor data dan Kelola tujuan ekspor.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643867"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="8503d-103">Destinasi ekspor (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="8503d-103">Export destinations (preview)</span></span>

<span data-ttu-id="8503d-104">Halaman **tujuan ekspor** menampilkan semua lokasi yang telah Anda konfigurasikan untuk mengekspor data.</span><span class="sxs-lookup"><span data-stu-id="8503d-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="8503d-105">Anda juga dapat menambahkan tujuan baru untuk ekspor.</span><span class="sxs-lookup"><span data-stu-id="8503d-105">You can also add new destinations for export.</span></span> <span data-ttu-id="8503d-106">Selain itu, ia menampilkan pilihan ekspor yang tersedia saat ini.</span><span class="sxs-lookup"><span data-stu-id="8503d-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="8503d-107">Dapatkan ikhtisar ringkas, deskripsi, dan cari tahu apa yang dapat Anda lakukan dengan setiap pilihan Ekstensibilitas.</span><span class="sxs-lookup"><span data-stu-id="8503d-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="8503d-108">Ekspor profil terpadu, langkah, dan segmen ke aplikasi yang didukung dan relevan untuk bisnis Anda.</span><span class="sxs-lookup"><span data-stu-id="8503d-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="8503d-109">Buka **Admin** > **tujuan ekspor** untuk menemukan pilihan Ekstensibilitas berikut:</span><span class="sxs-lookup"><span data-stu-id="8503d-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="8503d-110">Add-in Kartu Pelanggan Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8503d-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="8503d-111">Konektor manajer iklan Facebook</span><span class="sxs-lookup"><span data-stu-id="8503d-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="8503d-112">Konektor Power Automate</span><span class="sxs-lookup"><span data-stu-id="8503d-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="8503d-113">Konektor Power Apps</span><span class="sxs-lookup"><span data-stu-id="8503d-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="8503d-114">Konektor Power BI</span><span class="sxs-lookup"><span data-stu-id="8503d-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="8503d-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="8503d-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="8503d-116">Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="8503d-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="8503d-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="8503d-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="8503d-118">Penyimpanan Blob Azure</span><span class="sxs-lookup"><span data-stu-id="8503d-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="8503d-119">Konektor LiveRamp&reg;</span><span class="sxs-lookup"><span data-stu-id="8503d-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="8503d-120">Bot untuk Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8503d-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="8503d-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="8503d-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="8503d-122">API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="8503d-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="8503d-123">Menambahkan tujuan ekspor baru</span><span class="sxs-lookup"><span data-stu-id="8503d-123">Add a new export destination</span></span>

<span data-ttu-id="8503d-124">Untuk menambahkan tujuan ekspor, Anda memiliki [izin administrator](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8503d-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="8503d-125">Jika Anda mengekspor ke layanan Microsoft, kami menganggap kedua layanan tersebut berada di organisasi yang sama.</span><span class="sxs-lookup"><span data-stu-id="8503d-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="8503d-126">Buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="8503d-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8503d-127">Beralih ke **tab tujuan ekspor saya**.</span><span class="sxs-lookup"><span data-stu-id="8503d-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="8503d-128">Pilih **Tambah tujuan** untuk membuat tujuan ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="8503d-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="8503d-129">Di **panel Tambah tujuan**, pilih **jenis** tujuan ekspor di drop-down.</span><span class="sxs-lookup"><span data-stu-id="8503d-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="8503d-130">Berikan rincian yang diperlukan dan pilih **berikutnya** untuk membuat tujuan ekspor.</span><span class="sxs-lookup"><span data-stu-id="8503d-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="8503d-131">Anda juga dapat memilih **konfigurasi** di ubin pada tab **temukan**.</span><span class="sxs-lookup"><span data-stu-id="8503d-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="8503d-132">Lihat Tujuan Ekspor</span><span class="sxs-lookup"><span data-stu-id="8503d-132">View Export destinations</span></span>

<span data-ttu-id="8503d-133">Setelah membuat tujuan ekspor, Anda akan menemukannya dalam tabel di tab **tujuan ekspor saya**. Tabel ini memiliki tiga kolom:</span><span class="sxs-lookup"><span data-stu-id="8503d-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="8503d-134">**Nama tampilan**: nama yang Anda masukkan ketika membuat tujuan.</span><span class="sxs-lookup"><span data-stu-id="8503d-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="8503d-135">**Jenis**: jenis tujuan ekspor yang Anda tetapkan ketika membuat tujuan.</span><span class="sxs-lookup"><span data-stu-id="8503d-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="8503d-136">**Dibuat**: tanggal Anda membuat tujuan.</span><span class="sxs-lookup"><span data-stu-id="8503d-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="8503d-137">Edit tujuan ekspor</span><span class="sxs-lookup"><span data-stu-id="8503d-137">Edit an export destination</span></span>

1. <span data-ttu-id="8503d-138">Pilih elipsis vertikal untuk tujuan ekspor yang akan diedit.</span><span class="sxs-lookup"><span data-stu-id="8503d-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8503d-139">![Elipsis vertikal](media/export-destinations-page-ellipsis.png "Elipsis vertikal")</span><span class="sxs-lookup"><span data-stu-id="8503d-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="8503d-140">Pilih **Edit** dari menu menurun.</span><span class="sxs-lookup"><span data-stu-id="8503d-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="8503d-141">Ubah nilai yang memerlukan pembaruan dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="8503d-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="8503d-142">Ekspor data sesuai permintaan</span><span class="sxs-lookup"><span data-stu-id="8503d-142">Export data on demand</span></span>

<span data-ttu-id="8503d-143">Setelah mengkonfigurasi konektor untuk tujuan ekspor, ekspor akan dijalankan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8503d-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="8503d-144">Untuk mengekspor data tanpa menunggu refresh terjadwal, buka tab **tujuan ekspor saya** pada **admin** > **tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="8503d-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8503d-145">![Elipsis vertikal](media/export-destinations-page-ellipsis.png "Elipsis vertikal")</span><span class="sxs-lookup"><span data-stu-id="8503d-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="8503d-146">Pilih **ekspor** di atas daftar untuk menjalankan ekspor ke semua tujuan ekspor secara bersamaan.</span><span class="sxs-lookup"><span data-stu-id="8503d-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="8503d-147">Pilih elipsis (...) setelah item daftar, lalu pilih pilihan **ekspor** untuk menjalankan ekspor untuk satu tujuan ekspor.</span><span class="sxs-lookup"><span data-stu-id="8503d-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="8503d-148">Menghapus tujuan ekspor</span><span class="sxs-lookup"><span data-stu-id="8503d-148">Remove an Export destination</span></span>

<span data-ttu-id="8503d-149">Untuk menghapus tujuan ekspor, mulai dari halaman **tujuan ekspor** utama.</span><span class="sxs-lookup"><span data-stu-id="8503d-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="8503d-150">Pilih elipsis vertikal untuk tujuan ekspor yang akan dihilangkan.</span><span class="sxs-lookup"><span data-stu-id="8503d-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8503d-151">![Elipsis vertikal](media/export-destinations-page-ellipsis.png "Elipsis vertikal")</span><span class="sxs-lookup"><span data-stu-id="8503d-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="8503d-152">Dari menu dropdown, pilih **hilangkan**.</span><span class="sxs-lookup"><span data-stu-id="8503d-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="8503d-153">Konfirmasikan penghapusan dengan memilih **Hapus** di layar konfirmasi.</span><span class="sxs-lookup"><span data-stu-id="8503d-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
