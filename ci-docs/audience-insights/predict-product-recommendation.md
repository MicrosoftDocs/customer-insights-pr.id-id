---
title: prediksi Rekomendasi produk
description: Memperkirakan produk yang mungkin dibeli atau berinteraksi dengan pelanggan.
ms.date: 03/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 60d511181aa85e3e939eff3e5931f0de7807c01c8f38134ebca5c5604cd53871
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034960"
---
# <a name="product-recommendation-prediction-preview"></a>prediksi Rekomendasi produk (pratinjau)

Model rekomendasi produk membuat rangkaian rekomendasi produk prediktif. Rekomendasi didasarkan pada perilaku pembelian sebelumnya dan pelanggan dengan pola pembelian yang serupa. Anda dapat membuat prediksi rekomendasi produk baru pada halaman **Intelijen** > **Prediksi**. Pilih **prediksi saya** untuk melihat prediksi lain yang Anda buat.

Rekomendasi produk dapat dipengaruhi oleh hukum dan peraturan setempat dan harapan pelanggan, yang modelnya tidak dibangun untuk memperhitungkan secara khusus.  Sebagai pengguna kemampuan prediktif ini, **Anda harus meninjau rekomendasi sebelum mengirimkannya kepada pelanggan Anda** untuk memastikan bahwa Anda mematuhi hukum atau peraturan yang berlaku, dan harapan pelanggan atas apa yang mungkin Anda rekomendasikan. 

Selain itu, output model ini akan memberikan rekomendasi berdasarkan ID produk. Mekanisme pengiriman Anda perlu memetakan ID produk yang diprediksi ke konten yang sesuai untuk pelanggan Anda untuk memperhitungkan pelokalan, konten gambar, dan konten atau perilaku khusus bisnis lainnya.

## <a name="sample-guide"></a>Panduan Sampel

Jika Anda ingin mencoba fitur ini tetapi tidak memiliki data untuk melengkapi persyaratan di bawah, Anda dapat [membuat implementasi sampel](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md) di Customer Insights.

- Pengetahuan bisnis untuk memahami berbagai jenis produk untuk bisnis Anda dan cara pelanggan Berinteraksi dengan mereka. Kami mendukung rekomendasi produk yang telah dibeli sebelumnya oleh pelanggan atau rekomendasi untuk produk baru.

- Data tentang transaksi, pembelian dan Riwayat mereka:
    - Pengidentifikasi transaksi untuk membedakan pembelian atau transaksi.
    - Pengidentifikasi pelanggan untuk memetakan transaksi dengan pelanggan Anda.
    - Tanggal aktivitas transaksi, yang menentukan tanggal terjadinya transaksi.
    - Informasi ID produk untuk transaksi.
    - (Opsional) Entitas data katalog produk untuk menggunakan filter produk.
    - (Opsional) Jika transaksi adalah retur atau tidak.
    - Skema data semantik memerlukan informasi berikut:
        - **ID transaksi:** pengidentifikasi unik pembelian atau transaksi.
        - **Tanggal transaksi:** tanggal pembelian atau transaksi.
        - **Nilai transaksi:** nilai numerik dari pembelian atau transaksi.
        - **ID Produk unik:** id produk atau layanan yang dibeli jika data Anda berada pada tingkat item baris.
        - (Opsional) **Pembelian atau retur:** Bidang boolean di mana nilai yang *benar* mengidentifikasi bahwa transaksi adalah retur. Jika data Pembelian atau Retur tidak disediakan model dan **Nilai transaksi** negatif, kita juga akan menggunakan informasi ini untuk menyimpulkan retur.
- Karakteristik Data yang Disarankan:
    - Data historis yang cukup: Setidaknya satu tahun data transaksional, sebaiknya dua hingga tiga tahun untuk memasukkan beberapa musiman.
    - Beberapa pembelian per pelanggan: Tiga atau lebih transaksi per ID Pelanggan
    - Jumlah pelanggan: Setidaknya 100 pelanggan, lebih disukai lebih dari 10.000 pelanggan. Model akan gagal dengan kurang dari 100 pelanggan.

> [!NOTE]
> - Model ini memerlukan riwayat transaksi pelanggan Anda. Definisi transaksi cukup fleksibel. Data apa pun yang menjelaskan interaksi produk pengguna dapat berfungsi sebagai input. Misalnya, membeli produk, mengikuti kelas, atau menghadiri acara.
> - Hanya satu entitas riwayat transaksi yang dapat dikonfigurasi saat ini. Jika ada beberapa entitas pembelian, satukan di Power Query sebelum menyerap data.
> - Jika detail pesanan dan pesanan adalah entitas yang berbeda, gabunglah mereka sebelum digunakan dalam model. Model tidak hanya berfungsi dengan ID pesanan atau ID tanda terima dalam entitas.


## <a name="create-a-product-recommendation-prediction"></a>buat prediksi Rekomendasi produk

1. Di Customer Insights, buka **Intelijen** > **Prediksi**.

1. Pilih petak **model rekomendasi produk (pratinjau)** dan pilih **gunakan model ini**.
   > [!div class="mx-imgBorder"]
   > ![petak model Rekomendasi Produk dengan Tombol Gunakan model ini.](media/product-recommendation-usethismodel.PNG "petak model Rekomendasi Produk dengan Tombol Gunakan model ini")

1. Tinjau informasi tentang persyaratan model. Jika Anda memiliki data yang diperlukan, pilih **Mulai**.

### <a name="name-model"></a>Beri nama model

1. Berikan nama model untuk membedakannya dari model lain.

1. Masukkan nama untuk entitas output hanya menggunakan huruf dan angka, tanpa spasi apa pun. Itulah nama yang akan digunakan oleh entitas model. Kemudian pilih **Berikutnya**.

### <a name="define-product-recommendation-configuration"></a>Tentukan konfigurasi rekomendasi produk

1. Atur **Jumlah produk** yang akan direkomendasikan ke pelanggan. Nilai ini tergantung pada cara metode pengiriman Anda mengisi data. Jika Anda dapat merekomendasikan tiga produk, atur nilai ini dengan sesuai.
   
   >[!TIP]
   > Anda dapat memilih **Simpan dan tutup** Kapan pun untuk menyimpan prediksi sebagai draf. Anda akan menemukan draf prediksi di tab **prediksi saya**.

1. Pilih jika Anda ingin **menyarankan produk yang baru saja dibeli pelanggan**.

1. Jika Anda memilih untuk *tidak* menyarankan produk yang baru dibeli, atur **Periode Lihat kembali**. Pengaturan ini menentukan jangka waktu yang dipertimbangkan model sebelum merekomendasikan produk kepada pengguna lagi. Misalnya, tunjukkan pelanggan membeli laptop setiap dua tahun. Jendela ini akan melihat riwayat pembelian selama dua tahun terakhir, dan jika mereka menemukan item, item akan difilter dari rekomendasi.

1. Pilih **berikutnya**

### <a name="add-required-data"></a>Tambahkan data wajib

1. Pilih **Tambah data** untuk **Riwayat transaksi pelanggan** dan pilih entitas yang menyediakan informasi riwayat transaksi/pembelian sebagaimana dijelaskan dalam [prasyarat](#prerequisites).

1. Petakan bidang semantik ke atribut dalam entitas Riwayat Pembelian Anda dan pilih **berikutnya**. Untuk Deskripsi bidang, lihat [prasyarat](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Tentukan relasi entitas.](media/product-recommendation-purchasehistorymapping.PNG "Halaman riwayat pembelian yang menampilkan atribut semantis yang dipetakan ke bidang dalam entitas riwayat pembelian yang dipilih")

1. Jika bidang tidak diisi, konfigurasikan relasi dari entitas Riwayat Pembelian Anda ke entitas *pelanggan*.
    1. Pilih **Entitas riwayat pembelian**.
    1. Pilih **bidang** yang mengidentifikasi pelanggan di entitas riwayat pembelian. Ini perlu dikaitkan dengan ID pelanggan utama entitas *pelanggan* Anda.
    1. Pilih **entitas pelanggan** yang cocok dengan entitas pelanggan utama Anda.
    1. Masukkan nama yang mendeskripsikan relasi.
       > [!div class="mx-imgBorder"]
       > ![Halaman Riwayat pembelian yang menunjukkan pembuatan relasi dengan pelanggan.](media/model-purchase-join.png "Halaman Riwayat pembelian yang menunjukkan pembuatan relasi dengan pelanggan")

1. Pilih **Simpan**.

1. Pilih **Selanjutnya**.

### <a name="configure-product-filters"></a>Konfigurasikan filter produk

Terkadang, hanya produk tertentu yang bermanfaat atau sesuai untuk jenis prediksi yang Anda bangun. Filter produk memungkinkan Anda mengidentifikasi subkumpulan produk dengan karakteristik khusus untuk direkomendasikan kepada pelanggan Anda. Model ini akan menggunakan semua produk yang tersedia untuk mempelajari pola tetapi hanya menggunakan produk yang cocok dengan filter produk dalam outputnya.

1. Dalam langkah **Tambahkan informasi produk**, tambahkan katalog produk Anda dengan informasi untuk setiap produk. Petakan informasi yang diperlukan dan pilih **Berikutnya**.

3. Di langkah **Filter produk**, pilih di antara opsi berikut.

   * **Tidak ada filter**: Gunakan semua produk dalam prediksi rekomendasi produk.

   * **Tentukan filter produktertentu**: Gunakan produk tertentu dalam prediksi rekomendasi produk.

1. Pilih **Selanjutnya**.

1. Jika Anda memilih untuk menentukan filter produk, Anda perlu mendefinisikannya sekarang. Di panel **atribut katalog Produk**, pilih atribut dari *entitas Katalog Produk* yang ingin Anda sertakan dalam filter.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Panel samping ditampilkan diatribusikan dalam entitas katalog produk untuk memilih filter produk.":::

1. Pilih apakah Anda ingin filter produk menggunakan konektor **and** atau **or** untuk secara logis menggabungkan pilihan atribut Anda dari katalog produk.
   
   :::image type="content" source="media/product-filters-sample.png" alt-text="Contoh konfigurasi filter produk dikombinasikan dengan konektor AND logis.":::

1. Pilih **Selanjutnya**.

### <a name="set-update-schedule-and-review-configuration"></a>Mengatur jadwal pembaruan dan meninjau konfigurasi

1. Atur frekuensi untuk melatih ulang model Anda. Pengaturan ini penting untuk memperbarui keakuratan prediksi karena data baru diimpor ke Customer Insights. Sebagian besar bisnis dapat melatih sekali per bulan dan mendapatkan akurasi yang baik untuk prediksi mereka.

1. Pilih **Selanjutnya**.

1. Tinjau Konfigurasi. Anda dapat kembali ke bagian apa pun dari konfigurasi prediksi dengan memilih **Edit** dalam nilai yang ditampilkan. Atau Anda dapat memilih langkah konfigurasi dari indikator progres.

1. Jika semua nilai dikonfigurasi dengan benar, pilih **Simpan dan jalankan** untuk memulai proses prediksi. Pada **tab prediksi saya**, Anda dapat melihat status prediksi Anda. Proses dapat berlangsung selama beberapa jam hingga selesai, tergantung pada jumlah data yang digunakan dalam prediksi.

## <a name="review-a-prediction-status-and-results"></a>Meninjau status dan hasil prediksi

1. Buka tab **prediksi saya** pada **intelijen** > **prediksi**.
   > [!div class="mx-imgBorder"]
   > ![Tampilan halaman prediksi saya.](media/product-recommendation-mypredictions.PNG "Tampilan halaman prediksi saya")

1. Pilih prediksi yang ingin Anda tinjau.
   - **Nama prediksi:** nama prediksi yang diberikan saat membuatnya.
   - **Jenis prediksi:** jenis model yang digunakan untuk prediksi
   - **Entitas output:** nama entitas untuk menyimpan output dari prediksi. Anda dapat menemukan entitas dengan nama ini pada **data** > **entitas**.    
      *Skor* dalam entitas output adalah ukuran kuantitatif dari rekomendasi. Model ini merekomendasikan produk dengan skor yang lebih tinggi atas produk dengan skor yang lebih rendah.
   - **Bidang yang diprediksi**: Bidang ini hanya diisi untuk beberapa jenis prediksi, dan tidak digunakan dalam prediksi Rekomendasi Produk.
   - **Status:** status saat ini prediksi berjalan.
        - **Mengantri:** prediksi saat ini sedang menunggu proses lainnya untuk dijalankan.
        - **Menyegarkan:** prediksi saat ini menjalankan tahapan pemrosesan "Skor" untuk menghasilkan hasil yang akan mengalir ke entitas output.
        - **Gagal:** prediksi gagal. Pilih **Log** untuk rincian lebih lanjut.
        - **Berhasil:** prediksi telah berhasil. Pilih **Lihat** di bawah elips vertikal untuk meninjau prediksi
   - **Diedit:** tanggal konfigurasi untuk prediksi telah diubah.
   - **Terakhir Diperbarui:** tanggal prediksi yang disegarkan dihasilkan dalam entitas output.

1. Pilih elips vertikal di samping prediksi yang ingin Anda tinjau hasilnya dan pilih **Lihat**.
   > [!div class="mx-imgBorder"]
   > ![Lihat pilihan dalam menu elipsis vertikal untuk prediksi termasuk Edit, segarkan, tampilan, log, dan Hapus.](media/product-recommendation-verticalellipses.PNG "Lihat pilihan dalam menu elipsis vertikal untuk prediksi termasuk Edit, segarkan, tampilan, log, dan Hapus")

1. Ada lima bagian utama data dalam halaman hasil:
    1. **Performa model pelatihan:** A, B, atau C adalah Skor yang mungkin. Skor ini menunjukkan performa prediksi, dan dapat membantu Anda membuat keputusan untuk menggunakan hasil yang tersimpan di entitas output.
        - Skor ditentukan berdasarkan aturan berikut:
            - **A** Model akan dianggap sebagai Kualitas **A** jika metrik "Berhasil @ K" sekurangnya 10% lebih dari dasar. 
            - **B** Model akan dianggap sebagai Kualitas **B** jika metrik "Berhasil @ K" adalah 0% hingga 10% dari dasar.
            - **C** Model akan dianggap sebagai Kualitas **C** jika metrik "Berhasil @ K" adalah kurang dari dasar.
               
               > [!div class="mx-imgBorder"]
               > ![Tampilan hasil kinerja model.](media/product-recommendation-modelperformance.PNG "Tampilan hasil kinerja model")
            - **Dasar**: Model mengambil produk yang paling direkomendasikan teratas menurut jumlah pembelian di seluruh pelanggan, dan menggunakan aturan yang diidentifikasi berdasarkan model untuk membuat rangkaian rekomendasi untuk pelanggan. Selanjutnya, prediksi akan dibandingkan dengan produk teratas, sebagaimana dihitung menurut jumlah pelanggan yang membeli produk tersebut. Jika pelanggan memiliki minimal satu produk dalam produk rekomendasinya yang juga terlihat di produk pembelian teratas, maka produk tersebut dianggap sebagai bagian dari dasar. Jika ada 10 pelanggan tersebut yang memiliki rekomendasi pembelian produk dari 100 total pelanggan, maka dasar akan menjadi 10%.
            - **Berhasil @ K**: Menggunakan rangkaian validasi periode waktu transaksi, rekomendasi dibuat untuk semua pelanggan dan dibandingkan dengan rangkaian validasi transaksi. Contohnya, dalam periode 12 bulan, bulan 12 dapat disisihkan sebagai rangkaian validasi data. Jika model memperkirakan sekurangnya satu hal yang akan Anda beli dalam bulan 12 berdasarkan apa yang ia pelajari dari 11 bulan sebelumnya, pelanggan akan meningkatkan metrik "Berhasil @ K".
    
    1. **Sebagian besar produk yang disarankan (dengan tally):** Lima produk teratas yang diprediksi untuk pelanggan Anda.
       > [!div class="mx-imgBorder"]
       > ![Grafik yang menampilkan 5 produk rekomendasi teratas.](media/product-recommendation-topproducts.PNG "Grafik yang menampilkan 5 produk rekomendasi teratas")
    
    1. **Faktor rekomendasi utama**: Model menggunakan riwayat transaksi pelanggan untuk membuat rekomendasi produk. Ini mempelajari pola berdasarkan pembelian sebelumnya dan menemukan kesamaan antara pelanggan dan produk. Kesamaan ini kemudian digunakan untuk menghasilkan rekomendasi produk.
    Berikut ini adalah faktor-faktor yang dapat mempengaruhi rekomendasi produk yang dihasilkan oleh model. 
        - **Transaksi sebelumnya**: Pola pembelian di masa lalu dimanfaatkan oleh model untuk menghasilkan rekomendasi produk. Misalnya, model dapat merekomendasikan _Surface Arc Mouse_ jika seseorang baru saja membeli _Surface Book 3_ dan _Surface Pen_. Model ini mengetahui bahwa secara historis, banyak pelanggan telah membeli _Surface Arc Mouse_ setelah membeli _Surface Book 3_ dan _Surface Pen_.
        - **Kesamaan pelanggan**: Produk yang direkomendasikan secara historis dibeli oleh pelanggan lain yang menunjukkan pola pembelian serupa. Misalnya, John direkomendasikan _Surface Headphones 2_ karena Jennifer dan Brad baru-baru ini membeli _Surface Headphones 2_. Model ini percaya John mirip dengan Jennifer dan Brad karena mereka secara historis memiliki pola pembelian yang sama.
        - **Kesamaan produk**: Produk yang direkomendasikan mirip dengan produk lain yang dibeli pelanggan sebelumnya. Model ini menganggap dua produk mirip jika dibeli bersama atau oleh pelanggan serupa. Misalnya, seseorang mendapatkan rekomendasi untuk _Drive Penyimpanan USB_ karena mereka sebelumnya membeli _Adaptor USB-C ke USB_ dan model percaya bahwa _Drive Penyimpanan USB_ mirip dengan _Adaptor USB-C ke USB_ berdasarkan pola pembelian historis.

        Setiap rekomendasi produk dipengaruhi oleh satu atau lebih faktor-faktor ini. Persentase rekomendasi di mana setiap faktor yang mempengaruhi memainkan peran divisualisasikan dalam bagan. Dalam contoh berikut, 100% dari rekomendasi dipengaruhi oleh transaksi sebelumnya, 60% oleh kesamaan pelanggan dan 22% berdasarkan kesamaan produk. Arahkan kursor ke bilah di bagan untuk melihat persentase yang tepat di mana faktor yang memengaruhi berkontribusi.

        > [!div class="mx-imgBorder"]
        > ![Faktor rekomendasi utama.](media/product-recommendation-keyrecommendationfactors.png "Faktor rekomendasi utama yang dipelajari oleh model untuk menghasilkan rekomendasi produk")
       
     
   1. **Statistik data**: Memberikan gambaran jumlah transaksi, pelanggan, dan produk yang dipertimbangkan model. Hal ini didasarkan pada data input yang digunakan untuk mempelajari pola dan menghasilkan rekomendasi produk.

      > [!div class="mx-imgBorder"]
      > ![Statistik data.](media/product-recommendation-datastatistics.png "Statistik data di sekitar data input yang digunakan oleh model untuk mempelajari pola")

      Bagian ini menunjukkan statistik di sekitar titik data yang digunakan oleh model untuk mempelajari pola dan menghasilkan rekomendasi produk. Pemfilteran, seperti yang dikonfigurasi dalam konfigurasi model, akan berlaku pada output yang dihasilkan oleh model. Namun, model ini menggunakan semua data yang tersedia untuk mempelajari pola. Oleh karena itu, jika Anda menggunakan pemfilteran produk dalam konfigurasi model, bagian ini akan menunjukkan jumlah total produk yang dianalisis model untuk mempelajari pola, yang mungkin berbeda dari jumlah produk yang sesuai dengan kriteria pemfilteran yang ditentukan.

   1. **Rekomendasi produk dengan tingkat keyakinan tinggi:** Sampel rekomendasi yang diberikan kepada pelanggan yang diyakini oleh model kemungkinan dibeli oleh pelanggan.    
      Jika katalog produk ditambahkan, ID produk diganti dengan nama produk. Nama produk memberikan informasi yang lebih dapat ditindaklanjuti dan intuitif tentang prediksi.
       > [!div class="mx-imgBorder"]
       > ![Daftar yang menampilkan saran dengan keyakinan tinggi untuk rangkaian pelanggan individual tertentu.](media/product-recommendation-highconfidence.PNG "Daftar yang menampilkan saran dengan keyakinan tinggi untuk rangkaian pelanggan individual tertentu")

## <a name="manage-predictions"></a>Kelola prediksi

Anda dapat mengoptimalkan, memecahkan masalah, menyegarkan, atau menghapus prediksi. Tinjau laporan kegunaan data input untuk mengetahui cara membuat prediksi lebih cepat dan lebih dapat diandalkan. Untuk informasi lebih lanjut, lihat [Kelola prediksi](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
