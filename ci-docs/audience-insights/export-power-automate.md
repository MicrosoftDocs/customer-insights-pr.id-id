---
title: Konektor Power Automate | Microsoft Docs
description: Buat alur di Microsoft Power Automate dari Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406035"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="d7d25-103">Power Automate connector (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="d7d25-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="d7d25-104">Picu aktivitas tertentu agar terjadi secara otomatis jika data Anda berubah dan kelola aliran yang lebih kompleks secara langsung di [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="d7d25-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="d7d25-105">Pemicu Power Automate</span><span class="sxs-lookup"><span data-stu-id="d7d25-105">Power Automate triggers</span></span>

<span data-ttu-id="d7d25-106">Anda dapat menggunakan berbagai pemicu yang memungkinkan Anda membuat alur untuk mengotomatisasi tugas yang berulang-ulang, seperti pemberitahuan atau tindakan yang lebih canggih.</span><span class="sxs-lookup"><span data-stu-id="d7d25-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="d7d25-107">Memicu saat refresh sumber data gagal.</span><span class="sxs-lookup"><span data-stu-id="d7d25-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="d7d25-108">Memicu saat refresh sumber data berhasil.</span><span class="sxs-lookup"><span data-stu-id="d7d25-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="d7d25-109">Memicu bila ambang terlewati pada segmen.</span><span class="sxs-lookup"><span data-stu-id="d7d25-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="d7d25-110">Pemicu terbatas untuk melebihi atas ambang batas.</span><span class="sxs-lookup"><span data-stu-id="d7d25-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="d7d25-111">Memicu bila ambang terlewati pada ukuran bisnis.</span><span class="sxs-lookup"><span data-stu-id="d7d25-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="d7d25-112">Pemicu terbatas untuk melebihi atas ambang batas.</span><span class="sxs-lookup"><span data-stu-id="d7d25-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="d7d25-113">Picu saat penyegaran penuh (sumber data, segmen, ukuran,...) selesai.</span><span class="sxs-lookup"><span data-stu-id="d7d25-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="d7d25-114">Pemicu saat refresh proses penyatuan (peta, pencocokan, penggabungan) selesai.</span><span class="sxs-lookup"><span data-stu-id="d7d25-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="d7d25-115">[Konfigurasikan pemicu di Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="d7d25-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="d7d25-116">Tindakan Power Automate</span><span class="sxs-lookup"><span data-stu-id="d7d25-116">Power Automate actions</span></span>
<span data-ttu-id="d7d25-117">Konektor Power Automate menyediakan tindakan lain selain pemicu yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="d7d25-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="d7d25-118">Untuk informasi lebih lanjut, lihat [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="d7d25-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="d7d25-119">Membuat alur Power Automate di wawasan audiens</span><span class="sxs-lookup"><span data-stu-id="d7d25-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="d7d25-120">Di wawasan audiens, buka **Admin** > **Sistem**.</span><span class="sxs-lookup"><span data-stu-id="d7d25-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="d7d25-121">Di halaman **Sistem**, pilih tab **Status**.</span><span class="sxs-lookup"><span data-stu-id="d7d25-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="d7d25-122">Di Bagian **sumber data**, pilih **alur**, lalu pilih **buat alur** dari daftar menurun.</span><span class="sxs-lookup"><span data-stu-id="d7d25-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d7d25-123">![Power Automate connector yang menampilkan tindakan membuat alur](media/power-automate-connector-create-flow.png "Power Automate connector yang menampilkan tindakan membuat alur")</span><span class="sxs-lookup"><span data-stu-id="d7d25-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="d7d25-124">Di Power Automate, pilih salah satu pemicu yang tersedia untuk membuat alur yang diinginkan.</span><span class="sxs-lookup"><span data-stu-id="d7d25-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="d7d25-125">Jika Anda membuat alur pertama, Anda harus mengotentikasi dengan Power Automate connector terlebih dulu.</span><span class="sxs-lookup"><span data-stu-id="d7d25-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
