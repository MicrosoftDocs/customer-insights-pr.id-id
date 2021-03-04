---
title: Konektor Power Automate | Microsoft Docs
description: Buat alur di Microsoft Power Automate dari Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268828"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="2401a-103">Power Automate connector (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="2401a-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="2401a-104">Picu aktivitas tertentu agar terjadi secara otomatis jika data Anda berubah dan kelola aliran yang lebih kompleks secara langsung di [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="2401a-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="2401a-105">Pemicu Power Automate</span><span class="sxs-lookup"><span data-stu-id="2401a-105">Power Automate triggers</span></span>

<span data-ttu-id="2401a-106">Gunakan memicu untuk membuat alur cloud dan mengotomatisasi tugas berulang, seperti pemberitahuan atau tindakan yang lebih lanjut.</span><span class="sxs-lookup"><span data-stu-id="2401a-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="2401a-107">Memicu saat refresh sumber data gagal.</span><span class="sxs-lookup"><span data-stu-id="2401a-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="2401a-108">Memicu saat refresh sumber data berhasil.</span><span class="sxs-lookup"><span data-stu-id="2401a-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="2401a-109">Memicu bila ambang terlewati pada segmen.</span><span class="sxs-lookup"><span data-stu-id="2401a-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="2401a-110">Pemicu terbatas untuk melebihi atas ambang batas.</span><span class="sxs-lookup"><span data-stu-id="2401a-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="2401a-111">Memicu bila ambang terlewati pada ukuran bisnis.</span><span class="sxs-lookup"><span data-stu-id="2401a-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="2401a-112">Pemicu terbatas untuk melebihi atas ambang batas.</span><span class="sxs-lookup"><span data-stu-id="2401a-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="2401a-113">Picu saat penyegaran penuh (sumber data, segmen, ukuran,...) selesai.</span><span class="sxs-lookup"><span data-stu-id="2401a-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="2401a-114">Pemicu saat refresh proses penyatuan (peta, pencocokan, penggabungan) selesai.</span><span class="sxs-lookup"><span data-stu-id="2401a-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="2401a-115">[Konfigurasikan pemicu di Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="2401a-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="2401a-116">Tindakan Power Automate</span><span class="sxs-lookup"><span data-stu-id="2401a-116">Power Automate actions</span></span>
<span data-ttu-id="2401a-117">Konektor Power Automate menyediakan tindakan lain selain pemicu yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="2401a-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="2401a-118">Untuk informasi lebih lanjut, lihat [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="2401a-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="2401a-119">Buat Alur Power Automate</span><span class="sxs-lookup"><span data-stu-id="2401a-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="2401a-120">Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="2401a-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2401a-121">Di petak **Power Automate**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="2401a-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="2401a-122">Customer Insights Connector (pratinjau) dalam Power Automate terbuka.</span><span class="sxs-lookup"><span data-stu-id="2401a-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="2401a-123">**Masuk** ke Power Automate.</span><span class="sxs-lookup"><span data-stu-id="2401a-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="2401a-124">Pilih salah satu pemicu yang tersedia dan tambahkan langkah lainnya ke alur baru Anda.</span><span class="sxs-lookup"><span data-stu-id="2401a-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="2401a-125">Untuk informasi lebih lanjut, lihat [Membuat alur cloud dalam Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="2401a-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="2401a-126">Contoh cara menggunakan alur:</span><span class="sxs-lookup"><span data-stu-id="2401a-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="2401a-127">Posting pesan ke saluran Microsoft Teams jika penyegaran sumber data gagal.</span><span class="sxs-lookup"><span data-stu-id="2401a-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="2401a-128">Kirim email ke pemilik data saat ambang batas pada segmen terlewati.</span><span class="sxs-lookup"><span data-stu-id="2401a-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]