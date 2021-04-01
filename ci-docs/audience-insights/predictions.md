---
title: Melengkapi data parsial menggunakan prediksi
description: Gunakan prediksi untuk mengisi data pelanggan yang tidak lengkap.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595905"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="b0887-103">Lengkapi data parsial dengan prediksi</span><span class="sxs-lookup"><span data-stu-id="b0887-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b0887-104">Prediksi memungkinkan Anda dengan mudah membuat nilai prediksi yang dapat meningkatkan pemahaman Anda tentang pelanggan.</span><span class="sxs-lookup"><span data-stu-id="b0887-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="b0887-105">Pada halaman **intelijen** > **prediksi**, anda dapat memilih **prediksi saya** untuk melihat prediksi yang telah dikonfigurasi di bagian lain dari wawasan audiens, dan memungkinkan anda menyesuaikannya lebih lanjut.</span><span class="sxs-lookup"><span data-stu-id="b0887-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="b0887-106">Anda tidak dapat menggunakan fitur ini jika lingkungan Anda menggunakan penyimpanan Azure data Lake gen 2.</span><span class="sxs-lookup"><span data-stu-id="b0887-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="b0887-107">Fitur prediksi menggunakan cara otomatis untuk mengevaluasi data dan membuat prediksi berdasarkan data tersebut, sehingga memiliki kemampuan untuk digunakan sebagai metode pembuatan profil, sebagaimana istilah tersebut didefinisikan oleh peraturan perlindungan data umum ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="b0887-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="b0887-108">Penggunaan fitur ini oleh pelanggan untuk memproses data dapat tergantung pada GDPR atau hukum atau peraturan lain.</span><span class="sxs-lookup"><span data-stu-id="b0887-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="b0887-109">Anda bertanggung jawab untuk memastikan bahwa penggunaan Dynamics 365 Customer Insights, termasuk prediksi, mematuhi semua hukum dan peraturan yang berlaku, termasuk hukum yang terkait dengan privasi, data pribadi, data biometrik, perlindungan data, dan kerahasiaan komunikasi.</span><span class="sxs-lookup"><span data-stu-id="b0887-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b0887-110">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="b0887-110">Prerequisites</span></span>

<span data-ttu-id="b0887-111">Sebelum organisasi Anda dapat menggunakan fitur prediksi, prasyarat berikut harus terpenuhi:</span><span class="sxs-lookup"><span data-stu-id="b0887-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="b0887-112">Organisasi Anda memiliki instans yang [disiapkan di Common Data Service](/ai-builder/build-model#prerequisites) dan ada di organisasi yang sama seperti Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b0887-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="b0887-113">Lingkungan Anda melekat pada instans Common Data Service Anda.</span><span class="sxs-lookup"><span data-stu-id="b0887-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="b0887-114">Jika Anda [membuat lingkungan pertama](manage-environments.md), konfigurasikan di dialog **buat lingkungan** dan pilih **lanjutan**.</span><span class="sxs-lookup"><span data-stu-id="b0887-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="b0887-115">Jika Anda telah membuat lingkungan, buka pengaturannya dan pilih **lanjutan**.</span><span class="sxs-lookup"><span data-stu-id="b0887-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="b0887-116">Apa pun, di bagian **gunakan prediksi**, masukkan URL instans Common Data Service yang ingin Anda lampirkan lingkungan Anda.</span><span class="sxs-lookup"><span data-stu-id="b0887-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="b0887-117">Membuat prediksi di entitas pelanggan</span><span class="sxs-lookup"><span data-stu-id="b0887-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="b0887-118">Di wawasan audiens, buka **Data** > **Entitas**.</span><span class="sxs-lookup"><span data-stu-id="b0887-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="b0887-119">Pilih entitas **pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="b0887-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="b0887-120">Di entitas **pelanggan: CustomerInsights**, pilih pada tab **bidang**.</span><span class="sxs-lookup"><span data-stu-id="b0887-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="b0887-121">Temukan nama atribut yang diinginkan untuk memprediksi nilai, lalu pilih ikon **Ikhtisar** di kolom **ringkasan**.</span><span class="sxs-lookup"><span data-stu-id="b0887-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b0887-122">![Ikon Ikhtisar](media/intelligence-overviewicon.png "Ikon Ikhtisar")</span><span class="sxs-lookup"><span data-stu-id="b0887-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="b0887-123">Jika ada tingkat tinggi nilai yang hilang untuk atribut Anda, pilih **Prediksikan nilai yang hilang** untuk melanjutkan prediksi Anda.</span><span class="sxs-lookup"><span data-stu-id="b0887-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b0887-124">![Ikhtisar status dengan tombol memprediksi nilai hilang ditampilkan](media/intelligence-overviewpredictmissingvalues.png "Ikhtisar status dengan tombol memprediksi nilai hilang ditampilkan")</span><span class="sxs-lookup"><span data-stu-id="b0887-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="b0887-125">Berikan **nama tampilan** dan **nama entitas Output** untuk hasil prediksi.</span><span class="sxs-lookup"><span data-stu-id="b0887-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="b0887-126">Daftar pilihan yang telah diisi akan menampilkan lokasi Anda dapat memetakan nilai ke kategori yang diramalkan.</span><span class="sxs-lookup"><span data-stu-id="b0887-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="b0887-127">Dalam kasus ini, satu-satunya pilihan kategori Anda adalah 0 atau 1 saat memetakan ke sifat prediksi true/false atau biner.</span><span class="sxs-lookup"><span data-stu-id="b0887-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="b0887-128">Dalam kolom Kategori, petakan nilai bidang yang ingin Anda klasifikasikan sebagai "0" di prediksi akhir ke "0", dan item yang ingin diklasifikasikan sebagai "1" di prediksi akhir ke "1".</span><span class="sxs-lookup"><span data-stu-id="b0887-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b0887-129">![Contoh yang menampilkan nilai bidang yang dipetakan ke kategori](media/intelligence-categorymapping.png "Contoh yang menampilkan nilai bidang yang dipetakan ke kategori")</span><span class="sxs-lookup"><span data-stu-id="b0887-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="b0887-130">Pilih **selesai** dan prediksi akan diproses.</span><span class="sxs-lookup"><span data-stu-id="b0887-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="b0887-131">Pemrosesan akan memakan waktu, tergantung pada ukuran dan kompleksitas data.</span><span class="sxs-lookup"><span data-stu-id="b0887-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="b0887-132">Hasil akan tersedia di entitas baru berdasarkan **nama entitas output** prediksi yang Anda buat.</span><span class="sxs-lookup"><span data-stu-id="b0887-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="b0887-133">Buat prediksi saat membuat segmen</span><span class="sxs-lookup"><span data-stu-id="b0887-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="b0887-134">Memprediksi nilai yang hilang untuk atribut tertentu pilihan juga dapat dilakukan saat membuat segmen.</span><span class="sxs-lookup"><span data-stu-id="b0887-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="b0887-135">Khususnya, bila Anda dengan cepat membuat segmen berdasarkan entitas pelanggan atau entitas Customer_Measure terpadu.</span><span class="sxs-lookup"><span data-stu-id="b0887-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="b0887-136">Sebagai bagian dari alur ini, Anda memilih atribut khusus untuk mendasarkan segmen Anda seperti kepuasan pelanggan atau jumlah pembelian.</span><span class="sxs-lookup"><span data-stu-id="b0887-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="b0887-137">Setelah pembuatan segmen, sistem akan menyarankan metode untuk memprediksi nilai yang hilang untuk atribut ini.</span><span class="sxs-lookup"><span data-stu-id="b0887-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="b0887-138">Di wawasan audiens, buka **segmen,** lalu pilih petak **profil**.</span><span class="sxs-lookup"><span data-stu-id="b0887-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="b0887-139">Pilih **bidang** untuk membuat segmen dan memilih **operator**, lalu pilih **tinjau**.</span><span class="sxs-lookup"><span data-stu-id="b0887-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="b0887-140">Berikan **nama** dan **nama tampilan** untuk segmen.</span><span class="sxs-lookup"><span data-stu-id="b0887-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="b0887-141">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="b0887-141">Select **Save**.</span></span>

5. <span data-ttu-id="b0887-142">Jika segmen yang Anda buat memiliki data yang tidak lengkap di bidang sumber, Anda dapat memilih untuk memprediksi nilai yang tidak ada.</span><span class="sxs-lookup"><span data-stu-id="b0887-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b0887-143">![Tombol prediksi](media/segments-predictoption.png "Tombol prediksi")</span><span class="sxs-lookup"><span data-stu-id="b0887-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="b0887-144">Berikan **nama tampilan** dan **nama entitas Output** untuk hasil prediksi.</span><span class="sxs-lookup"><span data-stu-id="b0887-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="b0887-145">Pilih **Selesai**.</span><span class="sxs-lookup"><span data-stu-id="b0887-145">Select **Done**.</span></span> <span data-ttu-id="b0887-146">Prediksi Anda akan segera dibuat di entitas baru dengan nama yang Anda berikan untuk **nama entitas output**.</span><span class="sxs-lookup"><span data-stu-id="b0887-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="b0887-147">Lihat Prediksi</span><span class="sxs-lookup"><span data-stu-id="b0887-147">View a prediction</span></span>

1. <span data-ttu-id="b0887-148">Di wawasan audiens, buka **Intelijen** > **Prediksi** > **Prediksi Saya**.</span><span class="sxs-lookup"><span data-stu-id="b0887-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="b0887-149">Pilih prediksi yang ingin Anda tinjau.</span><span class="sxs-lookup"><span data-stu-id="b0887-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="b0887-150">Pilih elipsis di kolom **tindakan** dan pilih **tampilan**.</span><span class="sxs-lookup"><span data-stu-id="b0887-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="b0887-151">Anda akan melihat sejumlah poin data dalam tampilan prediksi.</span><span class="sxs-lookup"><span data-stu-id="b0887-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b0887-152">![Halaman Prediksi](media/intelligence-predictionsviewpage.png "Halaman Prediksi")</span><span class="sxs-lookup"><span data-stu-id="b0887-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="b0887-153">**Nilai yang diprediksi** menunjukkan pemetaan yang Anda buat selama fase pemetaan nilai bidang ke kategori.</span><span class="sxs-lookup"><span data-stu-id="b0887-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="b0887-154">Ini adalah nilai dalam himpunan data Anda yang telah dipetakan ke kategori tertentu.</span><span class="sxs-lookup"><span data-stu-id="b0887-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="b0887-155">-**Pemberi pengaruh teratas** adalah faktor dalam himpunan data Anda yang kemungkinan besar akan mempengaruhi tingkat keyakinan prediksi nilai bidang Anda yang dipetakan ke kategori tertentu.</span><span class="sxs-lookup"><span data-stu-id="b0887-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="b0887-156">**Kinerja** menunjukkan kinerja prediksi.</span><span class="sxs-lookup"><span data-stu-id="b0887-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="b0887-157">Pilih tautan untuk mempelajari lebih lanjut.</span><span class="sxs-lookup"><span data-stu-id="b0887-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="b0887-158">**Pratinjau** menampilkan contoh data output dari prediksi Anda dan kemungkinan, atau keyakinan kita, atas nilai prediksi di mana 0 tidak pasti, dan 1 adalah pasti.</span><span class="sxs-lookup"><span data-stu-id="b0887-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="b0887-159">Perbarui prediksi</span><span class="sxs-lookup"><span data-stu-id="b0887-159">Update a prediction</span></span>

1. <span data-ttu-id="b0887-160">Di wawasan audiens, buka **Intelijen** > **Prediksi** > **Prediksi Saya**.</span><span class="sxs-lookup"><span data-stu-id="b0887-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="b0887-161">Pilih prediksi yang ingin Anda perbarui dan pilih ikon **Perbarui**.</span><span class="sxs-lookup"><span data-stu-id="b0887-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="b0887-162">Prediksi akan dijadwalkan untuk diproses.</span><span class="sxs-lookup"><span data-stu-id="b0887-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="b0887-163">Anda dapat melihat waktu terakhir diperbarui dalam kolom **diperbarui** pada halaman **prediksi**.</span><span class="sxs-lookup"><span data-stu-id="b0887-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="b0887-164">Edit Prediksi</span><span class="sxs-lookup"><span data-stu-id="b0887-164">Edit a prediction</span></span>

<span data-ttu-id="b0887-165">Setelah membuat prediksi, Anda dapat menyesuaikan model di AI Builder untuk meningkatkan efektivitas model Anda.</span><span class="sxs-lookup"><span data-stu-id="b0887-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="b0887-166">Di wawasan audiens, buka **Intelijen** > **Prediksi** > **Prediksi Saya**.</span><span class="sxs-lookup"><span data-stu-id="b0887-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="b0887-167">Pilih prediksi yang akan diedit.</span><span class="sxs-lookup"><span data-stu-id="b0887-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="b0887-168">Pilih elipsis di kolom **tindakan** dan pilih **tampilan**.</span><span class="sxs-lookup"><span data-stu-id="b0887-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="b0887-169">pilih **Sesuaikan di AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="b0887-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="b0887-170">Perbarui model Anda di AI Builder.</span><span class="sxs-lookup"><span data-stu-id="b0887-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="b0887-171">[Pelajari lebih lanjut tentang cara mengelola model di AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="b0887-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="b0887-172">Langkah berikutnya dari prediksi Anda akan menggunakan model yang telah diperbarui yang telah Anda buat.</span><span class="sxs-lookup"><span data-stu-id="b0887-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="b0887-173">Model baru yang dibuat di AI Builder tidak akan ditampilkan di wawasan audiens kecuali model dibuat dari pengalaman yang tercantum di atas.</span><span class="sxs-lookup"><span data-stu-id="b0887-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="b0887-174">Hilangkan prediksi</span><span class="sxs-lookup"><span data-stu-id="b0887-174">Remove a prediction</span></span>

1. <span data-ttu-id="b0887-175">Di wawasan audiens, buka **Intelijen** > **Prediksi** > **Prediksi Saya**.</span><span class="sxs-lookup"><span data-stu-id="b0887-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="b0887-176">Pilih prediksi yang ingin Anda hapus.</span><span class="sxs-lookup"><span data-stu-id="b0887-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="b0887-177">Pilih elipsis di kolom **tindakan** dan pilih **Hapus**.</span><span class="sxs-lookup"><span data-stu-id="b0887-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="b0887-178">Konfirmasikan Penghapusan.</span><span class="sxs-lookup"><span data-stu-id="b0887-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b0887-179">Pemecahan masalah</span><span class="sxs-lookup"><span data-stu-id="b0887-179">Troubleshooting</span></span>

<span data-ttu-id="b0887-180">Jika Anda tidak dapat menyelesaikan proses lampirkan Common Data Service karena kesalahan, Anda dapat mencoba menyelesaikan proses secara manual.</span><span class="sxs-lookup"><span data-stu-id="b0887-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="b0887-181">Ada dua masalah umum yang dapat terjadi di proses melampirkan:</span><span class="sxs-lookup"><span data-stu-id="b0887-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="b0887-182">Solusi Add-in kartu pelanggan tidak diinstal.</span><span class="sxs-lookup"><span data-stu-id="b0887-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="b0887-183">Selesaikan petunjuk untuk [menginstal dan mengkonfigurasi solusi](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="b0887-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="b0887-184">Izin aplikasi tidak diberikan.</span><span class="sxs-lookup"><span data-stu-id="b0887-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="b0887-185">Tuju [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b0887-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="b0887-186">Pilih **lingkungan**.</span><span class="sxs-lookup"><span data-stu-id="b0887-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="b0887-187">Pilih elipsis di sebelah lingkungan yang akan ditambahkan izin dan pilih **pengaturan**.</span><span class="sxs-lookup"><span data-stu-id="b0887-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="b0887-188">Perluas **pengguna + izin** dan pilih **pengguna**.</span><span class="sxs-lookup"><span data-stu-id="b0887-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="b0887-189">Pilih **+ Baru** dan pilih **Pengguna**.</span><span class="sxs-lookup"><span data-stu-id="b0887-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="b0887-190">Pilih **pengguna aplikasi** jika belum dipilih dan masukkan informasi berikut:</span><span class="sxs-lookup"><span data-stu-id="b0887-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="b0887-191">**Nama Pengguna:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b0887-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="b0887-192">**ID Aplikasi:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="b0887-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="b0887-193">**Nama Depan:** Pelanggan</span><span class="sxs-lookup"><span data-stu-id="b0887-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="b0887-194">**Nama Belakang:** Insights</span><span class="sxs-lookup"><span data-stu-id="b0887-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="b0887-195">**Email Utama:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b0887-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="b0887-196">Pilih **Simpan & Tutup**.</span><span class="sxs-lookup"><span data-stu-id="b0887-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="b0887-197">Pilih pengguna yang baru saja Anda buat.</span><span class="sxs-lookup"><span data-stu-id="b0887-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="b0887-198">Pilih **Kelola peran** di bilah menu atas.</span><span class="sxs-lookup"><span data-stu-id="b0887-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="b0887-199">Pilih **administrator sistem**, lalu pilih **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0887-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]