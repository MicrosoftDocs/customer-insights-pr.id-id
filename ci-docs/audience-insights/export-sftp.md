---
title: Ekspor data Customer Insights ke host SFTP
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke lokasi SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760423"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="daffe-103">Mengekspor daftar segmen dan data lainnya ke SFTP (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="daffe-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="daffe-104">Gunakan data pelanggan Anda dalam aplikasi pihak ketiga dengan mengekspornya ke lokasi Secure File Transfer Protocol (SFTP).</span><span class="sxs-lookup"><span data-stu-id="daffe-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="daffe-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="daffe-105">Prerequisites for connection</span></span>

- <span data-ttu-id="daffe-106">Ketersediaan host SFTP dan kredensial yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="daffe-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="daffe-107">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="daffe-107">Known limitations</span></span>

- <span data-ttu-id="daffe-108">Runtime ekspor tergantung pada kinerja sistem Anda.</span><span class="sxs-lookup"><span data-stu-id="daffe-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="daffe-109">Sebaiknya dua inti CPU dan memori 1 Gb sebagai konfigurasi minimal server Anda.</span><span class="sxs-lookup"><span data-stu-id="daffe-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="daffe-110">Mengekspor entitas dengan hingga 100 juta profil pelanggan dapat berlangsung selama 90 menit bila menggunakan konfigurasi minimal yang disarankan untuk dua inti CPU dan 1 Gb memori.</span><span class="sxs-lookup"><span data-stu-id="daffe-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="daffe-111">Siapkan koneksi ke SFTP</span><span class="sxs-lookup"><span data-stu-id="daffe-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="daffe-112">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="daffe-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="daffe-113">Pilih **Tambahkan koneksi** dan pilih **SFTP** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="daffe-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="daffe-114">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="daffe-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="daffe-115">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="daffe-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="daffe-116">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="daffe-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="daffe-117">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="daffe-117">Choose who can use this connection.</span></span> <span data-ttu-id="daffe-118">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="daffe-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="daffe-119">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="daffe-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="daffe-120">Berikan **nama pengguna**, **sandi**, **nama host**, dan **folder Ekspor** untuk akun SFTP Anda.</span><span class="sxs-lookup"><span data-stu-id="daffe-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="daffe-121">Pilih **Verifikasi** untuk menguji koneksi.</span><span class="sxs-lookup"><span data-stu-id="daffe-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="daffe-122">Pilih jika Anda ingin mengekspor data **dengan di-zip** atau **tidak di-zip** dan **pembatas bidang** untuk file yang diekspor.</span><span class="sxs-lookup"><span data-stu-id="daffe-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="daffe-123">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="daffe-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="daffe-124">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="daffe-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="daffe-125">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="daffe-125">Configure an export</span></span>

<span data-ttu-id="daffe-126">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="daffe-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="daffe-127">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="daffe-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="daffe-128">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="daffe-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="daffe-129">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="daffe-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="daffe-130">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian SFTP.</span><span class="sxs-lookup"><span data-stu-id="daffe-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="daffe-131">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="daffe-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="daffe-132">Pilih entitas, misalnya segmen, yang akan diekspor.</span><span class="sxs-lookup"><span data-stu-id="daffe-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="daffe-133">Setiap entitas yang dipilih akan dibagi menjadi hingga lima file output saat diekspor.</span><span class="sxs-lookup"><span data-stu-id="daffe-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="daffe-134">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="daffe-134">Select **Save**.</span></span>

<span data-ttu-id="daffe-135">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="daffe-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="daffe-136">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="daffe-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="daffe-137">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="daffe-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="daffe-138">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="daffe-138">Data privacy and compliance</span></span>

<span data-ttu-id="daffe-139">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan melalui SFTP, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="daffe-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="daffe-140">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa tujuan ekspor memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="daffe-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="daffe-141">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="daffe-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="daffe-142">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="daffe-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
