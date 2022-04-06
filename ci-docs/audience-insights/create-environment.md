---
title: Membuat lingkungan di Customer Insights
description: Langkah-langkah membuat lingkungan dengan langganan berlisensi untuk Dynamics 365 Customer Insights.
ms.date: 03/28/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: a538237322615f69f0a5cb43d394275bf79af00b
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491917"
---
# <a name="create-an-environment-in-audience-insights"></a>Buat lingkungan di wawasan audiens

Artikel ini menjelaskan cara membuat lingkungan baru setelah organisasi Anda membeli langganan Dynamics 365 Customer Insights. 

Organisasi dapat membuat *dua* lingkungan untuk setiap lisensi Customer Insights. Jika organisasi Anda membeli lebih dari satu lisensi, [hubungi tim dukungan kami](https://go.microsoft.com/fwlink/?linkid=2079641) untuk meningkatkan jumlah lingkungan yang tersedia. Untuk informasi lebih lanjut tentang kapasitas dan kapasitas add-on, unduh [panduan lisensi Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Jika Anda ingin mencoba layanan, lihat [Mengkonfigurasi lingkungan uji coba](../trial-signup.md).

## <a name="create-a-new-environment"></a>Buat lingkungan baru

Setelah membeli lisensi langganan untuk Customer Insights, administrator Microsoft 365 global penyewa menerima email yang mengundang mereka untuk membuat lingkungan. Buka [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) untuk memulai. 

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

Berikan lingkungan Anda sendiri Microsoft Dataverse untuk berbagi data (profil dan wawasan) dengan aplikasi bisnis berdasarkan Dataverse, seperti Dynamics 365 Marketing atau aplikasi berbasis model di Indonesia Power Apps. Biarkan bidang ini kosong jika Anda tidak memiliki lingkungan sendiri Dataverse dan kami akan menyediakannya untuk Anda.

Menghubungkan ke lingkungan Anda Dataverse juga memungkinkan Anda untuk [menelan data dari sumber data lokal menggunakan Power Platform aliran data dan gateway](data-sources.md#add-data-from-on-premises-data-sources). Anda juga dapat menggunakan [model](predictions-overview.md?tabs=b2c#out-of-box-models) prediksi di luar kotak dengan menghubungkan ke Dataverse lingkungan.

> [!IMPORTANT]
> 1. Wawasan Pelanggan dan Dataverse harus berada di wilayah yang sama untuk mengaktifkan berbagi data.
> 1. Anda harus memiliki peran administrator global di Dataverse lingkungan. Verifikasi apakah lingkungan ini [Dataverse terkait dengan](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) grup keamanan tertentu dan pastikan Anda ditambahkan ke grup keamanan tersebut.
> 1. Tidak ada lingkungan Customer Insights yang sudah terkait dengan lingkungan tersebut Dataverse. Pelajari cara [menghapus koneksi yang ada ke Dataverse lingkungan](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="berbagi data dengan Microsoft Dataverse otomatis diaktifkan untuk instans baru bersih.":::

Untuk informasi selengkapnya tentang mengaktifkan berbagi Microsoft Dataverse data dari Anda sendiri Azure Data Lake Storage, lihat [Sambungkan ke Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Customer Insights tidak mendukung skenario berbagi data berikut ini:
- Jika Anda mengaktifkan berbagi data dengan Dataverse, Anda tidak akan dapat [membuat nilai yang terduga atau tidak ada dalam entitas](predictions.md).

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
