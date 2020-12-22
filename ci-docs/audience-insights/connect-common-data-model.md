---
title: Sambungkan data Common Data Model ke akun Azure Data Lake
description: Bekerja dengan Common Data Model menggunakan Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643462"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Sambungkan ke folder Common Data Model dengan akun Azure Data Lake Store

Artikel ini memberikan informasi tentang cara menyerap data dari folder Common Data Model menggunakan akun Azure Data Lake Storage Gen2 Anda.

## <a name="important-considerations"></a>Pertimbangan penting

- Data di Azure Data Lake data harus mengikuti standar Common Data Model. Format lain tidak didukung saat ini.

- Konsumsi data mendukung akun penyimpanan Azure data Lake *Gen2* secara eksklusif. Anda tidak dapat menggunakan akun penyimpanan Azure Data Lake Gen1 untuk menyerap data.

- Untuk mengautentikasi dengan prinsipal Layanan Azure, pastikan perangkat dikonfigurasi di penyewa Anda. Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md).

- Azure Data Lake yang akan disambungkan dan diserap datanya harus berada di kawasan Azure yang sama dengan lingkungan Dynamics 365 Customer Insights. Koneksi ke folder Common Data Model dari Data Lake di kawasan Azure berbeda tidak didukung. Untuk mengetahui kawasan Azure lingkungan, buka **Admin** > **sistem** > **tentang** di wawasan audiens.

- Data yang tersimpan di layanan online, dapat disimpan di lokasi yang berbeda dengan data yang diproses atau disimpan di Dynamics 365 Customer Insights.Dengan mengimpor atau menyambung ke data yang tersimpan di layanan online, Anda setuju bahwa data dapat ditransfer ke dan disimpan dengan Dynamics 365 Customer Insights. [Pelajari lebih lanjut di pusat kepercayaan Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Sambungkan ke folder Model Data Umum

1. Di wawasan audiens, buka **Data** > **Sumber data**.

1. Pilih **Tambahkan sumber data**.

1. Pilih **sambungkan ke folder Common Data Model**, masukkan **nama** untuk sumber data, lalu pilih **berikutnya**.

1. Anda dapat memilih antara menggunakan pilihan berbasis sumber daya dan pilihan berbasis langganan untuk autentikasi. Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md). Masukkan informasi **penampung** dan pilih **berikutnya**.
   > [!div class="mx-imgBorder"]
   > ![Kotak dialog untuk memasukkan rincian sambungan untuk Azure Data Lake](media/enter-new-storage-details.png)

1. Di dialog **Pilih folder Common Data Model**, pilih file model.JSON untuk diimpor datanya, lalu pilih **berikutnya**.
   > [!NOTE]
   > File model.JSON apa pun yang terkait dengan sumber data lain di lingkungan tidak akan ditampilkan dalam daftar.

1. Anda akan mendapatkan daftar entitas yang tersedia dalam file model.JSON yang dipilih. Anda dapat meninjau dan memilih dari daftar entitas yang tersedia dan pilih **Simpan**. Semua entitas yang dipilih akan diserap dari sumber data baru.
   > [!div class="mx-imgBorder"]
   > ![Kotak dialog menampilkan daftar entitas dari file model.JSON](media/review-entities.png)

8. Tunjukkan entitas data mana yang Anda inginkan untuk mengaktifkan pembuatan profil data dan pilih **Simpan**. Pembuatan profil data memungkinkan kemampuan analitik dan kemampuan lainnya. Anda dapat memilih seluruh entitas, yang memilih semua atribut dari entitas, atau memilih atribut tertentu pilihan Anda. Secara default, entitas tidak diaktifkan untuk pembuatan profil data.
   > [!div class="mx-imgBorder"]
   > ![Kotak dialog menampilkan profil data](media/dataprofiling-entities.png)

9. Setelah menyimpan pilihan, halaman **sumber data** akan terbuka. Anda seharusnya sekarang melihat koneksi folder Common Data Model sebagai sumber data.

> [!NOTE]
> File model.json hanya dapat dikaitkan dengan satu sumber data di lingkungan yang sama. Namun, file model.JSON yang sama dapat digunakan untuk sumber data di beberapa lingkungan.

## <a name="edit-a-common-data-model-folder-data-source"></a>Mengedit sumber data folder Common Data Model

Anda dapat memperbarui kunci akses untuk akun penyimpanan yang berisi folder Common Data Model. Anda juga dapat mengubah file model.JSON. Untuk menyambung ke kontainer lain dari akun penyimpanan, atau mengubah nama akun, buat [sambungan sumber data baru](#connect-to-a-common-data-model-folder).

1. Di wawasan audiens, buka **Data** > **Sumber data**.

2. Di samping sumber data yang ingin anda perbarui, pilih elipsis.

3. Pilih opsi **Edit** dari daftar.

4. Atau, perbarui **tombol akses** dan pilih **berikutnya**.

   ![Dialog untuk mengedit dan memperbarui kunci akses untuk sumber data yang ada](media/edit-access-key.png)

5. Atau, Anda dapat memperbarui dari sambungan kunci akun ke sambungan berbasis sumber daya atau berbasis langganan. Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md). Anda tidak dapat **mengubah** informasi penampung saat memperbarui sambungan.
   > [!div class="mx-imgBorder"]
   > ![Kotak dialog untuk memasukkan rincian sambungan untuk Azure Data Lake](media/enter-existing-storage-details.png)

6. Atau, pilih file model.JSON yang berbeda dengan kumpulan entitas yang berbeda dari kontainer.

7. Atau, Anda dapat memilih entitas tambahan untuk diserap. Anda juga dapat menghapus entitas yang telah dipilih jika tidak ada dependensi.

   > [!IMPORTANT]
   > Jika ada ketergantungan pada file model.JSON yang ada dan kumpulan entitas, Anda akan melihat pesan kesalahan dan tidak dapat memilih file model.JSON yang berbeda. Hapus dependensi tersebut sebelum mengubah file model.json atau buat sumber data baru dengan file model.json yang ingin anda gunakan untuk menghindari penghapusan dependensi.

8. Atau, Anda dapat memilih atribut atau entitas tambahan untuk mengaktifkan pemrofilan data atau menonaktifkan yang telah dipilih.   
