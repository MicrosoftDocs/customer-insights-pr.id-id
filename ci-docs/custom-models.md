---
title: Model Pembelajaran Mesin kustom | Microsoft Docs
description: Bekerja dengan model kustom dari Azure Machine Learning di Dynamics 365 Customer Insights
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609750"
---
# <a name="custom-machine-learning-models"></a>Model Pembelajaran Mesin kustom

> [!NOTE]
> Dukungan untuk Pembelajaran Mesin Studio (klasik) akan berakhir pada 31 Agustus 2024. Sebaiknya Anda beralih ke [Azure Pembelajaran Mesin](/azure/machine-learning/overview-what-is-azure-machine-learning) pada tanggal tersebut.
>
> Mulai 1 Desember 2021, Anda tidak akan dapat membuat sumber daya Pembelajaran Mesin Studio (klasik) baru. Hingga 31 Agustus 2024, Anda dapat terus menggunakan sumber daya Pembelajaran Mesin Studio (klasik) yang ada. Untuk informasi selengkapnya, lihat [Bermigrasi ke Azure Pembelajaran Mesin](/azure/machine-learning/migrate-overview).

Model kustom memungkinkan Anda mengelola alur kerja berdasarkan model Azure Pembelajaran Mesin. Alur kerja membantu Anda memilih data yang ingin Anda hasilkan wawasannya dan memetakan hasil ke data pelanggan terpadu Anda. Untuk informasi lebih lanjut tentang cara membuat model kustom ML, lihat [menggunakan model berbasis pembelajaran mesin Azure](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Prasyarat

- Layanan web yang diterbitkan melalui [Azure Pembelajaran Mesin alur batch](/azure/machine-learning/concept-ml-pipelines).
- Alur harus diterbitkan di bawah [titik akhir alur](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Akun [penyimpanan](/azure/storage/blobs/data-lake-storage-quickstart-create-account) Azure Data Lake Gen2 yang terkait dengan instans Azure Studio Anda.
- Untuk ruang kerja Azure Pembelajaran Mesin dengan alur, izin Pemilik, atau Administrator Akses Pengguna ke Ruang Kerja Azure Pembelajaran Mesin.

  > [!NOTE]
  > Data akan ditransfer antara instans Customer Insights dan alur atau layanan web Azure terpilih dalam alur kerja. Jika Anda mentransfer data ke layanan Azure, pastikan layanan dikonfigurasi untuk memproses data dengan cara dan lokasi yang diperlukan agar sesuai dengan persyaratan hukum atau peraturan untuk data tersebut di organisasi Anda.

## <a name="add-a-new-workflow"></a>Tambahkan alur kerja baru

1. Buka **kecerdasan** > **model kustom** dan pilih **alur kerja baru**.

1. Berikan Nama **yang dapat** dikenali.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Tangkapan layar panel alur kerja baru.":::

1. Pilih organisasi yang berisi layanan web dalam **penyewa yang berisi layanan web Anda**.

1. Jika langganan Pembelajaran Mesin Azure Anda berada di penyewa berbeda dari pada Customer Insights, pilih **masuk** dengan kredensial anda untuk organisasi yang dipilih.

1. Pilih **ruang kerja** yang terkait dengan layanan web Anda.

1. Pilih alur Azure Pembelajaran Mesin di **layanan Web yang berisi menu tarik-turun model** Anda. Kemudian pilih **Berikutnya**.
   Pelajari lebih lanjut tentang cara [mempublikasi alur kerja di Pembelajaran Mesin Azure menggunakan desainer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) atau [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Untuk setiap **input Layanan web**, pilih **entitas** yang cocok dari Customer Insights. Kemudian pilih **Berikutnya**.
   > [!NOTE]
   > Alur kerja model kustom akan menerapkan heuristik untuk memetakan bidang input layanan web ke atribut entitas berdasarkan nama dan jenis data bidang. Anda akan melihat kesalahan jika bidang layanan web tidak dapat dipetakan ke entitas.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Mengonfigurasikan alur kerja.":::

1. Untuk **Parameter** Output Model, atur properti berikut:
   - **Nama entitas** untuk hasil output alur
   - **Nama parameter penyimpanan data output** dari alur batch Anda
   - **Nama** parameter Jalur Output dari alur batch Anda

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Panel parameter output model.":::

1. Pilih atribut yang cocok dari **ID Pelanggan dalam hasil** yang mengidentifikasi pelanggan dan pilih **Simpan**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Kaitkan hasil ke panel data pelanggan.":::

   Layar **Workflow Saved** menampilkan detail tentang alur kerja. Jika Anda mengonfigurasi alur kerja untuk alur Azure Pembelajaran Mesin, Customer Insights melampirkan ke ruang kerja yang berisi alur. Customer Insights akan mendapatkan **peran kontributor** di ruang kerja Azure.

1. Pilih **Selesai**. Halaman **Model** Kustom ditampilkan.

1. Pilih elipsis vertikal (&vellip;) untuk alur kerja dan pilih **Jalankan**. Alur kerja Anda juga berjalan secara otomatis dengan setiap [refresh](schedule-refresh.md) terjadwal.

## <a name="manage-an-existing-workflow"></a>Mengelola alur kerja yang sudah ada

Buka **Model** > **Kustom Kecerdasan** untuk menampilkan alur kerja yang Anda buat.

Pilih alur kerja untuk menampilkan tindakan yang tersedia.

- **Mengedit** alur kerja
- **Menjalankan** alur kerja
- [**Menghapus**](#delete-a-workflow) alur kerja

### <a name="edit-a-workflow"></a>Edit alur kerja

1. Buka **model** > **Kustom Intelijen**.

1. Di samping alur kerja yang ingin Anda perbarui, pilih elipsis vertikal (&vellip;) dan pilih **Edit**.

1. Ubah **nama tampilan** jika diperlukan, dan pilih **Berikutnya**.

1. Untuk setiap **input** layanan Web, perbarui Entitas **yang** cocok dari Customer Insights, jika diperlukan. Kemudian pilih **Berikutnya**.

1. Untuk **Parameter** Output Model, ubah salah satu hal berikut ini:
   - **Nama entitas** untuk hasil output alur
   - **Nama parameter penyimpanan data output** dari alur batch Anda
   - **Nama** parameter Jalur Output dari alur batch Anda

1. Ubah atribut pencocokan dari **ID Pelanggan dalam hasil** untuk mengidentifikasi pelanggan. Pilih atribut dari output inferensi dengan nilai yang serupa dengan kolom ID pelanggan dari entitas pelanggan. Jika Anda tidak memiliki kolom seperti itu di himpunan data Anda, pilih atribut yang secara unik mengidentifikasi baris tersebut.

1. Pilih **Simpan**

### <a name="delete-a-workflow"></a>Hapus alur kerja

1. Buka **model** > **Kustom Intelijen**.

1. Di samping alur kerja yang ingin Anda hapus, pilih elipsis vertikal (&vellip;) dan pilih **Hapus**.

1. Konfirmasikan penghapusan.

Alur kerja Anda akan dihapus. Entitas [yang](entities.md) dibuat saat Anda membuat alur kerja tetap ada, dan dapat dilihat dari **halaman Entitas** > **Data**.

## <a name="view-the-results"></a>Lihat hasilnya

Hasil dari alur kerja disimpan dalam nama entitas yang ditentukan untuk **Parameter** Output Model. Akses data ini dari [**halaman** > **Entitas** Data](entities.md) atau dengan [akses](apis.md) API.

### <a name="api-access"></a>Akses API

Agar kueri OData tertentu dapat memperoleh data dari entitas model kustom, gunakan format berikut:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Ganti `<your instance id>` dengan ID lingkungan Customer Insights Anda, yang ditampilkan di bilah alamat browser Anda saat mengakses Customer Insights.

1. Ganti `<custom model output entity>` dengan nama entitas yang Anda berikan untuk **Parameter** Output Model.

1. Ganti `<guid value>` dengan ID Pelanggan pelanggan yang ingin Anda akses. ID ini ditampilkan pada [halaman](customer-profiles.md) profil pelanggan di bidang CustomerID.

## <a name="frequently-asked-questions"></a>Tanya Jawab Umum

- Mengapa saya tidak dapat melihat alur kerja saat menyiapkan alur kerja model kustom?
  Masalah ini sering disebabkan oleh masalah konfigurasi dalam alur. Pastikan [parameter input dikonfigurasi](azure-machine-learning-experiments.md#dataset-configuration), dan [parameter datastore dan jalur output](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) juga dikonfigurasi.

- Apa artinya kesalahan "Tidak Dapat menyimpan alur kerja cerdas"? 
  Pengguna biasanya melihat pesan kesalahan ini jika mereka tidak memiliki hak istimewa Pemilik atau Administrator Akses Pengguna di ruang kerja. Pengguna memerlukan tingkat izin yang lebih tinggi agar Customer Insights dapat memproses alur kerja sebagai layanan dan bukan menggunakan kredensial pengguna untuk alur kerja berikutnya.

- Apakah tautan titik akhir /pribadi pribadi pribadi untuk alur kerja model kustom saya didukung?
  Customer Insights saat ini tidak mendukung titik akhir pribadi untuk model kustom di luar kotak, tetapi solusi manual tersedia. Silakan hubungi dukungan untuk detailnya.

## <a name="responsible-ai"></a>AI yang bertanggung jawab

Prediksi menawarkan kemampuan untuk membuat pengalaman pelanggan yang lebih baik, meningkatkan kemampuan Bisnis, dan aliran pendapatan. Kami sangat menyarankan agar anda menyeimbangkan nilai prediksi anda terhadap dampak dan bias yang dapat ditimbulkan dengan cara yang etis. Pelajari lebih lanjut tentang cara Microsoft [menangani AI yang bertanggung jawab](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Anda juga dapat mempelajari [teknik dan proses untuk Pembelajaran Mesin bertanggung jawab](/azure/machine-learning/concept-responsible-ml) yang spesifik untuk Pembelajaran Mesin Azure.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
