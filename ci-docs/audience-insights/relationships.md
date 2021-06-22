---
title: Hubungan antara entitas dan jalur entitas
description: Buat dan kelola Relasi antara entitas dari beberapa sumber data.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171168"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="60602-103">Relasi di antara dua entitas</span><span class="sxs-lookup"><span data-stu-id="60602-103">Relationships between entities</span></span>

<span data-ttu-id="60602-104">Relasi menghubungkan entitas dan menentukan grafik data Anda saat entitas berbagi pengidentifikasi umum, kunci asing.</span><span class="sxs-lookup"><span data-stu-id="60602-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="60602-105">Kunci asing ini dapat dirujuk dari satu entitas ke entitas lain.</span><span class="sxs-lookup"><span data-stu-id="60602-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="60602-106">Entitas tersambung memungkinkan definisi segmen dan ukuran berdasarkan beberapa sumber data.</span><span class="sxs-lookup"><span data-stu-id="60602-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="60602-107">Ada tiga jenis dasbor di relasi:</span><span class="sxs-lookup"><span data-stu-id="60602-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="60602-108">Sistem Relasi yang tidak dapat dapat diedit, yang dibuat oleh sistem sebagai bagian dari proses penyatuan data</span><span class="sxs-lookup"><span data-stu-id="60602-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="60602-109">Konten Relasi warisan yang tidak dapat diedit, yang dibuat secara otomatis dari menyerap sumber data</span><span class="sxs-lookup"><span data-stu-id="60602-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="60602-110">Relasi kustom yang dapat diedit, yang dibuat dan dikonfigurasi oleh pengguna</span><span class="sxs-lookup"><span data-stu-id="60602-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="60602-111">Relasi sistem yang tidak dapat diedit</span><span class="sxs-lookup"><span data-stu-id="60602-111">Non-editable system relationships</span></span>

<span data-ttu-id="60602-112">Selama penyatuan data, Relasi sistem dibuat secara otomatis berdasarkan pencocokan cerdas.</span><span class="sxs-lookup"><span data-stu-id="60602-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="60602-113">Relasi ini membantu mengaitkan rekaman profil pelanggan dengan rekaman terkait lainnya.</span><span class="sxs-lookup"><span data-stu-id="60602-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="60602-114">Diagram berikut menggambarkan pembuatan Relasi berbasis tiga sistem.</span><span class="sxs-lookup"><span data-stu-id="60602-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="60602-115">Entitas pelanggan dicocokkan dengan entitas lain untuk menghasilkan entitas *Pelanggan* terpadu.</span><span class="sxs-lookup"><span data-stu-id="60602-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram dengan jalur relasi untuk entitas pelanggan dengan tiga Relasi 1-n.":::

- <span data-ttu-id="60602-117">**Relasi *CustomerToContact*** dibuat antara entitas *pelanggan* dan entitas *kontak*.</span><span class="sxs-lookup"><span data-stu-id="60602-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="60602-118">Entitas *pelanggan* mendapatkan bidang penting **Contact_contactId** untuk dikaitkan dengan bidang kunci entitas *kontak* **contactId**.</span><span class="sxs-lookup"><span data-stu-id="60602-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="60602-119">**Relasi *CustomerToAccount*** dibuat antara entitas *pelanggan* dan entitas *Akun*.</span><span class="sxs-lookup"><span data-stu-id="60602-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="60602-120">Entitas *pelanggan* mendapatkan bidang penting **Account_accountID** untuk dikaitkan dengan bidang kunci entitas *Akun* **accountId**.</span><span class="sxs-lookup"><span data-stu-id="60602-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="60602-121">**Relasi *CustomerToWebAccount*** dibuat antara entitas *pelanggan* dan entitas *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="60602-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="60602-122">Entitas *pelanggan* mendapatkan bidang kunci **WebAccount_webaccountID** untuk dikaitkan dengan bidang kunci entitas *WebAccount* **webaccountID**.</span><span class="sxs-lookup"><span data-stu-id="60602-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="60602-123">Relasi warisan yang tidak dapat diedit</span><span class="sxs-lookup"><span data-stu-id="60602-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="60602-124">Selama proses penyerapan data, sistem memeriksa sumber data untuk Relasi yang ada.</span><span class="sxs-lookup"><span data-stu-id="60602-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="60602-125">Jika tidak ada hubungan, sistem secara otomatis membuatnya.</span><span class="sxs-lookup"><span data-stu-id="60602-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="60602-126">Relasi produk ini juga digunakan dalam proses hilir.</span><span class="sxs-lookup"><span data-stu-id="60602-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="60602-127">Membuat relasi kustom</span><span class="sxs-lookup"><span data-stu-id="60602-127">Create a custom relationship</span></span>

<span data-ttu-id="60602-128">Hubungan terdiri dari *entitas sumber* yang berisi kunci asing dan *entitas target* yang diarahkan pada kunci asing entitas sumber.</span><span class="sxs-lookup"><span data-stu-id="60602-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="60602-129">Di wawasan audiens, buka **Data** > **Relasi**.</span><span class="sxs-lookup"><span data-stu-id="60602-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="60602-130">Pilih **relasi baru**.</span><span class="sxs-lookup"><span data-stu-id="60602-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="60602-131">Di panel **Relasi rakyat**, berikan informasi berikut:</span><span class="sxs-lookup"><span data-stu-id="60602-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Panel sisi relasi baru dengan bidang input kosong.":::

   - <span data-ttu-id="60602-133">**Nama relasi**: Nama yang mencerminkan tujuan relasi.</span><span class="sxs-lookup"><span data-stu-id="60602-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="60602-134">Contoh: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="60602-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="60602-135">**Deskripsi** deskripsi relasi.</span><span class="sxs-lookup"><span data-stu-id="60602-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="60602-136">**Entitas sumber**: Entitas yang digunakan sebagai sumber dalam relasi tersebut.</span><span class="sxs-lookup"><span data-stu-id="60602-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="60602-137">Contoh: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="60602-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="60602-138">**Entitas target**: Entitas yang digunakan sebagai target dalam relasi tersebut.</span><span class="sxs-lookup"><span data-stu-id="60602-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="60602-139">Contoh: Pelanggan.</span><span class="sxs-lookup"><span data-stu-id="60602-139">Example: Customer.</span></span>
   - <span data-ttu-id="60602-140">**Kardinalitas sumber**: Menentukan Kardinalitas entitas sumber.</span><span class="sxs-lookup"><span data-stu-id="60602-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="60602-141">Kardinalitas menjelaskan jumlah elemen yang mungkin dalam satu set.</span><span class="sxs-lookup"><span data-stu-id="60602-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="60602-142">Ini selalu berkaitan dengan kardinalitas target.</span><span class="sxs-lookup"><span data-stu-id="60602-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="60602-143">Anda dapat memilih antara **Satu** dan **Banyak**.</span><span class="sxs-lookup"><span data-stu-id="60602-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="60602-144">Hanya Relasi banyak ke satu dan satu-ke-satu yang didukung.</span><span class="sxs-lookup"><span data-stu-id="60602-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="60602-145">Banyak ke satu: Beberapa rekaman sumber dapat berhubungan dengan satu rekaman target.</span><span class="sxs-lookup"><span data-stu-id="60602-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="60602-146">Contoh: Beberapa kasus dukungan dari satu pelanggan.</span><span class="sxs-lookup"><span data-stu-id="60602-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="60602-147">Satu-ke-satu: Rekaman sumber tunggal berkaitan dengan satu rekaman target.</span><span class="sxs-lookup"><span data-stu-id="60602-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="60602-148">Contoh: Satu ID loyalitas untuk satu pelanggan.</span><span class="sxs-lookup"><span data-stu-id="60602-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="60602-149">Relasi banyak ke banyak dapat dibuat menggunakan dua Relasi banyak ke satu dan penautan entitas, yang menghubungkan entitas sumber dan entitas target.</span><span class="sxs-lookup"><span data-stu-id="60602-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="60602-150">**Kardinalitas target**: pilih menunjukkan Kardinalitas rekaman entitas target.</span><span class="sxs-lookup"><span data-stu-id="60602-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="60602-151">**Bidang kunci sumber**: Bidang kunci asing di entitas sumber.</span><span class="sxs-lookup"><span data-stu-id="60602-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="60602-152">Contoh: SupportCase dapat menggunakan CaseID sebagai bidang kunci asing.</span><span class="sxs-lookup"><span data-stu-id="60602-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="60602-153">**Bidang kunci target**: bidang kunci dari entitas target.</span><span class="sxs-lookup"><span data-stu-id="60602-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="60602-154">Contoh Pelanggan dapat menggunakan bidang kunci **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="60602-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="60602-155">Pilih **Simpan** untuk membuat relasi kustom.</span><span class="sxs-lookup"><span data-stu-id="60602-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="60602-156">Lihat relasi</span><span class="sxs-lookup"><span data-stu-id="60602-156">View relationships</span></span>

<span data-ttu-id="60602-157">Halaman Relasi mencantumkan semua Relasi yang telah dibuat.</span><span class="sxs-lookup"><span data-stu-id="60602-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="60602-158">Setiap baris mewakili relasi, yang juga mencakup detail tentang entitas sumber, entitas target, dan kardinalitas.</span><span class="sxs-lookup"><span data-stu-id="60602-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Daftar Relasi dan opsi di bilah tindakan halaman Relasi.":::

<span data-ttu-id="60602-160">Halaman ini menawarkan sekumpulan opsi untuk relasi yang lama dan baru:</span><span class="sxs-lookup"><span data-stu-id="60602-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="60602-161">**Relasi baru**: Pilih [Buat Relasi kustom](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="60602-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="60602-162">**Visualisator**: [Jelajahi visualisator relasi](#explore-the-relationship-visualizer) untuk melihat diagram jaringan dari Relasi yang ada dan kardinalitas mereka.</span><span class="sxs-lookup"><span data-stu-id="60602-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="60602-163">**Filter menurut**: Pilih tipe Relasi untuk ditampilkan dalam daftar.</span><span class="sxs-lookup"><span data-stu-id="60602-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="60602-164">**Cari Relasi**: Gunakan pencarian berbasis teks pada properti Relasi.</span><span class="sxs-lookup"><span data-stu-id="60602-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="60602-165">Jelajahi visualisator relasi</span><span class="sxs-lookup"><span data-stu-id="60602-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="60602-166">Visualisator relasi menampilkan diagram jaringan dari Relasi yang ada antara entitas yang dihubungkan dan kardinalitas mereka.</span><span class="sxs-lookup"><span data-stu-id="60602-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="60602-167">Untuk mengkustomisasi tampilan, Anda bisa mengubah posisi kotak dengan menyeretnya ke kanvas.</span><span class="sxs-lookup"><span data-stu-id="60602-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Tangkapan layar diagram jaringan visualisator relasi dengan sambungan di antara entitas terkait.":::

<span data-ttu-id="60602-169">Pilihan yang Tersedia:</span><span class="sxs-lookup"><span data-stu-id="60602-169">Available options:</span></span> 
- <span data-ttu-id="60602-170">**Ekspor sebagai gambar**: Simpan tampilan saat ini sebagai file gambar.</span><span class="sxs-lookup"><span data-stu-id="60602-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="60602-171">**Mengubah ke tata letak horizontal/vertikal**: Mengubah perataan entitas dan Relasi.</span><span class="sxs-lookup"><span data-stu-id="60602-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="60602-172">**Edit**: Perbarui properti Relasi kustom di panel edit dan simpan perubahan.</span><span class="sxs-lookup"><span data-stu-id="60602-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="60602-173">Kelola relasi yang ada</span><span class="sxs-lookup"><span data-stu-id="60602-173">Manage existing relationships</span></span> 

<span data-ttu-id="60602-174">Di halaman Relasi, setiap relasi ditunjukkan dengan baris.</span><span class="sxs-lookup"><span data-stu-id="60602-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="60602-175">Pilih relasi, lalu tentukan salah satu pilihan berikut:</span><span class="sxs-lookup"><span data-stu-id="60602-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="60602-176">**Edit**: Perbarui properti Relasi kustom di panel edit dan simpan perubahan.</span><span class="sxs-lookup"><span data-stu-id="60602-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="60602-177">**Hapus**: Hapus Relasi kustom.</span><span class="sxs-lookup"><span data-stu-id="60602-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="60602-178">**Lihat**: Melihat relasi warisan dan yang dibuat sistem.</span><span class="sxs-lookup"><span data-stu-id="60602-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="60602-179">Langkah selanjutnya</span><span class="sxs-lookup"><span data-stu-id="60602-179">Next step</span></span>

<span data-ttu-id="60602-180">Relasi sistem dan kustom digunakan untuk [membuat segmen](segments.md) berdasarkan beberapa sumber data yang tidak lagi diisolasi.</span><span class="sxs-lookup"><span data-stu-id="60602-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
