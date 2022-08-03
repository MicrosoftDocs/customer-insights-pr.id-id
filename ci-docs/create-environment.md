---
title: 'Cara: Membuat lingkungan baru'
description: Langkah-langkah untuk membuat lingkungan di Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 33c8910b7a4dd8723c0d62f2e28228cd2d8df4b7
ms.sourcegitcommit: 5716025eb4828425ca237377b02a892de8689f4a
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/13/2022
ms.locfileid: "9142823"
---
# <a name="how-to-create-a-new-environment"></a>Cara: Membuat lingkungan baru

Setelah [membeli lisensi berlangganan untuk Dynamics 365 Customer Insights](paid-license.md), administrator Microsoft 365 global penyewa menerima email yang mengundang mereka untuk membuat lingkungan. Buka [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) untuk memulai. Dalam skenario ini, Anda dapat langsung menuju ke [Langkah 1: Berikan informasi dasar](#step-1-provide-basic-information).

Setelah lingkungan pertama dibuat, administrator Microsoft 365 global penyewa dapat [menambahkan pengguna dari organisasi mereka sebagai administrator](permissions.md). Ke depannya, administrator ini dapat mengelola pengguna dan lingkungan. Jika organisasi Anda membeli lebih dari satu lisensi untuk Customer Insights, [hubungi tim](https://go.microsoft.com/fwlink/?linkid=2079641) dukungan kami untuk meningkatkan jumlah lingkungan yang tersedia. Untuk informasi selengkapnya tentang kapasitas dan kapasitas add-on, tinjau [panduan](https://go.microsoft.com/fwlink/?LinkId=866544) lisensi Dynamics 365.

> [!TIP]
> Jika Anda ingin mencoba layanan, lihat [Mengkonfigurasi lingkungan uji coba](trial-signup.md).

## <a name="prerequisites"></a>Prasyarat

Anda memerlukan [izin](permissions.md) administrator di Customer Insights untuk membuat atau mengelola lingkungan.

## <a name="start-the-environment-creation-process"></a>Mulai proses pembuatan lingkungan

1. Buka pemilih lingkungan dan pilih **+ Baru**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Pilih pemilih Lingkungan.":::

1. Ikuti pengalaman terpandu yang diuraikan di bagian berikut untuk memberikan semua informasi yang diperlukan untuk lingkungan baru. Jika Anda mengonfigurasi lingkungan sebelumnya, Anda juga [dapat menyalin konfigurasi](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Langkah 1: Berikan informasi dasar

Pada langkah **informasi Dasar**, pilih apakah Anda ingin membuat lingkungan dari awal atau [menyalin data dari lingkungan lain](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Dialog untuk membuat lingkungan Customer Insights baru.":::

Sediakan rincian berikut:

- **Nama**: Ketik nama untuk lingkungan ini. Bidang ini telah diisi jika Anda telah menyalin dari lingkungan yang ada, namun Anda dapat mengubahnya.
- **Pilih bisnis Anda**: Pilih audiens primer untuk lingkungan baru. Anda dapat bekerja dengan konsumen individual (B-to-C) atau [akun bisnis](work-with-business-accounts.md) (B-to-B). Jika organisasi Anda terutama melakukan bisnis dengan individu, seperti pengecer atau kedai kopi, pilih konsumen individu. Jika audiens utama Anda adalah perusahaan lain, seperti produsen mobil atau perusahaan kertas, pilih akun bisnis.
- **Jenis**: Pilih Apakah Anda ingin membuat lingkungan produksi atau Sandbox. Lingkungan sandbox tidak mengizinkan pembaruan data terjadwal dan ditujukan untuk penerapan dan pengujian sebelumnya. Lingkungan sandbox menggunakan audiens utama yang sama seperti lingkungan produksi yang saat ini dipilih.
- **Kawasan**: kawasan tempat layanan disebarkan dan dihosting. Untuk [menggunakan akun Azure Data Lake Storage Anda sendiri](own-data-lake-storage.md) atau [terhubung ke organisasi Microsoft Dataverse yang sudah ada](customer-insights-dataverse.md), lingkungan Customer Insights harus berada di wilayah yang sama.

## <a name="step-2-configure-data-storage"></a>Langkah 2: Konfigurasikan penyimpanan data

**Di langkah Penyimpanan** data, pilih tempat untuk menyimpan data Customer Insights.

Ada dua opsi yang dapat Anda pilih:

- **Penyimpanan Customer Insights**: Penyimpanan data dikelola oleh tim Customer Insights. Ini adalah opsi default dan kecuali ada persyaratan khusus untuk menyimpan data di akun penyimpanan Anda sendiri, kami sarankan menggunakan opsi ini.
- **Azure Data Lake Storage**: Tentukan akun Anda sendiri Azure Data Lake Storage untuk menyimpan data sehingga Anda memiliki kontrol penuh di mana data disimpan. Untuk informasi selengkapnya, lihat [Menggunakan akun Azure Data Lake Storage Anda sendiri](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Pilih opsi yang diinginkan untuk menyimpan data Anda.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Langkah 3: Hubungkan ke Microsoft Dataverse

Langkah **Microsoft Dataverse** memungkinkan Anda menghubungkan Customer Insights dengan lingkungan Dataverse Anda. Bagikan data dengan Dataverse untuk menggunakannya dengan aplikasi bisnis berdasarkan Dataverse, seperti Dynamics 365 Marketing atau aplikasi berbasis model di Power Apps.

Biarkan bidang ini kosong jika Anda tidak memiliki lingkungan sendiri Dataverse dan kami akan membuatnya untuk Anda.

Untuk informasi selengkapnya, lihat [Bekerja dengan data Customer Insights di Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="berbagi data dengan Microsoft Dataverse diaktifkan secara otomatis untuk lingkungan baru bersih.":::

### <a name="step-4-finalize-the-settings"></a>Langkah 4: Selesaikan Pengaturan

**Di langkah Tinjau**, buka semua pengaturan yang ditentukan. Setelah semuanya terlihat selesai, pilih **Buat** untuk mengkonfigurasi lingkungan.

Anda dapat mengubah beberapa pengaturan nanti. Untuk informasi lebih lanjut, lihat [Kelola lingkungan](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Bekerja dengan lingkungan baru Anda

Lihat artikel berikut untuk membantu Anda memulai konfigurasi Customer Insights:

- [Tambahkan lebih banyak pengguna dan tetapkan izin](permissions.md).
- [Serap sumber data Anda](data-sources.md) dan jalankan semua melalui [proses penyatuan data](data-unification.md) untuk mendapatkan [profil pelanggan terpadu](customer-profiles.md).
- [Perkaya profil pelanggan terpadu](enrichment-hub.md) atau [jalankan model prediktif](predictions-overview.md).
- [Buat segmen](segments.md) untuk mengelompokkan pelanggan dan [ukuran](measures.md) untuk meninjau KPI.
- [Siapkan koneksi](connections.md) dan [ekspor](export-destinations.md) untuk memproses subkumpulan data Anda di aplikasi lain.

## <a name="copy-the-environment-configuration"></a>Salin konfigurasi lingkungan

Sebagai admin, Anda dapat memilih untuk menyalin konfigurasi dari lingkungan yang ada saat membuat yang baru.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Cuplikan layar pilihan pengaturan di pengaturan lingkungan.":::

Anda akan melihat daftar semua lingkungan yang tersedia di organisasi tempat Anda dapat menyalin data.

Pengaturan konfigurasi berikut disalin:

- Sumber data yang diimpor melalui Power Query
- Konfigurasi penyatuan data
- Segmen
- Tindakan
- Hubungan
- Aktivitas
- Indeks pencarian & filter
- Ekspor
- Jadwal refresh
- Pengayaan
- Model prediksi
- Penetapan peran

## <a name="set-up-a-copied-environment"></a>Menyiapkan lingkungan yang disalin

Saat Anda menyalin konfigurasi lingkungan, Anda harus melalui beberapa langkah tambahan untuk mengonfirmasi kredensial:

- Profil pelanggan. Pertama, autentikasi dan penyerapan sumber data Anda dan jalankan penyatuan data untuk membuat ulang profil pelanggan.
- Kredensial sumber data. Anda harus memberikan kredensial untuk setiap sumber data untuk mengautentikasi dan me-refresh sumber data secara manual.
- Sumber data dari folder Common Data Model dan Dataverse. Anda harus membuat sumber data tersebut secara manual dengan nama yang sama seperti di lingkungan sumber.
- Rahasia koneksi yang digunakan untuk ekspor dan pengayaan. Anda harus mengautentikasi ulang koneksi dan kemudian mengaktifkan kembali pengayaan dan ekspor.

Anda akan melihat pesan konfirmasi ketika lingkungan yang disalin telah dibuat. Pilih **buka sumber data** untuk melihat daftar sumber data.

Semua sumber data akan menampilkan status **kredensial yang diperlukan**. Edit sumber data dan masukkan kredensial untuk me-refresh mereka.

:::image type="content" source="media/data-sources-copied.png" alt-text="Daftar sumber data yang disalin dan memerlukan otentikasi.":::

Setelah menyegarkan sumber data, buka **data** > **Satukan**. Di sini Anda akan menemukan pengaturan dari lingkungan sumber. Edit sesuai kebutuhan atau pilih **Jalankan** untuk memulai proses penyatuan data dan buat entitas pelanggan terpadu.

Bila penyatuan data selesai, buka **langkah** dan **segmen** untuk me-refresh juga.

Sebelum Anda mengaktifkan kembali ekspor dan pengayaan, buka **Koneksi** > **Admin** untuk mengautentikasi ulang koneksi di lingkungan baru Anda.

[!INCLUDE [footer-include](includes/footer-banner.md)]
