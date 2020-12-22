---
title: Sambungkan ke entitas di Danau terkelola Common Data Service
description: Impor data dari Data Lake terkelola Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643402"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="0cf65-103">Menyambung ke data di Data Lake yang dikelola oleh Common Data Service</span><span class="sxs-lookup"><span data-stu-id="0cf65-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0cf65-104">Artikel ini memberikan informasi tentang bagaimana pelanggan Dynamics 365 yang ada dapat dengan cepat terhubung ke entitas analitik mereka di Danau terkelola Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0cf65-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="0cf65-105">Anda harus menjadi admin pada organisasi Common Data Service untuk melanjutkan dan melihat daftar entitas yang tersedia di Danau terkelola.</span><span class="sxs-lookup"><span data-stu-id="0cf65-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="0cf65-106">Pertimbangan penting</span><span class="sxs-lookup"><span data-stu-id="0cf65-106">Important considerations</span></span>

<span data-ttu-id="0cf65-107">Data yang tersimpan di layanan online, misalnya Azure Data Lake Storage, dapat disimpan di lokasi yang berbeda dengan data yang diproses atau disimpan di Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0cf65-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="0cf65-108">Dengan mengimpor atau menyambung ke data yang tersimpan di layanan online, Anda setuju bahwa data dapat ditransfer ke dan disimpan dengan Dynamics 365 Customer Insights. [Pelajari lebih lanjut di pusat kepercayaan Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="0cf65-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="0cf65-109">Terhubung ke danau yang dikelola Common Data Service</span><span class="sxs-lookup"><span data-stu-id="0cf65-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="0cf65-110">Di wawasan audiens, buka **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="0cf65-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="0cf65-111">Pilih **Tambahkan sumber data**.</span><span class="sxs-lookup"><span data-stu-id="0cf65-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="0cf65-112">Pilih **Sambungkan ke Common Data Service** dan pilih **berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="0cf65-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="0cf65-113">Masukkan **nama** untuk sumber data, lalu pilih **Berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="0cf65-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="0cf65-114">Berikan **Alamat server** untuk organisasi Anda Common Data Service, lalu pilih **masuk**.</span><span class="sxs-lookup"><span data-stu-id="0cf65-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0cf65-115">![Kotak dialog untuk memasukkan Alamat server Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="0cf65-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="0cf65-116">Pilih entitas yang ingin Anda serap dari daftar yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="0cf65-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="0cf65-117">Jika beberapa entitas telah dipilih, mereka dapat digunakan oleh aplikasi dynamics 365 lainnya (seperti Dynamics 365 Sales Insights atau Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="0cf65-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="0cf65-118">Anda tidak dapat mengubah pilihan.</span><span class="sxs-lookup"><span data-stu-id="0cf65-118">You can't change the selection.</span></span> <span data-ttu-id="0cf65-119">Entitas ini akan tersedia setelah sumber data dibuat.</span><span class="sxs-lookup"><span data-stu-id="0cf65-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0cf65-120">![Kotak dialog menampilkan daftar entitas di organisasi Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="0cf65-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="0cf65-121">Simpan pilihan Anda untuk mulai mensinkronisasi entitas yang dipilih ke Danau terkelola Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0cf65-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="0cf65-122">Anda akan menemukan sambungan yang baru ditambahkan pada halaman **sumber data**.</span><span class="sxs-lookup"><span data-stu-id="0cf65-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="0cf65-123">Ini akan diantre untuk refresh dan menampilkan jumlah entitas sebagai 0 hingga semua entitas disinkronisasikan.</span><span class="sxs-lookup"><span data-stu-id="0cf65-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="0cf65-124">Hanya satu sumber data dari lingkungan yang dapat secara simultan menggunakan danau terkelola Common Data Service yang sama.</span><span class="sxs-lookup"><span data-stu-id="0cf65-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="0cf65-125">Edit sumber data danau terkelola Common Data Service</span><span class="sxs-lookup"><span data-stu-id="0cf65-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="0cf65-126">Anda hanya mengedit pilihan entitas setelah membuat sumber data.</span><span class="sxs-lookup"><span data-stu-id="0cf65-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="0cf65-127">Misalnya, jika entitas tambahan ditambahkan ke Common Data Service dan Anda ingin mengimpornya juga.</span><span class="sxs-lookup"><span data-stu-id="0cf65-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="0cf65-128">Untuk menghubungkan ke Common Data Service berbeda, [buat sumber data baru](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="0cf65-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="0cf65-129">Di wawasan audiens, buka **Data** > **Sumber data**.</span><span class="sxs-lookup"><span data-stu-id="0cf65-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="0cf65-130">Di samping sumber data yang ingin anda perbarui, pilih elipsis.</span><span class="sxs-lookup"><span data-stu-id="0cf65-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="0cf65-131">Pilih opsi **Edit** dari daftar.</span><span class="sxs-lookup"><span data-stu-id="0cf65-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="0cf65-132">Pilih entitas tambahan dari daftar entitas yang tersedia dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="0cf65-132">Select additional entities from the available list of entities and select **Save**.</span></span>
