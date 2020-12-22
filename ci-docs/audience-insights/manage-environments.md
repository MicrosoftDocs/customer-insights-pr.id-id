---
title: Membuat dan mengelola lingkungan
description: Pelajari cara mendaftar ke layanan dan cara mengelola lingkungan.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644137"
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

Untuk membuat lingkungan:

1. Pilih simbol **pengaturan** di header aplikasi.

1. Pilih **Lingkungan baru**.

   > [!div class="mx-imgBorder"]
   > ![Pengaturan Lingkungan](media/environment-settings-dialog.png)

1. Di dialog **buat lingkungan baru**, pilih **lingkungan baru**.

   Jika Anda ingin [menyalin data dari lingkungan saat ini](#additional-considerations-for-copy-configuration-preview), pilih **salinan dari lingkungan yang ada**. Anda akan melihat daftar semua lingkungan yang tersedia di organisasi tempat Anda dapat menyalin data.

1. Sediakan rincian berikut:
   - **Nama**: Ketik nama untuk lingkungan ini. Bidang ini telah diisi jika Anda telah menyalin dari lingkungan yang ada, namun Anda dapat mengubahnya.
   - **Kawasan**: kawasan tempat layanan disebarkan dan dihosting.
   - **Jenis**: Pilih Apakah Anda ingin membuat lingkungan produksi atau Sandbox.

2. Atau, Anda dapat memilih **pengaturan tingkat lanjut**:

   - **Simpan semua data ke**: menentukan lokasi penyimpanan data output yang dihasilkan dari Customer Insights. Anda akan memiliki dua pilihan: **penyimpanan Customer Insights** (Azure Data Lake yang dikelola oleh tim Customer Insights) dan **Azure Data Lake Storage Gen2** (Azure Data Lake Storage milik Anda). Secara default, pilihan penyimpanan Customer Insights dipilih.

   > [!NOTE]
   > Dengan menyimpan data ke Azure Data Lake Storage, Anda setuju bahwa data akan ditransfer ke dan disimpan di lokasi geografis yang sesuai untuk akun Azure Storage, yang mungkin berbeda dari lokasi penyimpanan data di Dynamics 365 Customer Insights. [Pelajari lebih lanjut di pusat kepercayaan Microsoft.](https://www.microsoft.com/trust-center)
   >
   > Saat ini, entitas yang diserap akan selalu tersimpan di data Lake yang dikelola oleh customer Insights.
   > Kami hanya mendukung akun penyimpanan Azure data Lake Gen2 dari wilayah Azure yang sama yang Anda pilih saat membuat lingkungan.
   > Kami hanya mendukung akun penyimpanan yang diaktifkan Azure Data Lake Gen2 Hierarchical Name Space (HNS).

   - Untuk opsi Azure Data Lake Storage Gen2, Anda dapat memilih antara menggunakan pilihan berbasis sumber daya dan pilihan berbasis langganan untuk autentikasi. Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md). Nama **penampung** tidak dapat diubah dan akan menjadi "customerinsights".
   
   - Jika Anda ingin menggunakan [prediksi](predictions.md), masukkan URL instans Common Data Service di bidang **alamat server** dalam **gunakan prediksi**.

   Bila Anda menjalankan proses, seperti konsumsi data atau pembuatan segmen, folder yang sesuai akan dibuat di akun penyimpanan yang Anda tentukan di atas. File data dan file model .json akan dibuat dan ditambahkan ke subfolder masing-masing berdasarkan proses yang Anda jalankan.

   Jika Anda membuat beberapa lingkungan dari Customer Insights dan memilih untuk menyimpan entitas output dari lingkungan tersebut di akun penyimpanan, folder terpisah akan dibuat untuk setiap lingkungan dengan ci_<environmentid> dalam penampung.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Pertimbangan tambahan untuk konfigurasi salinan (pratinjau)

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

1. Buka **Admin** > **Sistem** > **Tentang**.

2. Pilih **Edit**.

3. Anda dapat memperbarui **nama tampilan** lingkungan, namun anda tidak dapat mengubah **kawasan** atau **jenis**.

4. Jika lingkungan dikonfigurasi untuk menyimpan data di Azure Data Lake Storage Gen2, Anda dapat memperbarui **kunci akun**. Namun, Anda tidak dapat mengubah **nama akun** atau nama **penampung**.

5. Atau, Anda dapat memperbarui dari sambungan berbasis kunci akun ke sambungan berbasis sumber daya atau berbasis langganan. Setelah ditingkatkan, Anda tidak dapat kembali ke kunci akun setelah pembaruan. Untuk informasi lebih lanjut, lihat [menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure](connect-service-principal.md). Anda tidak dapat **mengubah** informasi penampung saat memperbarui sambungan.

## <a name="reset-an-existing-environment"></a>Mengatur ulang lingkungan yang ada

Anda dapat mengatur ulang lingkungan ke status kosong jika Anda ingin menghapus semua konfigurasi dan menghapus data yang diserap.

1.  Buka **Admin** > **Sistem** > **Tentang**.

2.  Pilih **Atur ulang**. 

3.  Untuk mengkonfirmasi penghapusan, masukkan nama lingkungan dan pilih **Atur ulang**.


## <a name="delete-an-existing-environment"></a>Menghapus lingkungan yang ada

1. Buka **Admin** > **Sistem** > **Tentang**.

1. Pilih **Hapus**.

1. Untuk mengonfirmasikan penghapusan, masukkan nama lingkungan dan pilih **Hapus**.
