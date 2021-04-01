---
title: Wawasan segmen untuk segmen yang ada
description: Dapatkan wawasan tentang segmen yang ada untuk melihat perbedaan dan kesamaan.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 90ebcaab896c628b04e751ad9857e924749895e7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595338"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="6312e-103">Wawasan segmen (Pratinjau)</span><span class="sxs-lookup"><span data-stu-id="6312e-103">Segment insights (preview)</span></span>

<span data-ttu-id="6312e-104">Temukan informasi dan wawasan tambahan seputar segmen yang ada.</span><span class="sxs-lookup"><span data-stu-id="6312e-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="6312e-105">Cari tahu apa yang membedakan dua segmen atau kesamaan.</span><span class="sxs-lookup"><span data-stu-id="6312e-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="6312e-106">Tumpang Tindih Segmen</span><span class="sxs-lookup"><span data-stu-id="6312e-106">Segment overlap</span></span>

<span data-ttu-id="6312e-107">Analisis tumpang tindih segmen menunjukkan berapa banyak dan pelanggan mana yang memiliki kesamaan untuk dua atau beberapa segmen.</span><span class="sxs-lookup"><span data-stu-id="6312e-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="6312e-108">Misalnya, cara segmen pelanggan sering tumpang tindih dengan segmen yang berisi Pelanggan yang puas dengan layanan atau produk Anda.</span><span class="sxs-lookup"><span data-stu-id="6312e-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="6312e-109">Anda juga dapat menganalisis bagaimana perubahan tumpang tindih untuk atribut tertentu.</span><span class="sxs-lookup"><span data-stu-id="6312e-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="6312e-110">Menjalankan analisis tumpang tindih</span><span class="sxs-lookup"><span data-stu-id="6312e-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="6312e-111">Buka **segmen**, lalu pilih tab **wawasan (pratinjau)**.</span><span class="sxs-lookup"><span data-stu-id="6312e-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="6312e-112">Pilih **baru**, lalu pilih pilihan **tumpang tindih** di panel **Pilih jenis wawasan**.</span><span class="sxs-lookup"><span data-stu-id="6312e-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="6312e-113">Pilih segmen minat dan pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="6312e-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="6312e-114">Atau, pilih satu atau beberapa bidang yang diinginkan untuk menganalisis tumpang tindih untuk setiap nilai bidang yang mungkin dan pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="6312e-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="6312e-115">Berikan nama untuk analisis tumpang tindih, nama tampilan opsional, dan deskripsi.</span><span class="sxs-lookup"><span data-stu-id="6312e-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="6312e-116">Untuk mulai menganalisis, pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="6312e-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="6312e-117">Analisis tumpang tindih siap saat status berubah dari penyegaran menjadi berhasil.</span><span class="sxs-lookup"><span data-stu-id="6312e-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="6312e-118">Melihat dan mengoptimalkan analisis tumpang tindih</span><span class="sxs-lookup"><span data-stu-id="6312e-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="6312e-119">Setelah menyelesaikan analisis, temukan rincian tentang wawasan ini di **segmen** > **wawasan (pratinjau)**.</span><span class="sxs-lookup"><span data-stu-id="6312e-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Rincian wawasan tumpang tindih segmen":::

<span data-ttu-id="6312e-121">Pilih wawasan untuk melihat hasil analisis:</span><span class="sxs-lookup"><span data-stu-id="6312e-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="6312e-122">Jumlah anggota yang tumpang tindih di segmen yang dipilih untuk analisis.</span><span class="sxs-lookup"><span data-stu-id="6312e-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="6312e-123">Jumlah anggota yang tercakup dalam salah satu segmen namun tidak di segmen lainnya.</span><span class="sxs-lookup"><span data-stu-id="6312e-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="6312e-124">Jika Anda memilih bidang saat mengkonfigurasi analisis tumpang tindih, Anda akan menemukannya di tab yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="6312e-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="6312e-125">Anda dapat menggunakan drop-down filter untuk memilih tingkat atribut yang menarik dan tabel di bagian bawah akan menampilkan data yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="6312e-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="6312e-126">Pembeda segmen</span><span class="sxs-lookup"><span data-stu-id="6312e-126">Segment differentiators</span></span>

<span data-ttu-id="6312e-127">Pembeda segmen membantu Anda mengetahui apa yang membedakan segmen dari pelanggan atau segmen lain.</span><span class="sxs-lookup"><span data-stu-id="6312e-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="6312e-128">Anda hanya perlu memilih segmen dan sistem akan mengidentifikasi atribut dan ukuran profil yang membedakan segmen yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="6312e-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="6312e-129">Menjalankan analisis pembeda</span><span class="sxs-lookup"><span data-stu-id="6312e-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="6312e-130">Buka **segmen**, lalu pilih tab **wawasan (pratinjau)**.</span><span class="sxs-lookup"><span data-stu-id="6312e-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="6312e-131">Pilih **baru**, lalu pilih pilihan **tumpang tindih** di panel **Pilih jenis wawasan**.</span><span class="sxs-lookup"><span data-stu-id="6312e-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="6312e-132">Pilih segmen yang akan dianalisis sebagai **segmen utama,** lalu pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="6312e-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="6312e-133">Pilih **semua pelanggan** atau **segmen sekunder** untuk membandingkan segmen utama dengan dan pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="6312e-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="6312e-134">Atau, pilih satu atau beberapa bidang menarik untuk memfokuskan analisis pada atribut tertentu dan pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="6312e-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="6312e-135">Berikan nama untuk analisis tumpang tindih, nama tampilan opsional, dan deskripsi.</span><span class="sxs-lookup"><span data-stu-id="6312e-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="6312e-136">Untuk mulai menganalisis, pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="6312e-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="6312e-137">Analisis tumpang tindih siap saat status berubah dari penyegaran menjadi berhasil.</span><span class="sxs-lookup"><span data-stu-id="6312e-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="6312e-138">Melihat dan mengoptimalkan analisis pembeda</span><span class="sxs-lookup"><span data-stu-id="6312e-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="6312e-139">Setelah menyelesaikan analisis, temukan rincian tentang wawasan ini di **segmen** > **wawasan (pratinjau)**.</span><span class="sxs-lookup"><span data-stu-id="6312e-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Rincian wawasan pembeda segmen":::

<span data-ttu-id="6312e-141">Pilih wawasan untuk melihat hasil analisis.</span><span class="sxs-lookup"><span data-stu-id="6312e-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="6312e-142">Analisis pembeda mencakup dua tab.</span><span class="sxs-lookup"><span data-stu-id="6312e-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="6312e-143">Tab **atribut** berisi daftar atribut profil yang dianggap sebagai pembeda.</span><span class="sxs-lookup"><span data-stu-id="6312e-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="6312e-144">Tab **Ukuran** mencantumkan pembeda.</span><span class="sxs-lookup"><span data-stu-id="6312e-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="6312e-145">Setiap tab mencakup rincian berikut:</span><span class="sxs-lookup"><span data-stu-id="6312e-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="6312e-146">Daftar pembeda peringkat, diurutkan berdasarkan Skor perbedaan.</span><span class="sxs-lookup"><span data-stu-id="6312e-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="6312e-147">**Skor perbedaan** untuk setiap pembeda.</span><span class="sxs-lookup"><span data-stu-id="6312e-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="6312e-148">Skor perbedaan menunjukkan tingkat perbedaan atribut antara dua segmen.</span><span class="sxs-lookup"><span data-stu-id="6312e-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="6312e-149">Semakin tinggi Skor perbedaannya, semakin banyak atribut yang berbeda di antara kedua segmen.</span><span class="sxs-lookup"><span data-stu-id="6312e-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="6312e-150">Pilih Skor untuk membuka panel **Skor perbedaan** dengan distribusi nilai untuk atribut tersebut.</span><span class="sxs-lookup"><span data-stu-id="6312e-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="6312e-151">Mengelola wawasan segmen</span><span class="sxs-lookup"><span data-stu-id="6312e-151">Manage segment insights</span></span>

<span data-ttu-id="6312e-152">Anda dapat menggunakan pilihan berikut pada wawasan Anda dari bilah perintah:</span><span class="sxs-lookup"><span data-stu-id="6312e-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="6312e-153">**Kembali** untuk mengembalikan daftar wawasan</span><span class="sxs-lookup"><span data-stu-id="6312e-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="6312e-154">**Segarkan** untuk menjalankan analisis lagi</span><span class="sxs-lookup"><span data-stu-id="6312e-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="6312e-155">**Hapus** untuk menghapus wawasan ini</span><span class="sxs-lookup"><span data-stu-id="6312e-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]