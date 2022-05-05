---
title: Eksperimen Pembelajaran Mesin Azure
description: Gunakan model berbasis pembelajaran mesin Azure di Dynamics 365 Customer Insights.
ms.date: 12/02/2021
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cefd037a021b669e827f0593d63b938d452963f7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642609"
---
# <a name="use-azure-machine-learning-based-models"></a>Gunakan model berbasis pembelajaran mesin Azure

Data terpadu di Dynamics 365 Customer Insights adalah sumber untuk membangun model Pembelajaran Mesin yang dapat menghasilkan wawasan bisnis tambahan. Customer Insights berintegrasi dengan Pembelajaran Mesin Azure untuk menggunakan model kustom Anda sendiri.

## <a name="prerequisites"></a>Prasyarat

- Akses ke Customer Insights
- Langganan Azure Enterprise aktif
- [Profil pelanggan terpadu](data-unification.md)
- [Ekspor entitas ke penyimpanan Azure Blob](export-azure-blob-storage.md) dikonfigurasi

## <a name="set-up-azure-machine-learning-workspace"></a>Atur ruang kerja Pembelajaran Mesin Azure

1. Lihat [membuat ruang kerja Pembelajaran Mesin Azure](/azure/machine-learning/concept-workspace#-create-a-workspace) untuk pilihan yang berbeda untuk membuat ruang kerja. Untuk performa terbaik, buat ruang kerja di kawasan Azure yang secara geografis paling dekat dengan lingkungan Customer Insights Anda.

1. Akses ruang kerja anda melalui [Studio Pembelajaran Mesin Azure](https://ml.azure.com/). Ada beberapa [cara untuk berinteraksi](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) dengan ruang kerja Anda.

## <a name="work-with-azure-machine-learning-designer"></a>Bekerja dengan desainer Pembelajaran Mesin Azure

Azure Pembelajaran Mesin designer menyediakan kanvas visual tempat Anda dapat menyeret dan melepas himpunan data dan modul. Alur kerja batch yang dibuat dari desainer dapat diintegrasikan ke dalam Customer Insights jika dikonfigurasi dengan sesuai. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Bekerja dengan SDK Pembelajaran Mesin Azure

Ilmuwan Data dan pengembang AI menggunakan [SDK Pembelajaran Mesin Azure](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) untuk membuat alur kerja Pembelajaran Mesin. Saat ini, model yang dilatih menggunakan SDK tidak dapat diintegrasikan langsung dengan Customer Insights. Alur inferensi batch yang mengkonsumsi model diperlukan untuk integrasi dengan Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Persyaratan alur jalur batch untuk diintegrasikan dengan Customer Insights

### <a name="dataset-configuration"></a>Konfigurasi himpunan data

Anda harus membuat dataset untuk menggunakan data entitas dari Customer Insights ke alur kerja inferensi batch Anda. Kumpulan data ini harus didaftarkan di ruang kerja. Saat ini, kami hanya mendukung [himpunan data tabel](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) dalam format .CSV. Kumpulan data yang terkait dengan data entitas harus diberi parameter sebagai parameter alur kerja.
   
* Parameter himpunan data dalam desainer
   
     Di desainer, buka **pilih kolom dalam himpunan data** dan pilih **Atur sebagai parameter alur kerja** saat Anda memberikan nama untuk parameter.

     > [!div class="mx-imgBorder"]
     > ![Parameterisasi himpunan data dalam desainer.](media/intelligence-designer-dataset-parameters.png "Parameterisasi himpunan data dalam desainer")
   
* Parameter himpunan data dalam SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Alur kerja inferensi Batch
  
* Pada desainer, alur pelatihan dapat digunakan untuk membuat atau memperbarui alur inferensi. Saat ini, hanya alur kerja inferensi batch yang didukung.

* Menggunakan SDK, anda dapat mempublikasikan alur ke titik akhir. Saat ini, Customer Insights terintegrasi dengan alur default di titik akhir alur batch di ruang kerja Pembelajaran Mesin.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Impor data alur jalur ke Customer Insights

* Desainer menyediakan [ekspor modul data](/azure/machine-learning/algorithm-module-reference/export-data) yang memungkinkan output alur untuk diekspor ke Azure Storage. Saat ini, modul harus menggunakan penyimpanan jenis **Penyimpanan Blob Azure** dan memparameterisasi **himpunan data** dan **jalur** relatif. Customer Insights mengesampingkan parameter ini selama eksekusi alur kerja dengan himpunandata dan jalur yang dapat diakses oleh produk.
   > [!div class="mx-imgBorder"]
   > ![Ekspor Konfigurasi Modul Data.](media/intelligence-designer-importdata.png "Ekspor Konfigurasi Modul Data")
   
* Saat menulis output inferensi menggunakan kode, Anda dapat mengunggah output ke jalur di dalam *himpunan data terdaftar* di ruang kerja. Jika jalur dan himpunan data yang parameterized di alur kerja, Customer Insights akan dapat membaca, dan mengimpor inferensi output. Saat ini, satu output tabular dalam format CSV didukung. Jalur harus mencakup direktori dan nama file.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]