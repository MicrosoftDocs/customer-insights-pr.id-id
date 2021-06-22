---
title: Fitur baru dan mendatang
description: Informasi tentang fitur, peningkatan, dan perbaikan bug baru.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 355dc22ac381145b231848830cefc47eda7968f4
ms.sourcegitcommit: 6944c1592877eb92ec789df5f2e0dbecef638837
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/15/2021
ms.locfileid: "6263255"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Yang baru di kemampuan audiens wawasan Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Kami sangat senang mengumumkan pembaruan terbaru kami! Artikel ini merangkum fitur pratinjau umum, fitur pratinjau, penyempurnaan ketersediaan umum, dan pembaruan fitur. Untuk melihat paket fitur jangka panjang, lihat [Dynamics 365 dan rencana rilis Power Platform](/dynamics365/release-plans/).

Kami meluncurkan pembaruan pada basis kawasan per kawasan. Sehingga wilayah tertentu mungkin melihat fitur sebelum orang lain. Kecuali ditentukan berbeda, Anda tidak perlu melakukan tindakan apa pun dan kami akan memperbarui aplikasi secara otomatis tanpa waktu henti.

> [!TIP]
> Untuk mengirimkan dan memilih permintaan fitur dan saran produk, buka [portal ide aplikasi Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="may-2021-updates"></a>Pembaruan Mei 2021

Pembaruan pada bulan Mei 2021 mencakup beberapa fitur, peningkatan kinerja, dan perbaikan bug.

### <a name="data-ingestion"></a>Penyerapan data

- **Melihat atau memodifikasi metadata atau definisi entitas saat melampirkan data dari Azure Data Lake Storage** Sekarang Anda dapat melihat dan mengedit metadata atau definisi entitas dalam wawasan audiens saat melampirkan data dari folder Common Data Model di Azure Data Lake Storage Anda. Kemampuan ini memberikan tanggapan real-time, validasi model, dan pemeriksaan kesalahan. Memungkinkan Anda mengedit model.json dan manifest.json dengan lancar.

### <a name="extensibility"></a>Dapat diperluas

- **Ekspor segmen yang lebih baik, jadwal kustom, dan duplikasi** Anda sekarang dapat [melihat semua ekspor untuk segmen tertentu](export-destinations.md#view-exports-and-export-details) dalam suatu daftar. Tampilan baru ini akan membantu mengelola cara kerja segmen tertentu dan menyesuaikan ekspor yang ada atau membuat ekspor baru.    
  Anda dapat [menentukan jadwal refresh kustom](export-destinations.md#schedule-and-run-exports) untuk ekspor individual atau beberapa ekspor sekaligus. Hingga saat ini, semua ekspor berjalan dengan setiap pembaruan sistem.    
  Daripada membuat ekspor baru dari awal, Anda dapat memulainya berdasarkan yang ada untuk menghemat waktu.

- **Segmen ekspor ke Microsoft Advertising** Kami telah memperluas tujuan ekspor kami untuk menyertakan Microsoft Advertising. Buat audiens Customer Match di Microsoft Advertising dengan data profil pelanggan terpadu Anda, dan gunakan audiens ini untuk kampanye Periklanan Anda. Untuk informasi lebih lanjut, lihat [Mengekspor segmen ke Microsoft Advertising](export-microsoft-advertising.md).

- **Ekspor segmen ke LinkedIn Ads** Kami telah memperluas tujuan ekspor kami untuk mencakup LinkedIn Ads dan memungkinkan Anda membuka Penargetan Kontak dan Penargetan Perusahaan melalui LinkedIn dengan mengekspor data profil pelanggan terpadu Anda. Untuk informasi lebih lanjut, lihat [Mengekspor segmen ke LinkedIn Ads](export-linkedin-ads.md).


- **Segmen ekspor ke Omnisend** Kami telah memperluas tujuan ekspor kami untuk menyertakan Omnisend. Gunakan segmen yang dibuat di wawasan audiens untuk membuat kampanye, menyediakan pemasaran melalui email, dan menggunakan grup pelanggan tertentu dengan Omnisend. Untuk informasi lebih lanjut, lihat [Mengekspor segmen ke Omnisend](export-omnisend.md)

### <a name="predictions"></a>Prediksi

- **Laporan Kegunaan Data Input** Laporan kegunaan data input memberikan tampilan kesalahan yang dikonsolidasikan dan peringatan yang mungkin dihasilkan prediksi standar Anda. Ini juga memberikan rekomendasi bagaimana meningkatkan kinerja model.    
  Laporan tersedia setelah model menyelesaikan proses pelatihannya. Ini dibuat untuk tiap model secara terpisah, apakah selesai dengan sukses atau tidak.
  Saat ini, fitur ini hanya tersedia untuk model Kehilangan Transaksi. Untuk informasi lebih lanjut, lihat [Laporan kegunaan data input](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Hubungan

- **Visualisator relasi** Tampilan Visualisator visual relasi memungkinkan Anda melihat semua Relasi yang ada antara entitas dan kardinalitasnya. Relasi kini dikelola dalam grup: pengguna yang dibuat, sistem, dan Relasi warisan. Anda juga dapat mengekspor tampilan sebagai gambar. Untuk informasi lebih lanjut lihat [Lihat relasi](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Pembaruan April 2021

Pembaruan pada bulan April 2021 mencakup beberapa fitur, peningkatan kinerja, dan perbaikan bug.

### <a name="data-unification"></a>Penyatuan data
 
- **Pengalaman penggabungan yang disempurnakan untuk penyatuan data**    
  
   Kami sekarang memiliki pengalaman pengguna yang disempurnakan dalam konfigurasi gabungan proses penyatuan data. Perubahannya mencakup pengurutan intuitif untuk bidang gabungan dan statistik rinci pada bidang gabungan dan tunggal.

- **Pengurutan ulang entitas dan konfigurasikan semua rekaman sumber ke entitas Pelanggan**  
      
   Anda sekarang dapat mengurut ulang dan menghilangkan entitas dari rencana penggabungan yang ada dalam proses penyatuan data. Ia memberikan fleksibilitas untuk menyusun ulang entitas dalam proses kecocokan sesuai dengan kebutuhan bisnis. Selain itu, kami mengaktifkan mencakup semua rekaman yang tidak cocok ke dalam entitas *Pelanggan* final, yang memungkinkan mereka menentukan definisi himpunan data profil pelanggan.

### <a name="enrichments"></a>Pengayaan

 - **Pengayaan baru: alamat yang disempurnakan**    
  
   Dengan bangga kami perkenalkan pengayaan baru untuk meningkatkan alamat pada data pelanggan Anda. Alamat pada data dapat tidak terstruktur, tidak lengkap, atau salah. Fitur menggunakan model Microsoft untuk menormalkan dan memperkaya alamat Anda ke dalam format Common Data Model untuk keakuratan dan wawasan yang lebih baik.
 
   Untuk informasi lebih lanjut, lihat [Pengayaan profil pelanggan dengan alamat yang disempurnakan](enrichment-enhanced-addresses.md).

- **Pengalaman konfigurasi terpandu untuk pengayaan**    
  
   Kita lihat kembali pengalaman konfigurasi untuk pengayaan dengan pengalaman sederhana yang dipandu. Anda sekarang memiliki proses langkah demi langkah yang jelas untuk membuat dan mengedit pengayaan.
 
   Selain itu, kami memisahkan konfigurasi sambungan untuk pengayaan pihak ketiga agar sambungan yang sama dapat digunakan oleh beberapa pengayaan. Hanya administrator yang dapat mengonfigurasi koneksi baru tetapi koneksi yang dibuat tersedia untuk administrator dan kontributor.    

   Untuk informasi lebih lanjut, lihat [Ikhtisar koneksi](connections.md).

- **Beberapa pengayaan dengan tipe yang sama**    
  
   Kami sekarang memungkinkan pengguna membuat dan mengelola beberapa pengayaan dengan jenis pengayaan yang sama. Misalnya, anda sekarang dapat membuat dua pengayaan alamat terpisah untuk memperkaya dua segmen pelanggan yang berbeda. Batas berlaku pada seberapa banyak pengayaan dari jenis yang sama dapat dibuat dan bervariasi tergantung pada jenis pengayaan.
  
   Untuk informasi lebih lanjut, lihat [pengayaan untuk profil pelanggan](enrichment-hub.md).

## <a name="march-2021-updates"></a>Pembaruan Maret 2021

Pembaruan pada bulan Maret 2021 mencakup beberapa fitur, peningkatan kinerja, dan perbaikan bug.

### <a name="activities"></a>Aktivitas

- **Wizard aktivitas dan jenis semantik**

   Kami telah meningkatkan dan memperbarui pengalaman pemetaan aktivitas kami untuk memandu dan menyederhanakan pembuatan pemetaan aktivitas. Dalam pengalaman baru ini, pengguna mendapatkan pengalaman terpandu untuk membantu menyelesaikan setiap langkah proses. Pada langkah pemetaan aktivitas, selain memilih dari banyak jenis aktivitas, pengguna dapat memilih untuk memetakan data secara semantik untuk *Langganan* dan/atau *SalesOrderLine* ke skema standar industri, yang dapat digunakan untuk konsumsi hilir.   

   Untuk informasi lebih lanjut, lihat [Aktivitas pelanggan](activities.md).

### <a name="data-ingestion"></a>Penyerapan data

- **Menyambungkan ke sumber data lokal menggunakan aliran data Power Platform dan gateway** Kami dengan senang hati mengumumkan pratinjau aliran data Power Platform dan konektivitas lokal menggunakan gateway di Customer Insights dengan lingkungan Power Platform atau Dataverse terkait. Setiap sumber data baru yang dibuat di lingkungan Customer Insights dengan lingkungan Dataverse tertaut akan default ke aliran data Power Platform yang membawa konektivitas data lokal dan serangkaian konektor dan kemampuan transformasi yang kaya.

### <a name="extensibility"></a>Dapat diperluas

- **Ekspor diatur dalam koneksi dan ekspor** Kami telah mengubah nama halaman **Ekspor tujuan** ke **Koneksi** dan menambahkan halaman terpisah untuk **Ekspor**. Sebagai bagian dari pembaruan ini, kami akan mentransisikan ekspor yang ada menjadi pasangan koneksi dan ekspor menggunakan koneksi tersebut. Administrator sekarang memiliki lebih banyak kejelasan atas data keluar di halaman **Koneksi**. Semua peran pengguna memiliki akses ke halaman **Ekspor**, tetapi hanya administrator yang dapat memilih untuk mengizinkan kontributor mengedit ekspor tertentu dengan koneksi bersama.     
  Untuk informasi selengkapnya, lihat [Gambaran umum koneksi](connections.md) dan [gambaran umum Ekspor](export-destinations.md).

- **Segmen ekspor ke Campaign Monitor** Kami telah memperluas tujuan ekspor kami untuk menyertakan Campaign Monitor. Kini Anda dapat mengekspor segmen dari Customer Insights ke daftar Campaign Monitor dan menggunakannya sebagai dasar untuk kampanye pemasaran Anda.    
   Untuk informasi lebih lanjut, lihat [Mengekspor ke Campaign Monitor](export-campaign-monitor.md).

- **Segmen ekspor ke Constant Contact** Kami telah memperluas tujuan ekspor kami untuk menyertakan Constant Contact. Kini Anda dapat mengekspor segmen dari Customer Insights ke daftar Constant Contact dan menggunakannya sebagai dasar untuk kampanye pemasaran Anda.   
   Untuk informasi lebih lanjut, lihat [Mengekspor ke Constant Contact](export-constant-contact.md).

- **Segmen ekspor ke RollWorks** Kami telah memperluas tujuan ekspor kami untuk menyertakan RollWorks. Kini Anda dapat mengekspor segmen dari Customer Insights ke audiens RollWorks dan menggunakannya sebagai dasar untuk periklanan B2B Anda.    
   Untuk informasi lebih lanjut, lihat [Mengekspor ke RollWorks ](export-rollworks.md).

- **Segmen ekspor ke Snapchat** Kami telah memperluas tujuan ekspor kami untuk menyertakan Snapchat. Kini Anda dapat mengekspor segmen dari Customer Insights ke audiens Snapchat dan menggunakannya sebagai dasar untuk periklanan Anda.     
   Untuk informasi lebih lanjut, lihat [Mengekspor ke Snapchat](export-snapchat.md).

### <a name="predictions"></a>Prediksi

- **Gunakan filter produk dalam rekomendasi produk prediktif** Kami telah menambahkan kemampuan untuk menggunakan filter produk dalam model rekomendasi produk kami. Anda sekarang dapat membuat prediksi yang hanya menggunakan subkumpulan produk Anda.    
   Untuk informasi selengkapnya, lihat [Mengonfigurasi filter produk](predict-product-recommendation.md#configure-product-filters).

- **Buat segmen dari prediksi model** Kami telah menambahkan cara cepat untuk membuat segmen menggunakan hasil model prediksi. Dari halaman hasil model, Anda dapat dengan mudah membuat segmen baru dengan memilih opsi **Buat segmen** baru.    
  Untuk informasi selengkapnya, lihat [Membuat segmen berdasarkan model prediksi](prediction-based-segment.md).

- **Penjelasan untuk rekomendasi produk** Kami telah menambahkan informasi yang menjelaskan faktor-faktor kunci yang dipelajari oleh model AI untuk menghasilkan rekomendasi produk dan tingkat di mana faktor-faktor tersebut berkontribusi terhadap rekomendasi produk. Informasi ini ditambahkan ke layar hasil model.    
   Untuk informasi lebih lanjut, lihat [meninjau status dan hasil prediksi](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Pembaruan Februari 2021

Pembaruan pada Februari 2021 mencakup beberapa fitur, peningkatan kinerja, dan perbaikan bug.

#### <a name="extensibility"></a>Dapat diperluas

- **Ekspor segmen ke AdRoll**

  Kami telah memperluas tujuan ekspor kami untuk mencakup AdRoll. Anda sekarang dapat mengekspor segmen dari Customer Insights ke audiens AdRoll dan menggunakannya sebagai baseline untuk iklan Anda. Untuk informasi lebih lanjut, lihat [Konektor untuk AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmen
 
- **Buat duplikat Segmen**
  
  Untuk membuat segmen baru berdasarkan segmen yang ada, Anda sekarang dapat menduplikasi segmen dan mengedit segmen duplikat untuk menyempurnakannya lebih lanjut. 

- **Menambahkan atribut tambahan ke segmen**

  Anda sekarang dapat menyertakan atribut dalam output segmen, meskipun atribut ini bukan bagian dari profil pelanggan. Contohnya, sertakan ID langganan dalam segmen meskipun merupakan bagian dari entitas langganan yang memiliki relasi M:1 dengan entitas pelanggan. Selama atribut menjadi milik entitas yang terkait dengan entitas pelanggan, Anda sekarang dapat menyertakan atribut ini.  

#### <a name="predictions"></a>Prediksi

- **Buat rekomendasi produk prediktif**

  Memahami apa yang ingin dibeli pelanggan adalah salah satu langkah pertama yang diperlukan untuk meningkatkan pendapatan bisnis dan membangun loyalitas pelanggan melalui personalisasi dan keterlibatan. Memberikan rekomendasi untuk produk yang tidak selaras dengan kepentingan pelanggan Dapat menciptakan rasa tidak terhubung antara pelanggan dan bisnis Anda, dan pada akhirnya membatasi keseluruhan pendapatan dan pengalaman calon pelanggan. 

  Menggunakan data Anda sendiri, Anda sekarang dapat membuat prediksi untuk produk yang kemungkinan dibeli pelanggan Anda di masa mendatang. Untuk informasi lebih lanjut, lihat [prediksi Rekomendasi produk](predict-product-recommendation.md).

#### <a name="system-administration"></a>Administrasi Sistem

- **Salin lingkungan mendukung lebih banyak jenis sumber data**

  Admin dapat menyalin konfigurasi lingkungan ke lingkungan baru di organisasi yang sama. Fitur ini memperluas fungsi salin lingkungan untuk kasus di mana sumber data berdasarkan danau data Common Data Service atau folder Common Data Model digunakan.

## <a name="january-2021-updates"></a>Pembaruan Januari 2021

Pembaruan pada Januari 2021 mencakup beberapa fitur, peningkatan kinerja, dan perbaikan bug.

#### <a name="extensibility"></a>Dapat diperluas

- **Fungsi tambahan dan peningkatan performa untuk ekspor SFTP** Anda sekarang dapat mengekspor semua entitas output dari Customer Insights ke host SFTP. Sebelumnya, ekspor terbatas pada entitas segmen. Selain itu, performa ekspor SFTP memungkinkan volume data lebih banyak dalam waktu lebih sedikit, tergantung pada performa host SFTP.    
  Untuk informasi lebih lanjut, lihat [Konektor SFTP (pratinjau)](export-sftp.md).  

#### <a name="segments"></a>Segmen

- **Pembelajaran Mesin menyarankan segmen yang didukung untuk meningkatkan metrik**, Ada cara baru temukan dan buat segmen baru. Sistem menggunakan model AI untuk menyarankan segmen yang dapat membantu meningkatkan KPI (ukuran) yang telah Anda lacak. Kami menunjukkan tingkat pengaruh atribut yang Anda pilih pada ukuran atau atribut utama lainnya. Informasi ini akan membantu menemukan segmen potensial yang menyajikan peluang.    
  Untuk informasi lebih lanjut, lihat [Segmen yang disarankan (pratinjau)](suggested-segments.md).

#### <a name="data-unification"></a>Penyatuan data

- **Pengalaman kecocokan yang disempurnakan** Di area penyatuan data, pengalaman kecocokan diperbarui. Anda dapat mengkonfigurasi dan melihat aturan pencocokan, termasuk status rinci untuk menjelaskan lebih lanjut cara kerja pencocokan. Ada beberapa pilihan untuk menonaktifkan aturan kecocokan, sehingga aturan tidak aktif lagi saat mempertahankan konfigurasi, menarik dan melepas aturan kecocokan, dan banyak lagi.
  Untuk informasi lebih lanjut lihat [Entitas Kecocokan](match-entities.md).

- **Output deduplikasi dari proses kecocokan tersedia sebagai entitas** output proses Deduplikasi dari proses kecocokan sekarang ditulis ke entitas terpisah untuk analisis lebih lanjut. Entitas ini terdiri dari bidang yang digunakan dalam proses deduplikasi dan rekaman pemenang dan rekaman alternatif terkait yang digabungkan dengan rekaman pemenang.
  Untuk informasi lebih lanjut, lihat [Output deduplikasi sebagai entitas](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Administrasi Sistem

- **Dengan lancar berbagi data ke Microsoft Dataverse** Anda, sekarang Anda dapat berbagi output Customer Insights dengan aplikasi Microsoft Dataverse menggunakan Data Lake terkelola Microsoft Dataverse. Setelah mengaitkan lingkungan Dataverse dengan Customer Insights, Anda mendapatkan pilihan untuk mengaktifkan berbagi data.
  Untuk informasi lebih lanjut, lihat [Kelola lingkungan](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]