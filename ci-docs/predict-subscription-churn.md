---
title: Prediksi churn langganan (berisi video)
description: Memprediksi apakah pelanggan kemungkinan besar tidak lagi menggunakan produk atau layanan langganan perusahaan Anda.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 415cd5d675512b4f434998afaa8265c8e45c562b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643819"
---
# <a name="subscription-churn-prediction"></a>Prediksi kehilangan langganan

Prediksi kehilangan langganan membantu memprediksi apakah pelanggan kemungkinan besar tidak lagi menggunakan produk atau layanan langganan perusahaan Anda. Anda dapat membuat prediksi kehilangan langganan baru pada halaman **intelijen** > **prediksi**. Pilih **prediksi saya** untuk melihat prediksi lain yang Anda buat.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Cobalah tutorial untuk prediksi kehilangan pelanggan berlangganan menggunakan data sampel: [panduan sampel prediksi kehilangan pelanggan langganan](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md).
- Pengetahuan bisnis untuk memahami apa arti kehilangan untuk bisnis Anda. Kami mendukung definisi kehilangan berdasarkan waktu, yang berarti pelanggan dianggap telah bergejolak selama beberapa waktu setelah langganan mereka berakhir.
- Data tentang langganan Anda dan Riwayat mereka:
    - Pengidentifikasi langganan untuk membedakan langganan.
    - Pengidentifikasi pelanggan untuk mencocokkan langganan dengan pelanggan Anda.
    - Tanggal acara langganan, yang menentukan tanggal mulai, tanggal berakhir, dan tanggal aktivitas langganan terjadi.
    - Informasi langganan untuk menentukan apakah langganan berulang dan frekuensi perpanjangan dilakukan.
    - Skema data semantik untuk langganan memerlukan informasi berikut ini:
        - **ID langganan:** pengidentifikasi unik langganan.
        - **Tanggal berakhir langganan:** tanggal kedaluwarsa langganan untuk pelanggan.
        - **Tanggal awal langganan:** tanggal awal langganan untuk pelanggan.
        - **Tanggal transaksi:** tanggal perubahan langganan terjadi. Misalnya, pelanggan membeli atau membatalkan langganan.
        - **Apakah langganan berulang:** bidang benar/salah Boolean yang menentukan apakah langganan akan diperpanjang dengan ID langganan yang sama tanpa intervensi pelanggan
        - **Frekuensi pengulangan (dalam bulan):** untuk langganan yang berulang, periode waktu langganan akan diperpanjang. Ini diwakili dalam bulan. Misalnya, langganan tahunan yang secara otomatis diperpanjang untuk pelanggan setiap tahun untuk satu tahun lagi memiliki nilai 12.
        - (Opsional) **Jumlah langganan:** jumlah mata uang yang dibayarkan pelanggan untuk perpanjangan langganan. Hal ini dapat membantu mengidentifikasi pola untuk tingkat langganan yang berbeda.
- Data tentang aktivitas pelanggan:
    - Pengidentifikasi aktivitas untuk membedakan aktivitas dari jenis yang sama.
    - Pengidentifikasi pelanggan untuk memetakan aktivitas dengan pelanggan Anda.
    - Informasi aktivitas berisi nama dan tanggal aktivitas.
    - Skema data semantik untuk aktivitas pelanggan mencakup:
        - **Kunci primer:** pengidentifikasi unik untuk aktivitas. Misalnya, kunjungan situs web atau rekaman penggunaan yang menampilkan pelanggan melihat episode acara TV.
        - **Cap waktu:** tanggal dan waktu aktivitas yang diidentifikasi oleh kunci primer.
        - **Aktivitas**: nama aktivitas yang ingin Anda gunakan. Misalnya, bidang yang disebut "UserAction" di layanan video streaming dapat memiliki nilai "dilihat".
        - **Rincian:** informasi rinci tentang aktivitas. Misalnya, bidang yang disebut "ShowTitle" di layanan video streaming dapat memiliki nilai video yang ditonton pelanggan.
- Karakteristik Data yang Disarankan:
    - Data historis yang memadai: Data langganan untuk setidaknya dua kali lipat dari periode waktu yang dipilih. Sebaiknya, dua hingga tiga tahun data langganan.
    - Status langganan: Data menyertakan langganan aktif dan tidak aktif untuk setiap pelanggan sehingga ada beberapa entri per ID pelanggan.
    - Jumlah pelanggan: Setidaknya 10 profil pelanggan, lebih disukai lebih dari 1.000 pelanggan unik. Model akan gagal dengan kurang dari 10 pelanggan dan data historis yang tidak mencukupi.
    - Kelengkapan data: Kurang dari 20% nilai yang hilang di bidang data entitas yang disediakan.
   
   > [!NOTE]
   > Anda harus memiliki setidaknya dua rekaman aktivitas untuk 50% Pelanggan yang ingin Anda hitung angka kehilangannya.

## <a name="create-a-subscription-churn-prediction"></a>Buat prediksi kehilangan langganan

1. Pergi ke **IntelligencePredictions** > **·**.
1. Pilih petak **model** churn langganan dan pilih **Gunakan model ini**.
   > [!div class="mx-imgBorder"]
   > ![Ubin model kehilangan langganan dengan tombol Gunakan tombol model ini.](media/subscription-churn-usethismodel.PNG "Ubin model kehilangan langganan dengan tombol Gunakan tombol model ini")

### <a name="name-model"></a>Beri nama model

1. Berikan nama model untuk membedakannya dari model lain.
1. Berikan nama untuk entitas output hanya menggunakan huruf dan angka, tanpa spasi. Itulah nama yang akan digunakan oleh entitas model. Kemudian pilih **Berikutnya**.

### <a name="define-customer-churn"></a>Tentukan kehilangan pelanggan

1. Masukkan jumlah **hari sejak langganan berakhir** sehingga bisnis Anda mempertimbangkan pelanggan untuk berada dalam status bergejolak. Periode ini biasanya disukai untuk aktivitas bisnis seperti Penawaran atau upaya pemasaran lainnya yang mencoba mencegah hilangnya pelanggan.
1. Masukkan jumlah **hari untuk menyelidiki masa depan untuk memprediksi kehilangan pelanggan** untuk mengatur periode untuk memprediksi kehilangan pelanggan. Contohnya, untuk memprediksi risiko kehilangan pelanggan untuk pelanggan Anda selama 90 hari berikutnya untuk menyelaraskan upaya retensi Marketing Anda. Memprediksi risiko kehilangan untuk jangka waktu yang lebih lama atau lebih singkat dapat membuatnya lebih sulit untuk mengatasi faktor-faktor dalam profil risiko kehilangan Anda, tergantung pada persyaratan bisnis spesifik Anda. Untuk melanjutkan, klik **Berikutnya**
   >[!TIP]
   > Anda dapat memilih **Simpan draf** kapan saja untuk menyimpan prediksi sebagai draf. Anda akan menemukan draf prediksi dalam tab **prediksi saya** untuk melanjutkan.

### <a name="add-required-data"></a>Tambahkan data yang diperlukan

1. Pilih **Tambah data** untuk **Riwayat langganan** dan pilih entitas yang menyediakan informasi Riwayat langganan sebagaimana dijelaskan dalam [prasyarat](#prerequisites).
1. Jika bidang di bawah ini tidak terisi, konfigurasikan relasi dari entitas histori langganan Anda ke entitas pelanggan.
    1. Pilih **entitas riwayat langganan**.
    1. Pilih **bidang** yang mengidentifikasi pelanggan di entitas riwayat langganan. Ini perlu dikaitkan dengan ID pelanggan utama entitas pelanggan Anda.
    1. Pilih **entitas pelanggan** yang cocok dengan entitas pelanggan utama Anda.
    1. Masukkan nama yang mendeskripsikan relasi.
       > [!div class="mx-imgBorder"]
       > ![Halaman Riwayat langganan yang menampilkan pembuatan relasi dengan pelanggan.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Halaman Riwayat langganan yang menampilkan pembuatan relasi dengan pelanggan")
1. Pilih **Selanjutnya**.
1. Petakan bidang semantik ke atribut di dalam entitas riwayat langganan Anda dan pilih **Simpan**. Untuk Deskripsi bidang, lihat [prasyarat](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Halaman Riwayat langganan menampilkan atribut semantik yang dipetakan ke bidang pada entitas riwayat langganan yang dipilih.](media/subscription-churn-subscriptionhistorymapping.PNG "Halaman Riwayat langganan menampilkan atribut semantik yang dipetakan ke bidang pada entitas riwayat langganan yang dipilih")
1. Pilih **Tambah data** untuk **aktivitas pelanggan** dan pilih entitas yang menyediakan informasi aktivitas pelanggan sebagaimana dijelaskan dalam prasyarat.
1. Pilih jenis aktivitas yang cocok dengan jenis aktivitas Pelanggan yang Anda konfigurasikan.  Pilih **Buat baru** dan berikan nama jika Anda tidak melihat pilihan yang sesuai dengan jenis aktivitas yang Anda butuhkan.
1. Anda harus mengkonfigurasi relasi dari entitas aktivitas pelanggan Anda ke entitas pelanggan.
    1. Pilih bidang yang mengidentifikasi pelanggan di tabel aktivitas pelanggan, yang dapat langsung terkait dengan ID pelanggan utama entitas pelanggan Anda.
    1. Pilih entitas pelanggan yang cocok dengan entitas pelanggan utama Anda
    1. Masukkan nama yang mendeskripsikan relasi.
1. Pilih **Selanjutnya**.
1. Petakan bidang semantik ke atribut di dalam entitas aktivitas pelanggan Anda dan pilih **Simpan**. Untuk Deskripsi bidang, lihat [prasyarat](#prerequisites).
1. (Opsional)Jika Anda memiliki aktivitas pelanggan lain yang ingin Anda masukkan, ulangi langkah di atas.
   > [!div class="mx-imgBorder"]
   > ![Tentukan relasi entitas.](media/subscription-churn-customeractivitiesmapping.PNG "Halaman Aktivitas pelanggan menampilkan atribut semantik yang dipetakan ke bidang pada entitas aktivitas pelanggan yang dipilih")
1. Pilih **Selanjutnya**.

### <a name="set-schedule-and-review-configuration"></a>Mengatur konfigurasi jadwal dan ulasan

1. Atur frekuensi untuk melatih ulang model Anda. Pengaturan ini penting untuk memperbarui keakuratan prediksi karena data baru dicerna dalam Wawasan Pelanggan. Sebagian besar bisnis dapat melatih sekali per bulan dan mendapatkan akurasi yang baik untuk prediksi mereka.
1. Pilih **Selanjutnya**.
1. Tinjau Konfigurasi. Anda dapat kembali ke bagian apa pun dari konfigurasi prediksi dengan memilih **Edit** dalam nilai yang ditampilkan. Atau Anda dapat memilih langkah konfigurasi dari indikator progres.
1. Jika semua nilai dikonfigurasi dengan benar, pilih **Simpan dan jalankan** untuk memulai proses prediksi. Pada **tab prediksi saya**, Anda dapat melihat status prediksi Anda. Proses dapat berlangsung selama beberapa jam hingga selesai, tergantung pada jumlah data yang digunakan dalam prediksi.

## <a name="review-a-prediction-status-and-results"></a>Meninjau status dan hasil prediksi

1. Buka tab **prediksi saya** pada **intelijen** > **prediksi**.
   > [!div class="mx-imgBorder"]
   > ![Tampilan halaman prediksi saya.](media/subscription-churn-mypredictions.PNG "Tampilan halaman prediksi saya")
1. Pilih prediksi yang ingin Anda tinjau.
   - **Nama prediksi:** nama prediksi yang diberikan saat membuatnya.
   - **Jenis prediksi:** jenis model yang digunakan untuk prediksi
   - **Entitas output:** nama entitas untuk menyimpan output dari prediksi. Anda dapat menemukan entitas dengan nama ini pada **data** > **entitas**.    
     Dalam entitas output, *ChurnScore* adalah probabilitas kehilangan yang diprediksi dan *IsChurn* adalah label biner berdasarkan *ChurnScore* dengan ambang batas 0,5. Ambang batas default mungkin tidak berfungsi untuk skenario Anda. [Buat segmen baru](segments.md#create-a-new-segment) dengan ambang batas pilihan Anda.
   - **Bidang yang diprediksi:** bidang ini hanya diisi untuk beberapa jenis prediksi, dan tidak digunakan dalam prediksi kehilangan langganan.
   - **Status:** status saat ini prediksi berjalan.
        - **Mengantri:** prediksi saat ini sedang menunggu proses lainnya untuk dijalankan.
        - **Menyegarkan:** prediksi saat ini menjalankan tahapan pemrosesan "Skor" untuk menghasilkan hasil yang akan mengalir ke entitas output.
        - **Gagal:** prediksi gagal. Pilih **Log** untuk rincian lebih lanjut.
        - **Berhasil:** prediksi telah berhasil. Pilih **Lihat** di bawah elips vertikal untuk meninjau prediksi
   - **Diedit:** tanggal konfigurasi untuk prediksi telah diubah.
   - **Terakhir Diperbarui:** tanggal prediksi yang disegarkan dihasilkan dalam entitas output.
1. Pilih elips vertikal di samping prediksi yang ingin Anda tinjau hasilnya dan pilih **Lihat**.
   > [!div class="mx-imgBorder"]
   > ![Lihat pilihan dalam menu elipsis vertikal untuk prediksi termasuk Edit, segarkan, tampilan, log, dan Hapus.](media/subscription-churn-verticalellipses.PNG "Lihat pilihan dalam menu elipsis vertikal untuk prediksi termasuk Edit, segarkan, tampilan, log, dan Hapus")
1. Terdapat tiga bagian utama data dalam halaman hasil:
    1. **Performa model pelatihan:** A, B, atau C adalah Skor yang mungkin. Skor ini menunjukkan performa prediksi, dan dapat membantu Anda membuat keputusan untuk menggunakan hasil yang tersimpan di entitas output.
        - Skor ditentukan berdasarkan aturan berikut:
            - **A** bila model ini secara akurat memperkirakan minimal 50% dari total prediksi, dan bila persentase prediksi yang akurat untuk pelanggan yang hilang lebih besar dari tingkat kehilangan pelanggan rata-rata historis setidaknya 10% dari tingkat kehilangan pelanggan rata-rata historis.
            - **A** bila model ini secara akurat memperkirakan minimal 50% dari total prediksi, dan bila persentase prediksi yang akurat untuk pelanggan yang hilang lebih besar hingga 10% dari tingkat kehilangan pelanggan rata-rata historis.
            - **C** bila model akurat diprediksi kurang 50% dari total prediksi, atau ketika persentase prediksi yang akurat untuk pelanggan yang hilang kurang dari tingkat kehilangan pelanggan rata-rata historis.
               > [!div class="mx-imgBorder"]
               > ![Tampilan hasil kinerja model.](media/subscription-churn-modelperformance.PNG "Tampilan hasil kinerja model")
    1. **Kecenderungan untuk kehilangan (jumlah pelanggan):** grup pelanggan berdasarkan prediksi risiko kehilangan. Data ini dapat membantu Anda nanti jika Anda ingin membuat segmen pelanggan dengan risiko kehilangan tinggi. Segmen tersebut membantu memahami tempat batas Anda untuk keanggotaan segmen.
       > [!div class="mx-imgBorder"]
       > ![Grafik menunjukkan pembagian hasil kehilangan, yang dipecah dalam kisaran dari 0-100%.](media/subscription-churn-resultdistribution.PNG "Grafik menunjukkan pembagian hasil kehilangan, yang dipecah dalam kisaran dari 0-100%")
    1. **Faktor yang paling berpengaruh:** ada banyak faktor yang diperhitungkan saat membuat prediksi. Masing-masing faktor memiliki kepentingan yang diperhitungkan untuk prediksi gabungan yang dibuat model. Anda dapat menggunakan faktor ini untuk membantu memvalidasi hasil prediksi. Atau Anda dapat menggunakan informasi ini nanti untuk [membuat segmen](segments.md) yang dapat membantu mempengaruhi risiko kehilangan untuk pelanggan.
       > [!div class="mx-imgBorder"]
       > ![Daftar menunjukkan faktor berpengaruh dan pentingnya mereka dalam memprediksi hasil kehilangan.](media/subscription-churn-influentialfactors.PNG "Daftar menunjukkan faktor berpengaruh dan pentingnya mereka dalam memprediksi hasil kehilangan")

## <a name="manage-predictions"></a>Kelola prediksi

Anda dapat mengoptimalkan, memecahkan masalah, menyegarkan, atau menghapus prediksi. Tinjau laporan kegunaan data input untuk mengetahui cara membuat prediksi lebih cepat dan lebih dapat diandalkan. Untuk informasi lebih lanjut, lihat [Kelola prediksi](manage-predictions.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]