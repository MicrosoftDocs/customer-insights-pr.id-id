---
title: Hubungan antara entitas dan jalur entitas
description: Buat dan kelola Relasi antara entitas dari beberapa sumber data.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406081"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="b7d1e-103">Relasi di antara dua entitas</span><span class="sxs-lookup"><span data-stu-id="b7d1e-103">Relationships between entities</span></span>

<span data-ttu-id="b7d1e-104">Relasi membantu anda menghubungkan entitas dan menghasilkan grafik data saat entitas memiliki pengidentifikasi umum yang sama (kunci asing) yang dapat dirujuk dari satu entitas ke entitas lain.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="b7d1e-105">Entitas tersambung memungkinkan Anda menentukan segmen dan ukuran berdasarkan beberapa sumber data.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="b7d1e-106">Ada dua jenis dasbor di relasi.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-106">There are two types of relationships.</span></span> <span data-ttu-id="b7d1e-107">Relasi sistem yang tidak dapat diedit, yang dibuat secara otomatis, dan Relasi kustom yang dibuat dan dikonfigurasi oleh pengguna.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="b7d1e-108">Selama proses pencocokan dan penggabungan, Relasi sistem dibuat di belakang layar berdasarkan pencocokan cerdas.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="b7d1e-109">Relasi ini membantu mengaitkan rekaman profil pelanggan dengan rekaman entitas terkait lainnya.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="b7d1e-110">Diagram berikut mengilustrasikan pembuatan tiga Relasi sistem saat entitas pelanggan dicocokkan dengan entitas tambahan untuk menghasilkan entitas profil pelanggan akhir.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b7d1e-111">![Pembuatan Relasi](media/relationships-entities-merge.png "Pembuatan Relasi")</span><span class="sxs-lookup"><span data-stu-id="b7d1e-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="b7d1e-112">**Relasi *CustomerToContact*** dibuat antara entitas pelanggan dan entitas kontak.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="b7d1e-113">Entitas pelanggan mendapatkan bidang penting **Contact_contactId** untuk dikaitkan dengan bidang kunci entitas kontak **contactId**.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="b7d1e-114">**Relasi _CustomerToAccount_** dibuat antara entitas pelanggan dan entitas Akun.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-114">**_CustomerToAccount_ relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="b7d1e-115">Entitas pelanggan mendapatkan bidang penting **Account_accountId** untuk dikaitkan dengan bidang kunci entitas Akun **accountId**.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="b7d1e-116">**Relasi _CustomerToWebAccount_** dibuat antara entitas pelanggan dan entitas WebAccount.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-116">**_CustomerToWebAccount_ relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="b7d1e-117">Entitas pelanggan mendapatkan bidang penting **WebAccount_webaccountId** untuk dikaitkan dengan bidang kunci entitas WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="b7d1e-118">Buat Relasi</span><span class="sxs-lookup"><span data-stu-id="b7d1e-118">Create a relationship</span></span>

<span data-ttu-id="b7d1e-119">Tentukan Relasi kustom pada halaman **Relasi**.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="b7d1e-120">Setiap relasi terdiri dari entitas sumber (entitas yang memegang kunci asing) dan entitas target (entitas yang ditunjuk oleh kunci asing entitas sumber).</span><span class="sxs-lookup"><span data-stu-id="b7d1e-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="b7d1e-121">Di wawasan audiens, buka **Data** > **Relasi**.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="b7d1e-122">Pilih **relasi baru**.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="b7d1e-123">Di panel **Tambahkan Relasi**, berikan informasi berikut:</span><span class="sxs-lookup"><span data-stu-id="b7d1e-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b7d1e-124">![masukkan rincian relasi](media/relationships-add.png "masukkan rincian relasi")</span><span class="sxs-lookup"><span data-stu-id="b7d1e-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="b7d1e-125">**Nama relasi**: Nama yang mencerminkan tujuan relasi (misalnya, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="b7d1e-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="b7d1e-126">**Deskripsi** deskripsi relasi.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="b7d1e-127">**Entitas sumber**: pilih entitas yang digunakan sebagai sumber di relasi (misalnya, WebLog).</span><span class="sxs-lookup"><span data-stu-id="b7d1e-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="b7d1e-128">**Kardinalitas**: pilih Kardinalitas rekaman entitas sumber.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="b7d1e-129">Misalnya, "banyak" berarti bahwa beberapa rekaman weblog terkait dengan satu WebAccount.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="b7d1e-130">**Bidang kunci sumber**: ini menunjukkan bidang foreign key di entitas sumber.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="b7d1e-131">Misalnya, WebLog memiliki bidang foreign key **accountId**.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="b7d1e-132">**Entitas target**: pilih entitas yang digunakan sebagai target di relasi (misalnya, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="b7d1e-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="b7d1e-133">**Kardinalitas target**: pilih menunjukkan Kardinalitas rekaman entitas target.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="b7d1e-134">Misalnya, "satu" berarti bahwa beberapa rekaman weblog terkait dengan satu WebAccount.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="b7d1e-135">**Bidang kunci target**: bidang ini mewakili bidang kunci dari entitas target.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="b7d1e-136">Misalnya, WebAccount memiliki bidang kunci **accountId**.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="b7d1e-137">Hanya Relasi banyak ke satu dan satu-ke-satu yang didukung.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="b7d1e-138">Relasi banyak ke banyak dapat dibuat menggunakan dua Relasi banyak ke satu dan entitas tautan — (entitas yang digunakan untuk menghubungkan entitas sumber dan entitas target).</span><span class="sxs-lookup"><span data-stu-id="b7d1e-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="b7d1e-139">Hapus relasi</span><span class="sxs-lookup"><span data-stu-id="b7d1e-139">Delete a relationship</span></span>

1. <span data-ttu-id="b7d1e-140">Di wawasan audiens, buka **Data** > **Relasi**.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="b7d1e-141">Pilih kotak centang untuk relasi yang akan dihapus.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="b7d1e-142">Pilih **hapus** di bagian atas tabel **Relasi**.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="b7d1e-143">Konfirmasikan penghapusan.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="b7d1e-144">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="b7d1e-144">Next step</span></span>

<span data-ttu-id="b7d1e-145">Relasi sistem dan kustom digunakan untuk membuat segmen berdasarkan beberapa sumber data yang tidak lagi diisolasi.</span><span class="sxs-lookup"><span data-stu-id="b7d1e-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="b7d1e-146">Untuk informasi lebih lanjut, lihat [Segmen](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b7d1e-146">For more information, see [Segments](segments.md).</span></span>
