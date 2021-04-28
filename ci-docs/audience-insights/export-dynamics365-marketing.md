---
title: Ekspor data Customer Insights ke Dynamics 365 Marketing
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759641"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="27146-103">Gunakan segmen di Dynamics 365 Marketing (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="27146-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="27146-104">Gunakan [segmen](segments.md) untuk membuat kampanye dan hubungi grup pelanggan tertentu dengan Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="27146-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="27146-105">Untuk informasi lebih lanjut, lihat [menggunakan segmen dari Dynamics 365 Customer Insights dengan Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="27146-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="27146-106">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="27146-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="27146-107">Rekaman kontak harus ada di Dynamics 365 Marketing agar Anda dapat mengekspor segmen dari Customer Insights ke Marketing.</span><span class="sxs-lookup"><span data-stu-id="27146-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="27146-108">Baca selengkapnya tentang cara menyerap kontak di [Dynamics 365 Marketing menggunakan Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="27146-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="27146-109">Mengekspor segmen dari wawasan audiens ke Marketing tidak akan membuat rekaman kontak baru di instans Marketing.</span><span class="sxs-lookup"><span data-stu-id="27146-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="27146-110">Rekaman kontak dari Marketing harus digunakan dalam audiens wawasan dan digunakan sebagai sumber data.</span><span class="sxs-lookup"><span data-stu-id="27146-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="27146-111">Id pelanggan juga harus disertakan dalam entitas Pelanggan terpadu untuk memetakan ID pelanggan agar ID dapat dihubungi sebelum segmen dapat diekspor.</span><span class="sxs-lookup"><span data-stu-id="27146-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="27146-112">Konfigurasikan koneksi ke Marketing</span><span class="sxs-lookup"><span data-stu-id="27146-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="27146-113">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="27146-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="27146-114">Pilih **Tambahkan koneksi** dan pilih **Dynamics 365 Marketing** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="27146-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="27146-115">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="27146-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="27146-116">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="27146-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="27146-117">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="27146-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="27146-118">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="27146-118">Choose who can use this connection.</span></span> <span data-ttu-id="27146-119">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="27146-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="27146-120">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="27146-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="27146-121">Masukkan URL Marketing organisasi di **bidang alamat server**.</span><span class="sxs-lookup"><span data-stu-id="27146-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="27146-122">Di Bagian **akun admin server**, pilih **masuk** dan pilih akun Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="27146-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="27146-123">Petakan bidang ID pelanggan ke ID kontak Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="27146-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="27146-124">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="27146-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="27146-125">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="27146-125">Configure an export</span></span>

<span data-ttu-id="27146-126">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="27146-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="27146-127">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="27146-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="27146-128">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="27146-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="27146-129">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="27146-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="27146-130">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="27146-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="27146-131">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="27146-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="27146-132">Pilih satu atau beberapa segmen.</span><span class="sxs-lookup"><span data-stu-id="27146-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="27146-133">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="27146-133">Select **Save**.</span></span>

<span data-ttu-id="27146-134">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="27146-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="27146-135">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="27146-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="27146-136">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="27146-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
