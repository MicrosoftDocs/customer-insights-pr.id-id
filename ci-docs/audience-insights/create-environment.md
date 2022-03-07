---
title: Membuat lingkungan di Customer Insights
description: Langkah-langkah membuat lingkungan dengan langganan berlisensi untuk Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: c37afd5649f8cf40d5379f3d39d0cbd96cde3bd3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354099"
---
# <a name="create-an-environment-in-audience-insights"></a>Buat lingkungan di wawasan audiens

Artikel ini menjelaskan cara membuat lingkungan baru setelah organisasi Anda membeli langganan Dynamics 365 Customer Insights. 

Organisasi dapat membuat *dua* lingkungan untuk setiap lisensi Customer Insights. Jika organisasi Anda membeli lebih dari satu lisensi, [hubungi tim dukungan kami](https://go.microsoft.com/fwlink/?linkid=2079641) untuk meningkatkan jumlah lingkungan yang tersedia. Untuk informasi lebih lanjut tentang kapasitas dan kapasitas add-on, unduh [panduan lisensi Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Jika Anda ingin mencoba layanan, lihat [Mengkonfigurasi lingkungan uji coba](../trial-signup.md).

## <a name="create-a-new-environment"></a>Buat lingkungan baru

Setelah membeli lisensi langganan untuk Wawasan Pelanggan, administrator Microsoft 365 global penyewa menerima email yang mengundang mereka untuk menciptakan lingkungan. Buka [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) untuk memulai. 

Pengalaman terpandu akan membantu Anda melakukan langkah-langkah untuk mengumpulkan semua informasi yang diperlukan untuk lingkungan baru. Anda memerlukan [izin administrator](permissions.md) di wawasan audiens untuk membuat atau mengelola lingkungan.

1. Dalam wawasan audiens, buka pemilih lingkungan dan pilih **+ Baru**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Pilih pemilih Lingkungan.":::

1. Ikuti pengalaman terpandu yang diuraikan dalam bagian berikut.

### <a name="step-1-provide-environment-information"></a>Langkah 1: Berikan informasi lingkungan

Pada langkah **informasi Dasar**, pilih apakah Anda ingin membuat lingkungan dari awal atau [menyalin data dari lingkungan lain](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog untuk membuat lingkungan Customer Insights baru.":::

Sediakan rincian berikut:
   - **Nama**: Ketik nama untuk lingkungan ini. Bidang ini telah diisi jika Anda telah menyalin dari lingkungan yang ada, namun Anda dapat mengubahnya.
   - **Pilih bisnis Anda**: Pilih audiens primer untuk lingkungan baru. Anda dapat bekerja dengan konsumen individual (B-to-C) atau [akun bisnis](work-with-business-accounts.md) (B-to-B).
   - **Jenis**: Pilih Apakah Anda ingin membuat lingkungan produksi atau Sandbox. Lingkungan sandbox tidak mengizinkan pembaruan data terjadwal dan ditujukan untuk penerapan dan pengujian sebelumnya. Lingkungan sandbox menggunakan audiens utama yang sama seperti lingkungan produksi yang saat ini dipilih.
   - **Kawasan**: kawasan tempat layanan disebarkan dan dihosting.

### <a name="step-2-configure-data-storage"></a>Langkah 2: Konfigurasikan penyimpanan data

Pada langkah **penyimpanan Data**, pilih lokasi penyimpanan data dari wawasan audiens.

Anda akan memiliki dua pilihan: **penyimpanan Customer Insights** (Azure Data Lake yang dikelola oleh tim Customer Insights) dan **Azure Data Lake Storage** (Azure Data Lake Storage Anda sendiri). Secara default, pilihan penyimpanan Customer Insights dipilih.

:::image type="content" source="media/data-storage-environment.png" alt-text="Pilih Azure Data Lake Storage untuk menyimpan data audiens wawasan Anda.":::

Dengan menyimpan data ke Azure Data Lake Storage, berarti Anda menyetujui bahwa data akan ditransfer dan disimpan di lokasi geografi yang sesuai untuk akun penyimpanan Azure. Lokasi ini mungkin berbeda dengan lokasi penyimpanan data di Dynamics 365 Customer Insights. Pelajari lebih lanjut di [pusat kepercayaan Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights saat ini mendukung berikut:
> - Entitas yang diserap dari aliran data Power BI yang disimpan di Data Lake terkelola Microsoft Dataverse.  
> - Akun Azure Data Lake Storage dari kawasan Azure yang sama yang Anda pilih saat membuat lingkungan.
> - Azure Data Lake Storage akun yang Gen2 dan memiliki *ruang nama* hierarki diaktifkan. Akun penyimpanan Azure Data Lake Gen1 tidak didukung.

Untuk pilihan Azure Data Lake Storage tersebut, Anda dapat memilih antara pilihan berbasis sumber daya dan pilihan berbasis langganan untuk otentikasi. Untuk informasi lebih lanjut, lihat [Menyambung ke akun Azure Data Lake Storage menggunakan prinsipal layanan Azure](connect-service-principal.md). Nama **Wadah** akan menjadi `customerinsights` dan tidak dapat diubah.

Setelah proses sistem seperti penyerapan data selesai, sistem akan membuat folder terkait di akun penyimpanan yang Anda tentukan. File data dan file *model.json* dibuat dan ditambahkan ke folder berdasarkan nama proses.

Jika Anda membuat beberapa lingkungan Customer Insights dan memilih untuk menyimpan entitas output dari lingkungan tersebut ke akun penyimpanan Anda, Customer Insights akan membuat folder terpisah untuk setiap lingkungan dengan `ci_environmentID` dalam wadah.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Langkah 3: Hubungkan ke Microsoft Dataverse
   
Langkah **Microsoft Dataverse** memungkinkan Anda menghubungkan Customer Insights dengan lingkungan Dataverse Anda.

Menyediakan lingkungan Anda sendiri Microsoft Dataverse untuk berbagi data (profil dan wawasan) dengan aplikasi bisnis berdasarkan Dataverse, seperti Dynamics 365 Marketing atau aplikasi berbasis model di Power Apps. Biarkan bidang ini kosong jika Anda tidak memiliki lingkungan Anda sendiri Dataverse dan kami akan menyediakannya untuk Anda.

Menghubungkan ke lingkungan Anda Dataverse juga memungkinkan Anda untuk [menelan data dari sumber data lokal menggunakan Power Platform aliran data dan gateway](data-sources.md#add-data-from-on-premises-data-sources). Anda juga dapat menggunakan [model](predictions-overview.md?tabs=b2c#out-of-box-models) prediksi out-of-box dengan Dataverse terhubung ke lingkungan.

> [!IMPORTANT]
> Wawasan Pelanggan dan Dataverse harus berada di wilayah yang sama untuk memungkinkan berbagi data.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="berbagi data dengan Microsoft Dataverse auto diaktifkan untuk instans baru bersih.":::

> [!NOTE]
> Customer Insights tidak mendukung skenario berbagi data berikut ini:
> - Jika Anda menyimpan semua data ke Azure Data Lake Storage Anda sendiri, Anda tidak akan dapat mengaktifkan berbagi data dengan Data Lake Terkelola Dataverse.
> - Jika Anda mengaktifkan berbagi data dengan Dataverse, Anda tidak akan dapat [membuat nilai yang terduga atau tidak ada dalam entitas](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Langkah 4: Selesaikan Pengaturan

Pada langkah **Tinjauan**, buka semua pengaturan yang ditentukan. Setelah semuanya terlihat selesai, pilih **Buat** untuk mengkonfigurasi lingkungan. 

Anda juga dapat mengubah sebagian besar pengaturan nanti. Untuk informasi lebih lanjut, lihat [Kelola lingkungan](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Bekerja dengan lingkungan baru Anda

Lihat artikel berikut untuk membantu Anda memulai konfigurasi Customer Insights: 

- [Tambahkan lebih banyak pengguna dan tetapkan izin](permissions.md).
- [Serap sumber data Anda](data-sources.md) dan jalankan semua melalui [proses penyatuan data](data-unification.md) untuk mendapatkan [profil pelanggan terpadu](customer-profiles.md).
- [Perkaya profil pelanggan terpadu](enrichment-hub.md) atau [jalankan model prediktif](predictions-overview.md).
- [Buat segmen](segments.md) untuk mengelompokkan pelanggan dan [ukuran](measures.md) untuk meninjau KPI.
- [Siapkan koneksi](connections.md) dan [ekspor](export-destinations.md) untuk memproses subkumpulan data Anda di aplikasi lain.
