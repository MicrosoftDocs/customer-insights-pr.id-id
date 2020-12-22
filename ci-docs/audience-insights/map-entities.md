---
title: Entitas peta untuk penyatuan data
description: Memetakan data untuk membuat profil pelanggan terpadu.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406072"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="9e35c-103">Memetakan entitas dan atribut</span><span class="sxs-lookup"><span data-stu-id="9e35c-103">Map entities and attributes</span></span>

<span data-ttu-id="9e35c-104">**Peta** adalah tahap pertama dalam proses penyatuan data wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="9e35c-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="9e35c-105">Pemetaan terdiri dari tiga tahapan:</span><span class="sxs-lookup"><span data-stu-id="9e35c-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="9e35c-106">*Pilihan entitas*: mengidentifikasi entitas yang dapat dikombinasikan untuk mengarah ke himpunan data dengan informasi lebih lengkap tentang pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="9e35c-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="9e35c-107">*Pilihan atribut*: untuk setiap entitas, Identifikasikan kolom yang akan digabungkan dan direkonsiliasi dalam fase *pencocokan* dan *penggabungan*.</span><span class="sxs-lookup"><span data-stu-id="9e35c-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="9e35c-108">Kolom ini disebut *atribut*.</span><span class="sxs-lookup"><span data-stu-id="9e35c-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="9e35c-109">*Pilihan kunci primer dan jenis semantik*: untuk setiap entitas, Identifikasikan atribut yang ingin Anda definisikan sebagai kunci primer untuk entitas tersebut, dan untuk setiap atribut, Identifikasikan jenis semantik yang paling tepat menggambarkan atribut tersebut.</span><span class="sxs-lookup"><span data-stu-id="9e35c-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="9e35c-110">Untuk informasi lebih lanjut tentang aliran umum penyatuan data, lihat [menyatukan](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="9e35c-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="9e35c-111">Pilih entitas pertama</span><span class="sxs-lookup"><span data-stu-id="9e35c-111">Select the first entities</span></span>

1. <span data-ttu-id="9e35c-112">Di wawasan audiens, buka **Data** > **Satukan** > **Peta**.</span><span class="sxs-lookup"><span data-stu-id="9e35c-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="9e35c-113">Mulai fase peta dengan memilih **pilih entitas**.</span><span class="sxs-lookup"><span data-stu-id="9e35c-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="9e35c-114">Pilih entitas dan atribut yang akan digunakan dalam fase *pencocokan* dan *penggabungan*.</span><span class="sxs-lookup"><span data-stu-id="9e35c-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="9e35c-115">Anda dapat memilih atribut yang diperlukan secara terpisah dari entitas atau mencakup semua atribut dari entitas dengan memilih kotak centang **Sertakan semua bidang** di tingkat entitas.</span><span class="sxs-lookup"><span data-stu-id="9e35c-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="9e35c-116">Sebaiknya Pilih minimal dua entitas untuk mendapatkan manfaat dari proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="9e35c-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e35c-117">![Tambah contoh entitas](media/data-manager-configure-map-add-entities-example.png "Tambah contoh entitas")</span><span class="sxs-lookup"><span data-stu-id="9e35c-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="9e35c-118">Dalam contoh ini, kami akan menambahkan entitas **ecommercecontacts** dan **loycustomer**.</span><span class="sxs-lookup"><span data-stu-id="9e35c-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="9e35c-119">Dengan memilih entitas ini, Anda dapat memperoleh wawasan tentang pelanggan bisnis online mana yang merupakan anggota program loyalitas.</span><span class="sxs-lookup"><span data-stu-id="9e35c-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="9e35c-120">Anda dapat mencari pada kata kunci di semua atribut dan entitas untuk memilih atribut yang diperlukan yang akan dipetakan.</span><span class="sxs-lookup"><span data-stu-id="9e35c-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e35c-121">![Contoh bidang pencarian](media/data-manager-configure-map-search-fields-example.png "Contoh bidang pencarian")</span><span class="sxs-lookup"><span data-stu-id="9e35c-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="9e35c-122">Pilih **Terapkan** untuk mengonfirmasi pilihan Anda.</span><span class="sxs-lookup"><span data-stu-id="9e35c-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="9e35c-123">Pilih kunci primer dan jenis semantik untuk atribut</span><span class="sxs-lookup"><span data-stu-id="9e35c-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="9e35c-124">Setelah memilih entitas, Halaman **peta** akan berisi entitas yang dipilih untuk peninjauan.</span><span class="sxs-lookup"><span data-stu-id="9e35c-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="9e35c-125">Tentukan kunci primer untuk entitas dan identifikasi jenis semantik untuk atribut di entitas.</span><span class="sxs-lookup"><span data-stu-id="9e35c-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="9e35c-126">**Kunci primer**: Pilih satu atribut sebagai Kunci primer untuk tiap entitas.</span><span class="sxs-lookup"><span data-stu-id="9e35c-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="9e35c-127">Agar atribut menjadi kunci primer yang valid, ia seharusnya tidak menyertakan nilai duplikat, nilai yang tidak ada, atau nilai null.</span><span class="sxs-lookup"><span data-stu-id="9e35c-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="9e35c-128">Atribut jenis data string, bilangan bulat, dan GUID didukung sebagai primary key dan akan ditampilkan di bidang agar Anda dapat memilih darinya.</span><span class="sxs-lookup"><span data-stu-id="9e35c-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="9e35c-129">**Jenis semantik atribut**: Kategori atribut Anda, seperti alamat email atau nama.</span><span class="sxs-lookup"><span data-stu-id="9e35c-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="9e35c-130">Untuk menggunakan model AI untuk prediksi cerdas dari semantik, menghemat waktu dan meningkatkan akurasi, atur **pemetaan cerdas** ke **aktif**.</span><span class="sxs-lookup"><span data-stu-id="9e35c-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="9e35c-131">Pemetaan cerdas menyoroti rekomendasi semantik berbasis AI di bidang **jenis**.</span><span class="sxs-lookup"><span data-stu-id="9e35c-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="9e35c-132">Jika Anda mengaturnya ke **NONAKTIF**, Anda akan melihat rekomendasi pemetaan rutin kami.</span><span class="sxs-lookup"><span data-stu-id="9e35c-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="9e35c-133">Anda dapat memilih jenis semantik dari daftar pilihan yang tersedia dan menimpa pilihan yang disarankan.</span><span class="sxs-lookup"><span data-stu-id="9e35c-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9e35c-134">![jenis atribut dan prediksi semantik](media/data-manager-configure-map-add-attributes-semantic-prediction.png "jenis atribut dan prediksi semantik")</span><span class="sxs-lookup"><span data-stu-id="9e35c-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="9e35c-135">Menambahkan jenis semantik kustom juga dapat dilakukan.</span><span class="sxs-lookup"><span data-stu-id="9e35c-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="9e35c-136">Pilih bidang jenis untuk atribut tersebut, dan ketik nama jenis semantik kustom Anda.</span><span class="sxs-lookup"><span data-stu-id="9e35c-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="9e35c-137">Dengan demikian, Anda juga dapat mengubah jenis atribut yang diidentifikasi oleh sistem.</span><span class="sxs-lookup"><span data-stu-id="9e35c-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="9e35c-138">Semua atribut yang memiliki jenis semantik yang secara otomatis teridentifikasi dikelompokkan dalam Bagian **Tinjau bidang yang dipetakan**.</span><span class="sxs-lookup"><span data-stu-id="9e35c-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="9e35c-139">Tinjau atribut dan jenis semantik mereka karena akan digunakan untuk menggabungkan entitas Anda dalam langkah gabungan penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="9e35c-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="9e35c-140">Atribut yang tidak secara otomatis dipetakan ke jenis semantik dikelompokkan dalam bagian **Tentukan data di bidang yang tidak dipetakan**.</span><span class="sxs-lookup"><span data-stu-id="9e35c-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="9e35c-141">Pilih bidang jenis semantik untuk atribut yang tidak dipetakan, atau masukkan nama jenis atribut kustom Anda.</span><span class="sxs-lookup"><span data-stu-id="9e35c-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9e35c-142">![Kunci primer dan jenis atribut](media/data-manager-configure-map-add-attributes.png "Kunci primer dan jenis atribut")</span><span class="sxs-lookup"><span data-stu-id="9e35c-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="9e35c-143">Satu bidang harus dipetakan ke jenis semantik Person FullName untuk mengisi nama pelanggan di kartu pelanggan.</span><span class="sxs-lookup"><span data-stu-id="9e35c-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="9e35c-144">Jika tidak, kartu pelanggan akan muncul tanpa nama.</span><span class="sxs-lookup"><span data-stu-id="9e35c-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="9e35c-145">Menambah dan menghapus atribut dan entitas</span><span class="sxs-lookup"><span data-stu-id="9e35c-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="9e35c-146">Di **Satukan** > **peta**, pilih **Edit bidang**.</span><span class="sxs-lookup"><span data-stu-id="9e35c-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="9e35c-147">Di panel **edit bidang**, Tambah atau Hapus atribut dan entitas.</span><span class="sxs-lookup"><span data-stu-id="9e35c-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="9e35c-148">Gunakan pencarian atau gulir untuk mencari dan memilih atribut dan entitas yang diinginkan.</span><span class="sxs-lookup"><span data-stu-id="9e35c-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="9e35c-149">Anda tidak dapat menghapus atribut atau entitas jika sudah dicocokkan.</span><span class="sxs-lookup"><span data-stu-id="9e35c-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9e35c-150">![Tambah atau hapus atribut](media/configure-data-map-edit.png "Tambah atau hapus atribut")</span><span class="sxs-lookup"><span data-stu-id="9e35c-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="9e35c-151">Pilih **Terapkan**.</span><span class="sxs-lookup"><span data-stu-id="9e35c-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="9e35c-152">Menambahkan gambar ke profil</span><span class="sxs-lookup"><span data-stu-id="9e35c-152">Add images to profiles</span></span>

<span data-ttu-id="9e35c-153">Jika entitas berisi URL untuk gambar atau logo profil yang tersedia secara publik, Anda dapat menambahkannya ke profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="9e35c-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="9e35c-154">Pilih entitas dan Cari bidang yang berisi URL ke gambar profil.</span><span class="sxs-lookup"><span data-stu-id="9e35c-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="9e35c-155">Di bidang input **jenis**, secara manual masukkan nilai berikut:</span><span class="sxs-lookup"><span data-stu-id="9e35c-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="9e35c-156">Untuk orang: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="9e35c-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="9e35c-157">Untuk organisasi: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="9e35c-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="9e35c-158">Lanjutkan dengan langkah penyatuan dan pastikan atribut yang berisi URL gambar juga ditambahkan di langkah [penggabungan](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="9e35c-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="9e35c-159">Mengatur atribut untuk organisasi</span><span class="sxs-lookup"><span data-stu-id="9e35c-159">Set attributes for organizations</span></span>

<span data-ttu-id="9e35c-160">Untuk organisasi (pratinjau), jenis atribut harus dipetakan ke "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="9e35c-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="9e35c-161">![Kunci primer dan jenis atribut B2B](media/configure-data-map-edit-b2b.png "Kunci primer dan jenis atribut atribut")</span><span class="sxs-lookup"><span data-stu-id="9e35c-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="9e35c-162">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="9e35c-162">Next step</span></span>

<span data-ttu-id="9e35c-163">Sebagai bagian dari proses penyatuan data, buka halaman **pencocokan**.</span><span class="sxs-lookup"><span data-stu-id="9e35c-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="9e35c-164">Kunjungi [**kecocokan**](match-entities.md) untuk mempelajari fase ini.</span><span class="sxs-lookup"><span data-stu-id="9e35c-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="9e35c-165">Lihat video berikut: [memulai: membuat profil pelanggan terpadu](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="9e35c-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>
