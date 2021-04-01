---
title: Konektor LiveRamp
description: Pelajari cara mengekspor data ke LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597561"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="e4cf4-103">Konektor LiveRamp&reg; (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="e4cf4-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="e4cf4-104">Aktifkan data Anda di LiveRamp untuk terhubung dengan lebih dari 500 platform lintas ekosistem digital, sosial, dan TV.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="e4cf4-105">Bekerja dengan data Anda di LiveRamp untuk menargetkan, menekan, dan mempersonalisasi kampanye iklan.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e4cf4-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="e4cf4-106">Prerequisites</span></span>

- <span data-ttu-id="e4cf4-107">Anda memerlukan langganan LiveRamp untuk menggunakan konektor ini.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="e4cf4-108">Untuk mendapatkan langganan, [hubungi langsung LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="e4cf4-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="e4cf4-109">[Pelajari lebih lanjut tentang LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="e4cf4-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="e4cf4-110">Hubungkan ke LiveRamp</span><span class="sxs-lookup"><span data-stu-id="e4cf4-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="e4cf4-111">Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e4cf4-112">Di petak **LiveRamp** pilih **Konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="e4cf4-113">Beri nama yang dikenali di bidang **nama tampilan** tujuan anda.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e4cf4-114">Berikan **nama pengguna** dan **sandi** untuk akun LiveRamp Secure FTP (SFTP) Anda.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="e4cf4-115">Kredensial ini mungkin berbeda dengan kredensial LiveRamp Onboarding Anda.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="e4cf4-116">Pilih **Verifikasikan** untuk menguji sambungan ke LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="e4cf4-117">Setelah verifikasi berhasil, berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="e4cf4-118">Pilih **berikutnya** untuk mengkonfigurasi konektor liveramp.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e4cf4-119">Konfigurasikan konektor</span><span class="sxs-lookup"><span data-stu-id="e4cf4-119">Configure the connector</span></span>

1. <span data-ttu-id="e4cf4-120">Di bidang **Pilih pengidentifikasi kunci Anda**, pilih **email**,  **nama dan alamat**, atau **telepon** untuk dikirim ke LiveRamp untuk resolusi identitas.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="e4cf4-121">Petakan atribut yang terkait dari entitas pelanggan terpadu Anda untuk pengidentifikasi kunci yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="e4cf4-122">Pilih **Tambah atribut** untuk memetakan atribut tambahan untuk dikirim ke LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="e4cf4-123">Mengirimkan lebih banyak atribut pengidentifikasi kunci ke LiveRamp kemungkinan akan memberi Anda tingkat kecocokan yang lebih tinggi.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="e4cf4-124">Pilih segmen yang ingin Anda ekspor ke LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="e4cf4-125">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e4cf4-126">![Konektor LiveRamp dengan pemetaan atribut](media/export-liveramp-segments.png "Konektor LiveRamp dengan pemetaan atribut")</span><span class="sxs-lookup"><span data-stu-id="e4cf4-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e4cf4-127">Mengekspor data</span><span class="sxs-lookup"><span data-stu-id="e4cf4-127">Export the data</span></span>

<span data-ttu-id="e4cf4-128">Ekspor akan segera dimulai jika semua prasyarat untuk ekspor telah diselesaikan.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="e4cf4-129">Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e4cf4-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="e4cf4-130">Setelah ekspor berhasil diselesaikan, Anda dapat masuk ke LiveRamp Onboarding untuk mengaktifkan dan mendistribusikan data.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e4cf4-131">Privasi dan kepatuhan data</span><span class="sxs-lookup"><span data-stu-id="e4cf4-131">Data privacy and compliance</span></span>

<span data-ttu-id="e4cf4-132">Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Liveramp, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e4cf4-133">Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Liveramp memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e4cf4-134">Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e4cf4-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e4cf4-135">Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.</span><span class="sxs-lookup"><span data-stu-id="e4cf4-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]