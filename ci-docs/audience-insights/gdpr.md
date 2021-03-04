---
title: Permintaan hak subjek data (DSR) di bawah GDPR | Microsoft Docs
description: Merespons permintaan subjek Data untuk kemampuan wawasan audiens Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268690"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="1cadd-103">Permintaan hak subjek data (DSR) di bawah GDPR</span><span class="sxs-lookup"><span data-stu-id="1cadd-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="1cadd-104">Merespons permintaan penghapusan subjek GDPR untuk kemampuan wawasan audiens Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="1cadd-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="1cadd-105">"Hak untuk menghapus" data pribadi dari data pelanggan organisasi adalah perlindungan kunci dalam peraturan perlindungan data umum (GDPR).</span><span class="sxs-lookup"><span data-stu-id="1cadd-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="1cadd-106">Menghapus data pribadi mencakup penghapusan semua data pribadi dan log yang dihasilkan sistem, kecuali informasi log audit.</span><span class="sxs-lookup"><span data-stu-id="1cadd-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="1cadd-107">Mengelola permintaan penghapusan subjek data</span><span class="sxs-lookup"><span data-stu-id="1cadd-107">Manage data subject delete requests</span></span>

<span data-ttu-id="1cadd-108">Wawasan audiens menawarkan pengalaman dalam produk berikut untuk menghapus data pribadi untuk pelanggan tertentu atau pengguna:</span><span class="sxs-lookup"><span data-stu-id="1cadd-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="1cadd-109">**Mengelola permintaan untuk data pelanggan**: data pelanggan dalam Customer Insights terserap dari sumber data asli eksternal untuk Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1cadd-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="1cadd-110">Semua permintaan penghapusan GDPR harus dilakukan di sumber data asli.</span><span class="sxs-lookup"><span data-stu-id="1cadd-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="1cadd-111">**Mengelola permintaan penghapusan untuk data pengguna Customer Insights**: data untuk pengguna dibuat oleh Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1cadd-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="1cadd-112">Semua permintaan penghapusan GDPR harus dilakukan di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1cadd-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="1cadd-113">Mengelola permintaan untuk data pelanggan</span><span class="sxs-lookup"><span data-stu-id="1cadd-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="1cadd-114">Admin Customer Insights dapat mengikuti langkah berikut untuk menghapus data pelanggan yang telah dihapus di sumber data:</span><span class="sxs-lookup"><span data-stu-id="1cadd-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="1cadd-115">Masuk ke Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1cadd-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="1cadd-116">Di wawasan audiens, buka **Data** > **Sumber data**</span><span class="sxs-lookup"><span data-stu-id="1cadd-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="1cadd-117">Untuk setiap sumber data dalam daftar berisi data pelanggan yang telah dihapus:</span><span class="sxs-lookup"><span data-stu-id="1cadd-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="1cadd-118">Pilih (...) dan kemudian pilih **Segarkan**.</span><span class="sxs-lookup"><span data-stu-id="1cadd-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="1cadd-119">Periksa status sumber data dalam **status**.</span><span class="sxs-lookup"><span data-stu-id="1cadd-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="1cadd-120">Tanda centang berarti penyegaran berhasil.</span><span class="sxs-lookup"><span data-stu-id="1cadd-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="1cadd-121">Segitiga peringatan berarti terjadi kesalahan.</span><span class="sxs-lookup"><span data-stu-id="1cadd-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="1cadd-122">Jika segitiga peringatan ditampilkan, hubungi D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1cadd-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1cadd-123">![Menangani permintaan penghapusan GDPR untuk data pelanggan](media/gdpr-data-sources.png "Menangani permintaan penghapusan GDPR untuk data pelanggan")</span><span class="sxs-lookup"><span data-stu-id="1cadd-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="1cadd-124">Mengelola permintaan penghapusan untuk data pengguna</span><span class="sxs-lookup"><span data-stu-id="1cadd-124">Manage delete requests for user data</span></span>

<span data-ttu-id="1cadd-125">Admin Customer Insights dapat mengikuti langkah berikut untuk menghapus data pengguna Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="1cadd-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="1cadd-126">Masuk ke Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1cadd-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="1cadd-127">Di wawasan audiens, buka **Admin** > **Izin**.</span><span class="sxs-lookup"><span data-stu-id="1cadd-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="1cadd-128">Centang kotak untuk pengguna yang akan dihapus.</span><span class="sxs-lookup"><span data-stu-id="1cadd-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="1cadd-129">Pilih **Hapus**.</span><span class="sxs-lookup"><span data-stu-id="1cadd-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1cadd-130">![Menangani permintaan penghapusan untuk data pengguna](media/gdpr-permissions.png "Menangani permintaan penghapusan untuk data pengguna")</span><span class="sxs-lookup"><span data-stu-id="1cadd-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="1cadd-131">Merespons permintaan ekspor subjek data GDPR</span><span class="sxs-lookup"><span data-stu-id="1cadd-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="1cadd-132">Sebagai bagian dari komitmen kami untuk bermitra dengan Anda dalam perjalanan Anda ke peraturan perlindungan data umum (GDPR), kami telah mengembangkan dokumentasi untuk membantu Anda bersiap.</span><span class="sxs-lookup"><span data-stu-id="1cadd-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="1cadd-133">Dokumentasi ini menjelaskan langkah yang dapat anda lakukan hari ini untuk mendukung kepatuhan GDPR saat menggunakan wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="1cadd-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="1cadd-134">Mengelola ekspor dan lihat permintaan</span><span class="sxs-lookup"><span data-stu-id="1cadd-134">Manage export and view requests</span></span>

<span data-ttu-id="1cadd-135">Hak portabilitas data memungkinkan subjek data untuk meminta salinan data pribadi mereka dalam format elektronik (yaitu format "terstruktur, umum digunakan, dapat dibaca mesin, dan dapat dioperasikan") yang dapat ditransmisikan ke pengontrol data lainnya.</span><span class="sxs-lookup"><span data-stu-id="1cadd-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="1cadd-136">Ekspor data pelanggan (admin penyewa)</span><span class="sxs-lookup"><span data-stu-id="1cadd-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="1cadd-137">Administrator penyewa dapat mengikuti langkah berikut untuk mengekspor data:</span><span class="sxs-lookup"><span data-stu-id="1cadd-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="1cadd-138">Kirim email ke D365CI@microsoft.com yang menentukan alamat email pelanggan yang diminta.</span><span class="sxs-lookup"><span data-stu-id="1cadd-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="1cadd-139">Tim Customer Insights akan mengirim email ke alamat email admin penyewa yang terdaftar, meminta konfirmasi untuk mengekspor data.</span><span class="sxs-lookup"><span data-stu-id="1cadd-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="1cadd-140">Berikan konfirmasi untuk mengekspor data untuk pelanggan yang diminta.</span><span class="sxs-lookup"><span data-stu-id="1cadd-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="1cadd-141">Terima data yang diekspor melalui alamat email admin penyewa.</span><span class="sxs-lookup"><span data-stu-id="1cadd-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="1cadd-142">Ekspor data pengguna (admin penyewa)</span><span class="sxs-lookup"><span data-stu-id="1cadd-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="1cadd-143">Kirim email ke D365CI@microsoft.com yang menentukan alamat email pengguna yang diminta.</span><span class="sxs-lookup"><span data-stu-id="1cadd-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="1cadd-144">Tim Customer Insights akan mengirim email ke alamat email admin penyewa yang terdaftar, meminta konfirmasi untuk mengekspor data.</span><span class="sxs-lookup"><span data-stu-id="1cadd-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="1cadd-145">Berikan konfirmasi untuk mengekspor data untuk pengguna yang diminta.</span><span class="sxs-lookup"><span data-stu-id="1cadd-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="1cadd-146">Terima data yang diekspor melalui alamat email admin penyewa.</span><span class="sxs-lookup"><span data-stu-id="1cadd-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]