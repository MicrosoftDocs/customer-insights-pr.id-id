---
title: Konsumsi data real-time dan keterbatasan
description: Informasi umum tentang kemampuan real-time dalam wawasan audiens.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270284"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="50540-103">Konsumsi data real-time (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="50540-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="50540-104">Fungsi nyaris real-time memungkinkan Anda melihat, dalam hitungan detik, interaksi terbaru yang telah dibuat pelanggan dengan produk atau layanan Anda.</span><span class="sxs-lookup"><span data-stu-id="50540-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="50540-105">[Penyegaran terjadwal](system.md#schedule-tab) mencakup sejumlah besar rekaman dan beberapa operasi kompleks.</span><span class="sxs-lookup"><span data-stu-id="50540-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="50540-106">Pertama, data ditarik dari sumber data.</span><span class="sxs-lookup"><span data-stu-id="50540-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="50540-107">Selanjutnya, data disatukan, lalu diperkaya dengan informasi tambahan.</span><span class="sxs-lookup"><span data-stu-id="50540-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="50540-108">Setiap proses ini dapat berlangsung selama beberapa menit.</span><span class="sxs-lookup"><span data-stu-id="50540-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="50540-109">Fungsi real-time menyediakan data segera untuk dikonsumsi, hingga penyegaran terjadwal berikutnya menarik data ini dari sumber data.</span><span class="sxs-lookup"><span data-stu-id="50540-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="50540-110">Pembaruan Real-time memiliki waktu kedaluwarsa yang setelahnya tidak lagi mengesampingkan nilai dari sumber data:</span><span class="sxs-lookup"><span data-stu-id="50540-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="50540-111">Pembaruan profil akan disimpan selama 4 jam</span><span class="sxs-lookup"><span data-stu-id="50540-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="50540-112">Aktivitas akan disimpan selama 30 hari</span><span class="sxs-lookup"><span data-stu-id="50540-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="50540-113">Nilai ini adalah parameter panggilan API yang dapat Anda ubah.</span><span class="sxs-lookup"><span data-stu-id="50540-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="50540-114">Mereka bertujuan untuk memastikan bahwa data sumber Anda tetap menjadi sumber kebenaran.</span><span class="sxs-lookup"><span data-stu-id="50540-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="50540-115">Jika anda ingin pembaruan real-time dimasukkan lebih lama, anda harus menambahkannya ke sumber data sehingga ditarik selama refresh terjadwal berikutnya.</span><span class="sxs-lookup"><span data-stu-id="50540-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="50540-116">Pembaruan real-time atas bidang profil pelanggan terpadu</span><span class="sxs-lookup"><span data-stu-id="50540-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="50540-117">Profil yang diperbarui akan ditampilkan di tampilan kartu pelanggan, atau visualisasi lainnya, dalam beberapa detik.</span><span class="sxs-lookup"><span data-stu-id="50540-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="50540-118">Karena operasi real-time terjadi setelah penyatuan data terjadi, itu hanya berlaku untuk profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="50540-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="50540-119">Akibatnya, perubahan profil secara real-time tidak akan memperbarui tindakan, keanggotaan segmen, atau pengayaan.</span><span class="sxs-lookup"><span data-stu-id="50540-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="50540-120">Batasan</span><span class="sxs-lookup"><span data-stu-id="50540-120">Limitations</span></span>

- <span data-ttu-id="50540-121">Profil pelanggan dapat diperbarui, namun tidak dibuat atau dihapus.</span><span class="sxs-lookup"><span data-stu-id="50540-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="50540-122">Mengekspor pembaruan real-time ke sistem eksternal, seperti Power BI, tidak dapat dilakukan saat ini.</span><span class="sxs-lookup"><span data-stu-id="50540-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="50540-123">Pembuatan real-time aktivitas</span><span class="sxs-lookup"><span data-stu-id="50540-123">Real-time creation of activities</span></span>

<span data-ttu-id="50540-124">API real-time memungkinkan Anda mempublikasikan aktivitas baru dari sistem sumber (rekaman sumber individual) ke profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="50540-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="50540-125">Aktivitas baru akan tersedia sebagai aktivitas terpadu dalam Timeline profil pelanggan terpadu dalam hitungan detik.</span><span class="sxs-lookup"><span data-stu-id="50540-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="50540-126">Anda dapat melihat Timeline di tampilan kartu pelanggan atau integrasi Timeline lain yang Anda konfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="50540-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="50540-127">Aktivitas tidak dapat diubah.</span><span class="sxs-lookup"><span data-stu-id="50540-127">Activities are immutable.</span></span> <span data-ttu-id="50540-128">Mereka tidak berubah setelah dibuat.</span><span class="sxs-lookup"><span data-stu-id="50540-128">They don't change once created.</span></span>
> - <span data-ttu-id="50540-129">Saat ini, segmen dan langkah tidak diperbarui berdasarkan aktivitas baru.</span><span class="sxs-lookup"><span data-stu-id="50540-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="50540-130">Aktivitas yang ditambahkan hanya melalui API real-time bukan bagian dari ekspor dan tidak akan ditampilkan di PowerBI.</span><span class="sxs-lookup"><span data-stu-id="50540-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="50540-131">Ada dua cara untuk menyambung ke API real-time:</span><span class="sxs-lookup"><span data-stu-id="50540-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="50540-132">[secara tidak langsung](#connect-via-the-dynamics-365-customer-insights-connector), menggunakan [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="50540-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="50540-133">[secara langsung](#connect-directly-to-the-real-time-api), dengan kode</span><span class="sxs-lookup"><span data-stu-id="50540-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="50540-134">Kedua cara sama-sama memiliki prasyarat berikut:</span><span class="sxs-lookup"><span data-stu-id="50540-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="50540-135">Lingkungan Customer Insights</span><span class="sxs-lookup"><span data-stu-id="50540-135">A Customer Insights environment</span></span>
- <span data-ttu-id="50540-136">Profil pelanggan terpadu</span><span class="sxs-lookup"><span data-stu-id="50540-136">Unified customer profiles</span></span>
- <span data-ttu-id="50540-137">Aktivitas yang dikonfigurasi dan dijalankan</span><span class="sxs-lookup"><span data-stu-id="50540-137">Activities configured and run</span></span>
- <span data-ttu-id="50540-138">Izin kontributor atau Administrator untuk mengotentikasi akun anda</span><span class="sxs-lookup"><span data-stu-id="50540-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="50540-139">Sambungkan melalui Dynamics 365 Customer Insights connector</span><span class="sxs-lookup"><span data-stu-id="50540-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="50540-140">Real-Time API dapat menyerap data dari Power Platform connector khusus, [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), tanpa harus menulis dan menyebarkan kode apa pun.</span><span class="sxs-lookup"><span data-stu-id="50540-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="50540-141">Konektor dapat melakukan tindakan real-time yang sama dengan API.</span><span class="sxs-lookup"><span data-stu-id="50540-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="50540-142">Anda memerlukan lisensi yang valid untuk konektor Premium.</span><span class="sxs-lookup"><span data-stu-id="50540-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="50540-143">Untuk informasi lebih lanjut, lihat [pertanyaan umum lisensi Power Automate dan Power Apps](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="50540-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="50540-144">Power Platform [Power Apps dan/atau Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="50540-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="50540-145">Azure [Aplikasi Logika](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="50540-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="50540-146">Untuk rincian tentang pembuatan alur, lihat [dokumentasi Power Automate](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="50540-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="50540-147">Terhubung langsung ke API real-time</span><span class="sxs-lookup"><span data-stu-id="50540-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="50540-148">Anda dapat menggunakan kemampuan real-time dengan membuat alur sendiri dan terhubung langsung ke API real-time.</span><span class="sxs-lookup"><span data-stu-id="50540-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="50540-149">Anda dapat memposting aktivitas dalam format sistem sumber atau dalam format UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="50540-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="50540-150">Dapatkan format dengan membuat panggilan API ke /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="50540-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="50540-151">Rincian API ini, termasuk parameter dan respons, dapat ditemukan di bagian **EntityData** di [referensi API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="50540-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="50540-152">Untuk informasi lebih lanjut, lihat [bekerja dengan api Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="50540-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="50540-153">Memahami penggunaan real-time Anda dengan telemetri</span><span class="sxs-lookup"><span data-stu-id="50540-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="50540-154">Dapatkan ikhtisar tentang volume permintaan ke API real-time dan informasi tentang masalah yang mungkin dihadapi sistem.</span><span class="sxs-lookup"><span data-stu-id="50540-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="50540-155">Anda dapat [mengakses telemetri real-time](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="50540-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]