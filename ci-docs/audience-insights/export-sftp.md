---
title: Ekspor data Customer Insights ke host SFTP
description: Pelajari cara mengkonfigurasi sambungan ke host SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598389"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="e0336-103">Konektor untuk SFTP (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="e0336-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="e0336-104">Gunakan data pelanggan di aplikasi pihak ketiga dengan mengekspornya ke host Secure File Transfer Protocol(SFTP).</span><span class="sxs-lookup"><span data-stu-id="e0336-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e0336-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="e0336-105">Prerequisites</span></span>

- <span data-ttu-id="e0336-106">Ketersediaan host SFTP dan kredensial yang sesuai.</span><span class="sxs-lookup"><span data-stu-id="e0336-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="e0336-107">Sambungkan ke SFTP</span><span class="sxs-lookup"><span data-stu-id="e0336-107">Connect to SFTP</span></span>

1. <span data-ttu-id="e0336-108">Buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="e0336-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e0336-109">Di dalam **SFTP**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="e0336-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="e0336-110">Beri nama yang dikenali di bidang **nama tampilan** tujuan anda.</span><span class="sxs-lookup"><span data-stu-id="e0336-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e0336-111">Berikan **nama pengguna**, **sandi**, **nama host**, dan **folder Ekspor** untuk akun SFTP Anda.</span><span class="sxs-lookup"><span data-stu-id="e0336-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="e0336-112">Pilih **Verifikasi** untuk menguji koneksi.</span><span class="sxs-lookup"><span data-stu-id="e0336-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="e0336-113">Setelah verifikasi berhasil, pilih jika Anda ingin mengekspor data **Di-zip** atau **Tidak di-zip**, dan pilih **pembatas bidang** untuk file yang diekspor.</span><span class="sxs-lookup"><span data-stu-id="e0336-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="e0336-114">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="e0336-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e0336-115">Pilih **berikutnya** untuk mulai mengkonfigurasi ekspor.</span><span class="sxs-lookup"><span data-stu-id="e0336-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="e0336-116">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="e0336-116">Configure the export</span></span>

1. <span data-ttu-id="e0336-117">Pilih entitas, misalnya segmen, yang akan diekspor.</span><span class="sxs-lookup"><span data-stu-id="e0336-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e0336-118">Setiap entitas yang dipilih adalah maksimal lima file output saat diekspor.</span><span class="sxs-lookup"><span data-stu-id="e0336-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="e0336-119">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="e0336-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e0336-120">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="e0336-120">Export the data</span></span>

<span data-ttu-id="e0336-121">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e0336-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e0336-122">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e0336-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e0336-123">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="e0336-123">Known limitations</span></span>

- <span data-ttu-id="e0336-124">Runtime ekspor tergantung pada kinerja sistem Anda.</span><span class="sxs-lookup"><span data-stu-id="e0336-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="e0336-125">Sebaiknya dua inti CPU dan memori 1 Gb sebagai konfigurasi minimal server Anda.</span><span class="sxs-lookup"><span data-stu-id="e0336-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="e0336-126">Mengekspor entitas dengan hingga 100 juta profil pelanggan dapat berlangsung selama 90 menit bila menggunakan konfigurasi minimal yang disarankan untuk dua inti CPU dan 1 Gb memori.</span><span class="sxs-lookup"><span data-stu-id="e0336-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e0336-127">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="e0336-127">Data privacy and compliance</span></span>

<span data-ttu-id="e0336-128">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan melalui SFTP, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="e0336-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e0336-129">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa tujuan ekspor memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="e0336-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e0336-130">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e0336-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e0336-131">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="e0336-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]