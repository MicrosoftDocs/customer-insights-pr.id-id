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
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954491"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="94e17-103">Pengayaan untuk profil pelanggan (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="94e17-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="94e17-104">Gunakan data dari sumber seperti Microsoft dan mitra lainnya untuk memperkaya data pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="94e17-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Halaman hub pengayaan":::

<span data-ttu-id="94e17-106">Di wawasan audiens, buka **Data** > **pengayaan** untuk menangani pilihan pengayaan.</span><span class="sxs-lookup"><span data-stu-id="94e17-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="94e17-107">Anda harus memiliki izin kontributor atau Administrator untuk membuat atau mengedit pengayaan.</span><span class="sxs-lookup"><span data-stu-id="94e17-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="94e17-108">Untuk informasi lebih lanjut, lihat [izin](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="94e17-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="94e17-109">Pada tab **temukan**, Anda akan menemukan pengayaan berikut:</span><span class="sxs-lookup"><span data-stu-id="94e17-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="94e17-110">[Merek](enrichment-microsoft.md) disediakan oleh Microsoft</span><span class="sxs-lookup"><span data-stu-id="94e17-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="94e17-111">[Minat](enrichment-microsoft.md) disediakan oleh Microsoft</span><span class="sxs-lookup"><span data-stu-id="94e17-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="94e17-112">[Alamat disempurnakan](enrichment-enhanced-addresses.md) yang disediakan oleh Microsoft</span><span class="sxs-lookup"><span data-stu-id="94e17-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="94e17-113">[Data perusahaan](enrichment-leadspace.md) yang disediakan oleh Leadspace</span><span class="sxs-lookup"><span data-stu-id="94e17-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="94e17-114">[Demografi](enrichment-experian.md) Disediakan oleh Experian</span><span class="sxs-lookup"><span data-stu-id="94e17-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="94e17-115">[data lokasi](enrichment-here.md) disediakan oleh HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="94e17-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="94e17-116">[Data Kustom](enrichment-SFTP-custom-import.md) melalui Secure File Transfer Protocol (SFTP)</span><span class="sxs-lookup"><span data-stu-id="94e17-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="94e17-117">Pada **tab pengayaan saya**, Anda dapat melihat pengayaan yang telah dikonfigurasi dan mengedit properti mereka.</span><span class="sxs-lookup"><span data-stu-id="94e17-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="94e17-118">Mengelola pengayaan yang ada</span><span class="sxs-lookup"><span data-stu-id="94e17-118">Manage existing enrichments</span></span>

<span data-ttu-id="94e17-119">Buka **pengayaan saya** untuk melihat semua pengayaan yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="94e17-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="94e17-120">Setiap pengayaan ditunjukkan sebagai baris yang mencakup informasi tambahan tentang pengayaan.</span><span class="sxs-lookup"><span data-stu-id="94e17-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="94e17-121">Pilih pengayaan untuk melihat pilihan yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="94e17-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="94e17-122">Anda juga dapat memilih elipsis (...) pada item daftar untuk melihat opsi.</span><span class="sxs-lookup"><span data-stu-id="94e17-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Pilihan untuk mengelola pengayaan dalam daftar pengayaan":::

- <span data-ttu-id="94e17-124">**Lihat** rincian pengayaan dengan jumlah profil pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="94e17-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="94e17-125">**Edit** konfigurasi pengayaan.</span><span class="sxs-lookup"><span data-stu-id="94e17-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="94e17-126">**Jalankan** pengayaan untuk memperbarui profil pelanggan dengan data terbaru.</span><span class="sxs-lookup"><span data-stu-id="94e17-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="94e17-127">**Nonaktifkan** pengayaan yang ada untuk menghentikannya secara otomatis dengan setiap penyegaran terjadwal.</span><span class="sxs-lookup"><span data-stu-id="94e17-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="94e17-128">Data dari penyegaran yang berhasil terakhir akan terus tersedia.</span><span class="sxs-lookup"><span data-stu-id="94e17-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="94e17-129">**Aktifkan** pengayaan tidak aktif untuk me-restart penyegaran otomatis dengan setiap penyegaran terjadwal.</span><span class="sxs-lookup"><span data-stu-id="94e17-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="94e17-130">**Hapus** pengayaan.</span><span class="sxs-lookup"><span data-stu-id="94e17-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="94e17-131">Anda dapat menjalankan atau menonaktifkan beberapa pengayaan sekaligus dengan memilihnya dalam daftar.</span><span class="sxs-lookup"><span data-stu-id="94e17-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="94e17-132">Pilihan Lihat dan Edit tidak tersedia sebagai tindakan massal dan hanya berfungsi untuk satu pengayaan setiap kalinya.</span><span class="sxs-lookup"><span data-stu-id="94e17-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="94e17-133">Koneksi dan pengayaan</span><span class="sxs-lookup"><span data-stu-id="94e17-133">Enrichments and connections</span></span>

<span data-ttu-id="94e17-134">Pengayaan pihak ketiga dikonfigurasi menggunakan [koneksi](connections.md), yang diatur administrator dengan kredensial dan memberikan persetujuan untuk transfer data.</span><span class="sxs-lookup"><span data-stu-id="94e17-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="94e17-135">Koneksi dapat digunakan untuk mengonfigurasikan pengayaan oleh administrator dan kontributor.</span><span class="sxs-lookup"><span data-stu-id="94e17-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="94e17-136">Beberapa pengayaan dengan tipe yang sama</span><span class="sxs-lookup"><span data-stu-id="94e17-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="94e17-137">Entitas yang akan diperkaya ditentukan selama konfigurasi pengayaan, yang memungkinkan Anda hanya memperkaya subkumpulan profil Anda.</span><span class="sxs-lookup"><span data-stu-id="94e17-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="94e17-138">Untuk exmaple, perkaya data hanya untuk segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="94e17-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="94e17-139">Anda dapat mengonfigurasi beberapa pengayaan dengan tipe yang sama dan menggunakan kembali koneksi yang sama.</span><span class="sxs-lookup"><span data-stu-id="94e17-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="94e17-140">Beberapa pengayaan akan memiliki batasan jumlah pengayaan dengan jenis yang sama yang dapat dibuat.</span><span class="sxs-lookup"><span data-stu-id="94e17-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="94e17-141">Batas dan penggunaan saat ini dapat dilihat pada halaman **Pengayaan**.</span><span class="sxs-lookup"><span data-stu-id="94e17-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
