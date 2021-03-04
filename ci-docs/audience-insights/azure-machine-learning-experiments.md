---
title: Eksperimen Pembelajaran Mesin Azure
description: Gunakan model berbasis pembelajaran mesin Azure di Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267910"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="f6b2d-103">Gunakan model berbasis pembelajaran mesin Azure</span><span class="sxs-lookup"><span data-stu-id="f6b2d-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="f6b2d-104">Data terpadu di Dynamics 365 Customer Insights adalah sumber untuk membangun model Pembelajaran Mesin yang dapat menghasilkan wawasan bisnis tambahan.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="f6b2d-105">Customer Insights berintegrasi dengan Studio Pembelajaran Mesin (klasik) dan Pembelajaran Mesin Azure untuk menggunakan model kustom Anda sendiri.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="f6b2d-106">Lihat [eksperimen studio Pembelajaran Mesin (klasik)](machine-learning-studio-experiments.md) untuk contoh eksperimen yang dibuat di studio Pembelajaran Mesin (klasik).</span><span class="sxs-lookup"><span data-stu-id="f6b2d-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f6b2d-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="f6b2d-107">Prerequisites</span></span>

- <span data-ttu-id="f6b2d-108">Akses ke Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f6b2d-108">Access to Customer Insights</span></span>
- <span data-ttu-id="f6b2d-109">Langganan Azure Enterprise aktif</span><span class="sxs-lookup"><span data-stu-id="f6b2d-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="f6b2d-110">Profil pelanggan terpadu</span><span class="sxs-lookup"><span data-stu-id="f6b2d-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="f6b2d-111">[Ekspor entitas ke penyimpanan Azure Blob](export-azure-blob-storage.md) dikonfigurasi</span><span class="sxs-lookup"><span data-stu-id="f6b2d-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="f6b2d-112">Atur ruang kerja Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="f6b2d-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="f6b2d-113">Lihat [membuat ruang kerja Pembelajaran Mesin Azure](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) untuk pilihan yang berbeda untuk membuat ruang kerja.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="f6b2d-114">Untuk performa terbaik, buat ruang kerja di kawasan Azure yang secara geografis paling dekat dengan lingkungan Customer Insights Anda.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="f6b2d-115">Akses ruang kerja anda melalui [Studio Pembelajaran Mesin Azure](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="f6b2d-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="f6b2d-116">Ada beberapa [cara untuk berinteraksi](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) dengan ruang kerja Anda.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="f6b2d-117">Bekerja dengan desainer Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="f6b2d-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="f6b2d-118">Desainer Pembelajaran Mesin Azure menyediakan kanvas visual untuk menyeret dan menjatuhkan kumpulan data dan modul, mirip dengan Studio Pembelajaran Mesin (klasik).</span><span class="sxs-lookup"><span data-stu-id="f6b2d-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="f6b2d-119">Alur kerja batch yang dibuat dari desainer dapat diintegrasikan ke dalam Customer Insights jika dikonfigurasi dengan sesuai.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="f6b2d-120">Bekerja dengan SDK Pembelajaran Mesin Azure</span><span class="sxs-lookup"><span data-stu-id="f6b2d-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="f6b2d-121">Ilmuwan Data dan pengembang AI menggunakan [SDK Pembelajaran Mesin Azure](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) untuk membuat alur kerja Pembelajaran Mesin.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="f6b2d-122">Saat ini, model yang dilatih menggunakan SDK tidak dapat diintegrasikan langsung dengan Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="f6b2d-123">Alur inferensi batch yang mengkonsumsi model diperlukan untuk integrasi dengan Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="f6b2d-124">Persyaratan alur jalur batch untuk diintegrasikan dengan Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f6b2d-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="f6b2d-125">Konfigurasi himpunan data</span><span class="sxs-lookup"><span data-stu-id="f6b2d-125">Dataset Configuration</span></span>

<span data-ttu-id="f6b2d-126">Anda harus membuat dataset untuk menggunakan data entitas dari Customer Insights ke alur kerja inferensi batch Anda.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="f6b2d-127">Kumpulan data ini harus didaftarkan di ruang kerja.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="f6b2d-128">Saat ini, kami hanya mendukung [himpunan data tabel](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) dalam format .CSV.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="f6b2d-129">Kumpulan data yang terkait dengan data entitas harus diberi parameter sebagai parameter alur kerja.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="f6b2d-130">Parameter himpunan data dalam desainer</span><span class="sxs-lookup"><span data-stu-id="f6b2d-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="f6b2d-131">Di desainer, buka **pilih kolom dalam himpunan data** dan pilih **Atur sebagai parameter alur kerja** saat Anda memberikan nama untuk parameter.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="f6b2d-132">![Parameterisasi himpunan data dalam desainer](media/intelligence-designer-dataset-parameters.png "Parameterisasi himpunan data dalam desainer")</span><span class="sxs-lookup"><span data-stu-id="f6b2d-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="f6b2d-133">Parameter himpunan data dalam SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="f6b2d-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="f6b2d-134">Alur kerja inferensi Batch</span><span class="sxs-lookup"><span data-stu-id="f6b2d-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="f6b2d-135">Pada desainer, alur pelatihan dapat digunakan untuk membuat atau memperbarui alur inferensi.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="f6b2d-136">Saat ini, hanya alur kerja inferensi batch yang didukung.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="f6b2d-137">Menggunakan SDK, anda dapat mempublikasikan alur ke titik akhir.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="f6b2d-138">Saat ini, Customer Insights terintegrasi dengan alur default di titik akhir alur batch di ruang kerja Pembelajaran Mesin.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="f6b2d-139">Impor data alur jalur ke Customer Insights</span><span class="sxs-lookup"><span data-stu-id="f6b2d-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="f6b2d-140">Desainer menyediakan [ekspor modul data](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) yang memungkinkan output alur untuk diekspor ke Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="f6b2d-141">Saat ini, modul harus menggunakan penyimpanan jenis **Penyimpanan Blob Azure** dan memparameterisasi **himpunan data** dan **jalur** relatif.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="f6b2d-142">Customer Insights mengesampingkan parameter ini selama eksekusi alur kerja dengan himpunandata dan jalur yang dapat diakses oleh produk.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f6b2d-143">![Ekspor Konfigurasi Modul Data](media/intelligence-designer-importdata.png "Ekspor Konfigurasi Modul Data")</span><span class="sxs-lookup"><span data-stu-id="f6b2d-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="f6b2d-144">Saat menulis output inferensi menggunakan kode, Anda dapat mengunggah output ke jalur di dalam *himpunan data terdaftar* di ruang kerja.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="f6b2d-145">Jika jalur dan himpunan data yang parameterized di alur kerja, Customer Insights akan dapat membaca, dan mengimpor inferensi output.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="f6b2d-146">Saat ini, satu output tabular dalam format CSV didukung.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="f6b2d-147">Jalur harus mencakup direktori dan nama file.</span><span class="sxs-lookup"><span data-stu-id="f6b2d-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]