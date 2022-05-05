---
title: Sambungkan data Common Data Model ke akun Azure Data Lake
description: Bekerja dengan Common Data Model menggunakan Azure Data Lake Storage.
ms.date: 01/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: eeb6b9d97be5f9c0b9f6cbd6dbc6985559a1cd9d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642640"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Sambungkan ke folder Common Data Model dengan akun Azure Data Lake Store

Artikel ini memberikan informasi tentang cara menelan data dari Dynamics 365 Customer Insights folder Model Data Umum menggunakan akun Gen2 Anda Azure Data Lake Storage.

## <a name="important-considerations"></a>Pertimbangan penting

- Data di Azure Data Lake data harus mengikuti standar Common Data Model. Format lain tidak didukung saat ini.

- Konsumsi data mendukung akun penyimpanan Azure data Lake *Gen2* secara eksklusif. Anda tidak dapat menggunakan akun penyimpanan Azure Data Lake Gen1 untuk menyerap data.

- Akun penyimpanan Azure Data Lake harus mengaktifkan [ruang nama hierarki](/azure/storage/blobs/data-lake-storage-namespace).

- Untuk mengautentikasi dengan prinsipal Layanan Azure, pastikan perangkat dikonfigurasi di penyewa Anda. Untuk informasi selengkapnya, lihat [Menyambungkan ke Azure Data Lake Storage akun Gen2 dengan perwakilan layanan Azure](connect-service-principal.md).

- Azure Data Lake yang akan disambungkan dan diserap datanya harus berada di kawasan Azure yang sama dengan lingkungan Dynamics 365 Customer Insights. Koneksi ke folder Common Data Model dari Data Lake di kawasan Azure berbeda tidak didukung. Untuk mengetahui wilayah lingkungan Azure, buka **AdminSystemTentang** > **·** > **di** Wawasan Pelanggan.

- Data yang disimpan dalam layanan online dapat disimpan di lokasi yang berbeda dari tempat data diproses atau disimpan di Dynamics 365 Customer Insights.Dengan mengimpor atau menghubungkan ke data yang disimpan dalam layanan online, Anda setuju bahwa data dapat ditransfer ke dan disimpan dengan Dynamics 365 Customer Insights. [Pelajari lebih lanjut di Microsoft Trust Center](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Sambungkan ke folder Model Data Umum

1. Buka **Data** > **Sumber data**.

1. Pilih **Tambahkan sumber data**.

1. Pilih **penyimpanan** danau data Azure, masukkan **Nama** untuk sumber data, lalu pilih **Berikutnya**.

   - Jika diminta, pilih salah satu kumpulan data sampel yang berkaitan dengan industri Anda, lalu pilih **Berikutnya**. 

1. Anda dapat memilih antara menggunakan pilihan berbasis sumber daya dan pilihan berbasis langganan untuk autentikasi. Untuk informasi selengkapnya, lihat [Menyambungkan ke Azure Data Lake Storage akun Gen2 dengan perwakilan layanan Azure](connect-service-principal.md). **Masukkan alamat** Server, pilih **masuk**, lalu pilih **Berikutnya**.
   > [!div class="mx-imgBorder"]
   > ![Kotak dialog untuk memasukkan rincian sambungan baru untuk Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Anda memerlukan salah satu peran berikut, baik untuk wadah atau akun penyimpanan yang dirujuk di atas agar dapat terhubung dan membuat sumber data:
   >  - Pembaca Data Blob Penyimpanan
   >  - pemilik Data Blob Penyimpanan
   >  - Kontributor data Blob penyimpanan

1. Di dialog **Pilih folder Common Data Model**, pilih file model.JSON atau manifest.json untuk diimpor datanya, lalu pilih **berikutnya**.
   > [!NOTE]
   > File model.json atau manifest.json yang terkait dengan sumber data lain di lingkungan tidak akan ditampilkan dalam daftar.

1. Anda akan melihat daftar entitas yang tersedia di file model.json atau manifest.json yang dipilih. Tinjau dan pilih dari daftar entitas yang tersedia, lalu pilih **Simpan**. Semua entitas yang dipilih akan diserap dari sumber data baru.
   > [!div class="mx-imgBorder"]
   > ![Kotak dialog menampilkan daftar entitas dari file model.json.](media/review-entities.png)

8. Tunjukkan entitas data mana yang ingin Anda aktifkan pembuatan profil data, lalu pilih **Simpan**. Pembuatan profil data memungkinkan kemampuan analitik dan kemampuan lainnya. Anda dapat memilih seluruh entitas, yang memilih semua atribut dari entitas, atau memilih atribut tertentu pilihan Anda. Secara default, entitas tidak diaktifkan untuk pembuatan profil data.
   > [!div class="mx-imgBorder"]
   > ![Kotak dialog menampilkan profil data.](media/dataprofiling-entities.png)

9. Setelah menyimpan pilihan, halaman **sumber data** akan terbuka. Anda seharusnya sekarang melihat koneksi folder Common Data Model sebagai sumber data.

> [!NOTE]
> File model.json atau manifest.json hanya dapat dikaitkan dengan satu sumber data di lingkungan yang sama. Namun, file model.json atau manifest.json yang sama dapat digunakan untuk sumber data di beberapa lingkungan.

## <a name="edit-a-common-data-model-folder-data-source"></a>Mengedit sumber data folder Common Data Model

Anda dapat memperbarui kunci akses untuk akun penyimpanan yang berisi folder Common Data Model. Anda juga dapat mengubah file model.json atau manifest.json. Untuk menyambung ke kontainer lain dari akun penyimpanan, atau mengubah nama akun, buat [sambungan sumber data baru](#connect-to-a-common-data-model-folder).

1. Buka **Data** > **Sumber data**.

2. Di samping sumber data yang ingin anda perbarui, pilih elipsis.

3. Pilih opsi **Edit** dari daftar.

4. Atau, perbarui **tombol akses** dan pilih **berikutnya**.

   ![Dialog untuk mengedit dan memperbarui kunci akses untuk sumber data yang ada.](media/edit-access-key.png)

5. Atau, Anda dapat memperbarui dari sambungan kunci akun ke sambungan berbasis sumber daya atau berbasis langganan. Untuk informasi selengkapnya, lihat [Menyambungkan ke Azure Data Lake Storage akun Gen2 dengan perwakilan layanan Azure](connect-service-principal.md). Anda tidak dapat **mengubah** informasi penampung saat memperbarui sambungan.
   > [!div class="mx-imgBorder"]

   > ![Kotak dialog untuk memasukkan rincian sambungan untuk Azure Data Lake ke akun penyimpanan yang ada.](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Anda memerlukan salah satu peran berikut, baik untuk wadah atau akun penyimpanan yang dirujuk di atas agar dapat terhubung dan membuat sumber data:
   >  - Pembaca Data Blob Penyimpanan
   >  - pemilik Data Blob Penyimpanan
   >  - Kontributor data Blob penyimpanan


6. Atau, pilih file model.json atau manifest.json dengan rangkaian entitas yang berbeda dari wadah.

7. Atau, Anda dapat memilih entitas tambahan untuk diserap. Anda juga dapat menghapus entitas yang telah dipilih jika tidak ada dependensi.

   > [!IMPORTANT]
   > Jika ada dependensi pada file model.json atau manifest.json yang ada dan rangkaian entitas, Anda akan melihat pesan kesalahan dan tidak dapat memilih file model.json atau json yang berbeda. Hilangkan dependensi tersebut sebelum mengubah file model.json atau manifest.json atau buat sumber data baru dengan file model.json atau manifest.json yang ingin Anda gunakan untuk menghindari dependensi dihapus.

8. Atau, Anda dapat memilih atribut atau entitas tambahan untuk mengaktifkan pemrofilan data atau menonaktifkan yang telah dipilih.   


[!INCLUDE [footer-include](includes/footer-banner.md)]
