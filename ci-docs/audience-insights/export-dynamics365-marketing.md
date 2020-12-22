---
title: Ekspor data Customer Insights ke Dynamics 365 Marketing
description: Pelajari cara mengkonfigurasi sambungan ke Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643777"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="71882-103">Konektor untuk Dynamics 365 Marketing (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="71882-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="71882-104">Gunakan [segmen](segments.md) untuk membuat kampanye dan hubungi grup pelanggan tertentu dengan Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="71882-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="71882-105">Untuk informasi lebih lanjut, lihat [menggunakan segmen dari Dynamics 365 Customer Insights dengan Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="71882-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="71882-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="71882-106">Prerequisite</span></span>

<span data-ttu-id="71882-107">Kontak rekaman dari [Common Data Service yang diserap Dynamics 365 Marketing](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="71882-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="71882-108">Konfigurasikan konektor untuk Marketing</span><span class="sxs-lookup"><span data-stu-id="71882-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="71882-109">Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="71882-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="71882-110">Di dalam **Dynamics 365 Marketing**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="71882-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="71882-111">Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="71882-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="71882-112">Masukkan URL Marketing organisasi di **bidang alamat server**.</span><span class="sxs-lookup"><span data-stu-id="71882-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="71882-113">Di Bagian **akun admin server**, pilih **masuk** dan pilih akun Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="71882-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="71882-114">Petakan bidang ID pelanggan ke ID kontak Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="71882-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="71882-115">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="71882-115">Select **Next**.</span></span>

1. <span data-ttu-id="71882-116">Pilih satu atau beberapa segmen.</span><span class="sxs-lookup"><span data-stu-id="71882-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="71882-117">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="71882-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="71882-118">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="71882-118">Export the data</span></span>

<span data-ttu-id="71882-119">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="71882-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="71882-120">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="71882-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
