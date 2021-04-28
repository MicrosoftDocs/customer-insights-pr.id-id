---
title: Perkaya profil pelanggan terpadu
description: Gunakan kemampuan untuk memperkaya data pelanggan Anda.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896009"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="1fadf-103">Pengayaan untuk profil pelanggan (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="1fadf-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="1fadf-104">Gunakan data dari sumber seperti Microsoft dan mitra lainnya untuk memperkaya data pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="1fadf-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Halaman hub pengayaan":::

<span data-ttu-id="1fadf-106">Di wawasan audiens, buka **Data** > **pengayaan** untuk menangani pilihan pengayaan.</span><span class="sxs-lookup"><span data-stu-id="1fadf-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="1fadf-107">Anda harus memiliki izin kontributor atau Administrator untuk membuat atau mengedit pengayaan.</span><span class="sxs-lookup"><span data-stu-id="1fadf-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="1fadf-108">Untuk informasi lebih lanjut, lihat [izin](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="1fadf-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="1fadf-109">Pada tab **temukan**, Anda akan menemukan pengayaan berikut:</span><span class="sxs-lookup"><span data-stu-id="1fadf-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="1fadf-110">[Merek](enrichment-microsoft.md) disediakan oleh Microsoft</span><span class="sxs-lookup"><span data-stu-id="1fadf-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="1fadf-111">[Minat](enrichment-microsoft.md) disediakan oleh Microsoft</span><span class="sxs-lookup"><span data-stu-id="1fadf-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="1fadf-112">[Data perusahaan](enrichment-leadspace.md) yang disediakan oleh Leadspace</span><span class="sxs-lookup"><span data-stu-id="1fadf-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="1fadf-113">[Demografi](enrichment-experian.md) Disediakan oleh Experian</span><span class="sxs-lookup"><span data-stu-id="1fadf-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="1fadf-114">[data lokasi](enrichment-here.md) disediakan oleh HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="1fadf-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="1fadf-115">[Data Kustom](enrichment-SFTP-custom-import.md) melalui Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="1fadf-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="1fadf-116">Pada **tab pengayaan saya**, Anda dapat melihat pengayaan yang telah dikonfigurasi dan mengedit properti mereka.</span><span class="sxs-lookup"><span data-stu-id="1fadf-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="1fadf-117">Mengelola pengayaan yang ada</span><span class="sxs-lookup"><span data-stu-id="1fadf-117">Manage existing enrichments</span></span>

<span data-ttu-id="1fadf-118">Buka **pengayaan saya** untuk melihat semua pengayaan yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="1fadf-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="1fadf-119">Setiap pengayaan ditunjukkan sebagai baris yang mencakup informasi tambahan tentang pengayaan.</span><span class="sxs-lookup"><span data-stu-id="1fadf-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="1fadf-120">Pilih pengayaan untuk melihat pilihan yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="1fadf-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="1fadf-121">Anda juga dapat memilih elipsis (...) pada item daftar untuk melihat opsi.</span><span class="sxs-lookup"><span data-stu-id="1fadf-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Pilihan untuk mengelola pengayaan dalam daftar pengayaan":::

- <span data-ttu-id="1fadf-123">**Lihat** rincian pengayaan dengan jumlah profil pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="1fadf-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="1fadf-124">**Edit** konfigurasi pengayaan.</span><span class="sxs-lookup"><span data-stu-id="1fadf-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="1fadf-125">**Jalankan** pengayaan untuk memperbarui profil pelanggan dengan data terbaru.</span><span class="sxs-lookup"><span data-stu-id="1fadf-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="1fadf-126">**Nonaktifkan** pengayaan yang ada untuk menghentikannya secara otomatis dengan setiap penyegaran terjadwal.</span><span class="sxs-lookup"><span data-stu-id="1fadf-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="1fadf-127">Data dari penyegaran yang berhasil terakhir akan terus tersedia.</span><span class="sxs-lookup"><span data-stu-id="1fadf-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="1fadf-128">**Aktifkan** pengayaan tidak aktif untuk me-restart penyegaran otomatis dengan setiap penyegaran terjadwal.</span><span class="sxs-lookup"><span data-stu-id="1fadf-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="1fadf-129">**Hapus** pengayaan.</span><span class="sxs-lookup"><span data-stu-id="1fadf-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="1fadf-130">Anda dapat menjalankan atau menonaktifkan beberapa pengayaan sekaligus dengan memilihnya dalam daftar.</span><span class="sxs-lookup"><span data-stu-id="1fadf-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="1fadf-131">Pilihan Lihat dan Edit tidak tersedia sebagai tindakan massal dan hanya berfungsi untuk satu pengayaan setiap kalinya.</span><span class="sxs-lookup"><span data-stu-id="1fadf-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="1fadf-132">Koneksi dan pengayaan</span><span class="sxs-lookup"><span data-stu-id="1fadf-132">Enrichments and connections</span></span>

<span data-ttu-id="1fadf-133">Pengayaan pihak ketiga dikonfigurasi menggunakan [koneksi](connections.md), yang diatur administrator dengan kredensial dan memberikan persetujuan untuk transfer data.</span><span class="sxs-lookup"><span data-stu-id="1fadf-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="1fadf-134">Koneksi dapat digunakan untuk mengonfigurasikan pengayaan oleh administrator dan kontributor.</span><span class="sxs-lookup"><span data-stu-id="1fadf-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="1fadf-135">Beberapa pengayaan dengan tipe yang sama</span><span class="sxs-lookup"><span data-stu-id="1fadf-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="1fadf-136">Entitas yang akan diperkaya ditentukan selama konfigurasi pengayaan, yang memungkinkan Anda hanya memperkaya subkumpulan profil Anda.</span><span class="sxs-lookup"><span data-stu-id="1fadf-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="1fadf-137">Untuk exmaple, perkaya data hanya untuk segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="1fadf-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="1fadf-138">Anda dapat mengonfigurasi beberapa pengayaan dengan tipe yang sama dan menggunakan kembali koneksi yang sama.</span><span class="sxs-lookup"><span data-stu-id="1fadf-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="1fadf-139">Beberapa pengayaan akan memiliki batasan jumlah pengayaan dengan jenis yang sama yang dapat dibuat.</span><span class="sxs-lookup"><span data-stu-id="1fadf-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="1fadf-140">Batas dan penggunaan saat ini dapat dilihat pada halaman **Pengayaan**.</span><span class="sxs-lookup"><span data-stu-id="1fadf-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
