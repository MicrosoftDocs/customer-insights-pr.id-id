---
title: Buat lingkungan baru
description: Langkah-langkah untuk membuat lingkungan di Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304247"
---
# <a name="create-a-new-environment"></a>Buat lingkungan baru

Setelah [membeli lisensi berlangganan untuk Dynamics 365 Customer Insights](paid-license.md), administrator Microsoft 365 global penyewa menerima email yang mengundang mereka untuk membuat lingkungan. Buka [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) untuk memulai. Dalam skenario ini, mulailah dengan [Langkah 1: Berikan informasi dasar](#step-1-provide-basic-information).

Setelah lingkungan pertama dibuat, administrator Microsoft 365 global penyewa dapat [menambahkan pengguna dari organisasi mereka sebagai administrator](permissions.md). Administrator ini kemudian dapat mengelola pengguna dan lingkungan. Jika organisasi Anda membeli lebih dari satu lisensi untuk Customer Insights, [hubungi tim](https://go.microsoft.com/fwlink/?linkid=2079641) dukungan kami untuk meningkatkan jumlah lingkungan yang tersedia. Untuk informasi selengkapnya tentang kapasitas dan kapasitas add-on, tinjau [panduan](https://go.microsoft.com/fwlink/?LinkId=866544) lisensi Dynamics 365. Setelah Anda memiliki kemampuan untuk membuat lingkungan tambahan, buka [Memulai proses](#start-the-environment-creation-process) pembuatan lingkungan.

> [!TIP]
> Jika Anda ingin mencoba layanan, lihat [Mengkonfigurasi lingkungan uji coba](trial-signup.md).

## <a name="prerequisites"></a>Prasyarat

[Izin administrator](permissions.md) di Customer Insights

## <a name="start-the-environment-creation-process"></a>Mulai proses pembuatan lingkungan

1. Buka pemilih lingkungan dan pilih **+ Baru**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Pilih pemilih Lingkungan.":::

1. Ikuti pengalaman terpandu yang diuraikan di bagian berikut untuk memberikan semua informasi yang diperlukan untuk lingkungan baru.

## <a name="step-1-provide-basic-information"></a>Langkah 1: Berikan informasi dasar

1. Pilih apakah Anda ingin membuat lingkungan dari awal atau menyalin data dari lingkungan lain. [Menyalin data dari lingkungan](#copy-the-environment-configuration) lain memerlukan langkah-langkah tambahan.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog untuk membuat lingkungan Customer Insights baru.":::

1. Sediakan rincian berikut:

   - **Nama**: Nama untuk lingkungan ini. Bidang ini telah diisi jika Anda telah menyalin dari lingkungan yang ada, namun Anda dapat mengubahnya.
   - **Pilih bisnis** Anda: audiens utama untuk lingkungan baru: konsumen individu (B-to-C) atau [akun](work-with-business-accounts.md) bisnis (B-to-B). Jika organisasi Anda terutama melakukan bisnis dengan individu, seperti pengecer atau kedai kopi, pilih konsumen individu. Jika audiens utama Anda adalah perusahaan lain, seperti produsen mobil atau perusahaan kertas, pilih akun bisnis.
   - **Jenis**: Jenis lingkungan: produksi atau kotak pasir. Lingkungan sandbox tidak mengizinkan pembaruan data terjadwal dan ditujukan untuk penerapan dan pengujian sebelumnya. Lingkungan sandbox menggunakan audiens utama yang sama seperti lingkungan produksi yang saat ini dipilih.
   - **Wilayah**: Wilayah tempat layanan disebarkan dan dihosting. Untuk [menggunakan akun Azure Data Lake Storage Anda sendiri](own-data-lake-storage.md) atau [terhubung ke organisasi Microsoft Dataverse yang sudah ada](customer-insights-dataverse.md), lingkungan Customer Insights harus berada di wilayah yang sama.

1. Pilih **Selanjutnya**.

## <a name="step-2-configure-data-storage"></a>Langkah 2: Konfigurasikan penyimpanan data

1. Pilih tempat untuk menyimpan data Customer Insights:

   - **Penyimpanan Customer Insights**: Penyimpanan data dikelola secara otomatis. Ini adalah opsi default dan kecuali ada persyaratan khusus untuk menyimpan data di akun penyimpanan Anda sendiri, kami sarankan menggunakan opsi ini.
   - **Azure Data Lake Storage**: Akun Anda sendiri Azure Data Lake Storage untuk menyimpan data sehingga Anda memiliki kontrol penuh di mana data disimpan. Ikuti langkah-langkah dalam [Menggunakan akun Azure Data Lake Storage Anda sendiri](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Pilih opsi yang diinginkan untuk menyimpan data Anda.":::

1. Pilih **Selanjutnya**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>Langkah 3: Hubungkan ke Microsoft Dataverse

Jika Anda memiliki Dataverse lingkungan, hubungkan Customer Insights. Bagikan data dengan Dataverse untuk menggunakannya dengan aplikasi bisnis berdasarkan Dataverse, seperti Dynamics 365 Marketing atau aplikasi berbasis model di Power Apps.

1. Ikuti langkah-langkah dalam [Bekerja dengan data Customer Insights di Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="berbagi data dengan Microsoft Dataverse diaktifkan secara otomatis untuk lingkungan baru bersih.":::

1. Pilih **Selanjutnya**.

## <a name="step-4-finalize-the-settings"></a>Langkah 4: Selesaikan Pengaturan

Tinjau pengaturan yang ditentukan. Setelah semuanya terlihat selesai, pilih **Buat** untuk mengkonfigurasi lingkungan.

Untuk mengubah beberapa pengaturan nanti, lihat [Mengelola lingkungan](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Bekerja dengan lingkungan baru Anda

Lihat artikel berikut untuk membantu Anda memulai konfigurasi Customer Insights:

- [Tambahkan lebih banyak pengguna dan tetapkan izin](permissions.md).
- [Serap sumber data Anda](data-sources.md) dan jalankan semua melalui [proses penyatuan data](data-unification.md) untuk mendapatkan [profil pelanggan terpadu](customer-profiles.md).
- [Perkaya profil pelanggan terpadu](enrichment-hub.md) atau [jalankan model prediktif](predictions-overview.md).
- [Buat segmen](segments.md) untuk mengelompokkan pelanggan dan [ukuran](measures.md) untuk meninjau KPI.
- [Siapkan koneksi](connections.md) dan [ekspor](export-destinations.md) untuk memproses subkumpulan data Anda di aplikasi lain.

## <a name="copy-the-environment-configuration"></a>Salin konfigurasi lingkungan

Sebagai admin, jika Anda memilih untuk menyalin konfigurasi dari lingkungan yang ada, pilih dari daftar semua lingkungan yang tersedia di organisasi Anda.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Cuplikan layar pilihan pengaturan di pengaturan lingkungan.":::

Pengaturan konfigurasi berikut disalin:

- Sumber data yang diimpor melalui Power Query
- Konfigurasi penyatuan data
- Segmen
- Tindakan
- Hubungan
- Aktivitas
- Indeks pencarian & filter
- Ekspor
- Refresh jadwal
- Pengayaan
- Model prediksi
- Penetapan peran

### <a name="set-up-a-copied-environment"></a>Menyiapkan lingkungan yang disalin

Saat Anda menyalin konfigurasi lingkungan, pesan konfirmasi akan ditampilkan saat lingkungan yang disalin telah dibuat. Lakukan langkah-langkah berikut untuk mengonfirmasi kredensial.

1. Pilih **buka sumber data** untuk melihat daftar sumber data. Semua sumber data menunjukkan **status Kredensial yang Diperlukan**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Daftar sumber data yang disalin dan memerlukan otentikasi.":::

1. Edit sumber data dan masukkan kredensial untuk me-refresh mereka. Sumber data dari folder Common Data Model dan Dataverse harus dibuat secara manual dengan nama yang sama seperti di lingkungan sumber.

1. Setelah menyegarkan sumber data, buka **data** > **Satukan**. Di sini Anda akan menemukan pengaturan dari lingkungan sumber. Edit sesuai kebutuhan atau pilih **Satukan Satukan** > **Profil dan dependensi** pelanggan Unify untuk memulai proses penyatuan data dan membuat entitas pelanggan terpadu.

   > [!TIP]
   > Untuk akun dan kontak, pilih **Satukan akun** > **Satukan akun Satukan profil dan dependensi**.

1. Setelah penyatuan data selesai, buka **Pengukuran** dan **Segmen untuk me-refreshnya**.

1. Buka **Koneksi** > **Admin** untuk mengautentikasi ulang koneksi di lingkungan baru Anda.

1. Buka **Pengayaan** > **Data** dan **Ekspor** > **Data** untuk mengaktifkannya kembali.

[!INCLUDE [footer-include](includes/footer-banner.md)]
