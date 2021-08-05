---
title: Membuat dan mengonfigurasi uji coba Customer Insights
description: Langkah-langkah untuk mendapatkan langganan uji coba untuk Dynamics 365 Customer Insights dan mengonfigurasinya.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f80654f03252142ce08241ff3ca3606be4595740
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650479"
---
# <a name="set-up-a-trial-environment"></a>Mengkonfigurasi lingkungan uji coba 

Uji coba Dynamics 365 Customer Insights memungkinkan Anda meninjau kemampuan utama dan mempelajari selengkapnya tentang berbagai fitur. Langganan uji coba dihapus setelah kedaluwarsa. Lingkungan uji coba dibuat oleh pengguna individual yang menjadi administrator lingkungan uji coba mereka. Mereka dapat mengundang lebih banyak pengguna ke uji coba mereka dan mengonfigurasi berbagai fitur.

## <a name="create-a-trial-environment"></a>Buat lingkungan uji coba

Anda dapat mendaftar uji coba di halaman [pendaftaran uji coba](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Pilih **Mendaftar untuk pilihan uji coba gratis** dan pilih **Mendaftar sekarang**.

1. Berikan alamat email kantor atau sekolah Anda, beri tahu kami lebih banyak tentang diri Anda dan pilih **Mulai**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialog untuk mendaftar ke instans uji coba":::

1. Periksa persyaratan dan ketentuan, dan pilih **Lanjutkan** untuk mengonfirmasikan.

1. Berikan **nama** untuk lingkungan baru Anda. 

1. Atur **Jenis** lingkungan sebagai **Uji Coba**.

1. Di bidang **Pilih demo industri**, Anda dapat secara opsional memilih himpunan data spesifik industri. Anda juga dapat [mengubah ke demo industri](#use-industry-specific-demo-data-sets-in-audience-insights) nanti dan memulai dengan himpunan data.

1. Harap pilih **wilayah** untuk lingkungan Anda.

1. Secara opsional, jika Anda adalah admin organisasi Dynamics 365: Pilih **Pengaturan tingkat lanjut** dan sediakan URL organisasi Anda untuk menggunakan fitur prediksi seperti prediksi kehilangan pelanggan. 

1. Pilih **Buat**. 

Dibutuhkan beberapa saat untuk menyelesaikan konfigurasi lingkungan. Setelah selesai, Anda diarahkan ke lingkungan demo atau demo industri yang Anda pilih pada langkah di atas. Kini Anda dapat menjelajahi aplikasi dengan data demo baca-saja. Untuk menambahkan data Anda sendiri ke lingkungan, lihat [Membuat data demo khusus skenario di lingkungan Anda sendiri](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Cuplikan layar lingkungan uji coba yang baru dibuat.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Menggunakan himpunan data demo spesifik industri dalam wawasan audiens

Menghubungkan sumber data nyata adalah salah satu langkah penting dalam menggunakan kekuatan Customer Insights. Untuk mencoba fitur tanpa mengganggu data Anda sendiri, Anda dapat secara opsional menggunakan data demo spesifik industri. Ada beberapa himpunan data demo yang tersedia untuk industri berikut: 

-   Otomotif
-   Perbankan
-   Barang konsumen
-   Pemerintah
-   Perawatan Kesehatan
-   Keramahan
-   Asuransi
-   Produksi
-   Layanan Profesional
-   Ritel

### <a name="see-industry-specific-demo-data-in-trials"></a>Lihat data demo spesifik industri dalam uji coba

Untuk versi Customer Insights hanya baca, yang disesuaikan dengan industri atau skenario tertentu, mulailah di lingkungan Demo. 
 
1.  Dalam audiens, pilih lingkungan **Demo** di pemilih lingkungan.

2.  Di **Beranda**, pilih opsi dari menu tarik-turun Pilih demo industri.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Pilih industri untuk lingkungan uji coba.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Membuat data demo khusus skenario di lingkungan Anda sendiri

Sebagai administrator, pilih pemilih lingkungan di header aplikasi untuk membuat lingkungan baru. Di lingkungan baru, Anda dapat mengonfigurasi sumber data Anda sendiri dan menyiapkan aplikasi sesuai dengan kebutuhan Anda. 

1.  Di wawasan audiens, buka **Data** > **Sumber data**.

2.  Untuk mengimpor sumber data Anda sendiri, buka [panduan tentang penyerapan data](data-sources.md).     
   Jika Anda lebih suka bekerja dengan data sampel yang memungkinkan Anda mencoba menyerap data, Anda dapat menyerap data demo industri di lingkungan Anda. Pilih opsi **Impor dari Datahub** dan ikuti langkah-langkah di bawah ini.

3.  Pilih kartu industri yang sesuai dengan skenario Anda. 

4.  Tinjau atau perbarui nama yang disarankan dari sumber data. 

5.  Pilih **Berikutnya** untuk menyerap data sampel. 

Anda sekarang dapat menggunakan data yang diserap untuk menyesuaikan Customer Insights dengan skenario Anda. Untuk melihat lingkungan yang khusus untuk data demo yang diserap, pilih opsi **Demo <Industry>** di pemilih lingkungan.

## <a name="limitations-in-trials"></a>Batasan dalam uji coba

- Uji coba aktif selama 30 hari secara default. Namun, Anda dapat memperpanjangnya setelah hari ke-23 ketika Anda masuk ke uji coba Anda.
- Anda tidak dapat menggunakan akun Azure Data Lake Storage Anda sendiri untuk menyimpan data output selama uji coba. Namun, Anda dapat menyerap data dari akun Data Lake Storage.
- Anda dapat menyimpan data hingga 3 GB di lingkungan Dataverse yang disediakan secara otomatis saat Anda memulai uji coba Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Menyalin data dari uji coba ke langganan berbayar

Umumnya, kami sarankan untuk memulai dari awal dengan data Anda sendiri saat memutakhirkan ke versi berbayar Customer Insights. 

Secara opsional, Anda dapat menyalin data dari lingkungan uji coba jika membeli Customer Insights. Anda harus menjadi administrator uji coba Customer Insights dan admin global penyewa Microsoft 365 Anda, atau administrator Dynamics 365 di organisasi Anda untuk memigrasikan pengaturan dari lingkungan uji coba ke lingkungan berbayar. 

Setelah masuk ke instans Customer Insights berbayar Anda untuk pertama kalinya, Anda diminta untuk membuat lingkungan baru. Dalam proses ini, Anda dapat memilih untuk menyalin konfigurasi dari lingkungan yang ada dan memigrasikan sebagian besar pengaturan. Jika Anda memiliki izin yang disebutkan di atas, lingkungan uji coba akan ditampilkan dalam daftar ini. Untuk informasi selengkapnya, lihat [Menyalin konfigurasi lingkungan](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Langkah berikutnya

Tinjau artikel berikut untuk membantu Anda memulai mengonfigurasi Customer Insights. 

- [Tambahkan lebih banyak pengguna dan tetapkan izin](permissions.md).
- [Serap sumber data Anda](data-sources.md) dan jalankan semua melalui [proses penyatuan data](data-unification.md) untuk mendapatkan [profil pelanggan terpadu](customer-profiles.md).
- [Perkaya profil pelanggan terpadu](enrichment-hub.md) atau [jalankan model prediktif](predictions-overview.md).
- Buat [segmen](segments.md) untuk mengelompokkan pelanggan dan [mengukur](measures.md) KPI ulasan.
- Siapkan [koneksi](connections.md) dan [ekspor](export-destinations.md) untuk memproses subkumpulan data Anda di aplikasi lain.