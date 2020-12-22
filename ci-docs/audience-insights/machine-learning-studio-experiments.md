---
title: Eksperimen Studio Pembelajaran Mesin (Klasik)
description: Gunakan model Studio pembelajaran mesin (klasik) di Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: ameetj
manager: shellyha
ms.openlocfilehash: 556b6810db0ed2733a3f086291757bd85b77e371
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/03/2020
ms.locfileid: "4669022"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Gunakan model berbasis pembelajaran mesin Azure (klasik)

Data terpadu di Dynamics 365 Customer Insights adalah sumber untuk membangun model Pembelajaran Mesin yang dapat menghasilkan wawasan bisnis tambahan. Customer Insights berintegrasi dengan Studio Pembelajaran Mesin (klasik) untuk menggunakan model kustom Anda sendiri. Untuk melihat bagaimana model yang dikembangkan di Pembelajaran Mesin Azure terintegrasi dengan Customer Insights, lihat [eksperimen Pembelajaran Mesin Azure](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Prasyarat

- Akses ke Customer Insights
- Langganan Azure Enterprise aktif
- [Profil pelanggan terpadu](data-unification.md)
- [Ekspor entitas ke penyimpanan Blob Azure](export-azure-blob-storage.md) disiapkan

## <a name="set-up-machine-learning-studio-classic"></a>Konfigurasi Studio Pembelajaran Mesin Klasik

Pada langkah pertama, kita harus membuat ruang kerja untuk membuka Studio Pembelajaran Mesin (klasik).

1. Buka[https://www.portal.azure.com](https://www.portal.azure.com/) dan masuk.

1. Pilih **Buat sumber daya**.

1. Cari **Pembelajaran Mesin Studio Workspace**, lalu pilih **buat**.

1. Masukkan rincian yang diperlukan untuk [membuat ruang kerja](https://docs.microsoft.com/azure/machine-learning/studio/create-workspace). Pilih **tingkat paket Layanan web** berdasarkan jumlah data yang berencana Anda impor. Untuk performa terbaik, pilih **Lokasi** yang paling dekat dengan Anda.

1. Setelah membuat sumber daya, dasbor Pembelajaran Mesin Studio workspace akan muncul. Pilih **luncurkan Studio Pembelajaran Mesin**.

   ![Antarmuka pengguna Studio Pembelajaran Mesin Azure](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Bekerja dengan Studio Pembelajaran Mesin Azure

Anda sekarang dapat membuat eksperimen baru atau mengimpor template eksperimen yang ada dari Galeri sampel. Ada eksperimen sampel untuk tiga skenario standar:

- [prediksi kehilangan pelanggan](#churn-analysis)

- [Nilai sepanjang masa pelanggan](#customer-lifetime-value-prediction)

- [Rekomendasi produk atau tindakan terbaik berikutnya](#productrecommendation-or-next-best-action)

1. Jika Anda membuat eksperimen baru atau menggunakan template eksperimen dari Galeri, Anda harus mengkonfigurasikan properti **data impor**. Gunakan pengalaman terpandu atau berikan rincian secara langsung untuk mengakses penyimpanan Blob Azure yang berisi data Anda.  

   ![Eksperimen Studio Pembelajaran Mesin Azure](media/azure-machine-learning-studio-experiment.png)

1. Sekarang Anda dapat membangun alur pemrosesan kustom untuk membersihkan dan mengolah data, mengekstrak fitur, dan melatih model yang sesuai.

1. Uji dan Optimalkan kinerja model.

1. Bila Anda puas dengan kualitas model, pilih **Konfigurasikan layanan web** > **layanan web prediktif**. Pilihan ini mengimpor model terlatih dan alur prestasi dari eksperimen pelatihan hingga layanan prediktif. Layanan prediktif dapat menggunakan kumpulan data input lain dengan skema yang digunakan dalam eksperimen pelatihan untuk membuat prediksi.

   ![Mengkonfigurasi layanan web prediktif](media/predictive-webservice-control.png)

1. Setelah percobaan layanan web prediktif berhasil, Anda dapat menyebarkannya untuk penjadwalan otomatis. Agar layanan web berfungsi dengan Customer Insights, pilih **Sebarkan layanan web** > **Sebarkan pratinjau layanan web [baru]**. [Pelajari lebih lanjut tentang menyebarkan Layanan web](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Menyebarkan layanan web prediktif](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Contoh model dari Galeri

Kita akan menggunakan skenario fiktif tentang Aswono Hotel untuk model dalam artikel ini. Aswono Hotel mengumpulkan data berikut:

- Data CRM yang terdiri dari aktivitas menginap di hotel. Himpunan data mencakup informasi tentang tanggal menginap untuk setiap pelanggan terdaftar. Ini juga berisi informasi tentang Pemesanan, jenis kamar, rincian pembelanjaan, dan sebagainya. Data mencakup empat tahun, dari Januari 2014 hingga Januari 2018.
- Profil pelanggan tamu hotel. Profil ini berisi informasi tentang setiap pelanggan, termasuk nama, tanggal lahir, alamat pos, jenis kelamin, dan nomor telepon.
- Penggunaan layanan yang ditawarkan oleh hotel, seperti spa, laundry, WiFi, atau kurir. Informasi ini dicatat untuk setiap pelanggan terdaftar. Biasanya, penggunaan Layanan ditautkan dengan masa inap. Dalam beberapa kasus, Layanan dapat digunakan oleh pelanggan tanpa tinggal di Hotel.

## <a name="churn-analysis"></a>Analisis kehilangan pelanggan

Analisis kehilangan berlaku untuk area bisnis yang berbeda. Dalam contoh ini, kami akan melihat kehilangan pelanggan layanan, khususnya dalam konteks layanan hotel seperti dijelaskan di atas. Ini memberikan contoh kerja dari alur model end-to-end yang dapat digunakan sebagai titik awal untuk jenis model kehilangan pelanggan lainnya.

### <a name="definition-of-churn"></a>Definisi kehilangan pelanggan

Definisi kehilangan pelanggan dapat berbeda berdasarkan skenario. Dalam contoh ini, tamu yang belum mengunjungi Hotel di tahun lalu harus dilabeli sebagai pelanggan yang hilang.  

Template eksperimen dapat diimpor dari galeri. Pertama, pastikan Anda mengimpor data untuk **aktivitas menginap di Hotel**, **data pelanggan**, dan **data penggunaan Layanan** dari penyimpanan Azure Blob.

   ![Impor data untuk model kehilangan pelanggan](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Fiturisasi

Berdasarkan definisi kehilangan pelanggan, pertama kita mengidentifikasi fitur mentah yang akan mempengaruhi label. Kemudian, kita memproses fitur mentah ini ke dalam fitur numerik yang dapat digunakan dengan model Pembelajaran Mesin. Integrasi data terjadi di Customer Insights sehingga kita dapat menggabungkan tabel ini menggunakan *id pelanggan*.

   ![Gabungkan data impor](media/join-imported-data.png)

Fiturisasi untuk membangun model untuk analisis kehilangan pelanggan dapat sedikit rumit. Data adalah fungsi waktu dengan aktivitas hotel baru yang direkam setiap hari. Selama fiturisasi, kita ingin menghasilkan fitur statis dari data dinamis. Dalam kasus ini, kita menghasilkan beberapa fitur dari aktivitas hotel dengan jendela geser selama satu tahun. Kami juga memperluas fitur kategoris seperti jenis kamar atau jenis Pemesanan ke fitur terpisah menggunakan pengkodean one-hot.  

Daftar akhir fitur:

| **Nomor**  | **Original_Column**          | **Fitur turunan**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Jenis kamar                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Jenis Pemesanan                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Kategori perjalanan              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Dolar yang dihabiskan                | TotalDollarSpent                                                                                                                          |
| 5           | Tanggal check-in dan Check-Out  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Penggunaan Layanan                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Pilihan Model

Sekarang kita harus memilih algoritma optimal untuk digunakan. Dalam kasus ini, sebagian besar fitur didasarkan pada fitur kategoris. Biasanya, model berbasis pohon keputusan bekerja dengan baik. Jika hanya ada fitur numerik, jaringan saraf dapat menjadi pilihan yang lebih baik. Mesin vektor dukungan (SVM) juga adalah kandidat yang baik dalam situasi seperti; Namun, perlu sedikit penyelarasan untuk mengekstrak kinerja terbaik. Kami memilih **struktur keputusan ditingkatkan dua kelas** sebagai model pertama pilihan yang diikuti oleh **Svm dua kelas** sebagai model kedua. Studio Pembelajaran Mesin Azure memungkinkan anda melakukan pengujian A/B, sehingga bermanfaat untuk memulai dengan dua model, bukan satu.

Gambar berikut menunjukkan alur pelatihan model dan evaluasi dari Studio Pembelajaran Mesin Azure:

![Model kehilangan pelanggan dalam Studio Pembelajaran Mesin Azure](media/azure-machine-learning-model.png)

Kami juga menerapkan teknik yang disebut **nilai penting fitur permutasi**, aspek penting dari optimasi model. Model internal memiliki sedikit atau tidak ada wawasan tentang dampak dari fitur tertentu pada prediksi akhir. Kalkulator pentingnya fitur menggunakan algoritme kustom untuk menghitung pengaruh fitur individual pada hasil untuk model tertentu. Fitur penting dinormalkan antara + 1 hingga -1. Pengaruh negatif berarti fitur yang sesuai memiliki pengaruh kontra-intuitif pada hasil dan harus dihilangkan dari model. Pengaruh positif menunjukkan bahwa fitur ini sangat berkontribusi terhadap prediksi. Nilai ini bukan koefisien korelasi karena memiliki metrik yang berbeda. Untuk informasi lebih lanjut, lihat [nilai penting fitur permutasi](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Seluruh [Eksperimen kehilangan pelanggan tersedia di Galeri Azure AI](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>prediksi Nilai sepanjang masa pelanggan

Penghitungan nilai sepanjang masa pelanggan (CLTV) adalah salah satu metrik penting yang dapat digunakan oleh suatu bisnis untuk menilai dan menyegmentasikan pelanggan. Untuk bisnis Hotel, penting untuk mengetahui pelanggan. Misalnya, memahami faktor yang membentuk Pelanggan yang baik adalah informasi penting. Ini membantu manajemen hotel menilai fitur yang mereka butuhkan untuk fokus dan tingkatkan untuk memuaskan pelanggan mereka yang membayar tinggi. Keputusan ini dapat berdampak langsung pada penjualan dan pendapatan.  

### <a name="definition-of-cltv"></a>Definisi CLTV

Untuk contoh ini, kami mendefinisikan CLTV dari pelanggan sebagai total jumlah dolar yang diharapkan dibelanjakan oleh pelanggan dalam 365 hari berikutnya. Kami akan menggunakan data sebarkan tiga tahun terakhir untuk semua pelanggan untuk memprediksi nilai ini.

### <a name="featurization"></a>Fiturisasi

Dalam kasus ini, fiturisasi akan sangat mirip dengan skenario kehilangan pelanggan. Namun, label dan nilai yang diprediksi berbeda dari yang didefinisikan di atas.

### <a name="model-selection"></a>Pilihan Model

Memprediksi CLTV adalah masalah regresi karena nilai yang diprediksi adalah variabel kontinyu bernilai positif. Berdasarkan properti fitur, kita memilih **regresi pohon keputusan yang ditingkatkan** sebagai satu algoritma dan **regresi jaringan saraf** sebagai algoritma lain untuk melatih model.

## <a name="product-recommendation-or-next-best-action"></a>Rekomendasi produk atau tindakan terbaik berikutnya

Rekomendasi produk dalam skenario Hotel ditafsirkan sebagai layanan rekomendasi yang ditawarkan oleh hotel kepada pelanggan. Tujuannya adalah untuk memilih layanan yang sesuai untuk pelanggan sehingga penggunaannya dimaksimalkan. Ini mirip dengan rekomendasi film untuk pengguna layanan streaming video.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definisi Rekomendasi produk atau tindakan terbaik berikutnya

Kami mendefinisikan sasaran sebagai memaksimalkan jumlah dolar penggunaan layanan dengan menawarkan layanan pencocokan terbaik untuk pelanggan Hotel sesuai dengan minat mereka.

### <a name="featurization"></a>Fiturisasi

Seperti model kehilangan pelanggan, kita menggabungkan dengan ServiceCustomerID hotel dengan CustomerID agar dapat membangun rekomendasi secara konsisten per CustomerID.

![Fiturisasi model rekomendasi](media/azure-machine-learning-model-featurization.png)

Data bersumber dari tiga entitas yang berbeda, dan fitur berasal dari mereka. Fiturisasi untuk masalah rekomendasi berbeda dibandingkan dengan skenario kehilangan pelanggan atau CLTV. Model rekomendasi memerlukan data input berupa tiga rangkaian fitur.

### <a name="model-selection"></a>Pilihan Model

Kami memprediksi produk atau layanan dengan menggunakan algoritma bernama **Train Matchbox Recommender** untuk melatih model rekomendasi.

![Algoritme Rekomendasi Produk](media/azure-machine-learning-model-recommendation-algorithm.png)

Tiga port input untuk model **rekomendasi Train Matchbox** akan menggunakan data penggunaan layanan pelatihan, Deskripsi pelanggan (opsional), dan Deskripsi Layanan. Ada tiga cara yang berbeda dalam menilai model. Salah satunya adalah untuk evaluasi model dimana nilai keuntungan kumulatif (NDCG) Ternormalisasi dihitung untuk menentukan peringkat item. Dalam eksperimen ini, kita memiliki Skor NDCG sebesar 0,97. Dua pilihan lainnya adalah membuat penilaian model pada seluruh Katalog layanan yang bisa direkomendasikan, atau hanya pada item yang belum digunakan pengguna sebelumnya.

Melihat lebih lanjut tentang distribusi rekomendasi di seluruh Katalog layanan, kami melihat bahwa telepon, WiFi, dan kurir adalah layanan terbaik untuk disarankan. Hal ini konsisten dengan yang kami temukan dari distribusi data konsumsi Layanan:

![Output Model Rekomendasi](media/azure-machine-learning-model-output.png)

Seluruh [percobaan rekomendasi produk dapat diakses di Galeri Azure AI.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrasikan Model kustom

Untuk menggunakan prediksi ini dalam Customer Insights, Anda harus **mengekspor** prediksi bersama dengan ID pelanggan. [Ekspor ke lokasi penyimpanan Blob Azure yang sama dengan](https://docs.microsoft.com/azure/storage/common/storage-import-export-data-from-blobs) yang Anda ekspor ke data sumber. Layanan web prediktif dapat dijadwalkan untuk berjalan secara teratur dan memperbarui Skor.

Data yang dihasilkan oleh model kustom dapat digunakan untuk lebih memperkaya data pelanggan Anda. Untuk informasi lebih lanjut, lihat [model Pembelajaran Mesin kustom](custom-models.md).
