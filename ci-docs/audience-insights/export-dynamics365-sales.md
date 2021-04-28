---
title: Ekspor data Customer Insights ke Dynamics 365 Sales
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc1a05ba4d21d96aa1a9724d158687bbb86949b6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759608"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="2f51d-103">Gunakan segmen di Dynamics 365 Sales (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="2f51d-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="2f51d-104">Gunakan data pelanggan Anda untuk membuat daftar pemasaran, alur kerja tindak lanjut, dan mengirim promosi dengan Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="2f51d-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="2f51d-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="2f51d-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="2f51d-106">Rekaman kontak harus ada di Dynamics 365 Sales agar Anda dapat mengekspor segmen dari Customer Insights ke Sales.</span><span class="sxs-lookup"><span data-stu-id="2f51d-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="2f51d-107">Baca selengkapnya tentang cara menyerap kontak di [Dynamics 365 Sales menggunakan Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="2f51d-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="2f51d-108">Mengekspor segmen dari wawasan audiens ke Sales tidak akan membuat rekaman kontak baru di instans Sales.</span><span class="sxs-lookup"><span data-stu-id="2f51d-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="2f51d-109">Rekaman kontak dari Sales harus digunakan dalam audiens wawasan dan digunakan sebagai sumber data.</span><span class="sxs-lookup"><span data-stu-id="2f51d-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="2f51d-110">Id pelanggan juga harus disertakan dalam entitas Pelanggan terpadu untuk memetakan ID pelanggan agar ID dapat dihubungi sebelum segmen dapat diekspor.</span><span class="sxs-lookup"><span data-stu-id="2f51d-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="2f51d-111">Konfigurasikan koneksi ke Sales</span><span class="sxs-lookup"><span data-stu-id="2f51d-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="2f51d-112">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="2f51d-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2f51d-113">Pilih **Tambahkan koneksi** dan pilih **Dynamics 365 Sales** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="2f51d-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="2f51d-114">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="2f51d-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2f51d-115">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="2f51d-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2f51d-116">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="2f51d-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2f51d-117">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="2f51d-117">Choose who can use this connection.</span></span> <span data-ttu-id="2f51d-118">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="2f51d-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2f51d-119">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2f51d-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2f51d-120">Masukkan URL Sales organisasi di **bidang alamat server**.</span><span class="sxs-lookup"><span data-stu-id="2f51d-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="2f51d-121">Di Bagian **akun admin server**, pilih **masuk** dan pilih akun Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="2f51d-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="2f51d-122">Petakan bidang ID pelanggan ke ID kontak Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="2f51d-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="2f51d-123">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="2f51d-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="2f51d-124">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="2f51d-124">Configure an export</span></span>

<span data-ttu-id="2f51d-125">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="2f51d-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2f51d-126">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2f51d-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2f51d-127">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="2f51d-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2f51d-128">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="2f51d-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2f51d-129">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="2f51d-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="2f51d-130">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="2f51d-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2f51d-131">Pilih satu atau beberapa segmen.</span><span class="sxs-lookup"><span data-stu-id="2f51d-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="2f51d-132">Pilih **Simpan**</span><span class="sxs-lookup"><span data-stu-id="2f51d-132">Select **Save**</span></span>

<span data-ttu-id="2f51d-133">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="2f51d-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2f51d-134">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2f51d-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2f51d-135">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2f51d-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
