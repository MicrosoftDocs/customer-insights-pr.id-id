---
title: Model Pembelajaran Mesin kustom | Microsoft Docs
description: Bekerja dengan model kustom dari Azure Machine Learning di Dynamics 365 Customer Insights
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668907"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="826e8-103">Model Pembelajaran Mesin kustom</span><span class="sxs-lookup"><span data-stu-id="826e8-103">Custom machine learning models</span></span>

<span data-ttu-id="826e8-104">**Kecerdasan** > **Model Kustom** memungkinkan Anda mengelola alur kerja berdasarkan model Pembelajaran Mesin Azure.</span><span class="sxs-lookup"><span data-stu-id="826e8-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="826e8-105">Alur kerja membantu Anda memilih data yang ingin Anda hasilkan wawasannya dan memetakan hasil ke data pelanggan terpadu Anda.</span><span class="sxs-lookup"><span data-stu-id="826e8-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="826e8-106">Untuk informasi lebih lanjut tentang cara membuat model kustom ML, lihat [menggunakan model berbasis pembelajaran mesin Azure](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="826e8-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="826e8-107">AI yang bertanggung jawab</span><span class="sxs-lookup"><span data-stu-id="826e8-107">Responsible AI</span></span>

<span data-ttu-id="826e8-108">Prediksi menawarkan kemampuan untuk membuat pengalaman pelanggan yang lebih baik, meningkatkan kemampuan Bisnis, dan aliran pendapatan.</span><span class="sxs-lookup"><span data-stu-id="826e8-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="826e8-109">Kami sangat menyarankan agar anda menyeimbangkan nilai prediksi anda terhadap dampak dan bias yang dapat ditimbulkan dengan cara yang etis.</span><span class="sxs-lookup"><span data-stu-id="826e8-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="826e8-110">Pelajari lebih lanjut tentang cara Microsoft [menangani AI yang bertanggung jawab](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="826e8-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="826e8-111">Anda juga dapat mempelajari [teknik dan proses untuk Pembelajaran Mesin bertanggung jawab](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) yang spesifik untuk Pembelajaran Mesin Azure.</span><span class="sxs-lookup"><span data-stu-id="826e8-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="826e8-112">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="826e8-112">Prerequisites</span></span>

- <span data-ttu-id="826e8-113">Saat ini, fitur ini mendukung layanan web yang dipublikasikan melalui jalur [Studio Pembelajaran Mesin (klasik)](https://studio.azureml.net) dan [Alur kerja Azure Pembelajaran Mesin](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="826e8-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="826e8-114">Anda memerlukan akun Azure data Lake Gen2 Storage yang terkait dengan instans Azure studio Anda untuk menggunakan fitur ini.</span><span class="sxs-lookup"><span data-stu-id="826e8-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="826e8-115">Untuk informasi lebih lanjut, Lihat [membuat akun penyimpanan Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="826e8-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="826e8-116">Tambahkan alur kerja baru</span><span class="sxs-lookup"><span data-stu-id="826e8-116">Add a new workflow</span></span>

1. <span data-ttu-id="826e8-117">Buka **kecerdasan** > **model kustom** dan pilih **alur kerja baru**.</span><span class="sxs-lookup"><span data-stu-id="826e8-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="826e8-118">Beri model kustom Anda nama yang dikenali di bidang **nama**.</span><span class="sxs-lookup"><span data-stu-id="826e8-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="826e8-119">![Tangkapan layar panel alur kerja baru](media/new-workflowv2.png "Tangkapan layar panel alur kerja baru")</span><span class="sxs-lookup"><span data-stu-id="826e8-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="826e8-120">Pilih organisasi yang berisi layanan web dalam **penyewa yang berisi layanan web Anda**.</span><span class="sxs-lookup"><span data-stu-id="826e8-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="826e8-121">Jika langganan Pembelajaran Mesin Azure Anda berada di penyewa berbeda dari pada Customer Insights, pilih **masuk** dengan kredensial anda untuk organisasi yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="826e8-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="826e8-122">Pilih **ruang kerja** yang terkait dengan layanan web Anda.</span><span class="sxs-lookup"><span data-stu-id="826e8-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="826e8-123">Ada dua bagian terdaftar, satu untuk Pembelajaran Mesin azure v1 (Studio Pembelajaran Mesin (klasik)) dan Pembelajaran Mesin azure v2 (Pembelajaran Mesin azure).</span><span class="sxs-lookup"><span data-stu-id="826e8-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="826e8-124">Jika anda tidak yakin ruang kerja mana yang tepat untuk layanan web Studio Pembelajaran Mesin (klasik), pilih **Mana pun**.</span><span class="sxs-lookup"><span data-stu-id="826e8-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="826e8-125">Pilih layanan web Studio Pembelajaran Mesin (klasik) atau alur kerja Pembelajaran Mesin Azure di menu tarik turun **layanan web yang berisi model anda**.</span><span class="sxs-lookup"><span data-stu-id="826e8-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="826e8-126">Kemudian pilih **Berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="826e8-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="826e8-127">Pelajari lebih lanjut tentang [mempublikasi layanan web di Studio Pembelajaran Mesin (klasik)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="826e8-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="826e8-128">Pelajari lebih lanjut tentang cara [mempublikasi alur kerja di Pembelajaran Mesin Azure menggunakan desainer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) atau [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="826e8-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="826e8-129">Alur anda harus dipublikasikan dalam [titik akhir alur](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="826e8-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="826e8-130">Untuk setiap **input Layanan web**, pilih **entitas** yang cocok dari Customer Insights dari wawasan audiens dan pilih **Berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="826e8-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="826e8-131">![Mengonfigurasikan alur kerja](media/intelligence-screen2-updated.png "Mengonfigurasikan alur kerja")</span><span class="sxs-lookup"><span data-stu-id="826e8-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="826e8-132">Pada langkah **parameter output model**, atur properti berikut:</span><span class="sxs-lookup"><span data-stu-id="826e8-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="826e8-133">Studio Pembelajaran Mesin (Klasik)</span><span class="sxs-lookup"><span data-stu-id="826e8-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="826e8-134">Masukkan **nama entitas** yang Anda ingin hasil output layanan webnya mengalir ke dalamnya.</span><span class="sxs-lookup"><span data-stu-id="826e8-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="826e8-135">Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="826e8-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="826e8-136">Masukkan **nama entitas** yang Anda ingin hasil output alur kerjanya mengalir ke dalamnya.</span><span class="sxs-lookup"><span data-stu-id="826e8-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="826e8-137">Pilih **nama parameter penyimpanan data Output** alur kerja batch anda dari dropdown.</span><span class="sxs-lookup"><span data-stu-id="826e8-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="826e8-138">Pilih **nama parameter jalur Output** alur kerja batch anda dari dropdown.</span><span class="sxs-lookup"><span data-stu-id="826e8-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="826e8-139">![Panel parameter output model](media/intelligence-screen3-outputparameters.png "Panel parameter output model")</span><span class="sxs-lookup"><span data-stu-id="826e8-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="826e8-140">Pilih atribut yang cocok dari daftar drop- down **id pelanggan dalam hasil** yang mengidentifikasi pelanggan dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="826e8-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="826e8-141">![Kaitkan hasil ke panel data pelanggan](media/intelligence-screen4-relatetocustomer.png "Kaitkan hasil ke panel data pelanggan")</span><span class="sxs-lookup"><span data-stu-id="826e8-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="826e8-142">Anda akan melihat layar **alur kerja yang tersimpan** dengan rincian tentang alur kerja.</span><span class="sxs-lookup"><span data-stu-id="826e8-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="826e8-143">Jika Anda mengonfigurasikan alur kerja untuk alur Pembelajaran Mesin Azure, wawasan audiens akan dilampirkan ke ruang kerja yang berisi alur.</span><span class="sxs-lookup"><span data-stu-id="826e8-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="826e8-144">Wawasan audiens akan mendapatkan peran **kontributor** di ruang kerja Azure.</span><span class="sxs-lookup"><span data-stu-id="826e8-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="826e8-145">Pilih **Selesai**.</span><span class="sxs-lookup"><span data-stu-id="826e8-145">Select **Done**.</span></span>

1. <span data-ttu-id="826e8-146">Anda sekarang dapat menjalankan alur kerja dari halaman **model kustom**.</span><span class="sxs-lookup"><span data-stu-id="826e8-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="826e8-147">Edit alur kerja</span><span class="sxs-lookup"><span data-stu-id="826e8-147">Edit a workflow</span></span>

1. <span data-ttu-id="826e8-148">Pada halaman **Model Kustom**, pilih elipsis vertikal di kolom **tindakan** di sebelah alur kerja yang telah Anda buat sebelumnya dan pilih **Edit**.</span><span class="sxs-lookup"><span data-stu-id="826e8-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="826e8-149">Anda dapat memperbarui nama yang dikenali alur kerja di bidang **nama tampilan**, namun Anda tidak dapat mengubah layanan Web atau alur yang dikonfigurasikan.</span><span class="sxs-lookup"><span data-stu-id="826e8-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="826e8-150">Pilih **Selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="826e8-150">Select **Next**.</span></span>

1. <span data-ttu-id="826e8-151">Untuk setiap **input Layanan web**, Anda dapat memperbarui **entitas** yang cocok dari wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="826e8-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="826e8-152">Kemudian pilih **Berikutnya**.</span><span class="sxs-lookup"><span data-stu-id="826e8-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="826e8-153">Pada langkah **parameter output model**, atur properti berikut:</span><span class="sxs-lookup"><span data-stu-id="826e8-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="826e8-154">Studio Pembelajaran Mesin (Klasik)</span><span class="sxs-lookup"><span data-stu-id="826e8-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="826e8-155">Masukkan **nama entitas** yang Anda ingin hasil output layanan webnya mengalir ke dalamnya.</span><span class="sxs-lookup"><span data-stu-id="826e8-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="826e8-156">Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="826e8-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="826e8-157">Masukkan **nama entitas** yang Anda ingin hasil output alur kerjanya mengalir ke dalamnya.</span><span class="sxs-lookup"><span data-stu-id="826e8-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="826e8-158">Pilih **nama parameter penyimpanan data Output** untuk alur pengujian anda.</span><span class="sxs-lookup"><span data-stu-id="826e8-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="826e8-159">Pilih **nama parameter jalur Output** untuk alur pengujian anda.</span><span class="sxs-lookup"><span data-stu-id="826e8-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="826e8-160">Pilih atribut yang cocok dari daftar drop- down **id pelanggan dalam hasil** yang mengidentifikasi pelanggan dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="826e8-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="826e8-161">Anda harus memilih atribut dari output inferensi dengan nilai yang serupa dengan kolom ID pelanggan dari entitas pelanggan.</span><span class="sxs-lookup"><span data-stu-id="826e8-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="826e8-162">Jika tidak memiliki kolom di himpunan data, pilih atribut yang secara unik mengidentifikasi baris.</span><span class="sxs-lookup"><span data-stu-id="826e8-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="826e8-163">Menjalankan alur kerja</span><span class="sxs-lookup"><span data-stu-id="826e8-163">Run a workflow</span></span>

1. <span data-ttu-id="826e8-164">Pada halaman **Model Kustom**, pilih elipsis vertikal di kolom **tindakan** di sebelah alur kerja yang telah Anda buat sebelumnya.</span><span class="sxs-lookup"><span data-stu-id="826e8-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="826e8-165">Pilih **Jalankan**.</span><span class="sxs-lookup"><span data-stu-id="826e8-165">Select **Run**.</span></span>

<span data-ttu-id="826e8-166">Alur kerja Anda juga berjalan secara otomatis dengan setiap penyegaran terjadwal.</span><span class="sxs-lookup"><span data-stu-id="826e8-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="826e8-167">Pelajari lebih lanjut [cara mengkonfigurasi penyegaran terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="826e8-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="826e8-168">Hapus alur kerja</span><span class="sxs-lookup"><span data-stu-id="826e8-168">Delete a workflow</span></span>

1. <span data-ttu-id="826e8-169">Pada halaman **Model Kustom**, pilih elipsis vertikal di kolom **tindakan** di sebelah alur kerja yang telah Anda buat sebelumnya.</span><span class="sxs-lookup"><span data-stu-id="826e8-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="826e8-170">Klik **Hapus**, dan konfirmasi penghapusan Anda.</span><span class="sxs-lookup"><span data-stu-id="826e8-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="826e8-171">Alur kerja Anda akan dihapus.</span><span class="sxs-lookup"><span data-stu-id="826e8-171">Your workflow will be deleted.</span></span> <span data-ttu-id="826e8-172">[Entitas](entities.md) yang dibuat saat Anda membuat alur kerja tetap ada, dan dapat dilihat dari halaman **entitas**.</span><span class="sxs-lookup"><span data-stu-id="826e8-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
