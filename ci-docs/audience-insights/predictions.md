---
title: Melengkapi data parsial menggunakan prediksi
description: Gunakan prediksi untuk mengisi data pelanggan yang tidak lengkap.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 31b9b1b709540896c1dbc19f974df4ab056a7b8d
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692531"
---
# <a name="complete-your-partial-data-with-predictions"></a>Lengkapi data parsial dengan prediksi

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Prediksi memungkinkan Anda dengan mudah membuat nilai prediksi yang dapat meningkatkan pemahaman Anda tentang pelanggan. Pada halaman **intelijen** > **prediksi**, anda dapat memilih **prediksi saya** untuk melihat prediksi yang telah dikonfigurasi di bagian lain dari wawasan audiens, dan memungkinkan anda menyesuaikannya lebih lanjut.

> [!NOTE]
> Anda tidak dapat menggunakan fitur ini jika lingkungan Anda menggunakan penyimpanan Azure data Lake gen 2.
>
> Fitur prediksi menggunakan cara otomatis untuk mengevaluasi data dan membuat prediksi berdasarkan data tersebut, sehingga memiliki kemampuan untuk digunakan sebagai metode pembuatan profil, sebagaimana istilah tersebut didefinisikan oleh peraturan perlindungan data umum ("GDPR"). Penggunaan fitur ini oleh pelanggan untuk memproses data dapat tergantung pada GDPR atau hukum atau peraturan lain. Anda bertanggung jawab untuk memastikan bahwa penggunaan Dynamics 365 Customer Insights, termasuk prediksi, mematuhi semua hukum dan peraturan yang berlaku, termasuk hukum yang terkait dengan privasi, data pribadi, data biometrik, perlindungan data, dan kerahasiaan komunikasi.

## <a name="prerequisites"></a>Prasyarat

Sebelum organisasi Anda dapat menggunakan fitur prediksi, prasyarat berikut harus terpenuhi:

1. Organisasi Anda memiliki instans yang [disiapkan di Microsoft Dataverse](/ai-builder/build-model#prerequisites) dan berada di organisasi yang sama dengan Customer Insights.

2. Lingkungan audiens Anda melekat pada instans Dataverse Anda.

Jika Anda [membuat lingkungan pertama](get-started-paid.md), konfigurasikan di dialog **buat lingkungan** dan pilih **lanjutan**. Jika Anda telah membuat lingkungan, buka pengaturannya dan pilih **lanjutan**. Apa pun, di bagian **gunakan prediksi**, masukkan URL instans Dataverse yang ingin Anda lampirkan lingkungan Anda.

## <a name="create-a-prediction-in-the-customer-entity"></a>Membuat prediksi di entitas pelanggan

1. Di wawasan audiens, buka **Data** > **Entitas**.

2. Pilih entitas **pelanggan**.

3. Di entitas **pelanggan: CustomerInsights**, pilih pada tab **bidang**.

4. Temukan nama atribut yang diinginkan untuk memprediksi nilai, lalu pilih ikon **Ikhtisar** di kolom **ringkasan**.
   > [!div class="mx-imgBorder"]
   > ![Ikon Ikhtisar.](media/intelligence-overviewicon.png "Ikon Ikhtisar")

5. Jika ada tingkat tinggi nilai yang hilang untuk atribut Anda, pilih **Prediksikan nilai yang hilang** untuk melanjutkan prediksi Anda.
   > [!div class="mx-imgBorder"]
   > ![Ikhtisar status dengan tombol memprediksi nilai hilang ditampilkan.](media/intelligence-overviewpredictmissingvalues.png "Ikhtisar status dengan tombol memprediksi nilai hilang ditampilkan")

6. Berikan **nama tampilan** dan **nama entitas Output** untuk hasil prediksi.

7. Daftar pilihan yang telah diisi akan menampilkan lokasi Anda dapat memetakan nilai ke kategori yang diramalkan. Dalam kasus ini, satu-satunya pilihan kategori Anda adalah 0 atau 1 saat memetakan ke sifat prediksi true/false atau biner. Dalam kolom Kategori, petakan nilai bidang yang ingin Anda klasifikasikan sebagai "0" di prediksi akhir ke "0", dan item yang ingin diklasifikasikan sebagai "1" di prediksi akhir ke "1".
   > [!div class="mx-imgBorder"]
   > ![Contoh yang menampilkan nilai bidang yang dipetakan ke kategori.](media/intelligence-categorymapping.png "Contoh yang menampilkan nilai bidang yang dipetakan ke kategori")

8. Pilih **selesai** dan prediksi akan diproses. Pemrosesan akan memakan waktu, tergantung pada ukuran dan kompleksitas data. Hasil akan tersedia di entitas baru berdasarkan **nama entitas output** prediksi yang Anda buat.

## <a name="create-a-prediction-while-creating-a-segment"></a>Buat prediksi saat membuat segmen

Memprediksi nilai yang hilang untuk atribut tertentu pilihan juga dapat dilakukan saat membuat segmen. Khususnya, bila Anda dengan cepat membuat segmen berdasarkan entitas pelanggan atau entitas Customer_Measure terpadu.

Sebagai bagian dari alur ini, Anda memilih atribut khusus untuk mendasarkan segmen Anda seperti kepuasan pelanggan atau jumlah pembelian. Setelah pembuatan segmen, sistem akan menyarankan metode untuk memprediksi nilai yang hilang untuk atribut ini.

1. Di wawasan audiens, buka **segmen,** lalu pilih petak **profil**.

2. Pilih **bidang** untuk membuat segmen dan memilih **operator**, lalu pilih **tinjau**.

3. Berikan **nama** dan **nama tampilan** untuk segmen.

4. Pilih **Simpan**.

5. Jika segmen yang Anda buat memiliki data yang tidak lengkap di bidang sumber, Anda dapat memilih untuk memprediksi nilai yang tidak ada.
   > [!div class="mx-imgBorder"]
   > ![Tombol prediksi.](media/segments-predictoption.png "Tombol prediksi")

6. Berikan **nama tampilan** dan **nama entitas Output** untuk hasil prediksi.

7. Pilih **Selesai**. Prediksi Anda akan segera dibuat di entitas baru dengan nama yang Anda berikan untuk **nama entitas output**.

## <a name="view-a-prediction"></a>Lihat Prediksi

1. Di wawasan audiens, buka **Intelijen** > **Prediksi** > **Prediksi Saya**.

2. Pilih prediksi yang ingin Anda tinjau.

3. Pilih elipsis di kolom **tindakan** dan pilih **tampilan**.

4. Anda akan melihat sejumlah poin data dalam tampilan prediksi.
   > [!div class="mx-imgBorder"]
   > ![Halaman Prediksi.](media/intelligence-predictionsviewpage.png "Halaman Prediksi")

   - **Nilai yang diprediksi** menunjukkan pemetaan yang Anda buat selama fase pemetaan nilai bidang ke kategori. Ini adalah nilai dalam himpunan data Anda yang telah dipetakan ke kategori tertentu.
   -**Pemberi pengaruh teratas** adalah faktor dalam himpunan data Anda yang kemungkinan besar akan mempengaruhi tingkat keyakinan prediksi nilai bidang Anda yang dipetakan ke kategori tertentu.
   - **Kinerja** menunjukkan kinerja prediksi. Pilih tautan untuk mempelajari lebih lanjut.
   - **Pratinjau** menampilkan contoh data output dari prediksi Anda dan kemungkinan, atau keyakinan kita, atas nilai prediksi di mana 0 tidak pasti, dan 1 adalah pasti.

## <a name="update-a-prediction"></a>Perbarui prediksi

1. Di wawasan audiens, buka **Intelijen** > **Prediksi** > **Prediksi Saya**.

2. Pilih prediksi yang ingin Anda perbarui dan pilih ikon **Perbarui**.

3. Prediksi akan dijadwalkan untuk diproses. Anda dapat melihat waktu terakhir diperbarui dalam kolom **diperbarui** pada halaman **prediksi**.

## <a name="edit-a-prediction"></a>Edit Prediksi

Setelah membuat prediksi, Anda dapat menyesuaikan model di AI Builder untuk meningkatkan efektivitas model Anda.  

1. Di wawasan audiens, buka **Intelijen** > **Prediksi** > **Prediksi Saya**.

2. Pilih prediksi yang akan diedit.

3. Pilih elipsis di kolom **tindakan** dan pilih **tampilan**.

4. pilih **Sesuaikan di AI Builder**.

5. Perbarui model Anda di AI Builder. [Pelajari lebih lanjut tentang cara mengelola model di AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

Langkah berikutnya dari prediksi Anda akan menggunakan model yang telah diperbarui yang telah Anda buat.

> [!NOTE]
> Model baru yang dibuat di AI Builder tidak akan ditampilkan di wawasan audiens kecuali model dibuat dari pengalaman yang tercantum di atas.

## <a name="remove-a-prediction"></a>Hilangkan prediksi

1. Di wawasan audiens, buka **Intelijen** > **Prediksi** > **Prediksi Saya**.

2. Pilih prediksi yang ingin Anda hapus.

3. Pilih elipsis di kolom **tindakan** dan pilih **Hapus**.

4. Konfirmasikan Penghapusan.

## <a name="troubleshooting"></a>Pemecahan masalah

Jika Anda tidak dapat menyelesaikan proses lampirkan Dataverse karena kesalahan, Anda dapat mencoba menyelesaikan proses secara manual. Ada dua masalah umum yang dapat terjadi di proses melampirkan:

- Solusi Add-in kartu pelanggan tidak diinstal.
    1. Selesaikan petunjuk untuk [menginstal dan mengkonfigurasi solusi](customer-card-add-in.md).

- Izin aplikasi tidak diberikan.
    1. Tuju [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Pilih **lingkungan**.
    1. Pilih elipsis di sebelah lingkungan yang akan ditambahkan izin dan pilih **pengaturan**.
    1. Perluas **pengguna + izin** dan pilih **pengguna**.
    1. Pilih **+ Baru** dan pilih **Pengguna**.
    1. Pilih **pengguna aplikasi** jika belum dipilih dan masukkan informasi berikut:
        - **Nama Pengguna:** cihelp@microsoft.com
        - **ID Aplikasi:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Nama Depan:** Pelanggan
        - **Nama Belakang:** Insights
        - **Email Utama:** cihelp@microsoft.com
    1. Pilih **Simpan & Tutup**.
    1. Pilih pengguna yang baru saja Anda buat.
    1. Pilih **Kelola peran** di bilah menu atas.
    1. Pilih **administrator sistem**, lalu pilih **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]