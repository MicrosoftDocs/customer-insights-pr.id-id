---
title: Ekspor data Customer Insights ke Dynamics 365 Sales
description: Pelajari cara mengkonfigurasi sambungan ke Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598113"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="1f3f9-103">Konektor untuk Dynamics 365 Sales (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="1f3f9-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1f3f9-104">Gunakan data pelanggan Anda untuk membuat daftar pemasaran, alur kerja tindak lanjut, dan mengirim promosi dengan Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="1f3f9-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="1f3f9-105">Prerequisite</span></span>

1. <span data-ttu-id="1f3f9-106">Rekaman kontak harus ada di Dynamics 365 Sales agar Anda dapat mengekspor segmen dari Customer Insights ke Sales.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="1f3f9-107">Baca selengkapnya tentang cara menyerap kontak di [Dynamics 365 Sales menggunakan Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="1f3f9-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="1f3f9-108">Mengekspor segmen dari wawasan audiens ke Sales tidak akan membuat rekaman kontak baru di instans Sales.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="1f3f9-109">Rekaman kontak dari Sales harus digunakan dalam audiens wawasan dan digunakan sebagai sumber data.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="1f3f9-110">Id pelanggan juga harus disertakan dalam entitas Pelanggan terpadu untuk memetakan ID pelanggan agar ID dapat dihubungi sebelum segmen dapat diekspor.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="1f3f9-111">Konfigurasikan konektor untuk Sales</span><span class="sxs-lookup"><span data-stu-id="1f3f9-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="1f3f9-112">Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1f3f9-113">Di dalam **Dynamics 365 Sales**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="1f3f9-114">Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="1f3f9-115">Masukkan URL Sales organisasi di **bidang alamat server**.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="1f3f9-116">Di Bagian **akun admin server**, pilih **masuk** dan pilih akun Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="1f3f9-117">Petakan bidang ID pelanggan ke ID kontak Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="1f3f9-118">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-118">Select **Next**.</span></span>

1. <span data-ttu-id="1f3f9-119">Pilih satu atau beberapa segmen.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="1f3f9-120">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="1f3f9-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1f3f9-121">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="1f3f9-121">Export the data</span></span>

<span data-ttu-id="1f3f9-122">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1f3f9-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="1f3f9-123">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1f3f9-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]