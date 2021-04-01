---
title: prediksi Rekomendasi produk
description: Memperkirakan produk yang mungkin dibeli atau berinteraksi dengan pelanggan.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598067"
---
# <a name="product-recommendation-prediction-preview"></a>prediksi Rekomendasi produk (pratinjau)

Model rekomendasi produk membuat rangkaian rekomendasi produk prediktif. Rekomendasi didasarkan pada perilaku pembelian sebelumnya dan pelanggan dengan pola pembelian yang serupa. Anda dapat membuat prediksi rekomendasi produk baru pada halaman **Intelijen** > **Prediksi**. Pilih **prediksi saya** untuk melihat prediksi lain yang Anda buat.

Rekomendasi produk dapat diatur dalam hukum dan peraturan lokal serta ekspektasi pelanggan, yang modelnya tidak dibuat secara khusus untuk mempertimbangkan.  Sebagai pengguna kemampuan prediktif ini, **Anda harus memeriksa rekomendasi sebelum memberikannya kepada pelanggan** untuk memastikan bahwa Anda mematuhi hukum atau peraturan yang berlaku, serta memenuhi keinginan pelanggan atas apa yang dapat Anda sarankan. 

Selain itu, output model ini akan memberikan rekomendasi berdasarkan ID produk. Mekanisme pengiriman Anda harus mengambil ID produk yang diprediksi dan memetakannya ke konten yang sesuai bagi pelanggan untuk memperhitungkan pelokalan, konten gambar, dan konten atau perilaku khusus bisnis lainnya.

## <a name="sample-guide"></a>Panduan Sampel

Jika Anda ingin mencoba fitur ini tetapi tidak memiliki data untuk melengkapi persyaratan di bawah, Anda dapat [membuat implementasi sampel](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md) di Customer Insights.
- Pengetahuan bisnis untuk memahami berbagai jenis produk untuk bisnis Anda dan cara pelanggan Berinteraksi dengan mereka. Kami mendukung rekomendasi produk yang telah dibeli sebelumnya oleh pelanggan atau rekomendasi untuk produk baru.
- Data tentang transaksi, pembelian dan Riwayat mereka:
    - Pengidentifikasi transaksi untuk membedakan pembelian atau transaksi.
    - Pengidentifikasi pelanggan untuk memetakan transaksi dengan pelanggan Anda.
    - Tanggal aktivitas transaksi, yang menentukan tanggal terjadinya transaksi.
    - (Opsional) Informasi ID Produk untuk transaksi.
    - (Opsional) Jika transaksi adalah retur atau tidak.
    - Skema data semantik memerlukan informasi berikut:
        - **ID transaksi:** pengidentifikasi unik pembelian atau transaksi.
        - **Tanggal transaksi:** tanggal pembelian atau transaksi.
        - **Nilai transaksi:** nilai numerik dari pembelian atau transaksi.
        - **ID Produk unik:** id produk atau layanan yang dibeli jika data Anda berada pada tingkat item baris.
        - (Opsional) **Pembelian atau retur:** bidang benar/salah yang mengidentifikasi apakah transaksi tersebut merupakan retur atau tidak. Jika **nilai transaksi** negatif, kita juga akan menggunakan informasi ini untuk menyimpulkan retur.


## <a name="create-a-product-recommendation-prediction"></a>buat prediksi Rekomendasi produk

1. Di Customer Insights, buka **Intelijen** > **Prediksi**.

1. Pilih petak **model rekomendasi produk (pratinjau)** dan pilih **gunakan model ini**.
   > [!div class="mx-imgBorder"]
   > ![petak model Rekomendasi Produk dengan Tombol Gunakan model ini](media/product-recommendation-usethismodel.PNG "petak model Rekomendasi Produk dengan Tombol Gunakan model ini")

1. Tinjau informasi tentang persyaratan model. Jika Anda memiliki data yang diperlukan, pilih **Mulai**.

### <a name="name-model"></a>Beri nama model

1. Berikan nama model untuk membedakannya dari model lain.

1. Masukkan nama untuk entitas output hanya menggunakan huruf dan angka, tanpa spasi apa pun. Itulah nama yang akan digunakan oleh entitas model. Kemudian pilih **Berikutnya**.

### <a name="define-product-recommendation-configuration"></a>Tentukan konfigurasi rekomendasi produk

1. Atur **Jumlah produk** yang akan direkomendasikan ke pelanggan. Nilai ini tergantung pada cara metode pengiriman Anda mengisi data. Jika Anda dapat merekomendasikan tiga produk, atur nilai ini dengan sesuai.
   
   >[!TIP]
   > Anda dapat memilih **Simpan dan tutup** Kapan pun untuk menyimpan prediksi sebagai draf. Anda akan menemukan draf prediksi di tab **prediksi saya**.

1. Pilih jika Anda ingin **menyarankan produk yang baru saja dibeli pelanggan**.

1. Jika Anda memilih untuk *tidak* menyarankan produk yang baru dibeli, atur **Periode Lihat kembali**. Pengaturan ini menentukan jangka waktu yang dipertimbangkan model sebelum merekomendasikan produk kepada pengguna lagi. Misalnya, menunjukkan pelanggan membeli laptop setiap 2 tahun. Jendela ini akan melihat riwayat pembelian selama 2 tahun terakhir, dan jika item ditemukan, item akan difilter dari rekomendasi.

1. Pilih **berikutnya**

### <a name="add-required-data"></a>Tambahkan data wajib

1. Pilih **Tambah data** untuk **Riwayat transaksi pelanggan** dan pilih entitas yang menyediakan informasi riwayat transaksi/pembelian sebagaimana dijelaskan dalam [prasyarat](#prerequisites).

1. Petakan bidang semantik ke atribut dalam entitas Riwayat Pembelian Anda dan pilih **berikutnya**. Untuk Deskripsi bidang, lihat [prasyarat](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Tentukan relasi entitas](media/product-recommendation-purchasehistorymapping.PNG "Halaman riwayat pembelian yang menampilkan atribut semantis yang dipetakan ke bidang dalam entitas riwayat pembelian yang dipilih").

1. Jika bidang tidak diisi, konfigurasikan relasi dari entitas Riwayat Pembelian Anda ke entitas *pelanggan*.
    1. Pilih **Entitas riwayat pembelian**.
    1. Pilih **bidang** yang mengidentifikasi pelanggan di entitas riwayat pembelian. Ini perlu dikaitkan dengan ID pelanggan utama entitas *pelanggan* Anda.
    1. Pilih **entitas pelanggan** yang cocok dengan entitas pelanggan utama Anda.
    1. Masukkan nama yang mendeskripsikan relasi.
       > [!div class="mx-imgBorder"]
       > ![Halaman Riwayat pembelian yang menunjukkan pembuatan relasi dengan pelanggan](media/model-purchase-join.png "Halaman Riwayat pembelian yang menunjukkan pembuatan relasi dengan pelanggan")

1. Pilih **Simpan**.

1. Pilih **Selanjutnya**.

### <a name="set-schedule-and-review-configuration"></a>Mengatur konfigurasi jadwal dan ulasan

1. Atur frekuensi untuk melatih ulang model Anda. Pengaturan ini penting untuk memperbarui keakuratan prediksi karena data baru diimpor ke Customer Insights. Sebagian besar bisnis dapat melatih sekali per bulan dan mendapatkan akurasi yang baik untuk prediksi mereka.

1. Pilih **Selanjutnya**.

1. Tinjau Konfigurasi. Anda dapat kembali ke bagian apa pun dari konfigurasi prediksi dengan memilih **Edit** dalam nilai yang ditampilkan. Atau Anda dapat memilih langkah konfigurasi dari indikator progres.

1. Jika semua nilai dikonfigurasi dengan benar, pilih **Simpan dan jalankan** untuk memulai proses prediksi. Pada **tab prediksi saya**, Anda dapat melihat status prediksi Anda. Proses dapat berlangsung selama beberapa jam hingga selesai, tergantung pada jumlah data yang digunakan dalam prediksi.

## <a name="review-a-prediction-status-and-results"></a>Meninjau status dan hasil prediksi

1. Buka tab **prediksi saya** pada **intelijen** > **prediksi**.
   > [!div class="mx-imgBorder"]
   > ![Tampilan halaman prediksi saya](media/product-recommendation-mypredictions.PNG "Tampilan halaman prediksi saya")

1. Pilih prediksi yang ingin Anda tinjau.
   - **Nama prediksi:** nama prediksi yang diberikan saat membuatnya.
   - **Jenis prediksi:** jenis model yang digunakan untuk prediksi
   - **Entitas output:** nama entitas untuk menyimpan output dari prediksi. Anda dapat menemukan entitas dengan nama ini pada **data** > **entitas**.
   - **bidang terprediksi:** bidang ini hanya diisi untuk beberapa jenis prediksi, dan tidak digunakan dalam prediksi kehilangan pelanggan.
   - **Status:** status saat ini prediksi berjalan.
        - **Mengantri:** prediksi saat ini sedang menunggu proses lainnya untuk dijalankan.
        - **Menyegarkan:** prediksi saat ini menjalankan tahapan pemrosesan "Skor" untuk menghasilkan hasil yang akan mengalir ke entitas output.
        - **Gagal:** prediksi gagal. Pilih **Log** untuk rincian lebih lanjut.
        - **Berhasil:** prediksi telah berhasil. Pilih **Lihat** di bawah elips vertikal untuk meninjau prediksi
   - **Diedit:** tanggal konfigurasi untuk prediksi telah diubah.
   - **Terakhir Diperbarui:** tanggal prediksi yang disegarkan dihasilkan dalam entitas output.

1. Pilih elips vertikal di samping prediksi yang ingin Anda tinjau hasilnya dan pilih **Lihat**.
   > [!div class="mx-imgBorder"]
   > ![Lihat pilihan dalam menu elipsis vertikal untuk prediksi termasuk Edit, segarkan, tampilan, log, dan Hapus](media/product-recommendation-verticalellipses.PNG "Lihat pilihan dalam menu elipsis vertikal untuk prediksi termasuk Edit, segarkan, tampilan, log, dan Hapus")

1. Terdapat tiga bagian utama data dalam halaman hasil:
    1. **Performa model pelatihan:** A, B, atau C adalah Skor yang mungkin. Skor ini menunjukkan performa prediksi, dan dapat membantu Anda membuat keputusan untuk menggunakan hasil yang tersimpan di entitas output.
        - Skor ditentukan berdasarkan aturan berikut:
            - **A** Model akan dianggap sebagai Kualitas **A** jika metrik "Berhasil @ K" sekurangnya 10% lebih dari dasar. 
            - **B** Model akan dianggap sebagai Kualitas **B** jika metrik "Berhasil @ K" adalah 0 hingga 10% dari dasar.
            - **C** Model akan dianggap sebagai Kualitas **C** jika metrik "Berhasil @ K" kurang dari dasar.
               
               > [!div class="mx-imgBorder"]
               > ![Tampilan hasil kinerja model](media/product-recommendation-modelperformance.PNG "Tampilan hasil kinerja model")
            - **Dasar**: Model mengambil produk yang paling direkomendasikan teratas menurut jumlah pembelian di seluruh pelanggan, dan menggunakan aturan yang diidentifikasi berdasarkan model untuk membuat rangkaian rekomendasi untuk pelanggan. Selanjutnya, prediksi akan dibandingkan dengan produk teratas, sebagaimana dihitung menurut jumlah pelanggan yang membeli produk tersebut. Jika pelanggan memiliki minimal satu produk dalam produk rekomendasinya yang juga terlihat di produk pembelian teratas, maka produk tersebut dianggap sebagai bagian dari dasar. Jika ada 10 pelanggan tersebut yang memiliki rekomendasi pembelian produk dari 100 total pelanggan, maka dasar akan menjadi 10%.
            - **Berhasil @ K**: Menggunakan rangkaian validasi periode waktu transaksi, rekomendasi dibuat untuk semua pelanggan dan dibandingkan dengan rangkaian validasi transaksi. Contohnya, dalam periode 12 bulan, bulan 12 dapat disisihkan sebagai rangkaian validasi data. Jika model memperkirakan sekurangnya satu hal yang akan Anda beli dalam bulan 12 berdasarkan apa yang ia pelajari dari 11 bulan sebelumnya, pelanggan akan meningkatkan metrik "Berhasil @ K".
    
    1. **Produk yang paling disarankan (dengan hitungan):** 5 produk teratas yang diperkirakan untuk pelanggan Anda.
       > [!div class="mx-imgBorder"]
       > ![Grafik yang menampilkan 5 produk rekomendasi teratas](media/product-recommendation-topproducts.PNG "Grafik yang menampilkan 5 produk rekomendasi teratas")
    
    1. **Rekomendasi produk dengan tingkat keyakinan tinggi:** Sampel rekomendasi yang diberikan kepada pelanggan yang diyakini oleh model kemungkinan dibeli oleh pelanggan.
       > [!div class="mx-imgBorder"]
       > ![Daftar yang menampilkan saran dengan keyakinan tinggi untuk rangkaian pelanggan individual tertentu](media/product-recommendation-highconfidence.PNG "Daftar yang menampilkan saran dengan keyakinan tinggi untuk rangkaian pelanggan individual tertentu")

## <a name="fix-a-failed-prediction"></a>Perbaiki prediksi yang gagal

1. Buka tab **prediksi saya** pada **intelijen** > **prediksi**.

1. Pilih prediksi yang ingin Anda lihat log kesalahannya dan pilih **log**.

1. Memeriksa semua kesalahan. Ada beberapa jenis kesalahan yang dapat terjadi, dan menjelaskan kondisi yang menyebabkan kesalahan. Misalnya, kesalahan bahwa tidak ada cukup data yang dapat diprediksi secara akurat biasanya ditangani dengan memuat data tambahan ke dalam Customer Insights.

## <a name="refresh-a-prediction"></a>Segarkan prediksi

Prediksi akan me-refresh secara otomatis pada [jadwal yang sama saat data Anda di-refresh](system.md#schedule-tab) sebagaimana dikonfigurasi dalam pengaturan.

1. Buka tab **prediksi saya** pada **intelijen** > **prediksi**.

1. Pilih elipsis vertikal di sebelah prediksi yang ingin Anda segarkan.

1. Pilih **Segarkan**.

## <a name="delete-a-prediction"></a>Hapus prediksi

Menghapus prediksi juga akan menghapus entitas keluarannya.

1. Buka tab **prediksi saya** pada **intelijen** > **prediksi**.

1. Pilih elipsis vertikal di sebelah prediksi yang ingin Anda hapus.

1. Pilih **Hapus**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]