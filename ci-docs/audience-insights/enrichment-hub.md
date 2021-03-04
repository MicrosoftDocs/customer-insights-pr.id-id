---
title: Perkaya profil pelanggan terpadu
description: Gunakan kemampuan untuk memperkaya data pelanggan Anda.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269472"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="76311-103">Pengayaan untuk profil pelanggan (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="76311-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="76311-104">Gunakan data dari sumber seperti Microsoft dan mitra lainnya untuk memperkaya data pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="76311-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Halaman hub pengayaan":::

<span data-ttu-id="76311-106">Di wawasan audiens, buka **Data** > **pengayaan** untuk menangani pilihan pengayaan.</span><span class="sxs-lookup"><span data-stu-id="76311-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="76311-107">Anda harus memiliki izin kontributor atau Administrator untuk membuat atau mengedit pengayaan.</span><span class="sxs-lookup"><span data-stu-id="76311-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="76311-108">Untuk informasi lebih lanjut, lihat [izin](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="76311-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="76311-109">Pada tab **temukan**, Anda akan menemukan pengayaan berikut:</span><span class="sxs-lookup"><span data-stu-id="76311-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="76311-110">[Merek](enrichment-microsoft-graph.md) yang disediakan oleh Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="76311-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="76311-111">[Minat](enrichment-microsoft-graph.md) Data disediakan oleh Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="76311-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="76311-112">[Data perusahaan](enrichment-leadspace.md) yang disediakan oleh Leadspace</span><span class="sxs-lookup"><span data-stu-id="76311-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="76311-113">[Demografi](enrichment-experian.md) Disediakan oleh Experian</span><span class="sxs-lookup"><span data-stu-id="76311-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="76311-114">[data lokasi](enrichment-here.md) disediakan oleh HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="76311-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="76311-115">[Data Kustom](enrichment-SFTP-custom-import.md) melalui Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="76311-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="76311-116">Pada **tab pengayaan saya**, Anda dapat melihat pengayaan yang telah dikonfigurasi dan mengedit properti mereka.</span><span class="sxs-lookup"><span data-stu-id="76311-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="76311-117">Mengelola pengayaan yang ada</span><span class="sxs-lookup"><span data-stu-id="76311-117">Manage existing enrichments</span></span>

<span data-ttu-id="76311-118">Buka **pengayaan saya** untuk melihat semua pengayaan yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="76311-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="76311-119">Setiap pengayaan ditunjukkan sebagai baris yang mencakup informasi tambahan tentang pengayaan.</span><span class="sxs-lookup"><span data-stu-id="76311-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="76311-120">Pilih pengayaan untuk melihat pilihan yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="76311-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="76311-121">Atau, Anda dapat memilih elipsis (...) pada item daftar untuk melihat pilihan.</span><span class="sxs-lookup"><span data-stu-id="76311-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Pilihan untuk mengelola pengayaan dalam daftar pengayaan":::

- <span data-ttu-id="76311-123">**Lihat** rincian pengayaan dengan jumlah profil pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="76311-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="76311-124">**Edit** konfigurasi pengayaan.</span><span class="sxs-lookup"><span data-stu-id="76311-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="76311-125">**Jalankan** pengayaan untuk memperbarui profil pelanggan dengan data terbaru.</span><span class="sxs-lookup"><span data-stu-id="76311-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="76311-126">**Nonaktifkan** pengayaan yang ada untuk menghentikannya secara otomatis dengan setiap penyegaran terjadwal.</span><span class="sxs-lookup"><span data-stu-id="76311-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="76311-127">Data dari penyegaran yang berhasil terakhir akan terus tersedia.</span><span class="sxs-lookup"><span data-stu-id="76311-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="76311-128">**Aktifkan** pengayaan tidak aktif untuk me-restart penyegaran otomatis dengan setiap penyegaran terjadwal.</span><span class="sxs-lookup"><span data-stu-id="76311-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="76311-129">**Hapus** pengayaan.</span><span class="sxs-lookup"><span data-stu-id="76311-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="76311-130">Anda dapat menjalankan atau menonaktifkan beberapa pengayaan sekaligus dengan memilihnya dalam daftar.</span><span class="sxs-lookup"><span data-stu-id="76311-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="76311-131">Pilihan Lihat dan Edit tidak tersedia sebagai tindakan massal dan hanya berfungsi untuk satu pengayaan setiap kalinya.</span><span class="sxs-lookup"><span data-stu-id="76311-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]