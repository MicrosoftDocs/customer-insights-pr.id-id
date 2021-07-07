---
title: Konektor Power Automate | Microsoft Docs
description: Buat alur di Microsoft Power Automate dari Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 57be0a204ef920b7a4bb31cf9a5b3a77f96eca0d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305068"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="fe0f7-103">Power Automate connector (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="fe0f7-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="fe0f7-104">Picu aktivitas tertentu agar terjadi secara otomatis jika data Anda berubah dan kelola aliran yang lebih kompleks secara langsung di [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="fe0f7-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="fe0f7-105">Pemicu Power Automate</span><span class="sxs-lookup"><span data-stu-id="fe0f7-105">Power Automate triggers</span></span>

<span data-ttu-id="fe0f7-106">Gunakan memicu untuk membuat alur cloud dan mengotomatisasi tugas berulang, seperti pemberitahuan atau tindakan yang lebih lanjut.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="fe0f7-107">Memicu saat refresh sumber data gagal.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="fe0f7-108">Memicu saat refresh sumber data berhasil.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="fe0f7-109">Memicu bila ambang terlewati pada segmen.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="fe0f7-110">Pemicu terbatas untuk melebihi atas ambang batas.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="fe0f7-111">Memicu bila ambang terlewati pada ukuran bisnis.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="fe0f7-112">Hanya ukuran bisnis tanpa dimensi yang didukung.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="fe0f7-113">Pemicu terbatas untuk melebihi atas ambang batas.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-113">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="fe0f7-114">Picu saat penyegaran penuh (sumber data, segmen, ukuran, ...) selesai.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-114">Trigger when a full refresh of (data sources, segments, measures, ...) is completed.</span></span>
- <span data-ttu-id="fe0f7-115">Pemicu saat refresh proses penyatuan (peta, pencocokan, penggabungan) selesai.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

[<span data-ttu-id="fe0f7-116">Konfigurasikan pemicu di Power Automate.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-116">Configure your triggers in Power Automate.</span></span>](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a><span data-ttu-id="fe0f7-117">Tindakan Power Automate</span><span class="sxs-lookup"><span data-stu-id="fe0f7-117">Power Automate actions</span></span>

<span data-ttu-id="fe0f7-118">Konektor Power Automate menyediakan tindakan lain selain pemicu yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="fe0f7-119">Untuk informasi lebih lanjut, lihat [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="fe0f7-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="fe0f7-120">Buat Alur Power Automate</span><span class="sxs-lookup"><span data-stu-id="fe0f7-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="fe0f7-121">Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fe0f7-122">Di petak **Power Automate**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="fe0f7-123">Customer Insights Connector (pratinjau) dalam Power Automate terbuka.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="fe0f7-124">**Masuk** ke Power Automate.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="fe0f7-125">Pilih salah satu pemicu yang tersedia dan tambahkan langkah lainnya ke alur baru Anda.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="fe0f7-126">Untuk informasi lebih lanjut, lihat [Membuat alur cloud dalam Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="fe0f7-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="fe0f7-127">Contoh cara menggunakan alur:</span><span class="sxs-lookup"><span data-stu-id="fe0f7-127">Examples of how to use flows:</span></span> 
- <span data-ttu-id="fe0f7-128">Posting pesan ke saluran Microsoft Teams jika penyegaran sumber data gagal.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="fe0f7-129">Kirim email ke pemilik data saat ambang batas pada segmen terlewati.</span><span class="sxs-lookup"><span data-stu-id="fe0f7-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
