---
title: Prediksi kehilangan pelanggan transaksional
description: Prediksi apakah pelanggan berisiko tidak lagi membeli atau layanan Anda.
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af461d290c69687fb47bacfcff446a0c62978383
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268322"
---
# <a name="transactional-churn-prediction-preview"></a>Prediksi kehilangan pelanggan transaksional (pratinjau)

Prediksi kehilangan pelanggan transaksional membantu memprediksi apakah pelanggan tidak lagi membeli produk atau layanan Anda di periode waktu tertentu. Anda dapat membuat prediksi kehilangan pelanggan yang baru di **intelijen** > **prediksi**. Pilih **prediksi saya** untuk melihat prediksi lain yang Anda buat.

> [!TIP]
> Cobalah tutorial untuk prediksi kehilangan pelanggan transaksional menggunakan data sampel: [panduan sampel prediksi kehilangan pelanggan transaksional (pratinjau)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md) di Customer Insights.
- Pengetahuan bisnis untuk memahami apa arti kehilangan untuk bisnis Anda. Kami mendukung definisi kehilangan pelanggan berdasarkan waktu, yang berarti pelanggan dianggap bergejolak setelah periode tanpa pembelian.
- Data tentang transaksi/pembelian dan Riwayat mereka:
    - Pengidentifikasi transaksi untuk membedakan pembelian/transaksi.
    - Pengidentifikasi pelanggan untuk mencocokkan transaksi dengan pelanggan Anda.
    - Tanggal aktivitas transaksi, yang menentukan tanggal terjadinya transaksi.
    - Skema data semantik untuk pembelian/transaksi memerlukan informasi berikut:
        - **ID transaksi:** pengidentifikasi unik pembelian atau transaksi.
        - **Tanggal transaksi:** tanggal pembelian atau transaksi.
        - **Nilai transaksi:** mata uang/nilai numerik dari transaksi/item.
        - (Opsional) **ID Produk unik:** id produk atau layanan yang dibeli jika data Anda berada pada tingkat item baris.
        - (Opsional) **Apakah transaksi ini adalah retur:** bidang benar/salah yang mengidentifikasi apakah transaksi tersebut merupakan retur atau tidak. Jika **nilai transaksi** negatif, kita juga akan menggunakan informasi ini untuk menyimpulkan retur.
- (Opsional) Data tentang aktivitas pelanggan:
    - Pengidentifikasi aktivitas untuk membedakan aktivitas dari jenis yang sama.
    - Pengidentifikasi pelanggan untuk memetakan aktivitas dengan pelanggan Anda.
    - Informasi aktivitas berisi nama dan tanggal aktivitas.
    - Skema data semantik untuk aktivitas pelanggan mencakup:
        - **Kunci primer:** pengidentifikasi unik untuk aktivitas. Misalnya, kunjungan situs web atau rekaman penggunaan yang menunjukkan pelanggan mencoba sampel produk Anda.
        - **Cap waktu:** tanggal dan waktu aktivitas yang diidentifikasi oleh kunci primer.
        - **Aktivitas**: nama aktivitas yang ingin Anda gunakan. Misalnya, bidang yang disebut "UserAction" di toko kelontong mungkin adalah kupon yang digunakan oleh pelanggan.
        - **Rincian:** informasi rinci tentang aktivitas. Misalnya, bidang yang disebut "CouponValue" di toko kelontong mungkin merupakan nilai mata uang kupon.

## <a name="create-a-transactional-churn-prediction"></a>Buat prediksi kehilangan pelanggan transaksional

1. Di Customer Insights, buka **Intelijen** > **Prediksi**.

1. Pilih petak **model kehilangan pelanggan (pratinjau)** dan pilih **gunakan model ini**.
   
1. Di panel **model kehilangan pelanggan**, pilih **transaksional**, dan pilih **Mulai**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Screenshot dengan pilihan transaksi yang dipilih dalam panel model kehilangan pelanggan.":::

### <a name="name-model"></a>Beri nama model

1. Berikan nama model untuk membedakannya dari model lain.

1. Berikan nama untuk entitas output hanya menggunakan huruf dan angka, tanpa spasi. Itulah nama yang akan digunakan oleh entitas model. 

1. Pilih **Selanjutnya**.

### <a name="define-customer-churn"></a>Tentukan kehilangan pelanggan

1. Atur periode hari untuk memprediksi kehilangan pelanggan untuk **mengidentifikasi Pelanggan yang mungkin hilang** di bidang berikutnya. Misalnya, memprediksi risiko kehilangan pelanggan untuk pelanggan Anda selama 90 hari berikutnya untuk menyelaraskan upaya retensi pemasaran Anda. Memprediksi risiko kehilangan pelanggan selama periode waktu yang lebih lama atau lebih singkat dapat membuatnya lebih sulit untuk mengatasi faktor dalam profil risiko kehilangan pelanggan Anda, namun tergantung pada kebutuhan bisnis Anda yang spesifik. 
   >[!TIP]
   > Anda dapat memilih **Simpan dan tutup** Kapan pun untuk menyimpan prediksi sebagai draf. Anda akan menemukan draf prediksi dalam tab **prediksi saya** untuk melanjutkan.

1. Masukkan jumlah hari untuk menentukan kehilangan pelanggan di bidang **pelanggan telah pergi jika mereka tidak melakukan pembelian dalam**:. Contohnya, jika pelanggan tidak melakukan pembelian dalam 30 hari terakhir, maka pelanggan dapat dianggap pergi dari bisnis Anda. 

1. Untuk melanjutkan, klik **Berikutnya**

### <a name="add-required-data"></a>Tambahkan data wajib

1. Pilih **Tambah data** untuk **Riwayat Pembelian** dan pilih entitas yang menyediakan informasi riwayat transaksi/pembelian sebagaimana dijelaskan dalam [prasyarat](#prerequisites).

1. Petakan bidang semantik ke atribut dalam entitas Riwayat Pembelian Anda dan pilih **berikutnya**. Untuk Deskripsi bidang, lihat [prasyarat](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Memetakan bidang semantik entitas pembelian.":::

1. Jika bidang di bawah ini tidak terisi, konfigurasikan relasi dari entitas Riwayat Pembelian Anda ke entitas pelanggan.
    1. Pilih **Entitas riwayat pembelian**.
    1. Pilih **bidang** yang mengidentifikasi pelanggan di entitas riwayat pembelian. Ini perlu dikaitkan dengan ID pelanggan utama entitas pelanggan Anda.
    1. Pilih **entitas pelanggan** yang cocok dengan entitas pelanggan utama Anda.
    1. Masukkan nama yang mendeskripsikan relasi.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Halaman Riwayat pembelian yang menunjukkan pembuatan relasi dengan pelanggan.":::
   
1. Pilih **Selanjutnya**.

1. Atau, pilih **Tambah data** untuk **aktivitas pelanggan**. Pilih entitas yang menyediakan informasi aktivitas pelanggan sebagaimana dijelaskan dalam prasyarat.

1. Petakan bidang semantik ke atribut dalam entitas aktivitas pelanggan Anda dan pilih **berikutnya**. Untuk Deskripsi bidang, lihat [prasyarat](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Petakan bidang pelanggan untuk data transaksi.":::

1. Pilih jenis aktivitas yang cocok dengan jenis aktivitas Pelanggan yang Anda konfigurasikan. Pilih **Buat baru** dan pilih jenis aktivitas yang tersedia atau buat jenis baru.

1. Anda harus mengkonfigurasi relasi dari entitas aktivitas pelanggan Anda ke entitas pelanggan.
    1. Pilih bidang yang mengidentifikasi pelanggan di tabel aktivitas pelanggan. Hal ini dapat langsung terkait dengan ID pelanggan utama entitas pelanggan Anda.
    1. Pilih entitas pelanggan yang cocok dengan entitas pelanggan utama Anda
    1. Masukkan nama yang mendeskripsikan relasi.

1. Pilih **Simpan**.

1. Jika Anda memiliki aktivitas pelanggan lain yang ingin Anda masukkan, ulangi langkah di atas.

1. Pilih **Selanjutnya**.

### <a name="set-schedule-and-review-configuration"></a>Mengatur konfigurasi jadwal dan ulasan

1. Atur frekuensi untuk melatih ulang model Anda. Pengaturan ini penting untuk memperbarui keakuratan prediksi karena data baru terserap. Sebagian besar bisnis dapat melatih sekali per bulan dan mendapatkan akurasi yang baik untuk prediksi mereka.

1. Pilih **Selanjutnya**.

1. Tinjau konfigurasi prediksi. Anda dapat kembali ke langkah sebelumnya dengan memilih **Edit** di dalam nilai yang ditampilkan. Atau Anda dapat memilih langkah konfigurasi dari indikator progres.

1. Jika semua nilai dikonfigurasi dengan benar, pilih **Simpan dan jalankan** untuk memulai proses prediksi. Pada **tab prediksi saya**, Anda dapat melihat status prediksi Anda. Proses dapat berlangsung selama beberapa jam hingga selesai, tergantung pada jumlah data yang digunakan dalam prediksi.

## <a name="review-a-prediction-status-and-results"></a>Meninjau status dan hasil prediksi

1. Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.

1. Pilih prediksi yang ingin Anda tinjau.
   - **Nama prediksi:** nama prediksi yang diberika saat membuatnya.
   - **jenis prediksi:** jenis model yang digunakan untuk prediksi
   - **Entitas output:** nama entitas untuk menyimpan output dari prediksi. Anda dapat menemukan entitas dengan nama ini pada **data** > **entitas**.
   - **bidang terprediksi:** bidang ini hanya diisi untuk beberapa jenis prediksi, dan tidak digunakan dalam prediksi kehilangan pelanggan.
   - **Status:** Status prediksi dijalankan.
        - **mengantri:** prediksi sedang menunggu proses lain untuk dijalankan.
        - **Menyegarkan:** prediksi saat ini berjalan untuk menghasilkan hasil yang akan mengalir ke entitas output.
        - **gagal:** prediksi yang jalankan gagal. [Tinjau log](#troubleshoot-a-failed-prediction) untuk rincian selengkapnya.
        - **berhasil:** prediksi telah berhasil. Pilih **Lihat** di bawah elips vertikal untuk meninjau prediksi
   - **Diedit:** tanggal konfigurasi untuk prediksi telah diubah.
   - **Terakhir Diperbarui:** tanggal prediksi yang disegarkan dihasilkan dalam entitas output.

1. Pilih elips vertikal di samping prediksi yang ingin Anda tinjau hasilnya dan pilih **Lihat**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="lihat kontrol untuk melihat hasil prediksi.":::   

1. Terdapat tiga bagian utama data dalam halaman hasil:
    1. **Performa model pelatihan:** A, B, atau C adalah Skor yang mungkin. Skor ini menunjukkan performa prediksi, dan dapat membantu Anda membuat keputusan untuk menggunakan hasil yang tersimpan di entitas output. Skor ditentukan berdasarkan aturan berikut:
         
         - **A** bila model ini secara akurat memprediksi minimal 50% dari total prediksi, dan bila persentase prediksi yang akurat untuk pelanggan yang pergi lebih besar dari tingkat dasar setidaknya 10%.
            
         - **B** bila model ini secara akurat memprediksi minimal 50% dari total prediksi, dan bila persentase prediksi yang akurat untuk pelanggan yang pergi adalah hingga 10% lebih besar dari tingkat dasar.
            
         - **C** bila model ini secara akurat memprediksi kurang 50% dari total prediksi, atau bila persentase prediksi yang akurat untuk pelanggan yang pergi kurang dari tingkat dasar.
               
         - **Dasar** memerlukan input periode waktu prediksi untuk model (misalnya, satu tahun) dan model membuat pecahan waktu yang berbeda dengan membaginya dengan 2 hingga mencapai satu bulan atau kurang. Ia menggunakan pecahan ini untuk membuat aturan bisnis untuk pelanggan yang belum membeli dalam jangka waktu ini. Pelanggan ini dianggap sebagai pergi. Aturan bisnis berbasis waktu dengan kemampuan tertinggi untuk memprediksi siapa yang cenderung pergi dipilih sebagai model dasar.
            
    1. **Kecenderungan untuk kehilangan (jumlah pelanggan):** grup pelanggan berdasarkan prediksi risiko kehilangan. Data ini dapat membantu Anda nanti jika Anda ingin membuat segmen pelanggan dengan risiko kehilangan tinggi. Segmen tersebut membantu memahami tempat batas Anda untuk keanggotaan segmen.
       
    1. **Faktor yang paling berpengaruh:** ada banyak faktor yang diperhitungkan saat membuat prediksi. Masing-masing faktor memiliki kepentingan yang dihitung untuk membuat prediksi model agregat. Anda dapat menggunakan faktor ini untuk membantu memvalidasi hasil prediksi. Atau Anda dapat menggunakan informasi ini nanti untuk [membuat segmen](segments.md) yang dapat membantu mempengaruhi risiko kehilangan untuk pelanggan.

## <a name="troubleshoot-a-failed-prediction"></a>Memecahkan masalah prediksi gagal

1. Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.

1. Pilih elipsis vertikal di sebelah prediksi yang ingin anda lihat log kesalahannya.

1. Pilih **Log**.

1. Memeriksa semua kesalahan. Ada beberapa jenis kesalahan yang dapat terjadi, dan menjelaskan kondisi yang menyebabkan kesalahan. Misalnya, kesalahan bahwa tidak ada cukup data yang dapat diprediksi secara akurat biasanya ditangani dengan memuat data tambahan ke dalam Customer Insights.

## <a name="refresh-a-prediction"></a>Segarkan prediksi

Prediksi akan secara otomatis diperbarui pada jadwal yang sama [dengan penyegaran data Anda](system.md#schedule-tab) seperti dikonfigurasi dalam pengaturan. Anda juga dapat me-refresh secara manual.

1. Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.

1. Pilih elipsis vertikal di sebelah prediksi yang ingin Anda segarkan.

1. Pilih **Segarkan**.

## <a name="delete-a-prediction"></a>Hapus prediksi

Menghapus prediksi juga akan menghapus entitas keluarannya.

1. Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.

1. Pilih elipsis vertikal di sebelah prediksi yang ingin Anda hapus.

1. Pilih **Hapus**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]