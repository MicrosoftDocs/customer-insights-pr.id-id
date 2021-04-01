---
title: Ekspor data Customer Insights ke Dynamics 365 Marketing
description: Pelajari cara mengkonfigurasi sambungan ke Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597607"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="d9cc1-103">Konektor untuk Dynamics 365 Marketing (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="d9cc1-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d9cc1-104">Gunakan [segmen](segments.md) untuk membuat kampanye dan hubungi grup pelanggan tertentu dengan Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="d9cc1-105">Untuk informasi lebih lanjut, lihat [menggunakan segmen dari Dynamics 365 Customer Insights dengan Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="d9cc1-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="d9cc1-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="d9cc1-106">Prerequisite</span></span>

- <span data-ttu-id="d9cc1-107">Rekaman kontak harus ada di Dynamics 365 Marketing agar Anda dapat mengekspor segmen dari Customer Insights ke Marketing.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="d9cc1-108">Baca selengkapnya tentang cara menyerap kontak di [Dynamics 365 Marketing menggunakan Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="d9cc1-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="d9cc1-109">Mengekspor segmen dari wawasan audiens ke Marketing tidak akan membuat rekaman kontak baru di instans Marketing.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="d9cc1-110">Rekaman kontak dari Marketing harus digunakan dalam audiens wawasan dan digunakan sebagai sumber data.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="d9cc1-111">Id pelanggan juga harus disertakan dalam entitas Pelanggan terpadu untuk memetakan ID pelanggan agar ID dapat dihubungi sebelum segmen dapat diekspor.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="d9cc1-112">Konfigurasikan konektor untuk Marketing</span><span class="sxs-lookup"><span data-stu-id="d9cc1-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="d9cc1-113">Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d9cc1-114">Di dalam **Dynamics 365 Marketing**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="d9cc1-115">Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d9cc1-116">Masukkan URL Marketing organisasi di **bidang alamat server**.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="d9cc1-117">Di Bagian **akun admin server**, pilih **masuk** dan pilih akun Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="d9cc1-118">Petakan bidang ID pelanggan ke ID kontak Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="d9cc1-119">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-119">Select **Next**.</span></span>

1. <span data-ttu-id="d9cc1-120">Pilih satu atau beberapa segmen.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="d9cc1-121">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="d9cc1-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d9cc1-122">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="d9cc1-122">Export the data</span></span>

<span data-ttu-id="d9cc1-123">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d9cc1-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d9cc1-124">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d9cc1-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]