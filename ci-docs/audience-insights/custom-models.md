---
title: Model Pembelajaran Mesin kustom | Microsoft Docs
description: Bekerja dengan model kustom dari Azure Machine Learning di Dynamics 365 Customer Insights
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305640"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="6aec7-103">Model Pembelajaran Mesin kustom</span><span class="sxs-lookup"><span data-stu-id="6aec7-103">Custom machine learning models</span></span>

<span data-ttu-id="6aec7-104">**Kecerdasan** > **Model Kustom** memungkinkan Anda mengelola alur kerja berdasarkan model Pembelajaran Mesin Azure.</span><span class="sxs-lookup"><span data-stu-id="6aec7-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="6aec7-105">Alur kerja membantu Anda memilih data yang ingin Anda hasilkan wawasannya dan memetakan hasil ke data pelanggan terpadu Anda.</span><span class="sxs-lookup"><span data-stu-id="6aec7-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="6aec7-106">Untuk informasi lebih lanjut tentang cara membuat model kustom ML, lihat [menggunakan model berbasis pembelajaran mesin Azure](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="6aec7-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="6aec7-107">AI yang bertanggung jawab</span><span class="sxs-lookup"><span data-stu-id="6aec7-107">Responsible AI</span></span>

<span data-ttu-id="6aec7-108">Prediksi menawarkan kemampuan untuk membuat pengalaman pelanggan yang lebih baik, meningkatkan kemampuan Bisnis, dan aliran pendapatan.</span><span class="sxs-lookup"><span data-stu-id="6aec7-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="6aec7-109">Kami sangat menyarankan agar anda menyeimbangkan nilai prediksi anda terhadap dampak dan bias yang dapat ditimbulkan dengan cara yang etis.</span><span class="sxs-lookup"><span data-stu-id="6aec7-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="6aec7-110">Pelajari lebih lanjut tentang cara Microsoft [menangani AI yang bertanggung jawab](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="6aec7-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="6aec7-111">Anda juga dapat mempelajari [teknik dan proses untuk Pembelajaran Mesin bertanggung jawab](/azure/machine-learning/concept-responsible-ml) yang spesifik untuk Pembelajaran Mesin Azure.</span><span class="sxs-lookup"><span data-stu-id="6aec7-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6aec7-112">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="6aec7-112">Prerequisites</span></span>

- <span data-ttu-id="6aec7-113">Saat ini, fitur ini mendukung layanan web yang dipublikasikan melalui jalur [Studio Pembelajaran Mesin (klasik)](https://studio.azureml.net) dan [Alur kerja Azure Pembelajaran Mesin](/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="6aec7-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="6aec7-114">Anda memerlukan akun Azure data Lake Gen2 Storage yang terkait dengan instans Azure studio Anda untuk menggunakan fitur ini.</span><span class="sxs-lookup"><span data-stu-id="6aec7-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="6aec7-115">Untuk informasi lebih lanjut, Lihat [membuat akun penyimpanan Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="6aec7-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="6aec7-116">Untuk ruang kerja Pembelajaran Mesin Azure, Anda memerlukan izin Pemilik atau Administrator Akses Pengguna untuk ruang kerja Pembelajaran Mesin Azure.</span><span class="sxs-lookup"><span data-stu-id="6aec7-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6aec7-117">Data akan ditransfer antara instans Customer Insights dan alur atau layanan web Azure terpilih dalam alur kerja.</span><span class="sxs-lookup"><span data-stu-id="6aec7-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="6aec7-118">Jika Anda mentransfer data ke layanan Azure, pastikan layanan dikonfigurasi untuk memproses data dengan cara dan lokasi yang diperlukan agar sesuai dengan persyaratan hukum atau peraturan untuk data tersebut di organisasi Anda.</span><span class="sxs-lookup"><span data-stu-id="6aec7-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="6aec7-119">Tambahkan alur kerja baru</span><span class="sxs-lookup"><span data-stu-id="6aec7-119">Add a new workflow</span></span>

1. <span data-ttu-id="6aec7-120">Buka **kecerdasan** > **model kustom** dan pilih **alur kerja baru**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="6aec7-121">Beri model kustom Anda nama yang dikenali di bidang **nama**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6aec7-122">![Tangkapan layar panel alur kerja baru](media/new-workflowv2.png "Tangkapan layar panel alur kerja baru")</span><span class="sxs-lookup"><span data-stu-id="6aec7-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="6aec7-123">Pilih organisasi yang berisi layanan web dalam **penyewa yang berisi layanan web Anda**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="6aec7-124">Jika langganan Pembelajaran Mesin Azure Anda berada di penyewa berbeda dari pada Customer Insights, pilih **masuk** dengan kredensial anda untuk organisasi yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="6aec7-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="6aec7-125">Pilih **ruang kerja** yang terkait dengan layanan web Anda.</span><span class="sxs-lookup"><span data-stu-id="6aec7-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="6aec7-126">Ada dua bagian terdaftar, satu untuk Pembelajaran Mesin azure v1 (Studio Pembelajaran Mesin (klasik)) dan Pembelajaran Mesin azure v2 (Pembelajaran Mesin azure).</span><span class="sxs-lookup"><span data-stu-id="6aec7-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="6aec7-127">Jika anda tidak yakin ruang kerja mana yang tepat untuk layanan web Studio Pembelajaran Mesin (klasik), pilih **Mana pun**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="6aec7-128">Pilih layanan web Studio Pembelajaran Mesin (klasik) atau alur kerja Pembelajaran Mesin Azure di menu tarik turun **layanan web yang berisi model anda**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="6aec7-129">Kemudian pilih **Berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="6aec7-130">Pelajari lebih lanjut tentang [mempublikasi layanan web di Studio Pembelajaran Mesin (klasik)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="6aec7-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="6aec7-131">Pelajari lebih lanjut tentang cara [mempublikasi alur kerja di Pembelajaran Mesin Azure menggunakan desainer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) atau [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="6aec7-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="6aec7-132">Alur anda harus dipublikasikan dalam [titik akhir alur](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="6aec7-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="6aec7-133">Untuk setiap **input Layanan web**, pilih **entitas** yang cocok dari Customer Insights dari wawasan audiens dan pilih **Berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="6aec7-134">Alur kerja model kustom akan menerapkan heuristik untuk memetakan bidang input layanan web ke atribut entitas berdasarkan nama dan jenis data bidang.</span><span class="sxs-lookup"><span data-stu-id="6aec7-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="6aec7-135">Anda akan melihat kesalahan jika bidang layanan web tidak dapat dipetakan ke entitas.</span><span class="sxs-lookup"><span data-stu-id="6aec7-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6aec7-136">![Mengonfigurasikan alur kerja](media/intelligence-screen2-updated.png "Mengonfigurasikan alur kerja")</span><span class="sxs-lookup"><span data-stu-id="6aec7-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="6aec7-137">Pada langkah **parameter output model**, atur properti berikut:</span><span class="sxs-lookup"><span data-stu-id="6aec7-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="6aec7-138">Studio Pembelajaran Mesin (Klasik)</span><span class="sxs-lookup"><span data-stu-id="6aec7-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="6aec7-139">Masukkan **nama entitas** yang Anda ingin hasil output layanan webnya mengalir ke dalamnya.</span><span class="sxs-lookup"><span data-stu-id="6aec7-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="6aec7-140">Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="6aec7-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="6aec7-141">Masukkan **nama entitas** yang Anda ingin hasil output alur kerjanya mengalir ke dalamnya.</span><span class="sxs-lookup"><span data-stu-id="6aec7-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="6aec7-142">Pilih **nama parameter penyimpanan data Output** alur kerja batch anda dari dropdown.</span><span class="sxs-lookup"><span data-stu-id="6aec7-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="6aec7-143">Pilih **nama parameter jalur Output** alur kerja batch anda dari dropdown.</span><span class="sxs-lookup"><span data-stu-id="6aec7-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="6aec7-144">![Panel parameter output model](media/intelligence-screen3-outputparameters.png "Panel parameter output model")</span><span class="sxs-lookup"><span data-stu-id="6aec7-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="6aec7-145">Pilih atribut yang cocok dari daftar drop- down **id pelanggan dalam hasil** yang mengidentifikasi pelanggan dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-145">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6aec7-146">![Kaitkan hasil ke panel data pelanggan](media/intelligence-screen4-relatetocustomer.png "Kaitkan hasil ke panel data pelanggan")</span><span class="sxs-lookup"><span data-stu-id="6aec7-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="6aec7-147">Anda akan melihat layar **alur kerja yang tersimpan** dengan rincian tentang alur kerja.</span><span class="sxs-lookup"><span data-stu-id="6aec7-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="6aec7-148">Jika Anda mengonfigurasikan alur kerja untuk alur Pembelajaran Mesin Azure, wawasan audiens akan dilampirkan ke ruang kerja yang berisi alur.</span><span class="sxs-lookup"><span data-stu-id="6aec7-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="6aec7-149">Wawasan audiens akan mendapatkan peran **kontributor** di ruang kerja Azure.</span><span class="sxs-lookup"><span data-stu-id="6aec7-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="6aec7-150">Pilih **Selesai**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-150">Select **Done**.</span></span>

1. <span data-ttu-id="6aec7-151">Anda sekarang dapat menjalankan alur kerja dari halaman **model kustom**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="6aec7-152">Edit alur kerja</span><span class="sxs-lookup"><span data-stu-id="6aec7-152">Edit a workflow</span></span>

1. <span data-ttu-id="6aec7-153">Pada halaman **Model Kustom**, pilih elipsis vertikal di kolom **tindakan** di sebelah alur kerja yang telah Anda buat sebelumnya dan pilih **Edit**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="6aec7-154">Anda dapat memperbarui nama yang dikenali alur kerja di bidang **nama tampilan**, namun Anda tidak dapat mengubah layanan Web atau alur yang dikonfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="6aec7-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="6aec7-155">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-155">Select **Next**.</span></span>

1. <span data-ttu-id="6aec7-156">Untuk setiap **input Layanan web**, Anda dapat memperbarui **entitas** yang cocok dari wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="6aec7-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="6aec7-157">Kemudian pilih **Berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="6aec7-158">Pada langkah **parameter output model**, atur properti berikut:</span><span class="sxs-lookup"><span data-stu-id="6aec7-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="6aec7-159">Studio Pembelajaran Mesin (Klasik)</span><span class="sxs-lookup"><span data-stu-id="6aec7-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="6aec7-160">Masukkan **nama entitas** yang Anda ingin hasil output layanan webnya mengalir ke dalamnya.</span><span class="sxs-lookup"><span data-stu-id="6aec7-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="6aec7-161">Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="6aec7-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="6aec7-162">Masukkan **nama entitas** yang Anda ingin hasil output alur kerjanya mengalir ke dalamnya.</span><span class="sxs-lookup"><span data-stu-id="6aec7-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="6aec7-163">Pilih **nama parameter penyimpanan data Output** untuk alur pengujian anda.</span><span class="sxs-lookup"><span data-stu-id="6aec7-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="6aec7-164">Pilih **nama parameter jalur Output** untuk alur pengujian anda.</span><span class="sxs-lookup"><span data-stu-id="6aec7-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="6aec7-165">Pilih atribut yang cocok dari daftar drop- down **id pelanggan dalam hasil** yang mengidentifikasi pelanggan dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-165">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="6aec7-166">Pilih atribut dari output inferensi dengan nilai yang serupa dengan kolom ID pelanggan dari entitas pelanggan.</span><span class="sxs-lookup"><span data-stu-id="6aec7-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="6aec7-167">Jika tidak memiliki kolom di himpunan data, pilih atribut yang secara unik mengidentifikasi baris.</span><span class="sxs-lookup"><span data-stu-id="6aec7-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="6aec7-168">Menjalankan alur kerja</span><span class="sxs-lookup"><span data-stu-id="6aec7-168">Run a workflow</span></span>

1. <span data-ttu-id="6aec7-169">Pada halaman **Model Kustom**, pilih elipsis vertikal di kolom **tindakan** di sebelah alur kerja yang telah Anda buat sebelumnya.</span><span class="sxs-lookup"><span data-stu-id="6aec7-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="6aec7-170">Pilih **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-170">Select **Run**.</span></span>

<span data-ttu-id="6aec7-171">Alur kerja Anda juga berjalan secara otomatis dengan setiap penyegaran terjadwal.</span><span class="sxs-lookup"><span data-stu-id="6aec7-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="6aec7-172">Pelajari lebih lanjut [cara mengkonfigurasi penyegaran terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6aec7-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="6aec7-173">Hapus alur kerja</span><span class="sxs-lookup"><span data-stu-id="6aec7-173">Delete a workflow</span></span>

1. <span data-ttu-id="6aec7-174">Pada halaman **Model Kustom**, pilih elipsis vertikal di kolom **tindakan** di sebelah alur kerja yang telah Anda buat sebelumnya.</span><span class="sxs-lookup"><span data-stu-id="6aec7-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="6aec7-175">Klik **Hapus**, dan konfirmasi penghapusan Anda.</span><span class="sxs-lookup"><span data-stu-id="6aec7-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="6aec7-176">Alur kerja Anda akan dihapus.</span><span class="sxs-lookup"><span data-stu-id="6aec7-176">Your workflow will be deleted.</span></span> <span data-ttu-id="6aec7-177">[Entitas](entities.md) yang dibuat saat Anda membuat alur kerja tetap ada, dan dapat dilihat dari halaman **entitas**.</span><span class="sxs-lookup"><span data-stu-id="6aec7-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="6aec7-178">Hasil</span><span class="sxs-lookup"><span data-stu-id="6aec7-178">Results</span></span>

<span data-ttu-id="6aec7-179">Hasil dari alur kerja disimpan dalam entitas yang dikonfigurasi selama fase Parameter Output Model.</span><span class="sxs-lookup"><span data-stu-id="6aec7-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="6aec7-180">Anda dapat mengakses data ini dari [halaman entitas](entities.md) atau dengan [akses API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="6aec7-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="6aec7-181">Akses API</span><span class="sxs-lookup"><span data-stu-id="6aec7-181">API Access</span></span>

<span data-ttu-id="6aec7-182">Agar kueri OData tertentu dapat memperoleh data dari entitas model kustom, gunakan format berikut:</span><span class="sxs-lookup"><span data-stu-id="6aec7-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="6aec7-183">Ganti `<your instance id>` dengan ID lingkungan Customer Insights, yang dapat Anda temukan di bilah alamat browser saat mengakses Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6aec7-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="6aec7-184">Ganti `<custom model output entity>` dengan nama entitas yang Anda berikan selama langkah Parameter Output Model dari konfigurasi model kustom.</span><span class="sxs-lookup"><span data-stu-id="6aec7-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="6aec7-185">Ganti `<guid value>` dengan ID Pelanggan pelanggan yang akan anda akses rekamannya.</span><span class="sxs-lookup"><span data-stu-id="6aec7-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="6aec7-186">Anda biasanya dapat menemukan ID ini di [halaman profil pelanggan](customer-profiles.md) pada bidang CustomerID.</span><span class="sxs-lookup"><span data-stu-id="6aec7-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="6aec7-187">Pertanyaan Umum</span><span class="sxs-lookup"><span data-stu-id="6aec7-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="6aec7-188">Mengapa saya tidak dapat melihat alur kerja saat menyiapkan alur kerja model kustom?</span><span class="sxs-lookup"><span data-stu-id="6aec7-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="6aec7-189">Masalah ini sering disebabkan oleh masalah konfigurasi dalam alur.</span><span class="sxs-lookup"><span data-stu-id="6aec7-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="6aec7-190">Pastikan [parameter input dikonfigurasi](azure-machine-learning-experiments.md#dataset-configuration), dan [parameter datastore dan jalur output](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) juga dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="6aec7-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="6aec7-191">Apa artinya kesalahan "Tidak Dapat menyimpan alur kerja cerdas"?</span><span class="sxs-lookup"><span data-stu-id="6aec7-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="6aec7-192">Pengguna biasanya melihat pesan kesalahan ini jika mereka tidak memiliki hak istimewa Pemilik atau Administrator Akses Pengguna di ruang kerja.</span><span class="sxs-lookup"><span data-stu-id="6aec7-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="6aec7-193">Pengguna memerlukan tingkat izin yang lebih tinggi agar Customer Insights dapat memproses alur kerja sebagai layanan dan bukan menggunakan kredensial pengguna untuk alur kerja berikutnya.</span><span class="sxs-lookup"><span data-stu-id="6aec7-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
