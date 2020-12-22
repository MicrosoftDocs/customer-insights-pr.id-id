---
title: Ekspor data Customer Insights ke host SFTP
description: Pelajari cara mengkonfigurasi sambungan ke host SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643507"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="d75b7-103">Konektor untuk SFTP (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="d75b7-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="d75b7-104">Gunakan data pelanggan di aplikasi pihak ketiga dengan mengekspornya ke host Secure File Transfer Protocol(SFTP).</span><span class="sxs-lookup"><span data-stu-id="d75b7-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d75b7-105">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="d75b7-105">Prerequisites</span></span>

- <span data-ttu-id="d75b7-106">Ketersediaan host SFTP dan kredensial terkait.</span><span class="sxs-lookup"><span data-stu-id="d75b7-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="d75b7-107">Sambungkan ke SFTP</span><span class="sxs-lookup"><span data-stu-id="d75b7-107">Connect to SFTP</span></span>

1. <span data-ttu-id="d75b7-108">Buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="d75b7-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d75b7-109">Di dalam **SFTP**, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="d75b7-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="d75b7-110">Beri nama yang dikenali di bidang **nama tampilan** tujuan anda.</span><span class="sxs-lookup"><span data-stu-id="d75b7-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d75b7-111">Berikan **nama pengguna**, **sandi**, dan **nama host** untuk akun SFTP Anda.</span><span class="sxs-lookup"><span data-stu-id="d75b7-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="d75b7-112">Contoh: Jika folder root server SFTP Anda adalah/root/folder, dan Anda ingin data diekspor ke /root/folder/ci_export_destination_folder, host harus sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="d75b7-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="d75b7-113">Pilih **Verifikasi** untuk menguji koneksi.</span><span class="sxs-lookup"><span data-stu-id="d75b7-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="d75b7-114">Setelah berhasil melakukan verifikasi, pilih jika Anda ingin mengekspor data Anda **di-zip** atau **tidak di-zip**, dan pilih **pembatas bidang** untuk file yang diekspor.</span><span class="sxs-lookup"><span data-stu-id="d75b7-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="d75b7-115">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="d75b7-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d75b7-116">Pilih **berikutnya** untuk mulai mengkonfigurasi ekspor.</span><span class="sxs-lookup"><span data-stu-id="d75b7-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="d75b7-117">Mengonfigurasi koneksi</span><span class="sxs-lookup"><span data-stu-id="d75b7-117">Configure the connection</span></span>

1. <span data-ttu-id="d75b7-118">Pilih **atribut pelanggan** untuk diekspor.</span><span class="sxs-lookup"><span data-stu-id="d75b7-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="d75b7-119">Anda dapat mengekspor satu atau beberapa atribut.</span><span class="sxs-lookup"><span data-stu-id="d75b7-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="d75b7-120">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="d75b7-120">Select **Next**.</span></span>

1. <span data-ttu-id="d75b7-121">Pilih segmen yang ingin diekspor.</span><span class="sxs-lookup"><span data-stu-id="d75b7-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="d75b7-122">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="d75b7-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d75b7-123">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="d75b7-123">Export the data</span></span>

<span data-ttu-id="d75b7-124">Anda dapat [mengekspor data sesuai permintaan](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d75b7-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d75b7-125">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d75b7-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d75b7-126">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="d75b7-126">Data privacy and compliance</span></span>

<span data-ttu-id="d75b7-127">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan melalui SFTP, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="d75b7-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d75b7-128">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa tujuan ekspor memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="d75b7-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d75b7-129">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d75b7-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d75b7-130">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="d75b7-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
