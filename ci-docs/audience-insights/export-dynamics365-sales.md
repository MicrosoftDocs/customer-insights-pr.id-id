---
title: Ekspor data Customer Insights ke Dynamics 365 Sales
description: Pelajari cara mengkonfigurasi sambungan ke Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643822"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="a630e-103">Konektor untuk Dynamics 365 Sales (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="a630e-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a630e-104">Gunakan data pelanggan Anda untuk membuat daftar pemasaran, alur kerja tindak lanjut, dan mengirim promosi dengan Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a630e-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a630e-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="a630e-105">Prerequisite</span></span>

<span data-ttu-id="a630e-106">Kontak rekaman dari [Dynamics 365 sales yang diserap dengan Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a630e-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="a630e-107">Konfigurasikan konektor untuk Sales</span><span class="sxs-lookup"><span data-stu-id="a630e-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="a630e-108">Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="a630e-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a630e-109">Di dalam **Dynamics 365 Sales**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="a630e-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="a630e-110">Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="a630e-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a630e-111">Masukkan URL Sales organisasi di **bidang alamat server**.</span><span class="sxs-lookup"><span data-stu-id="a630e-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a630e-112">Di Bagian **akun admin server**, pilih **masuk** dan pilih akun Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="a630e-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="a630e-113">Petakan bidang ID pelanggan ke ID kontak Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a630e-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a630e-114">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="a630e-114">Select **Next**.</span></span>

1. <span data-ttu-id="a630e-115">Pilih satu atau beberapa segmen.</span><span class="sxs-lookup"><span data-stu-id="a630e-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="a630e-116">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="a630e-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a630e-117">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="a630e-117">Export the data</span></span>

<span data-ttu-id="a630e-118">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a630e-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a630e-119">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a630e-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
