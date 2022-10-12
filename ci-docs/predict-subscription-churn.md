---
title: Memprediksi churn langganan (berisi video)
description: Memprediksi apakah pelanggan kemungkinan besar tidak lagi menggunakan produk atau layanan langganan perusahaan Anda.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610240"
---
# <a name="predict-subscription-churn"></a>Memprediksi kehilangan langganan

Memprediksi apakah pelanggan kemungkinan besar tidak lagi menggunakan produk atau layanan langganan perusahaan Anda. Data langganan mencakup langganan aktif dan tidak aktif untuk setiap pelanggan sehingga ada beberapa entri per ID pelanggan.

Anda harus memiliki pengetahuan bisnis untuk memahami apa arti churn bagi bisnis Anda. Kami mendukung definisi churn berbasis waktu, yang berarti pelanggan dianggap telah melakukan churning dalam jangka waktu tertentu setelah langganan mereka berakhir.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Coba churn langganan prediksi menggunakan data sampel: [Panduan sampel prediksi churn langganan](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Prasyarat

- Sekurangnya [izin kontributor](permissions.md).
- Setidaknya 10 profil pelanggan, lebih disukai lebih dari 1.000 pelanggan unik.
- Pengidentifikasi Pelanggan, pengidentifikasi unik untuk mencocokkan langganan dengan pelanggan Anda.
- Data langganan setidaknya untuk menggandakan jendela waktu yang dipilih. Sebaiknya, dua hingga tiga tahun data langganan. Riwayat langganan harus mencakup:
  - **ID Langganan:** Pengidentifikasi unik langganan.
  - **Tanggal Akhir Langganan:** Tanggal langganan kedaluwarsa untuk pelanggan.
  - **Tanggal Mulai Langganan:** Tanggal langganan dimulai untuk pelanggan.
  - **Tanggal Transaksi:** Tanggal terjadinya perubahan langganan. Misalnya, pelanggan membeli atau membatalkan langganan.
  - **Apakah ini langganan berulang:** Bidang benar/salah Boolean yang menentukan apakah langganan akan diperpanjang dengan ID langganan yang sama tanpa campur tangan pelanggan.
  - **Frekuensi Pengulangan (dalam bulan):** Untuk langganan berulang, bulan langganan akan diperpanjang. Misalnya, langganan tahunan yang secara otomatis diperpanjang untuk pelanggan setiap tahun untuk satu tahun lagi memiliki nilai 12.
  - **Jumlah** Langganan: Jumlah mata uang yang dibayarkan pelanggan untuk perpanjangan langganan. Hal ini dapat membantu mengidentifikasi pola untuk tingkat langganan yang berbeda.
- Setidaknya dua catatan aktivitas untuk 50% pelanggan yang ingin Anda hitung churnnya. Aktivitas pelanggan harus mencakup:
  - **Kunci utama:** Pengidentifikasi unik untuk suatu aktivitas. Misalnya, kunjungan situs web atau rekaman penggunaan yang menampilkan pelanggan melihat episode acara TV.
  - **Stempel waktu:** Tanggal dan waktu peristiwa yang diidentifikasi oleh kunci utama.
  - **Acara:** Nama acara yang ingin Anda gunakan. Misalnya, bidang yang disebut "UserAction" di layanan video streaming dapat memiliki nilai "dilihat".
  - **Rincian:** informasi rinci tentang aktivitas. Misalnya, bidang yang disebut "ShowTitle" di layanan video streaming dapat memiliki nilai video yang ditonton pelanggan.
- Kurang dari 20% nilai yang hilang di bidang data entitas yang disediakan.

## <a name="create-a-subscription-churn-prediction"></a>Buat prediksi kehilangan langganan

Pilih **Simpan draf** kapan saja untuk menyimpan prediksi sebagai draf. Draf prediksi ditampilkan di tab **Prediksi** saya.

1. Pergi ke **Prediksi** > **Intelijen**.

1. Pada tab **Buat**, pilih **Gunakan model** pada **petak peta model** churn Pelanggan.

1. Pilih **Langganan** untuk jenis churn lalu **Mulai**.

1. **Namai model ini** dan **nama entitas Output** untuk membedakannya dari model atau entitas lain.

1. Pilih **Selanjutnya**.

### <a name="define-customer-churn"></a>Tentukan kehilangan pelanggan

1. Masukkan jumlah **hari sejak langganan berakhir** sehingga bisnis Anda mempertimbangkan pelanggan untuk berada dalam status bergejolak. Periode ini biasanya terkait dengan kegiatan bisnis seperti penawaran atau upaya pemasaran lainnya yang berusaha mencegah kehilangan pelanggan.

1. Masukkan jumlah **Hari untuk menyelidiki masa depan untuk memprediksi churn**. Misalnya, memprediksi risiko kehilangan pelanggan untuk pelanggan Anda selama 90 hari berikutnya untuk menyelaraskan upaya retensi pemasaran Anda. Memprediksi risiko kehilangan untuk jangka waktu yang lebih lama atau lebih singkat dapat membuatnya lebih sulit untuk mengatasi faktor-faktor dalam profil risiko kehilangan Anda, tergantung pada persyaratan bisnis spesifik Anda.

1. Pilih **Selanjutnya**.

### <a name="add-required-data"></a>Tambahkan data wajib

1. Pilih **Tambahkan data** untuk **Riwayat langganan**.

1. Pilih jenis **aktivitas semantik Langganan** yang berisi informasi riwayat langganan yang diperlukan. Jika aktivitas belum disiapkan, pilih **di sini** dan buat.

1. Di bawah **Aktivitas**, jika atribut aktivitas dipetakan secara semantik saat aktivitas dibuat, pilih atribut atau entitas tertentu yang ingin Anda fokuskan pada perhitungan. Jika pemetaan semantik tidak terjadi, pilih **Edit dan petakan** data Anda.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Menambahkan data yang diperlukan untuk model churn Langganan":::

1. Pilih **Berikutnya** dan tinjau atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Pilih **Tambahkan data** untuk **aktivitas** Pelanggan.

1. Pilih jenis aktivitas semantik yang menyediakan informasi aktivitas pelanggan. Jika aktivitas belum disiapkan, pilih **di sini** dan buat.

1. Di bawah **Aktivitas**, jika atribut aktivitas dipetakan secara semantik saat aktivitas dibuat, pilih atribut atau entitas tertentu yang ingin Anda fokuskan pada perhitungan. Jika pemetaan semantik tidak terjadi, pilih **Edit dan petakan** data Anda.

1. Pilih **Berikutnya** dan tinjau atribut yang diperlukan untuk model ini.

1. Pilih **Simpan**.

1. Tambahkan lebih banyak aktivitas atau pilih **Berikutnya**.

### <a name="set-update-schedule"></a>Atur Jadwal pembaruan

1. Pilih frekuensi untuk melatih kembali model Anda. Pengaturan ini penting untuk memperbarui akurasi prediksi karena data baru diserap dalam Customer Insights. Sebagian besar bisnis dapat melatih sekali per bulan dan mendapatkan akurasi yang baik untuk prediksi mereka.

1. Pilih **Selanjutnya**.

### <a name="review-and-run-the-model-configuration"></a>Memeriksa dan menjalankan konfigurasi model

Langkah **Tinjau dan jalankan** menunjukkan ringkasan konfigurasi dan memberikan kesempatan untuk membuat perubahan sebelum Anda membuat prediksi.

1. Pilih **Edit** pada salah satu langkah untuk meninjau dan membuat perubahan apa pun.

1. Jika Anda puas dengan pilihan Anda, pilih **Simpan dan jalankan** untuk mulai menjalankan model. Pilih **Selesai**. Tab **Prediksi** saya ditampilkan saat prediksi sedang dibuat. Proses dapat berlangsung selama beberapa jam hingga selesai, tergantung pada jumlah data yang digunakan dalam prediksi.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Lihat hasil prediksi

1. Pergi ke **Prediksi** > **Intelijen**.

1. Di tab **Prediksi** saya, pilih prediksi yang ingin Anda lihat.

Terdapat tiga bagian utama data dalam halaman hasil:

- **Performa model pelatihan**: Nilai A, B, atau C menunjukkan kinerja prediksi dan dapat membantu Anda membuat keputusan untuk menggunakan hasil yang disimpan dalam entitas output.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Gambar kotak informasi skor model dengan peringkat A.":::

  Peringkat ditentukan berdasarkan aturan berikut:
  - **A** ketika model secara akurat memprediksi setidaknya 50% dari total prediksi, dan ketika persentase prediksi akurat untuk pelanggan yang bergolak lebih besar dari tingkat churn rata-rata historis setidaknya 10%.
  - **B** ketika model secara akurat memprediksi setidaknya 50% dari total prediksi, dan ketika persentase prediksi akurat untuk pelanggan yang bergolak hingga 10% lebih besar dari tingkat churn rata-rata historis.
  - **C** ketika model secara akurat memprediksi kurang dari 50% dari total prediksi, atau ketika persentase prediksi akurat untuk pelanggan yang bergolak kurang dari tingkat churn rata-rata historis.
  
- **Kecenderungan untuk kehilangan (jumlah pelanggan)**: grup pelanggan berdasarkan prediksi risiko kehilangan. Secara opsional, [buat segmen pelanggan](prediction-based-segment.md) dengan risiko churn tinggi. Segmen tersebut membantu memahami tempat batas Anda untuk keanggotaan segmen.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Grafik menunjukkan pembagian hasil kehilangan, yang dipecah dalam kisaran dari 0-100%":::

- **Faktor yang paling berpengaruh:** ada banyak faktor yang diperhitungkan saat membuat prediksi. Masing-masing faktor memiliki kepentingan yang dihitung untuk membuat prediksi model agregat. Gunakan faktor-faktor ini untuk membantu memvalidasi hasil prediksi Anda. Atau gunakan informasi ini nanti untuk [membuat segmen](.//prediction-based-segment.md) yang dapat membantu memengaruhi risiko churn bagi pelanggan.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Daftar menunjukkan faktor berpengaruh dan pentingnya mereka dalam memprediksi hasil kehilangan.":::

> [!NOTE]
> Dalam entitas output untuk model ini, *ChurnScore* adalah probabilitas prediksi churn dan *IsChurn* adalah label biner berdasarkan *ChurnScore* dengan ambang batas 0,5. Jika ambang batas default ini tidak berfungsi untuk skenario Anda, [buat segmen](segments.md) baru dengan ambang batas pilihan Anda. Untuk melihat skor churn, buka **Entitas** > **Data** dan lihat tab data untuk entitas output yang Anda tentukan untuk model ini.

[!INCLUDE [footer-include](includes/footer-banner.md)]
