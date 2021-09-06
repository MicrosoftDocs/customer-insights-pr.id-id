---
title: Membuat dan mengonfigurasi lisensi berbayar Customer Insights
description: Langkah-langkah untuk mendapatkan langganan berlisensi untuk Dynamics 365 Customer Insights dan mengonfigurasinya.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034456"
---
# <a name="get-started-with-a-paid-subscription"></a>Mulai langganan berbayar

Artikel ini menjelaskan cara membuat lingkungan baru setelah organisasi Anda membeli langganan Dynamics 365 Customer Insights. Jika Anda ingin membeli Customer Insights, pilihan kontak kami akan tercantum di [situs web Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Jika Anda ingin mencoba layanan dan fitur, lihat [Mengkonfigurasi lingkungan uji coba](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Membuat lingkungan di organisasi yang ada

Setelah membeli lisensi langganan untuk Customer Insights, administrator global penyewa Microsoft 365 menerima email yang mengundang mereka untuk membuat lingkungan. Buka [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) untuk memulai. 

Customer Insights tidak berlisensi per pengguna, sehingga tidak akan ditampilkan di area Lisensi. Jika Anda mencari lisensi di pusat admin Microsoft 365, buka **produk Anda**. 

> [!NOTE]
> Organisasi dapat membuat *dua* lingkungan untuk setiap lisensi Customer Insights. Jika organisasi Anda membeli lebih dari lisensi satu kali, silakan [hubungi tim dukungan kami](https://go.microsoft.com/fwlink/?linkid=2079641) untuk meningkatkan jumlah lingkungan yang tersedia. Untuk informasi lebih lanjut tentang kapasitas dan kapasitas add-on, unduh [panduan lisensi Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Untuk membuat lingkungan:

1. Dalam dialog **Buat lingkungan**, pilih **Lingkungan baru**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog untuk membuat lingkungan Customer Insights baru.":::

   Sebaiknya mulai menyiapkan lingkungan dari awal. Namun, jika Anda admin atau anggota lingkungan uji coba, Anda dapat [menyalin data dari lingkungan lain](manage-environments.md#copy-the-environment-configuration), dengan memilih **Salin dari lingkungan yang ada**. Anda akan melihat daftar semua lingkungan yang tersedia di organisasi tempat Anda dapat menyalin data.

1. Sediakan rincian berikut:
   - **Nama**: Ketik nama untuk lingkungan ini. Bidang ini telah diisi jika Anda telah menyalin dari lingkungan yang ada, namun Anda dapat mengubahnya.
   - **Kawasan**: kawasan tempat layanan disebarkan dan dihosting.
   - **Jenis**: Pilih Apakah Anda ingin membuat lingkungan produksi atau Sandbox. Lingkungan sandbox tidak mengizinkan pembaruan data terjadwal dan ditujukan untuk penerapan dan pengujian sebelumnya.
   
1. Atau, Anda dapat memilih **pengaturan tingkat lanjut**:

   - **Simpan semua data ke**: menentukan lokasi penyimpanan data output yang dihasilkan dari Customer Insights. Anda akan memiliki dua pilihan: **penyimpanan Customer Insights** (Azure Data Lake yang dikelola oleh tim Customer Insights) dan **Azure Data Lake Storage** (Azure Data Lake Storage Anda sendiri). Secara default, pilihan penyimpanan Customer Insights dipilih.

     > [!NOTE]
     > Dengan menyimpan data ke Azure Data Lake Storage, Anda setuju bahwa data akan ditransfer ke dan disimpan di lokasi geografis yang sesuai untuk akun Azure Storage, yang mungkin berbeda dari lokasi penyimpanan data di Dynamics 365 Customer Insights. [Pelajari lebih lanjut di pusat kepercayaan Microsoft.](https://www.microsoft.com/trust-center)
     >
     > Saat ini, entitas yang diserap dari aliran data Power BI tersimpan di data Lake terkelola Microsoft Dataverse. 
     > 
     > Kami hanya mendukung akun Azure Data Lake Storage dari kawasan Azure yang sama yang Anda pilih saat membuat lingkungan. 
     > 
     > Kami hanya mendukung akun Azure Data Lake Storage yang mengaktifkan namespace hierarkis.


   - Untuk pilihan Azure Data Lake Storage tersebut, Anda dapat memilih antara pilihan berbasis sumber daya dan pilihan berbasis langganan untuk otentikasi. Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md). Nama **Wadah** tidak dapat diubah dan akan menjadi `customerinsights`.
   
   - Jika Anda ingin menggunakan [model siap pakai](predictions-overview.md#out-of-box-models), konfigurasikan pembagian data dengan Microsoft Dataverse, atau aktifkan pengalihan data dari sumber data lokal, berikan URL lingkungan Microsoft Dataverse dalam **Konfigurasikan berbagi data dengan Microsoft Dataverse dan aktifkan kemampuan tambahan**. Pilih **Aktifkan berbagi data** untuk berbagi data output Customer Insights dengan Data Lake terkelola Microsoft Dataverse.

     > [!NOTE]
     > - Berbagi data dengan Data Lake terkelola Microsoft Dataverse saat ini tidak didukung bila Anda menyimpan semua data untuk Azure Data Lake Storage Anda sendiri.
     > - [Prediksi nilai yang hilang dalam entitas](predictions.md) saat ini tidak didukung saat Anda mengaktifkan berbagi data dengan Data Lake Terkelola Microsoft Dataverse.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Pilihan konfigurasi untuk mengaktifkan berbagi data dengan Microsoft Dataverse.":::

   Bila proses sistem seperti penyerapan data selesai, sistem akan membuat folder terkait di akun penyimpanan yang Anda tentukan. File data dan file model.json dibuat dan ditambahkan ke folder berdasarkan nama proses.

   Jika Anda membuat beberapa lingkungan dari Customer Insights dan memilih untuk menyimpan entitas output dari lingkungan tersebut di akun penyimpanan, folder terpisah akan dibuat untuk setiap lingkungan dengan ci_<environmentid> dalam penampung.

1. Pilih **Buat** untuk konfigurasi lingkungan. 

## <a name="configure-an-environment"></a>Mengonfigurasi lingkungan

Tinjau artikel berikut untuk membantu Anda memulai mengonfigurasi Customer Insights. 

- [Tambahkan lebih banyak pengguna dan tetapkan izin](permissions.md).
- [Serap sumber data Anda](data-sources.md) dan jalankan semua melalui [proses penyatuan data](data-unification.md) untuk mendapatkan [profil pelanggan terpadu](customer-profiles.md).
- [Perkaya profil pelanggan terpadu](enrichment-hub.md) atau [jalankan model prediktif](predictions-overview.md).
- Buat [segmen](segments.md) untuk mengelompokkan pelanggan dan [mengukur](measures.md) KPI ulasan.
- Siapkan [koneksi](connections.md) dan [ekspor](export-destinations.md) untuk memproses subkumpulan data Anda di aplikasi lain.
