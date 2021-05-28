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
ms.openlocfilehash: 87fb517e9f0b380f9721f77470dceb3bcb7e5616
ms.sourcegitcommit: 55c00ea61c78db7b3b54894c01afb3246dff31c8
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/22/2021
ms.locfileid: "5700672"
---
# <a name="custom-machine-learning-models"></a>Model Pembelajaran Mesin kustom

**Kecerdasan** > **Model Kustom** memungkinkan Anda mengelola alur kerja berdasarkan model Pembelajaran Mesin Azure. Alur kerja membantu Anda memilih data yang ingin Anda hasilkan wawasannya dan memetakan hasil ke data pelanggan terpadu Anda. Untuk informasi lebih lanjut tentang cara membuat model kustom ML, lihat [menggunakan model berbasis pembelajaran mesin Azure](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>AI yang bertanggung jawab

Prediksi menawarkan kemampuan untuk membuat pengalaman pelanggan yang lebih baik, meningkatkan kemampuan Bisnis, dan aliran pendapatan. Kami sangat menyarankan agar anda menyeimbangkan nilai prediksi anda terhadap dampak dan bias yang dapat ditimbulkan dengan cara yang etis. Pelajari lebih lanjut tentang cara Microsoft [menangani AI yang bertanggung jawab](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Anda juga dapat mempelajari [teknik dan proses untuk Pembelajaran Mesin bertanggung jawab](/azure/machine-learning/concept-responsible-ml) yang spesifik untuk Pembelajaran Mesin Azure.

## <a name="prerequisites"></a>Prasyarat

- Saat ini, fitur ini mendukung layanan web yang dipublikasikan melalui jalur [Studio Pembelajaran Mesin (klasik)](https://studio.azureml.net) dan [Alur kerja Azure Pembelajaran Mesin](/azure/machine-learning/concept-ml-pipelines).

- Anda memerlukan akun Azure data Lake Gen2 Storage yang terkait dengan instans Azure studio Anda untuk menggunakan fitur ini. Untuk informasi lebih lanjut, Lihat [membuat akun penyimpanan Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Untuk ruang kerja Pembelajaran Mesin Azure, Anda memerlukan izin Pemilik atau Administrator Akses Pengguna untuk ruang kerja Pembelajaran Mesin Azure.

   > [!NOTE]
   > Data akan ditransfer antara instans Customer Insights dan alur atau layanan web Azure terpilih dalam alur kerja. Jika Anda mentransfer data ke layanan Azure, pastikan layanan dikonfigurasi untuk memproses data dengan cara dan lokasi yang diperlukan agar sesuai dengan persyaratan hukum atau peraturan untuk data tersebut di organisasi Anda.

## <a name="add-a-new-workflow"></a>Tambahkan alur kerja baru

1. Buka **kecerdasan** > **model kustom** dan pilih **alur kerja baru**.

1. Beri model kustom Anda nama yang dikenali di bidang **nama**.

   > [!div class="mx-imgBorder"]
   > ![Tangkapan layar panel alur kerja baru](media/new-workflowv2.png "Tangkapan layar panel alur kerja baru")

1. Pilih organisasi yang berisi layanan web dalam **penyewa yang berisi layanan web Anda**.

1. Jika langganan Pembelajaran Mesin Azure Anda berada di penyewa berbeda dari pada Customer Insights, pilih **masuk** dengan kredensial anda untuk organisasi yang dipilih.

1. Pilih **ruang kerja** yang terkait dengan layanan web Anda. Ada dua bagian terdaftar, satu untuk Pembelajaran Mesin azure v1 (Studio Pembelajaran Mesin (klasik)) dan Pembelajaran Mesin azure v2 (Pembelajaran Mesin azure). Jika anda tidak yakin ruang kerja mana yang tepat untuk layanan web Studio Pembelajaran Mesin (klasik), pilih **Mana pun**.

1. Pilih layanan web Studio Pembelajaran Mesin (klasik) atau alur kerja Pembelajaran Mesin Azure di menu tarik turun **layanan web yang berisi model anda**. Kemudian pilih **Berikutnya**.
   - Pelajari lebih lanjut tentang [mempublikasi layanan web di Studio Pembelajaran Mesin (klasik)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Pelajari lebih lanjut tentang cara [mempublikasi alur kerja di Pembelajaran Mesin Azure menggunakan desainer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) atau [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Alur anda harus dipublikasikan dalam [titik akhir alur](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Untuk setiap **input Layanan web**, pilih **entitas** yang cocok dari Customer Insights dari wawasan audiens dan pilih **Berikutnya**.
   > [!NOTE]
   > Alur kerja model kustom akan menerapkan heuristik untuk memetakan bidang input layanan web ke atribut entitas berdasarkan nama dan jenis data bidang. Anda akan melihat kesalahan jika bidang layanan web tidak dapat dipetakan ke entitas.

   > [!div class="mx-imgBorder"]
   > ![Mengonfigurasikan alur kerja](media/intelligence-screen2-updated.png "Mengonfigurasikan alur kerja")

1. Pada langkah **parameter output model**, atur properti berikut:
   - Studio Pembelajaran Mesin (Klasik)
      1. Masukkan **nama entitas** yang Anda ingin hasil output layanan webnya mengalir ke dalamnya.
   - Pembelajaran Mesin Azure
      1. Masukkan **nama entitas** yang Anda ingin hasil output alur kerjanya mengalir ke dalamnya.
      1. Pilih **nama parameter penyimpanan data Output** alur kerja batch anda dari dropdown.
      1. Pilih **nama parameter jalur Output** alur kerja batch anda dari dropdown.

      > [!div class="mx-imgBorder"]
      > ![Panel parameter output model](media/intelligence-screen3-outputparameters.png "Panel parameter output model")

1. Pilih atribut yang cocok dari daftar drop- down **id pelanggan dalam hasil** yang mengidentifikasi pelanggan dan pilih **Simpan**.

   > [!div class="mx-imgBorder"]
   > ![Kaitkan hasil ke panel data pelanggan](media/intelligence-screen4-relatetocustomer.png "Kaitkan hasil ke panel data pelanggan")

1. Anda akan melihat layar **alur kerja yang tersimpan** dengan rincian tentang alur kerja.    
   Jika Anda mengonfigurasikan alur kerja untuk alur Pembelajaran Mesin Azure, wawasan audiens akan dilampirkan ke ruang kerja yang berisi alur. Wawasan audiens akan mendapatkan peran **kontributor** di ruang kerja Azure.

1. Pilih **Selesai**.

1. Anda sekarang dapat menjalankan alur kerja dari halaman **model kustom**.

## <a name="edit-a-workflow"></a>Edit alur kerja

1. Pada halaman **Model Kustom**, pilih elipsis vertikal di kolom **tindakan** di sebelah alur kerja yang telah Anda buat sebelumnya dan pilih **Edit**.

1. Anda dapat memperbarui nama yang dikenali alur kerja di bidang **nama tampilan**, namun Anda tidak dapat mengubah layanan Web atau alur yang dikonfigurasikan. Pilih **Selanjutnya**.

1. Untuk setiap **input Layanan web**, Anda dapat memperbarui **entitas** yang cocok dari wawasan audiens. Kemudian pilih **Berikutnya**.

1. Pada langkah **parameter output model**, atur properti berikut:
   - Studio Pembelajaran Mesin (Klasik)
      1. Masukkan **nama entitas** yang Anda ingin hasil output layanan webnya mengalir ke dalamnya.
   - Pembelajaran Mesin Azure
      1. Masukkan **nama entitas** yang Anda ingin hasil output alur kerjanya mengalir ke dalamnya.
      1. Pilih **nama parameter penyimpanan data Output** untuk alur pengujian anda.
      1. Pilih **nama parameter jalur Output** untuk alur pengujian anda.

1. Pilih atribut yang cocok dari daftar drop- down **id pelanggan dalam hasil** yang mengidentifikasi pelanggan dan pilih **Simpan**.
   Pilih atribut dari output inferensi dengan nilai yang serupa dengan kolom ID pelanggan dari entitas pelanggan. Jika tidak memiliki kolom di himpunan data, pilih atribut yang secara unik mengidentifikasi baris.

## <a name="run-a-workflow"></a>Menjalankan alur kerja

1. Pada halaman **Model Kustom**, pilih elipsis vertikal di kolom **tindakan** di sebelah alur kerja yang telah Anda buat sebelumnya.

1. Pilih **Jalankan**.

Alur kerja Anda juga berjalan secara otomatis dengan setiap penyegaran terjadwal. Pelajari lebih lanjut [cara mengkonfigurasi penyegaran terjadwal](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Hapus alur kerja

1. Pada halaman **Model Kustom**, pilih elipsis vertikal di kolom **tindakan** di sebelah alur kerja yang telah Anda buat sebelumnya.

1. Klik **Hapus**, dan konfirmasi penghapusan Anda.

Alur kerja Anda akan dihapus. [Entitas](entities.md) yang dibuat saat Anda membuat alur kerja tetap ada, dan dapat dilihat dari halaman **entitas**.

## <a name="results"></a>Hasil

Hasil dari alur kerja disimpan dalam entitas yang dikonfigurasi selama fase Parameter Output Model. Anda dapat mengakses data ini dari [halaman entitas](entities.md) atau dengan [akses API](apis.md).

### <a name="api-access"></a>Akses API

Agar kueri OData tertentu dapat memperoleh data dari entitas model kustom, gunakan format berikut:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Ganti `<your instance id>` dengan ID lingkungan Customer Insights, yang dapat Anda temukan di bilah alamat browser saat mengakses Customer Insights.

1. Ganti `<custom model output entity>` dengan nama entitas yang Anda berikan selama langkah Parameter Output Model dari konfigurasi model kustom.

1. Ganti `<guid value>` dengan ID Pelanggan pelanggan yang akan anda akses rekamannya. Anda biasanya dapat menemukan ID ini di [halaman profil pelanggan](customer-profiles.md) pada bidang CustomerID.

## <a name="frequently-asked-questions"></a>Pertanyaan Umum

- Mengapa saya tidak dapat melihat alur kerja saat menyiapkan alur kerja model kustom?    
  Masalah ini sering disebabkan oleh masalah konfigurasi dalam alur. Pastikan [parameter input dikonfigurasi](azure-machine-learning-experiments.md#dataset-configuration), dan [parameter datastore dan jalur output](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) juga dikonfigurasi.

- Apa artinya kesalahan "Tidak Dapat menyimpan alur kerja cerdas"?    
  Pengguna biasanya melihat pesan kesalahan ini jika mereka tidak memiliki hak istimewa Pemilik atau Administrator Akses Pengguna di ruang kerja. Pengguna memerlukan tingkat izin yang lebih tinggi agar Customer Insights dapat memproses alur kerja sebagai layanan dan bukan menggunakan kredensial pengguna untuk alur kerja berikutnya.

[!INCLUDE[footer-include](../includes/footer-banner.md)]