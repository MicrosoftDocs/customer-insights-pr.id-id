---
title: Sambungkan ke folder Common Data Model dengan akun Azure Data Lake Store
description: Bekerja dengan Common Data Model menggunakan Azure Data Lake Storage.
ms.date: 07/27/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: b237c291bb4dd22ca22ab2cdd8b6293490aa83e1
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245837"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Menyambungkan ke data di Azure Data Lake Storage

Serap data agar Dynamics 365 Customer Insights menggunakan akun Gen2 Anda Azure Data Lake Storage. Penyerapan data bisa penuh atau bertahap.

## <a name="prerequisites"></a>Prasyarat

- Penyerapan data mendukung Azure Data Lake Storage *akun Gen2* secara eksklusif. Anda tidak dapat menggunakan akun Data Lake Storage Gen1 untuk menyerap data.

- Akun Azure Data Lake Storage harus mengaktifkan [namespace hierarki](/azure/storage/blobs/data-lake-storage-namespace). Data harus disimpan dalam format folder hierarki yang mendefinisikan folder root dan memiliki subfolder untuk setiap entitas. Subfolder dapat memiliki data lengkap atau folder data inkremental.

- Untuk mengautentikasi dengan prinsipal Layanan Azure, pastikan perangkat dikonfigurasi di penyewa Anda. Untuk informasi selengkapnya, lihat [Menyambungkan ke Azure Data Lake Storage akun Gen2 dengan perwakilan](connect-service-principal.md) layanan Azure.

- Anda Azure Data Lake Storage ingin menyambungkan dan menyerap data dari harus berada di wilayah Azure yang sama dengan Dynamics 365 Customer Insights lingkungan. Koneksi ke folder Common Data Model dari Data Lake di kawasan Azure berbeda tidak didukung. Untuk mengetahui wilayah lingkungan Azure, buka **Sistem** > **Admin** > **Tentang** di Customer Insights.

- Data yang disimpan dalam layanan online dapat disimpan di lokasi yang berbeda dari tempat data diproses atau disimpan di Dynamics 365 Customer Insights.Dengan mengimpor atau menghubungkan ke data yang disimpan dalam layanan online, Anda setuju bahwa data dapat ditransfer ke dan disimpan dengan Dynamics 365 Customer Insights. [Pelajari selengkapnya di Pusat](https://www.microsoft.com/trust-center) Kepercayaan Microsoft.

- Perwakilan layanan Customer Insights harus berada di salah satu peran berikut untuk mengakses akun penyimpanan. Untuk informasi selengkapnya, lihat [Memberikan izin kepada perwakilan layanan untuk mengakses akun](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account) penyimpanan.
  - Pembaca Data Blob Penyimpanan
  - pemilik Data Blob Penyimpanan
  - Kontributor data Blob penyimpanan

- Data di Data Lake Storage Anda harus mengikuti standar Common Data Model untuk penyimpanan data Anda dan memiliki manifes model data umum untuk mewakili skema file data (*.csv atau *.parquet). Manifes harus memberikan detail entitas seperti kolom entitas dan tipe data, serta lokasi file data dan jenis file. Untuk informasi selengkapnya, lihat [Manifes](/common-data-model/sdk/manifest) Common Data Model. Jika manifes tidak ada, pengguna Admin dengan Pemilik Data Blob Penyimpanan atau akses kontributor Data Blob Penyimpanan dapat menentukan skema saat menyerap data.

## <a name="connect-to-azure-data-lake-storage"></a>Menyambungkan ke Azure Data Lake Storage

1. Buka **Data** > **Sumber data**.

1. Pilih **Tambahkan sumber data**.

1. Pilih **Penyimpanan** danau data Azure.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Kotak dialog untuk memasukkan detail koneksi untuk Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. **Masukkan Nama** untuk sumber data dan Deskripsi **opsional**. Nama ini secara unik mengidentifikasi sumber data dan dirujuk dalam proses hilir dan tidak dapat diubah.

1. Pilih salah satu opsi berikut untuk **Menyambungkan penyimpanan Anda menggunakan**. Untuk informasi selengkapnya, lihat [Menyambungkan Customer Insights ke Azure Data Lake Storage akun Gen2 dengan perwakilan](connect-service-principal.md) layanan Azure.

   - **Sumber daya** Azure: Masukkan **Id** Sumber Daya. Secara opsional, jika Anda ingin menyerap data dari akun penyimpanan melalui Azure Private Link, pilih **Aktifkan Private Link**. Untuk informasi selengkapnya, lihat [Tautan](security-overview.md#set-up-an-azure-private-link) Pribadi.
   - **Langganan** Azure: Pilih **Langganan** lalu **Grup** sumber daya dan **akun** Penyimpanan. Secara opsional, jika Anda ingin menyerap data dari akun penyimpanan melalui Azure Private Link, pilih **Aktifkan Private Link**. Untuk informasi selengkapnya, lihat [Tautan](security-overview.md#set-up-an-azure-private-link) Pribadi.
  
   > [!NOTE]
   > Anda memerlukan salah satu peran berikut baik ke kontainer atau akun penyimpanan untuk membuat sumber data:
   >
   >  - Pembaca Data Blob Penyimpanan cukup untuk dibaca dari akun penyimpanan dan menyerap data ke Customer Insights. 
   >  - Data Blob Penyimpanan kontributor atau Pemilik diperlukan jika Anda ingin mengedit file manifes secara langsung di Customer Insights.  
  
1. Pilih nama **Kontainer** yang berisi data dan skema (file model.json atau manifest.json) untuk mengimpor data, dan pilih **Berikutnya**.
   > [!NOTE]
   > File model.json atau manifest.json yang terkait dengan sumber data lain di lingkungan tidak akan ditampilkan dalam daftar. Namun, file model.json atau manifest.json yang sama dapat digunakan untuk sumber data di beberapa lingkungan.

1. Untuk membuat skema baru, buka [Membuat file](#create-a-new-schema-file) skema baru.

1. Untuk menggunakan skema yang ada, navigasikan ke folder yang berisi file model.json atau manifest.cdm.json. Anda dapat mencari di dalam direktori untuk menemukan file.

1. Pilih file json dan pilih **Berikutnya**. Daftar entitas yang tersedia ditampilkan.

   :::image type="content" source="media/review-entities.png" alt-text="Kotak dialog daftar entitas yang akan dipilih":::

1. Pilih entitas yang ingin Anda sertakan.

   :::image type="content" source="media/ADLS_required.png" alt-text="Kotak dialog memperlihatkan Diperlukan untuk kunci Utama":::

   > [!TIP]
   > Untuk mengedit entitas di antarmuka pengeditan JSON, pilih entitas lalu **Edit file skema**. Buat perubahan dan pilih **Simpan**.

1. Untuk entitas yang dipilih yang memerlukan penyerapan inkremental, **Diperlukan** ditampilkan di bawah **Refresh** inkremental. Untuk setiap entitas ini, lihat [Mengonfigurasi refresh inkremental untuk sumber](incremental-refresh-data-sources.md) data Azure Data Lake.

1. Untuk entitas yang dipilih di mana kunci utama belum ditentukan, **Diperlukan** ditampilkan di bawah **Kunci utama**. Untuk masing-masing entitas ini:
   1. Pilih **Diperlukan**. Panel **Edit entitas** ditampilkan.
   1. Pilih kunci **Utama**. Kunci utama adalah atribut yang unik untuk entitas. Agar atribut menjadi kunci primer yang valid, ia seharusnya tidak menyertakan nilai duplikat, nilai yang tidak ada, atau nilai null. Atribut tipe data string, integer, dan GUID didukung sebagai kunci utama.
   1. Secara opsional, ubah pola partisi.
   1. Pilih **Tutup** untuk menyimpan dan menutup panel.

1. Pilih jumlah **Atribut** untuk setiap entitas yang disertakan. Halaman **Kelola atribut** ditampilkan.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Kotak dialog untuk memilih pembuatan profil data.":::

   1. Buat atribut baru, edit, atau hapus atribut yang ada. Anda dapat mengubah nama, format data, atau menambahkan tipe semantik.
   1. Untuk mengaktifkan analitik dan kemampuan lainnya, pilih **Pembuatan profil data** untuk seluruh entitas atau untuk atribut tertentu. Secara default, entitas tidak diaktifkan untuk pembuatan profil data.
   1. Pilih **Selesai**.

1. Pilih **Simpan**. Halaman **Sumber data** terbuka memperlihatkan sumber data baru dalam **status Refresh**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuat data dapat memakan waktu. Setelah refresh berhasil, data yang diserap dapat ditinjau dari [**halaman Entitas**](entities.md).

### <a name="create-a-new-schema-file"></a>Membuat file skema baru

1. Pilih **File skema baru**.

1. Masukkan nama untuk file tersebut dan pilih **Simpan**.

1. Pilih **Entitas baru**. Panel **Entitas** Baru ditampilkan.

1. Masukkan nama entitas dan pilih **lokasi File data**.
   - **Beberapa file** .csv atau .parquet: Telusuri ke folder akar, pilih jenis pola, dan masukkan ekspresi.
   - **File .csv tunggal atau .parquet**: Telusuri ke file .csv atau .parquet dan pilih file tersebut.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Kotak dialog untuk membuat entitas baru dengan lokasi file Data disorot.":::

1. Pilih **Simpan**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Kotak dialog untuk menentukan atau membuat atribut secara otomatis.":::

1. Pilih **tentukan atribut** untuk menambahkan atribut secara manual, atau pilih buat **atribut** secara otomatis. Untuk menentukan atribut, masukkan nama, pilih format data dan tipe semantik opsional. Untuk atribut yang dibuat secara otomatis:

   1. Setelah atribut dibuat secara otomatis, pilih **Tinjau atribut**. Halaman **Kelola atribut** ditampilkan.

   1. Pastikan format data sudah benar untuk setiap atribut.

   1. Untuk mengaktifkan analitik dan kemampuan lainnya, pilih **Pembuatan profil data** untuk seluruh entitas atau untuk atribut tertentu. Secara default, entitas tidak diaktifkan untuk pembuatan profil data.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Kotak dialog untuk memilih pembuatan profil data.":::

   1. Pilih **Selesai**. Halaman **Pilih entitas** ditampilkan.

1. Terus tambahkan entitas dan atribut, jika berlaku.

1. Setelah semua entitas ditambahkan, pilih **Sertakan** untuk menyertakan entitas dalam penyerapan sumber data.

   :::image type="content" source="media/ADLS_required.png" alt-text="Kotak dialog memperlihatkan Diperlukan untuk kunci Utama":::

1. Untuk entitas yang dipilih yang memerlukan penyerapan inkremental, **Diperlukan** ditampilkan di bawah **Refresh** inkremental. Untuk setiap entitas ini, lihat [Mengonfigurasi refresh inkremental untuk sumber](incremental-refresh-data-sources.md) data Azure Data Lake.

1. Untuk entitas yang dipilih di mana kunci utama belum ditentukan, **Diperlukan** ditampilkan di bawah **Kunci utama**. Untuk masing-masing entitas ini:
   1. Pilih **Diperlukan**. Panel **Edit entitas** ditampilkan.
   1. Pilih kunci **Utama**. Kunci utama adalah atribut yang unik untuk entitas. Agar atribut menjadi kunci primer yang valid, ia seharusnya tidak menyertakan nilai duplikat, nilai yang tidak ada, atau nilai null. Atribut tipe data string, integer, dan GUID didukung sebagai kunci utama.
   1. Secara opsional, ubah pola partisi.
   1. Pilih **Tutup** untuk menyimpan dan menutup panel.

1. Pilih **Simpan**. Halaman **Sumber data** terbuka memperlihatkan sumber data baru dalam **status Refresh**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuat data dapat memakan waktu. Setelah refresh berhasil, data yang diserap dapat ditinjau dari [**halaman Entitas**](entities.md).

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Azure Data Lake Storage Mengedit sumber data

Anda dapat memperbarui *opsi Sambungkan ke akun penyimpanan menggunakan*. Untuk informasi selengkapnya, lihat [Menyambungkan Customer Insights ke Azure Data Lake Storage akun Gen2 dengan perwakilan](connect-service-principal.md) layanan Azure. Untuk menyambung ke kontainer lain dari akun penyimpanan, atau mengubah nama akun, buat [sambungan sumber data baru](#connect-to-azure-data-lake-storage).

1. Buka **Data** > **Sumber data**.

1. Di samping sumber data yang ingin Anda perbarui, pilih **Edit**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Kotak dialog untuk mengedit sumber data Azure Data Lake.":::

1. Ubah salah satu informasi berikut:

   - **KETERANGAN**
   - **Hubungkan penyimpanan Anda menggunakan** dan informasi koneksi. Anda tidak dapat **mengubah** informasi penampung saat memperbarui sambungan.
      > [!NOTE]
      > Salah satu peran berikut harus ditetapkan ke akun penyimpanan atau kontainer:
        > - Pembaca Data Blob Penyimpanan
        > - pemilik Data Blob Penyimpanan
        > - Kontributor data Blob penyimpanan

   - **Aktifkan Private Link** jika Anda ingin menyerap data dari akun penyimpanan melalui Azure Private Link. Untuk informasi selengkapnya, lihat [Tautan](security-overview.md#set-up-an-azure-private-link) Pribadi.

1. Pilih **Selanjutnya**.
1. Ubah salah satu hal berikut ini:
   - Navigasikan ke file model.json atau manifest.json yang berbeda dengan sekumpulan entitas yang berbeda dari kontainer.
   - Untuk menambahkan entitas tambahan ke penyerapan, pilih **Entitas baru**.
   - Untuk menghapus entitas yang sudah dipilih jika tidak ada dependensi, pilih entitas dan **Hapus**.
      > [!IMPORTANT]
      > Jika ada dependensi pada file model.json atau manifest.json yang ada dan rangkaian entitas, Anda akan melihat pesan kesalahan dan tidak dapat memilih file model.json atau json yang berbeda. Hilangkan dependensi tersebut sebelum mengubah file model.json atau manifest.json atau buat sumber data baru dengan file model.json atau manifest.json yang ingin Anda gunakan untuk menghindari dependensi dihapus.
   - Untuk mengubah lokasi file data atau kunci utama, pilih **Edit**.
   - Untuk mengubah data penyerapan inkremental, lihat [Mengonfigurasi refresh inkremental untuk sumber data Azure Data Lake](incremental-refresh-data-sources.md).
   - Hanya ubah nama entitas agar sesuai dengan nama entitas dalam file .json.

     > [!NOTE]
     > Selalu jaga agar nama entitas di Customer Insights tetap sama dengan nama entitas di dalam file model.json atau manifest.json setelah penyerapan. Customer Insights memvalidasi semua nama entitas dengan model.json atau manifest.json selama setiap refresh sistem. Jika nama entitas diubah baik di dalam Customer Insights atau di luar, kesalahan terjadi karena Customer Insights tidak dapat menemukan nama entitas baru dalam file .json. Jika nama entitas yang diserap tidak sengaja diubah, edit nama entitas di Customer Insights agar sesuai dengan nama dalam file .json.

1. Pilih **Atribut** untuk menambahkan atau mengubah atribut, atau untuk mengaktifkan pembuatan profil data. Kemudian pilih **Selesai**.

1. Klik **Simpan** untuk menerapkan perubahan Anda dan kembali ke **halaman Sumber** data.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
