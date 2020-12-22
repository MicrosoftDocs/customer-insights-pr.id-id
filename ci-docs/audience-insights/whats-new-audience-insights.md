---
title: Fitur baru dan mendatang
description: Informasi tentang fitur, peningkatan, dan perbaikan bug baru.
ms.date: 11/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 07b4bee0445f9cd7d53a37cd405af839feb07ae3
ms.sourcegitcommit: 4004eadac7a65e50e0a409cb925958523c2b6348
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/30/2020
ms.locfileid: "4650008"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Yang baru di kemampuan audiens wawasan Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Kami sangat senang mengumumkan pembaruan terbaru kami! Artikel ini merangkum fitur pratinjau umum, fitur pratinjau, penyempurnaan ketersediaan umum, dan pembaruan fitur. Untuk melihat paket fitur jangka panjang, lihat [Dynamics 365 dan rencana rilis Power Platform](https://docs.microsoft.com/dynamics365/release-plans/).

Anda juga dapat menonton video berikut untuk mempelajari lebih lanjut tentang kemampuan yang direncanakan selama enam bulan terakhir.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Kami meluncurkan pembaruan pada basis kawasan per kawasan. Sehingga wilayah tertentu mungkin melihat fitur sebelum orang lain. Kecuali ditentukan berbeda, Anda tidak perlu melakukan tindakan apa pun dan kami akan memperbarui aplikasi secara otomatis tanpa waktu henti.

> [!TIP]
> Untuk mengirimkan dan memilih permintaan fitur dan saran produk, buka [portal ide aplikasi Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="november-2020-updates"></a>Pembaruan November 2020

Pembaruan pada November 2020 mencakup beberapa fitur, peningkatan kinerja, dan perbaikan bug.

### <a name="new-and-updated-features-in-november-2020"></a>Fitur baru dan yang diperbarui pada November 2020

#### <a name="data-enrichment"></a>Pengayaan data

- **Hadirkan data pengayaan Anda sendiri melalui impor kustom protokol transfer file aman (SFTP)**
  
  Impor kustom SFTP memungkinkan Anda mengimpor data pengayaan yang tidak harus melalui proses penyatuan data. Pelajari lebih lanjut tentang impor kustom SFTP.

  Untuk informasi lebih lanjut, lihat [memperkaya profil pelanggan dengan data kustom (pratinjau)](enrichment-SFTP-custom-import.md).
 
- **perkaya data pelanggan anda dengan data lokasi dari HERE Technologies**

  Dengan layanan pengayaan data HERE Technologies, Anda dapat membangun pemahaman lokasi yang lebih tepat tentang pelanggan Anda dengan normalisasi alamat, ekstraksi garis lintang dan bujur, dan banyak lagi. Pelajari selengkapnya tentang cara memperkaya dengan HERE Technologies.

  Untuk informasi lebih lanjut, lihat [Pengayaan profil pelanggan dengan HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Penyatuan data

- **Fleksibilitas untuk mengaktifkan pembuatan profil data pada entitas dan bidang tertentu dari akun penyimpanan Anda**

  Anda dapat menunjukkan entitas dan bidang data apa dari folder Common Data Model di akun penyimpanan Azure Data Lake yang ingin Anda Aktifkan pemprofilan datanya sebagai bagian dari proses penyerapan data.

  Untuk informasi lebih lanjut, lihat [menyambung ke folder Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Dapat diperluas

- **Aktifkan segmen Anda melalui Google Ads**

  Ekspor segmen dari daftar audiens Google Ads dan gunakan daftar ini untuk beriklan di Google Search, Google Display Network, YouTube, dan Gmail. Pelajari lebih lanjut tentang mengaktifkan segmen Anda melalui Google Ads.

  Untuk informasi lebih lanjut, lihat [Konektor untuk Google Ads](export-google-ads.md).

- **Aktifkan segmen Anda melalui Marketo**

  Ekspor segmen ke audiens Marketo dan gunakan audiens ini untuk otomatisasi pemasaran. Pelajari lebih lanjut tentang mengaktifkan segmen Anda melalui Marketo. 

  Untuk informasi lebih lanjut, lihat [Konektor untuk Marketo](export-marketo.md).

- **Aktifkan segmen Anda melalui DotDigital**

  Ekspor segmen ke DotDigital dan gunakan untuk tujuan pemasaran. Pelajari lebih lanjut tentang mengaktifkan segmen Anda melalui DotDigital. 

  Untuk informasi lebih lanjut, lihat [Konektor untuk DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Prediksi

- **Prediksi kehilangan pelanggan transaksional**

  Fitur prediksi kehilangan pelanggan transaksi memungkinkan anda, tanpa bantuan ilmuwan data, untuk memprediksi kemungkinan pelanggan menghentikan pembelian produk atau layanan.  Dengan menggunakan skor prediksi, Anda dapat menggabungkan informasi lain tentang pelanggan anda, seperti nilai pelanggan, untuk membuat segmen dari risiko kehilangan pelanggan tinggi, atau pelanggan bernilai tinggi. Gunakan segmen ini untuk langsung menargetkan pelanggan melalui aktivitas pemasaran, dukungan pelanggan, dan skenario lainnya untuk mengurangi risiko kehilangan pelanggan.
 
  Konfigurasikan definisi kehilangan pelanggan sebagai periode berdasarkan waktu yang spesifik untuk bisnis Anda dan tentukan Kapan pelanggan dianggap pergi. Misalnya, toko kelontong mungkin ingin mempertimbangkan Pelanggan sudah pergi jika mereka tidak membeli apa pun dalam 30 hari terakhir.
 
  Saat Anda terus membuat prediksi, kita akan memandu Anda data apa yang diperlukan, dan memungkinkan Anda memetakan data tentang bisnis Anda ke bidang yang diperlukan untuk memprediksi kehilangan pelanggan untuk pelanggan Anda. Anda juga dapat mengatur jadwal untuk melatih ulang model berdasarkan informasi baru di sistem Anda untuk beradaptasi dengan perubahan kondisi bisnis.
 
  Untuk informasi lebih lanjut, lihat [prediksi kehilangan pelanggan transaksional (pratinjau)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Administrasi Sistem

- **Atur ulang lingkungan**

  Atur ulang segala sesuatu di lingkungan dari instans Terpilih untuk mulai menyegarkan.

  Untuk informasi lebih lanjut, lihat [Atur ulang lingkungan yang ada](manage-environments.md#reset-an-existing-environment).


- **Sambungkan ke akun penyimpanan Azure Data Lake menggunakan prinsipal Layanan**

  Tulis output data ke dan Baca data dari akun penyimpanan menggunakan prinsipal Layanan Azure. Sambungan akun penyimpanan yang ada dapat terus menggunakan kunci akun. Mereka juga menawarkan pilihan peningkatan untuk menggunakan prinsipal layanan ke depannya. Sambungan baru akan didasarkan pada metode otentikasi prinsipal layanan untuk akun penyimpanan Anda.

  Untuk informasi lebih lanjut, lihat [menyambungkan ke Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure untuk wawasan audiens](connect-service-principal.md).

## <a name="october-2020-updates"></a>Pembaruan Oktober 2020

Pembaruan pada Oktober 2020 mencakup beberapa fitur, peningkatan kinerja, dan perbaikan bug.

### <a name="new-and-updated-features-in-october-2020"></a>Fitur baru dan yang diperbarui pada Oktober 2020

#### <a name="extensibility"></a>Dapat diperluas

- **Ekspor ke Mailchimp**

Ekspor segmen ke daftar audiens yang ada di Mailchimp untuk memberikan pengalaman email yang disesuaikan untuk pelanggan Anda.

Untuk informasi lebih lanjut, lihat [Konektor untuk Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Pengayaan data

- **Mendeduplikasi rekaman sumber di entitas Pencocokan**

Tentukan aturan deduplikasi pada entitas yang digunakan dalam proses pencocokan untuk mengidentifikasi rekaman duplikat. Gabungkan mereka menjadi satu rekaman dan tautkan semua rekaman sumber ke rekaman gabungan ini. Rekaman yang dideduplikasi ini kemudian akan digunakan dalam proses pencocokan lintas entitas.

Untuk informasi lebih lanjut, lihat [menentukan deduplikasi pada entitas kecocokan](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Administrasi Sistem

- **Orkestrasi: pilihan penyegaran baru di Gabung**

Hingga saat ini, bila Anda menjalankan proses penggabungan, sistem akan menjalankan semua proses hilir yang tergantung pada proses penggabungan dan selanjutnya. Anda sekarang dapat memverifikasi output dari proses penggabungan (entitas pelanggan terpadu) sebelum menggunakannya di pemrosesan hilir seperti segmen atau ukuran.
Pada halaman gabungan, Anda sekarang dapat memilih untuk menjalankan hanya langkah gabungan dan menjalankan hanya proses ini. Untuk me-refresh semua proses hilir juga, Anda dapat memilih Jalankan gabungan dan proses hilir. 

## <a name="september-2020-updates"></a>Pembaruan September 2020

Pembaruan pada September 2020 mencakup beberapa fitur, peningkatan kinerja, dan perbaikan bug.

### <a name="new-and-updated-features-in-september-2020"></a>Fitur baru dan yang diperbarui pada September 2020

#### <a name="activities"></a>Aktivitas

- **Prediksi cerdas dari semantik atribut**

Fitur baru ini memprediksi jenis semantik atribut input yang diteruskan ke proses penyatuan data. Ini menggunakan model Pembelajaran Mesin yang meningkatkan akurasi dan menghemat waktu.

#### <a name="enrichments"></a>Pengayaan

- **Pengayaan demografi dari Experian**

Pengayaan demografi dari Experian sekarang tersedia dalam pratinjau. Experian adalah pemimpin global dalam pelaporan kredit konsumen dan bisnis serta layanan pemasaran. Dengan [layanan pengayaan data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), Anda dapat membangun pemahaman yang lebih mendalam tentang pelanggan Anda dengan memperkaya profil pelanggan Anda dengan data demografis seperti ukuran rumah tangga, pendapatan, dan lainnya.

Untuk menggunakan fitur ini, Anda harus memiliki langganan Experian aktif.

Untuk informasi lebih lanjut, lihat [memperkaya profil pelanggan dengan demografi dari Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Administrasi Sistem

- **Panel detail tugas**

Panel rincian tugas memungkinkan Anda melihat rincian tentang tugas yang dijalankan oleh sistem. Ini adalah cara praktis untuk mengidentifikasi masalah dengan konfigurasi dan menemukan solusi.
Tinjau pesan kesalahan; lihat cara Anda mengatasi masalah potensial.
 
- **Informasi pemrosesan yang ditambahkan ke halaman tambahan**

Peningkatan ini akan menambahkan informasi tentang status entitas Anda pada halaman **entitas** dan **pelanggan**.
 
Selain itu, Anda dapat menemukan rincian tentang kemajuan proses, bersama dengan rincian tugas, di kedua Halaman ini.

- **Peningkatan halaman status sistem**

Kami meningkatkan struktur tabel rincian status di **Sistem** > **status** saat meninjau ekspor data.
 
Selain itu, kesalahan dalam kolom **rincian** sekarang lebih rinci dan dapat ditindaklanjuti. 
 
- **Membatalkan pengembalian pekerjaan kembali ke kondisi sebelumnya**

Bila Anda membatalkan tugas, misalnya, dalam proses pencocokan, ia akan kembali ke status teranyar. Misalnya, jika proses pertandingan selesai kemarin dan Anda membatalkannya hari ini, maka akan kembali ke kondisi sukses kemarin.


## <a name="august-2020-updates"></a>Pembaruan Agustus 2020

Pembaruan pada Agustus 2020 mencakup beberapa fitur, peningkatan kinerja, dan perbaikan bug.

### <a name="new-and-updated-features-in-august-2020"></a>Fitur baru dan yang diperbarui pada Agustus 2020

#### <a name="data-unification"></a>Penyatuan data

- **Peningkatan pengalaman untuk tahap peta selama penyatuan data**

  Pengalaman untuk tahap peta dalam proses penyatuan data memungkinkan Anda memilih entitas, atribut, dan menentukan semantik dengan cara yang lebih mulus.

  Perubahan meliputi:
  
  - Interaksi yang lebih sedikit diperlukan untuk menambahkan entitas dan bidang
  - Kemampuan pencarian yang disempurnakan pada halaman peta
  - Identifikasi yang mudah dan visual dari jenis bidang yang disarankan

#### <a name="enrichment"></a>Pengayaan

- **Pengayaan afinitas minat tersedia di pasar tambahan**

  Kami memperluas ketersediaan pengayaan afinitas minat di luar Amerika Serikat ke lima pasar tambahan: Kanada, Australia, Inggris, Prancis, dan Jerman. Dengan ekstensi ini, Anda dapat memperkaya data pelanggan dengan minat tambahan yang berlaku untuk pasar ini. Kami juga akan memperkaya profil pelanggan Anda yang terletak di pasar ini dengan menggunakan data kepemilikan lokal dari Microsoft graph.
  Untuk informasi lebih lanjut, lihat [memperkaya profil pelanggan dengan afinitas merek dan minat](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Pembaruan Juli 2020

Pembaruan pada juli 2020 mencakup beberapa fitur, peningkatan kinerja, dan perbaikan bug.

### <a name="new-and-updated-features-in-july-2020"></a>Fitur baru dan yang diperbarui pada Juli 2020

#### <a name="extensibility"></a>Dapat diperluas

- **pemicu Power Automate untuk proses penyatuan yang selesai**

  Kami telah memperluas pemicu kami untuk Power Automate dan memungkinkan Anda membuat pemberitahuan atau tindakan refresh proses penyatuan (pemetaan, pencocokan, penggabungan) diselesaikan.    
  Untuk informasi lebih lanjut, lihat [Power Automate connector](export-power-automate.md)

#### <a name="enrichment"></a>Pengayaan

- **Pengayaan afinitas merek tersedia di pasar tambahan**

  Kami memperluas ketersediaan pengayaan afinitas merek di luar Amerika Serikat hingga lima pasar tambahan: Kanada, Australia, Inggris, Prancis, dan Jerman. Dengan ekstensi ini, Anda dapat memperkaya data pelanggan Anda dengan merek lokal di pasar ini. Kami juga akan memperkaya profil pelanggan Anda yang terletak di pasar ini dengan menggunakan data kepemilikan lokal dari Microsoft graph.
  Untuk informasi lebih lanjut, lihat [memperkaya profil pelanggan dengan afinitas merek dan minat](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Pembaruan Juni 2020

Pembaruan pada Juni 2020 mencakup beberapa fitur, peningkatan kinerja, dan perbaikan bug.

### <a name="new-and-updated-features-in-june-2020"></a>Fitur baru dan yang diperbarui pada Juni 2020

#### <a name="enrichment"></a>Pengayaan

- **Pengayaan data perusahaan dari Leadspace**
  
  Tentukan bidang di profil pelanggan terpadu yang digunakan untuk mencari data perusahaan terkait dari Leadspace. Setelah menjalankan proses pengayaan, profil B2B diperkaya dengan atribut tambahan termasuk ukuran perusahaan, lokasi, industri, dan banyak lagi.    
  Kolaborasi ini memungkinkan Anda meningkatkan kualitas data dengan input dari layanan pihak ketiga. Untuk menggunakan pengayaan ini, Anda memerlukan lisensi dari Leadspace untuk mengakses data perusahaan B2B. Sistem akan menggunakan lisensi tersebut agar data Anda terus diperkaya.    
  Untuk informasi lebih lanjut, lihat [pengayaan profil perusahaan dengan Leadspace](enrichment-leadspace.md).

- **Halaman hub pengayaan**

  Semua pengayaan data yang tersedia dari penyedia pengayaan pihak pertama dan ketiga akan dikonfigurasi di tempat yang sama. Mengkonfigurasi pengayaan data adalah pengalaman mulus yang dikelola dari tempat umum.    
  Untuk informasi lebih lanjut, lihat [pengayaan untuk profil pelanggan](enrichment-hub.md).

- **Pengayaan afinitas merek dan minat terpisah**

  Kesamaan merek dan minat kini tersedia sebagai dua pengayaan independen. Pengayaan terpisah memberi Anda fleksibilitas untuk mengonfigurasi dan mengelolanya satu per satu, tergantung kebutuhan atau persyaratan bisnis Anda.    
  Untuk informasi lebih lanjut, lihat [memperkaya profil pelanggan dengan afinitas merek dan minat](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Dapat diperluas

- **URL yang dapat diklik untuk aktivitas terpadu pada Add-in kartu pelanggan Dynamics 365**

  Aktivitas terpadu di add-in kartu pelanggan kini menampilkan URL yang dapat diklik jika URL tersebut telah ditentukan selama konfigurasi aktivitas.    
  Untuk informasi lebih lanjut, lihat [Add-in kartu pelanggan](customer-card-add-in.md).

- **Afinitas merek dan minat tersedia pada Add-in kartu pelanggan Dynamics 365**

  Kontrol baru pada Add-in pelanggan kartu Dynamics 365 memungkinkan Anda menunjukkan pengayaan merek dan minat pada kontak Anda di aplikasi keterlibatan pelanggan di Dynamics 365.    
  Untuk informasi lebih lanjut, lihat [Add-in kartu pelanggan](customer-card-add-in.md).

- **Pemicu Power Automate tambahan**

  Kami telah memperluas pemicu Power Automate dan menambahkan pemicu berikut:
  - Mendapatkan pemberitahuan atau melakukan tindakan saat refresh penuh otomatis (sumber data, penyatuan, segmen, tindakan, ekspor) selesai
  - Tentukan ambang batas untuk ukuran bisnis. Misalnya, Anda dapat membuat pemberitahuan yang akan dikirim saat ambang batas yang ditentukan diteruskan. Selain itu, pemicu akan memberikan informasi yang memungkinkan Anda membangun alur kerja yang lebih kompleks di Power Automate.    
  Untuk informasi lebih lanjut, lihat [Power Automate connector](export-power-automate.md)

- **Ekspor ke pengelola iklan Facebook**
  
  Kemampuan ini memungkinkan Anda mengekspor segmen ke Facebook Ads Manager. Segmen diekspor sebagai pemirsa kustom untuk menggunakan profil pelanggan terpadu dalam kampanye dan iklan pemasaran Facebook. Pemirsa khusus juga dapat digunakan untuk membuat kampanye di Instagram melalui pengelola iklan Facebook.    
  Untuk informasi lebih lanjut, lihat [konektor untuk pengelola iklan Facebook](export-facebook.md).

#### <a name="predictions"></a>Prediksi

- **Prediksi kehilangan langganan**

  Ikuti pengalaman terpandu untuk membuat prediksi kehilangan pelanggan di area langganan seperti layanan cloud, keanggotaan pelanggan, dan sektor lainnya. 

  Fitur prediksi kehilangan langganan memungkinkan Anda memprediksi kemungkinan pelanggan menghentikan penggunaan produk atau layanan berbasis langganan tanpa melibatkan ilmuwan data. Dengan menggunakan skor prediksi, anda dapat menggabungkan informasi lain tentang pelanggan anda untuk membuat segmen dari risiko kehilangan tinggi. Dengan bantuan segmen ini, Anda dapat langsung menargetkan pelanggan di pemasaran, dukungan pelanggan, dan skenario lainnya untuk mengurangi risiko kehilangan pelanggan untuk pelanggan tertentu untuk meningkatkan pendapatan dan mengurangi biaya.

  Dalam pengalaman tersebut, Anda dapat mengonfigurasi definisi kehilangan pelanggan sebagai periode berbasis waktu yang spesifik untuk bisnis Anda. Contohnya, bisnis streaming video yang memiliki proses berlangganan bulanan mungkin ingin mempertimbangkan pelanggan untuk berhenti setelah 15 hari setelah berakhirnya langganan.

  Saat Anda melalui prediksi, kita akan memandu Anda melalui data yang diperlukan, dan memungkinkan Anda memetakan data tentang bisnis Anda ke bidang yang diperlukan untuk memprediksi kehilangan pelanggan untuk pelanggan Anda. Saat informasi bisnis berubah, Anda juga dapat mengatur jadwal untuk melatih ulang informasi baru dalam sistem Anda agar beradaptasi dengan perubahan kondisi bisnis.    
  Untuk informasi lebih lanjut, lihat [prediksi kehilangan pelanggan (pratinjau)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmen

- **Temukan pelanggan serupa**
  
  Temukan pelanggan serupa di basis pelanggan Anda menggunakan kecerdasan buatan. Model Pembelajaran Mesin klasifikasi biner menetapkan skor kesamaan untuk pelanggan di segmen diperluas. Skor didasarkan pada kemiripan dengan pelanggan di segmen sumber. Tergantung pada Skor kesamaan, profil pelanggan ditambahkan ke segmen yang baru dibuat.

  Terkadang disebut sebagai pemodelan serupa dalam pemasaran digital, ia menggunakan model AI untuk membantu menemukan Pelanggan yang serupa dengan segmen pelanggan lain Anda dengan memperhitungkan atribut tambahan. Anda tidak hanya dapat memilih atribut namun ia juga memungkinkan Anda menentukan jumlah maksimum Pelanggan yang harus ada di segmen baru ini. Model AI kemudian akan menghitung Skor kesamaan untuk setiap pelanggan berdasarkan atribut yang Anda pilih dan menemukan pelanggan dengan Skor kesamaan rata-rata yang lebih tinggi. Segmen yang dihasilkan akan mencakup pelanggan yang terlihat mirip dengan pelanggan di segmen asli Anda.    
  Untuk informasi selengkapnya, lihat [Pelanggan yang mirip](find-similar-customer-segments.md).

- **Segmen tumpang tindih dan pembeda**

  Segmentasi tumpang tindih memungkinkan Anda melihat berapa banyak dan pelanggan mana yang sama untuk dua atau beberapa segmen. Contohnya, cara kerja segmen berpengeluaran belanja tinggi tumpang tindih dengan segmen pelanggan yang memiliki kepuasan tinggi atau bagaimana segmen pelanggan yang berhenti tumpang tindih dengan segmen pelanggan dengan kepuasan rendah. Selain itu, Anda dapat menganalisis bagaimana perubahan tumpang tindih berdasarkan atribut tambahan pilihan Anda.

  Pembeda segmen mengungkapkan yang membedakan satu segmen dari pelanggan atau segmen lain. Yang perlu Anda lakukan adalah mengidentifikasi segmen dan sistem akan mengidentifikasi atribut dan langkah profil yang membedakan segmen dalam bentuk daftar peringkat pembeda-dari pembeda terkuat hingga yang paling lemah.    
  Untuk informasi lebih lanjut, lihat [wawasan segmen (pratinjau)](segment-insights.md).

- **Menyegmentasikan seumur hidup**
  
  Tentukan jadwal untuk mengaktifkan atau menonaktifkan segmen.    
  Untuk informasi lebih lanjut, lihat [Kelola segmen yang ada](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Pembaruan Mei 2020

Pembaruan pada mei 2020 mencakup beberapa fitur, peningkatan kinerja, dan perbaikan bug.

### <a name="new-and-updated-features-in-may-2020"></a>Fitur baru dan yang diperbarui pada Mei 2020

#### <a name="data-ingestion"></a>Penyerapan data

- **Penyerapan data waktu nyata: tampilan riwayat**

  Saat menggunakan API kami untuk menelan pembaruan waktu nyata, Anda dapat melihat hingga 30 hari Riwayat agregat untuk pembaruan ini. Anda memiliki akses untuk menggabungkan semua panggilan yang berhasil atau gagal, termasuk hasilnya, sistem sumber, dan metadata berguna lainnya.    
  Lihat [penyerapan data real-time](real-time-data-ingestion.md) untuk informasi lebih lanjut.

- **Proses konsumsi data real-time: pembaruan profil**

  Ekstensi dari proses konsumsi data real-time ini memungkinkan Anda melihat, dalam hitungan detik, perubahan pada bidang profil pengguna tertentu.    
  Selain fungsi real-time untuk aktivitas, sistem mendukung pembaruan latensi rendah ke bidang profil. Pembaruan real-time untuk bidang profil memiliki waktu kedaluwarsa dan oleh karena itu bukan pengganti penyegaran terjadwal.    
  Lihat [penyerapan data real-time](real-time-data-ingestion.md) untuk informasi lebih lanjut.

#### <a name="extensibility"></a>Dapat diperluas

- **Timeline diperbarui dan paginasi pada Add-in kartu pelanggan**

  Timeline solusi Add-in kartu pelanggan sesuai dengan Timeline aktivitas. Paginasi Timeline membaik, menampilkan hingga 50 aktivitas sekaligus. Hal ini juga memungkinkan pemuatan aktivitas tambahan di Timeline.    
  Untuk informasi lebih lanjut, lihat [Add-in kartu pelanggan](customer-card-add-in.md).

- **pemicu Power Automate untuk perubahan segmen**

  Pemicu untuk Power Automate menentukan apa yang dapat Anda buat dari alur. Pemicu yang baru ditambahkan memungkinkan Anda menentukan ambang batas untuk segmen. Misalnya, Anda dapat membuat pemberitahuan yang akan dikirim saat ambang batas yang ditentukan diteruskan.    
  Untuk informasi lebih lanjut, lihat [Power Automate connector](export-power-automate.md).

- **Dukungan multipenyewa untuk model kustom**

  Konfigurasikan alur kerja untuk model kustom dengan layanan web dari penyewa Pembelajaran Mesin Azure yang berbeda. Anda dapat masuk ke penyewa Pembelajaran Mesin Azure saat membuat alur kerja baru untuk model kustom. Kemampuan ini merupakan tambahan untuk kemampuan mengintegrasikan yang ada dengan layanan web Pembelajaran Mesin Azure kustom Anda sendiri.    
  Untuk informasi lebih lanjut, lihat [model Pembelajaran Mesin kustom](custom-models.md).

#### <a name="segments"></a>Segmen

- **Otomatisasi jalur entitas**

  Saat membuat segmen, pengguna harus menentukan jalur entitas. Kemampuan ini mengambil langkah pertama di mengotomatisasi definisi jalur entitas sehingga Anda dapat fokus pada kriteria segmentasi yang Anda miliki.    
  Jika entitas untuk mensegmentasikan pelanggan Anda secara langsung berhubungan dengan entitas pelanggan terpadu, Anda tidak perlu menentukan lagi jalur entitas. Namun, jika ada lebih dari satu jalur entitas yang mungkin, Anda tetap harus mendefinisikannya secara manual.

- **Tindakan pada beberapa segmen**
  
  Pengguna dapat memilih beberapa segmen dan melakukan tindakan pada mereka, seperti menyegarkan segmen, dengan satu klik.    

- **Refresh Segmen**

  Pengguna dapat menyegarkan segmen tunggal atau hanya memilih segmen yang ingin mereka segarkan.    

  
- **Peningkatan untuk segmen majemuk**

  Pengguna dapat membuat, mengedit, dan menghapus segmen yang didasarkan pada segmen lain. Misalnya, segmen yang dibuat pada segmen lain yang dibuat pada segmen ketiga.    

- **Halaman daftar segmen**

  Desain baru halaman segmen menggunakan format daftar yang memungkinkan Anda melihat lebih banyak segmen sekaligus. Bidang pencarian ditambahkan untuk menemukan segmen dengan cepat. Pengguna sekarang dapat menerapkan tindakan seperti mengunduh atau menghapus beberapa segmen sekaligus. Pengalaman tren baru diperkenalkan untuk dengan cepat mengidentifikasi perubahan signifikan pada segmen.    
  Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).

#### <a name="system-administration"></a>Administrasi Sistem

- **Customer Insights tersedia di Microsoft Dynamics 365 Online Government**

  Dengan semakin banyak saluran untuk interaksi, data warga tersebar di berbagai sistem, mengakibatkan data terisolasi, dan tampilan informasi yang terfragmentasi tentang interaksi warga. Tanpa tampilan lengkap setiap interaksi warga di seluruh saluran, tidak mungkin bagi pemerintah untuk memodernisasi pada suatu skala. Microsoft berkomitmen untuk mendukung kebutuhan teknologi pemerintah untuk mengikuti harapan warga untuk pengalaman yang konsisten dan responsif.    
  Dengan Rilis 2020 Gelombang 1, Dynamics 365 Customer Insights akan tersedia untuk Awan Komunitas Pemerintah Cloud (GCC), lingkungan yang dibangun untuk memenuhi kebutuhan kepatuhan yang lebih tinggi dari badan pemerintah Amerika Serikat. Agensi mendapatkan tampilan terpadu warga dan menggunakan AI yang telah ditanamkan untuk memperoleh wawasan yang meningkatkan interaksi, memberdayakan karyawan, dan mengubah komunitas, sekaligus mengurangi kompleksitas dan memenuhi standar kepatuhan dan keamanan Amerika Serikat. Dynamics 365 Government memenuhi persyaratan yang menuntut dari program manajemen risiko dan otorisasi Federal AS (FedRAMP), memungkinkan lembaga federal Amerika Serikat memanfaatkan penghematan biaya dan keamanan Microsoft Cloud yang ketat.

## <a name="april-2020-updates"></a>Pembaruan April 2020

Pembaruan pada April 2020 mencakup beberapa fitur, peningkatan kinerja, dan perbaikan bug.

### <a name="new-and-updated-features-in-april-2020"></a>Fitur baru dan yang diperbarui pada April 2020

#### <a name="activities"></a>Aktivitas

- **Memetakan entitas aktivitas ke jenis aktivitas standar**
  
  Konfigurasi aktivitas dan penyimpanan saat ini didasarkan pada desain statis untuk melihatnya di Timeline. Arti aktivitas semantik, yang memiliki potensi beberapa kasus penggunaan di model AI, tidak sepenuhnya digunakan saat ini. Kami berencana untuk membuat Timeline aktivitas lebih dinamis, berdasarkan jenis aktivitas dan pemahaman semantik aktivitas dengan lebih baik. Fitur ini bertujuan untuk mengidentifikasi jenis aktivitas sebagaimana didefinisikan dalam Common Data Model untuk aktivitas yang diserap.
  Untuk informasi lebih lanjut, lihat [Aktivitas pelanggan](activities.md).

#### <a name="data-ingestion"></a>Penyerapan data

- **Konsumsi data real-time: aktivitas**
  
  Penyerapan data real-time menyediakan data segera untuk dikonsumsi, hingga penyegaran terjadwal berikutnya menarik data ini dari sumber data.    
  Lihat [penyerapan data real-time](real-time-data-ingestion.md) untuk informasi lebih lanjut.

- **Peningkatan persiapan data**
  
  Pelajari lebih lanjut tentang data yang terserap di entitas. Dengan ringkasan data, Anda dapat memahami karakteristik kualitas data yang dapat membantu melakukan tindakan yang tepat.    
  Untuk informasi lebih lanjut, lihat [Mengeksplorasi Data entitas](entities.md#exploring-a-specific-entitys-data).

- **Serap Data analitik dari Dynamics 365 dengan Common Data Service**
  
  Common Data Service tersedia sebagai cara untuk membuat sumber data. Pelanggan Dynamics 365 yang ada dapat menyerap entitas analitik dari Common Data Service ke Customer Insights. Sumber data tunggal dapat secara bersamaan menggunakan danau yang dikelola Common Data Service yang sama di lingkungan Customer Insights.    
  Untuk informasi lebih lanjut, lihat [menyambung ke data di Data Lake yang dikelola Common Data Service](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Dapat diperluas

- **Ekspor ke LiveRamp**

  Aktifkan data Anda di LiveRamp® untuk terhubung dengan lebih dari 500 platform lintas ekosistem digital, sosial, dan TV. Manfaatkan data Anda di LiveRamp untuk menargetkan, menekan, dan mempersonalisasi kampanye iklan.    
  Untuk informasi lebih lanjut, lihat [LiveRamp&reg; connector](export-liveramp.md).

- **Add-in Teams Customer Insights**
  
  Bot memberikan kemampuan pencarian untuk profil pelanggan terpadu. Ini akan menampilkan kartu hingga 15 bidang dari profil pelanggan yang dihasilkan. Beberapa kecocokan menghasilkan daftar hasil di mana Anda dapat memilih profil.    
  Untuk informasi lebih lanjut, lihat [bot tim untuk Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Tindakan

- **Halaman daftar pengukuran**
  
  Perbaikan halaman pengukuran mencakup dukungan untuk tindakan pada satu ukuran dan beberapa ukuran sekaligus. Selain itu, Anda akan menemukan bidang pencarian untuk menemukan dan melacak pengukuran dengan cepat.    
  Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).

- **Peningkatan untuk ukuran majemuk**
  
  Pengguna dapat membuat, mengedit, dan menghapus ukuran yang didasarkan pada ukuran lain. Misalnya, ukuran yang dibuat pada ukuran lain yang dibuat pada ukuran ketiga.

#### <a name="segments"></a>Segmen

- **operator Tambahan**
  
  Operator aliran masuk memungkinkan segmentasi untuk pelanggan dengan beberapa nilai string yang mungkin. Sebelum operator ini ditambahkan, Anda harus membangun segmen tersebut dengan beberapa kondisi OR. Operator aliran masuk memungkinkan Anda melakukannya dengan satu kondisi.    
  Untuk informasi lebih lanjut, lihat [Membuat dan mengelola segmen](segments.md).

#### <a name="system-administration"></a>Administrasi Sistem

- **Salin pengaturan konfigurasi ke lingkungan baru**
  
  Salin konfigurasi Anda dari satu lingkungan ke lingkungan lainnya. Saat membuat lingkungan baru, Anda dapat memilih lingkungan yang ada yang akan disalin konfigurasinya. Saat ini kami mendukung sumber data, penyatuan data, Relasi, langkah, dan segmen untuk disalin. Kredensial sumber data dan data aktual tidak disalin.    
  Untuk informasi lebih lanjut, lihat [Kelola lingkungan](manage-environments.md).
