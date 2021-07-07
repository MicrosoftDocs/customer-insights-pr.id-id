---
title: Mengekspor data Customer Insights ke Salesforce Marketing Cloud
description: Pelajari lebih lanjut cara mengkonfigurasi sambungan dan mengekspor ke Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314627"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="11b77-103">Mengekspor segmen dan data lainnya ke Salesforce Marketing Cloud (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="11b77-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="11b77-104">Gunakan data pelanggan Anda di Salesforce Marketing Cloud dengan mengekspornya melalui lokasi SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="11b77-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="11b77-105">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="11b77-105">Prerequisites for connection</span></span>

- <span data-ttu-id="11b77-106">Ketersediaan host SFTP dan kredensial admin yang terkait.</span><span class="sxs-lookup"><span data-stu-id="11b77-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="11b77-107">Cara mengkonfigurasi lokasi SFTP untuk Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="11b77-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="11b77-108">Pembatasan yang diketahui</span><span class="sxs-lookup"><span data-stu-id="11b77-108">Known limitations</span></span>

- <span data-ttu-id="11b77-109">Runtime ekspor tergantung pada kinerja sistem Anda.</span><span class="sxs-lookup"><span data-stu-id="11b77-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="11b77-110">Sebaiknya dua inti CPU dan memori 1 Gb sebagai konfigurasi minimal server Anda.</span><span class="sxs-lookup"><span data-stu-id="11b77-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="11b77-111">Mengekspor entitas dengan hingga 100 juta profil pelanggan dapat berlangsung selama 90 menit bila menggunakan konfigurasi minimal yang disarankan.</span><span class="sxs-lookup"><span data-stu-id="11b77-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="11b77-112">Mengkonfigurasikan sambungan ke Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="11b77-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="11b77-113">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="11b77-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="11b77-114">Pilih **Tambah koneksi** dan pilih **Salesforce Marketing Cloud** untuk mengkonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="11b77-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="11b77-115">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="11b77-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="11b77-116">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="11b77-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="11b77-117">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="11b77-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="11b77-118">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="11b77-118">Choose who can use this connection.</span></span> <span data-ttu-id="11b77-119">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="11b77-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="11b77-120">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="11b77-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="11b77-121">Berikan **nama pengguna**, **sandi**, **nama host**, dan **folder Ekspor** untuk akun SFTP Anda.</span><span class="sxs-lookup"><span data-stu-id="11b77-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="11b77-122">Pilih **Verifikasi** untuk menguji koneksi.</span><span class="sxs-lookup"><span data-stu-id="11b77-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="11b77-123">Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.</span><span class="sxs-lookup"><span data-stu-id="11b77-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="11b77-124">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="11b77-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="11b77-125">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="11b77-125">Configure an export</span></span>

<span data-ttu-id="11b77-126">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="11b77-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="11b77-127">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="11b77-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="11b77-128">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="11b77-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="11b77-129">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="11b77-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="11b77-130">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian SFTP.</span><span class="sxs-lookup"><span data-stu-id="11b77-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="11b77-131">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="11b77-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="11b77-132">Pilih jika Anda ingin mengekspor data **dengan di-zip** atau **tidak di-zip** dan **pembatas bidang** untuk file yang diekspor.</span><span class="sxs-lookup"><span data-stu-id="11b77-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="11b77-133">Pilih entitas, misalnya segmen, yang akan diekspor.</span><span class="sxs-lookup"><span data-stu-id="11b77-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="11b77-134">Setiap entitas yang dipilih akan dibagi menjadi hingga lima file output saat diekspor.</span><span class="sxs-lookup"><span data-stu-id="11b77-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="11b77-135">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="11b77-135">Select **Save**.</span></span>

<span data-ttu-id="11b77-136">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="11b77-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="11b77-137">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="11b77-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="11b77-138">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="11b77-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="11b77-139">Mengimpor data Customer Insights dari lokasi SFTP ke Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="11b77-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="11b77-140">Buat [ekstensi data di Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) untuk mengimpor file data Customer Insights dari lokasi SFTP.</span><span class="sxs-lookup"><span data-stu-id="11b77-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="11b77-141">[Impor data dari lokasi SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) ke ekstensi data Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="11b77-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="11b77-142">Mengkonfigurasikan otomatisasi untuk mengimpor data ke ekstensi data.</span><span class="sxs-lookup"><span data-stu-id="11b77-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="11b77-143">Pelajari lebih lanjut tentang [otomatisasi peletakan file dan otomatisasi terjadwal](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="11b77-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="11b77-144">Menentukan [otomatisasi peletakan file](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) atau  [otomatisasi terjadwal](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="11b77-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="11b77-145">Berikut adalah contoh [otomatisasi dengan SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="11b77-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="11b77-146">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="11b77-146">Data privacy and compliance</span></span>

<span data-ttu-id="11b77-147">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan melalui SFTP, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="11b77-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="11b77-148">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa tujuan ekspor memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="11b77-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="11b77-149">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="11b77-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="11b77-150">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="11b77-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
