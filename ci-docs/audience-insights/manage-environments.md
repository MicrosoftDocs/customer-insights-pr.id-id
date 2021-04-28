---
title: Membuat dan mengelola lingkungan
description: Pelajari cara mendaftar ke layanan dan cara mengelola lingkungan.
ms.date: 03/26/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8cc1401251ed7c45c598bd4a8fb33a9709fabbc8
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887990"
---
# <a name="manage-environments"></a>Kelola lingkungan

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Artikel ini menjelaskan cara membuat organisasi baru dan cara menyediakan lingkungan.

## <a name="sign-up-and-create-an-organization"></a>Mendaftar dan membuat organisasi

1. Kunjungi situs web [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Pilih **Mulai**.

3. Pilih skenario daftar pilihan Anda dan pilih tautan yang sesuai.

4. Setujui persyaratan dan ketentuan, lalu pilih **Lanjutkan** untuk mulai membuat organisasi.

5. Setelah lingkungan dibuat, Anda akan diarahkan ke [Customer Insights](https://home.ci.ai.dynamics.com).

6. Gunakan lingkungan demo untuk menjelajahi aplikasi, atau membuat lingkungan baru dengan mengikuti langkah di bagian berikutnya.

7. Setelah menentukan pengaturan lingkungan, pilih **buat**.

8. Anda akan masuk setelah lingkungan berhasil dibuat.

## <a name="create-an-environment-in-an-existing-organization"></a>Membuat lingkungan di organisasi yang ada

Terdapat dua cara untuk membuat lingkungan baru. Anda dapat menentukan konfigurasi yang sama sekali baru atau Anda dapat menyalin beberapa pengaturan konfigurasi dari lingkungan yang ada.

> [!NOTE]
> Organisasi dapat membuat *dua* lingkungan untuk setiap lisensi Customer Insights. Jika organisasi Anda membeli lebih dari lisensi satu kali, silakan [hubungi tim dukungan kami](https://go.microsoft.com/fwlink/?linkid=2079641) untuk meningkatkan jumlah lingkungan yang tersedia. Untuk informasi selengkapnya tentang kapasitas dan kapasitas add-on, unduh [panduan lisensi Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Untuk membuat lingkungan:

1. Pilih pemilih **Lingkungan** di header aplikasi.

1. Pilih **baru**.

   > [!div class="mx-imgBorder"]
   > ![Pengaturan Lingkungan](media/environment-settings-dialog.png)

1. Di dialog **buat lingkungan baru**, pilih **lingkungan baru**.

   Jika Anda ingin [menyalin data dari lingkungan saat ini](#considerations-for-copy-configuration-preview), pilih **salinan dari lingkungan yang ada**. Anda akan melihat daftar semua lingkungan yang tersedia di organisasi tempat Anda dapat menyalin data.

1. Sediakan rincian berikut:
   - **Nama**: Ketik nama untuk lingkungan ini. Bidang ini telah diisi jika Anda telah menyalin dari lingkungan yang ada, namun Anda dapat mengubahnya.
   - **Kawasan**: kawasan tempat layanan disebarkan dan dihosting.
   - **Jenis**: Pilih Apakah Anda ingin membuat lingkungan produksi atau Sandbox.

1. Atau, Anda dapat memilih **pengaturan tingkat lanjut**:

   - **Simpan semua data ke**: menentukan lokasi penyimpanan data output yang dihasilkan dari Customer Insights. Anda akan memiliki dua pilihan: **penyimpanan Customer Insights** (Azure Data Lake yang dikelola oleh tim Customer Insights) dan **Azure Data Lake Storage Gen2** (Azure Data Lake Storage milik Anda). Secara default, pilihan penyimpanan Customer Insights dipilih.

   > [!NOTE]
   > Dengan menyimpan data ke Azure Data Lake Storage, Anda setuju bahwa data akan ditransfer ke dan disimpan di lokasi geografis yang sesuai untuk akun Azure Storage, yang mungkin berbeda dari lokasi penyimpanan data di Dynamics 365 Customer Insights. [Pelajari lebih lanjut di pusat kepercayaan Microsoft.](https://www.microsoft.com/trust-center)
   >
   > Saat ini, entitas yang diserap akan selalu tersimpan di data Lake yang dikelola oleh customer Insights.
   > Kami hanya mendukung akun penyimpanan Azure data Lake Gen2 dari wilayah Azure yang sama yang Anda pilih saat membuat lingkungan.
   > Kami hanya mendukung akun penyimpanan yang diaktifkan Azure Data Lake Gen2 Hierarchical Name Space (HNS).

   - Untuk opsi Azure Data Lake Storage Gen2, Anda dapat memilih antara menggunakan pilihan berbasis sumber daya dan pilihan berbasis langganan untuk autentikasi. Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md). Nama **penampung** tidak dapat diubah dan akan menjadi "customerinsights".
   
   - Jika Anda ingin menggunakan [prediksi](predictions.md), konfigurasikan berbagi data dengan aplikasi dan solusi berdasarkan Microsoft Dataverse, atau aktifkan penyerapan data dari sumber data lokal, berikan URL lingkungan Microsoft Dataverse di **Konfigurasikan berbagi data dengan Microsoft Dataverse dan aktifkan kemampuan tambahan**. Pilih **Aktifkan berbagi data** untuk berbagi data output Customer Insights dengan Data Lake terkelola Microsoft Dataverse.

     > [!NOTE]
     > - Berbagi data dengan Data Lake terkelola Microsoft Dataverse saat ini tidak didukung bila Anda menyimpan semua data untuk Azure Data Lake Storage Anda sendiri.
     > - [Prediksi nilai yang tidak ada pada entitas](predictions.md) saat ini tidak didukung bila Anda mengaktifkan berbagi data dengan Data Lake terkelola Microsoft Dataverse.

     > [!div class="mx-imgBorder"]
     > ![Pilihan konfigurasi untuk mengaktifkan berbagi data dengan Microsoft Dataverse](media/datasharing-with-DataverseMDL.png)

   Bila Anda menjalankan proses, seperti konsumsi data atau pembuatan segmen, folder yang sesuai akan dibuat di akun penyimpanan yang Anda tentukan di atas. File data dan file model .json akan dibuat dan ditambahkan ke subfolder masing-masing berdasarkan proses yang Anda jalankan.

   Jika Anda membuat beberapa lingkungan dari Customer Insights dan memilih untuk menyimpan entitas output dari lingkungan tersebut di akun penyimpanan, folder terpisah akan dibuat untuk setiap lingkungan dengan ci_<environmentid> dalam penampung.

### <a name="considerations-for-copy-configuration-preview"></a>Pertimbangan untuk konfigurasi salin (pratinjau)

Pengaturan konfigurasi berikut disalin:

- Konfigurasi fitur
- Sumber data yang diserap/diimpor
- Konfigurasi penyatuan data (petakan, cocokkan, gabungkan)
- Segmen
- Tindakan
- Relasi
- Aktivitas
- Indeks Pencarian & filter
- Tujuan ekspor
- Refresh terjadwal
- Pengayaan
- Manajemen model
- Penetapan peran

Pengaturan berikut *tidak* disalin:

- Profil pelanggan.
- Kredensial sumber data. Anda harus memberikan kredensial untuk setiap sumber data dan menyegarkan sumber data secara manual.
- Sumber data dari folder Common Data Model dan danau terkelola Common Data Service. Anda harus membuat sumber data secara manual dengan nama yang sama seperti di lingkungan sumber.

Bila Anda menyalin lingkungan, Anda akan melihat pesan konfirmasi bahwa lingkungan baru telah dibuat. Pilih **buka sumber data** untuk melihat daftar sumber data.

Semua sumber data akan menampilkan status **kredensial yang diperlukan**. Edit sumber data dan masukkan kredensial untuk me-refresh mereka.

> [!div class="mx-imgBorder"]
> ![Sumber data disalin](media/data-sources-copied.png)

Setelah menyegarkan sumber data, buka **data** > **Satukan**. Di sini Anda akan menemukan pengaturan dari lingkungan sumber. Edit sesuai kebutuhan atau pilih **Jalankan** untuk memulai proses penyatuan data dan buat entitas pelanggan terpadu.

Bila penyatuan data selesai, buka **langkah** dan **segmen** untuk me-refresh juga.

## <a name="edit-an-existing-environment"></a>Edit lingkungan yang ada

Anda dapat mengedit beberapa rincian lingkungan yang ada.

1.  Pilih pemilih **Lingkungan** di header aplikasi.

2.  Pilih ikon **Edit**.

3. Di kotak **Edit lingkungan**, Anda dapat memperbarui **nama tampilan** lingkungan, tetapi Anda tidak dapat mengubah **Kawasan** atau **Jenis**.

4. Jika lingkungan dikonfigurasi untuk menyimpan data di Azure Data Lake Storage Gen2, Anda dapat memperbarui **kunci akun**. Namun, Anda tidak dapat mengubah **nama akun** atau nama **penampung**.

5. Atau, Anda dapat memperbarui dari sambungan berbasis kunci akun ke sambungan berbasis sumber daya atau berbasis langganan. Setelah ditingkatkan, Anda tidak dapat kembali ke kunci akun setelah pembaruan. Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md). Anda tidak dapat **mengubah** informasi penampung saat memperbarui sambungan.

6. Secara opsional, Anda dapat menyediakan URL lingkungan Microsoft Dataverse di **konfigurasikan berbagi data dengan Microsoft Dataverse dan aktifkan kemampuan tambahan**. Kemampuan ini melibatkan berbagi data dengan aplikasi dan solusi berdasarkan Microsoft Dataverse, penyerapan data dari sumber data lokal, atau [prediksi](predictions.md) penggunaan. Pilih **Aktifkan berbagi data** untuk berbagi data output Customer Insights dengan Data Lake terkelola Microsoft Dataverse.

   > [!NOTE]
   > - Berbagi data dengan Data Lake terkelola Microsoft Dataverse saat ini tidak didukung bila Anda menyimpan semua data untuk Azure Data Lake Storage Anda sendiri.
   > - [Prediksi nilai yang hilang dalam entitas](predictions.md) saat ini tidak didukung saat Anda mengaktifkan berbagi data dengan Data Lake Terkelola Microsoft Dataverse.

   Setelah Anda mengaktifkan berbagi data dengan Microsoft Dataverse, refresh penuh pada sumber data Anda dan proses lainnya akan dipicu. Jika proses saat ini berjalan dan diantrekan, Anda tidak akan melihat opsi untuk mengaktifkan berbagi data dengan Microsoft Dataverse. Anda dapat menunggu proses tersebut selesai atau membatalkannya untuk mengaktifkan berbagi data. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Pilihan konfigurasi untuk mengaktifkan berbagi data dengan Microsoft Dataverse.":::
   
   Bila Anda menjalankan proses, seperti konsumsi data atau pembuatan segmen, folder yang sesuai akan dibuat di akun penyimpanan yang Anda tentukan di atas. File data dan file model.json akan dibuat dan ditambahkan ke subfolder masing-masing, tergantung pada proses yang Anda jalankan.

## <a name="reset-an-existing-environment"></a>Mengatur ulang lingkungan yang ada

Sebagai administrator, Anda dapat mengatur ulang lingkungan ke status kosong jika Anda ingin menghapus semua konfigurasi dan menghapus data yang diserap.

1.  Pilih pemilih **Lingkungan** di header aplikasi. 

2.  Pilih lingkungan yang ingin Anda atur ulang dan pilih elipsis **...**. 

3. Pilih opsi **Atur ulang**. 

4.  Untuk mengkonfirmasi penghapusan, masukkan nama lingkungan dan pilih **Atur ulang**.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>Menghapus lingkungan yang ada (hanya tersedia untuk admin)

Sebagai administrator, Anda dapat menghapus lingkungan yang dikelola.

1.  Pilih pemilih **Lingkungan** di header aplikasi.

2.  Pilih lingkungan yang ingin Anda atur ulang dan pilih elipsis **...**. 

3. Pilih opsi **Hapus**. 

4.  Untuk mengonfirmasikan penghapusan, masukkan nama lingkungan dan pilih **Hapus**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
