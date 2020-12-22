---
title: Temukan pelanggan serupa dengan AI
description: Temukan segmen pelanggan serupa dengan kecerdasan buatan.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406067"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="d43f4-103">Pelanggan serupa (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="d43f4-103">Similar Customers (preview)</span></span>

<span data-ttu-id="d43f4-104">Fitur ini memungkinkan Anda menemukan pelanggan serupa di basis pelanggan menggunakan kecerdasan buatan.</span><span class="sxs-lookup"><span data-stu-id="d43f4-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="d43f4-105">Anda harus memiliki minimal satu segmen yang dibuat untuk menggunakan fitur ini.</span><span class="sxs-lookup"><span data-stu-id="d43f4-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="d43f4-106">Memperluas kriteria segmen yang ada membantu menemukan Pelanggan yang serupa dengan segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="d43f4-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="d43f4-107">*Menemukan Pelanggan yang serupa* menggunakan sarana otomatis untuk mengevaluasi data dan membuat prediksi berdasarkan data tersebut, sehingga memiliki kemampuan untuk digunakan sebagai metode pembuatan profil, karena istilah tersebut ditentukan oleh peraturan perlindungan data umum ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="d43f4-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="d43f4-108">Penggunaan fitur ini oleh pelanggan untuk memproses data dapat tergantung pada GDPR atau hukum atau peraturan lain.</span><span class="sxs-lookup"><span data-stu-id="d43f4-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="d43f4-109">Anda bertanggung jawab untuk memastikan bahwa penggunaan Dynamics 365 Customer Insights, termasuk prediksi, mematuhi semua hukum dan peraturan yang berlaku, termasuk hukum yang terkait dengan privasi, data pribadi, data biometrik, perlindungan data, dan kerahasiaan komunikasi.</span><span class="sxs-lookup"><span data-stu-id="d43f4-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="d43f4-110">Menemukan Pelanggan serupa</span><span class="sxs-lookup"><span data-stu-id="d43f4-110">Finding similar customers</span></span>

1. <span data-ttu-id="d43f4-111">Di wawasan audiens, buka **segmen** lalu pilih segmen yang akan mendasari segmen baru anda.</span><span class="sxs-lookup"><span data-stu-id="d43f4-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="d43f4-112">Itulah *segmen sumber* Anda.</span><span class="sxs-lookup"><span data-stu-id="d43f4-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="d43f4-113">Di panel tindakan, pilih **temukan pelanggan serupa**.</span><span class="sxs-lookup"><span data-stu-id="d43f4-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="d43f4-114">Tinjau nama yang disarankan untuk segmen baru Anda dan ubah jika perlu.</span><span class="sxs-lookup"><span data-stu-id="d43f4-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="d43f4-115">Tinjau bidang yang menentukan segmen baru Anda.</span><span class="sxs-lookup"><span data-stu-id="d43f4-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="d43f4-116">Bidang ini menentukan dasar untuk sistem mencoba menemukan pelanggan serupa dengan segmen sumber Anda.</span><span class="sxs-lookup"><span data-stu-id="d43f4-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="d43f4-117">Sistem akan memilih bidang yang disarankan secara default.</span><span class="sxs-lookup"><span data-stu-id="d43f4-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="d43f4-118">Bidang yang secara signifikan dapat mengurangi performa model secara otomatis dikecualikan:</span><span class="sxs-lookup"><span data-stu-id="d43f4-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="d43f4-119">Bidang dengan jenis data berikut: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="d43f4-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="d43f4-120">Bidang dengan kardinalitas (jumlah elemen dalam bidang) kurang dari 2 atau lebih dari 30</span><span class="sxs-lookup"><span data-stu-id="d43f4-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="d43f4-121">Pilih jika Anda ingin menyertakan **semua pelanggan** atau hanya pelanggan di **segmen tertentu yang ada** di segmen baru.</span><span class="sxs-lookup"><span data-stu-id="d43f4-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="d43f4-122">Kecualikan pelanggan di segmen sumber Anda dengan memilih kotak centang **Kecualikan semua orang di segmen sumber**.</span><span class="sxs-lookup"><span data-stu-id="d43f4-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="d43f4-123">Secara default, sistem menyarankan memasukkan hanya 20% dari ukuran audiens target dalam output anda.</span><span class="sxs-lookup"><span data-stu-id="d43f4-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="d43f4-124">Edit ambang ini bila diperlukan.</span><span class="sxs-lookup"><span data-stu-id="d43f4-124">Edit this threshold as needed.</span></span> <span data-ttu-id="d43f4-125">Meningkatkan ambang batas akan mengurangi presisi.</span><span class="sxs-lookup"><span data-stu-id="d43f4-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="d43f4-126">Pilih **jalankan** di bagian bawah halaman untuk memulai tugas klasifikasi biner (metode Pembelajaran Mesin) yang menganalisis himpunan data.</span><span class="sxs-lookup"><span data-stu-id="d43f4-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="d43f4-127">Melihat segmen serupa</span><span class="sxs-lookup"><span data-stu-id="d43f4-127">View the similar segment</span></span>

<span data-ttu-id="d43f4-128">Setelah memproses segmen serupa, Anda akan menemukan segmen baru yang tercantum pada halaman **segmen**.</span><span class="sxs-lookup"><span data-stu-id="d43f4-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d43f4-129">![Segmen pelanggan serupa](media/expanded-segment.png "Segmen pelanggan serupa")</span><span class="sxs-lookup"><span data-stu-id="d43f4-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="d43f4-130">Pilih **tampilan** di bilah tindakan untuk membuka detail segmen.</span><span class="sxs-lookup"><span data-stu-id="d43f4-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="d43f4-131">Tampilan ini berisi informasi tentang distribusi hasil di seluruh [skor kemiripan](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="d43f4-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="d43f4-132">Anda juga akan menemukan nilai skor kemiripan dalam **pratinjau anggota segmen**.</span><span class="sxs-lookup"><span data-stu-id="d43f4-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="d43f4-133">Gunakan output dari segmen yang serupa</span><span class="sxs-lookup"><span data-stu-id="d43f4-133">Use the output of a similar segment</span></span>

<span data-ttu-id="d43f4-134">Anda dapat [bekerja dengan output segmen yang serupa](segments.md) seperti yang Anda lakukan dengan segmen lain.</span><span class="sxs-lookup"><span data-stu-id="d43f4-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="d43f4-135">Misalnya, ekspor segmen atau buat ukuran.</span><span class="sxs-lookup"><span data-stu-id="d43f4-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="d43f4-136">Segarkan dan edit segmen serupa</span><span class="sxs-lookup"><span data-stu-id="d43f4-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="d43f4-137">Untuk menyegarkan segmen yang serupa, pilih segmen pada halaman **segmen** dan pilih **Segarkan** di bilah tindakan.</span><span class="sxs-lookup"><span data-stu-id="d43f4-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="d43f4-138">Mengedit segmen serupa akan memproses ulang data Anda.</span><span class="sxs-lookup"><span data-stu-id="d43f4-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="d43f4-139">Segmen yang dibuat sebelumnya akan diperbarui dengan data yang diperbarui.</span><span class="sxs-lookup"><span data-stu-id="d43f4-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="d43f4-140">Untuk mengedit segmen yang serupa, pilih segmen pada halaman **segmen** dan pilih **Edit** di bilah tindakan.</span><span class="sxs-lookup"><span data-stu-id="d43f4-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="d43f4-141">Terapkan perubahan dan pilih **Jalankan** untuk memulai pemrosesan.</span><span class="sxs-lookup"><span data-stu-id="d43f4-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="d43f4-142">Menghapus segmen yang sama</span><span class="sxs-lookup"><span data-stu-id="d43f4-142">Delete a similar segment</span></span>

<span data-ttu-id="d43f4-143">Pilih segmen pada halaman **segmen** dan pilih **Hapus** di bilah tindakan.</span><span class="sxs-lookup"><span data-stu-id="d43f4-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="d43f4-144">Kemudian, konfirmasikan penghapusan.</span><span class="sxs-lookup"><span data-stu-id="d43f4-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="d43f4-145">Tentang skor kemiripan</span><span class="sxs-lookup"><span data-stu-id="d43f4-145">About similarity scores</span></span>

<span data-ttu-id="d43f4-146">Model Pembelajaran Mesin klasifikasi biner menetapkan skor untuk pelanggan di segmen serupa.</span><span class="sxs-lookup"><span data-stu-id="d43f4-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="d43f4-147">Skor didasarkan pada kemiripan dengan pelanggan di segmen sumber.</span><span class="sxs-lookup"><span data-stu-id="d43f4-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="d43f4-148">skor kemiripan di bawah 0,55 adalah pelanggan yang diklasifikasikan sistem sebagai *tidak mirip dengan* pelanggan di segmen sumber</span><span class="sxs-lookup"><span data-stu-id="d43f4-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="d43f4-149">Nilai kemiripan antara 0,55 – 0,7 diklasifikasikan sebagai *agak mirip*</span><span class="sxs-lookup"><span data-stu-id="d43f4-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="d43f4-150">Nilai kemiripan antara 0,7 – 0,85 diklasifikasikan sebagai *mirip*</span><span class="sxs-lookup"><span data-stu-id="d43f4-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="d43f4-151">Nilai kemiripan antara 0,85 – 1 adalah pelanggan yang diklasifikasikan sistem sebagai *sangat mirip*</span><span class="sxs-lookup"><span data-stu-id="d43f4-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="d43f4-152">Pelanggan dengan Skor kemiripan di bawah 0,4 tidak disertakan dalam output model.</span><span class="sxs-lookup"><span data-stu-id="d43f4-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="d43f4-153">Sistem tidak menganggapnya cukup mirip dengan segmen sumber.</span><span class="sxs-lookup"><span data-stu-id="d43f4-153">The system doesn't consider them similar enough to the source segment.</span></span>
