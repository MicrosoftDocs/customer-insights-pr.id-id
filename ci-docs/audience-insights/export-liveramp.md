---
title: Konektor LiveRamp
description: Pelajari cara mengonfigurasi koneksi dan ekspor ke LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760331"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="06d86-103">Mengekspor segmen ke LiveRamp&reg; (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="06d86-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="06d86-104">Aktifkan data Anda di LiveRamp untuk terhubung dengan lebih dari 500 platform di seluruh digital, sosial, dan TV.</span><span class="sxs-lookup"><span data-stu-id="06d86-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="06d86-105">Bekerja dengan data Anda di LiveRamp untuk menargetkan, menekan, dan mempersonalisasi kampanye iklan.</span><span class="sxs-lookup"><span data-stu-id="06d86-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="06d86-106">Prasyarat untuk koneksi</span><span class="sxs-lookup"><span data-stu-id="06d86-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="06d86-107">Anda memerlukan langganan LiveRamp untuk menggunakan konektor ini.</span><span class="sxs-lookup"><span data-stu-id="06d86-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="06d86-108">Untuk mendapatkan langganan, [hubungi langsung LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="06d86-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="06d86-109">[Pelajari lebih lanjut tentang LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="06d86-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="06d86-110">Konfigurasikan koneksi ke LiveRamp</span><span class="sxs-lookup"><span data-stu-id="06d86-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="06d86-111">Buka **Admin** > **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="06d86-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="06d86-112">Pilih **Tambahkan koneksi** dan pilih **LiveRamp** untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="06d86-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="06d86-113">Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="06d86-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="06d86-114">Nama dan tipe koneksi menjelaskan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="06d86-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="06d86-115">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.</span><span class="sxs-lookup"><span data-stu-id="06d86-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="06d86-116">Pilih siapa saja yang dapat menggunakan sambungan ini.</span><span class="sxs-lookup"><span data-stu-id="06d86-116">Choose who can use this connection.</span></span> <span data-ttu-id="06d86-117">Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator.</span><span class="sxs-lookup"><span data-stu-id="06d86-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="06d86-118">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="06d86-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="06d86-119">Berikan **nama pengguna** dan **sandi** untuk akun LiveRamp Secure FTP (SFTP) Anda.</span><span class="sxs-lookup"><span data-stu-id="06d86-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="06d86-120">Kredensial ini mungkin berbeda dengan kredensial LiveRamp Onboarding Anda.</span><span class="sxs-lookup"><span data-stu-id="06d86-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="06d86-121">Pilih **Verifikasikan** untuk menguji sambungan ke LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="06d86-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="06d86-122">Setelah verifikasi berhasil, berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="06d86-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="06d86-123">Pilih **Simpan** untuk menyelesaikan koneksi.</span><span class="sxs-lookup"><span data-stu-id="06d86-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="06d86-124">Mengonfigurasi ekspor</span><span class="sxs-lookup"><span data-stu-id="06d86-124">Configure an export</span></span>

<span data-ttu-id="06d86-125">Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini.</span><span class="sxs-lookup"><span data-stu-id="06d86-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="06d86-126">Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="06d86-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="06d86-127">Buka **Data** > **Ekspor**.</span><span class="sxs-lookup"><span data-stu-id="06d86-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="06d86-128">Pilih **Tambahkan ekspor** untuk membuat ekspor baru.</span><span class="sxs-lookup"><span data-stu-id="06d86-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="06d86-129">Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="06d86-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="06d86-130">Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.</span><span class="sxs-lookup"><span data-stu-id="06d86-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="06d86-131">Di bidang **Pilih pengidentifikasi kunci Anda**, pilih **email**,  **nama dan alamat**, atau **telepon** untuk dikirim ke LiveRamp untuk resolusi identitas.</span><span class="sxs-lookup"><span data-stu-id="06d86-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="06d86-132">![Konektor LiveRamp dengan pemetaan atribut](media/export-liveramp-segments.png "Konektor LiveRamp dengan pemetaan atribut")</span><span class="sxs-lookup"><span data-stu-id="06d86-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="06d86-133">Petakan atribut yang terkait dari entitas pelanggan terpadu Anda untuk pengidentifikasi kunci yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="06d86-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="06d86-134">Pilih **Tambahkan atribut** untuk memetakan lebih banyak atribut untuk dikirim ke LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="06d86-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="06d86-135">Mengirimkan lebih banyak atribut pengidentifikasi kunci ke LiveRamp kemungkinan akan memberi Anda tingkat kecocokan yang lebih tinggi.</span><span class="sxs-lookup"><span data-stu-id="06d86-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="06d86-136">Pilih segmen yang ingin Anda ekspor ke LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="06d86-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="06d86-137">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="06d86-137">Select **Save**.</span></span>

<span data-ttu-id="06d86-138">Menyimpan ekspor tidak segera menjalankan ekspor.</span><span class="sxs-lookup"><span data-stu-id="06d86-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="06d86-139">Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="06d86-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="06d86-140">Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="06d86-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="06d86-141">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="06d86-141">Data privacy and compliance</span></span>

<span data-ttu-id="06d86-142">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Liveramp, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="06d86-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="06d86-143">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Liveramp memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="06d86-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="06d86-144">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="06d86-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="06d86-145">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="06d86-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
