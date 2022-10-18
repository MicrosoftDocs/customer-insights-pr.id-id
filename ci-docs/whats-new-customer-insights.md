---
title: Yang baru di Dynamics 365 Customer Insights
description: Informasi tentang fitur, peningkatan, dan perbaikan bug baru.
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: dcee60a73e0c32278553253040478c31e45237ae
ms.sourcegitcommit: 618ef15b434de0a68213383b6521ce2a60753afb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2022
ms.locfileid: "9638355"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Yang baru di Dynamics 365 Customer Insights

Kami sangat senang mengumumkan pembaruan terbaru kami! Artikel ini merangkum fitur pratinjau umum, fitur pratinjau, penyempurnaan ketersediaan umum, dan pembaruan fitur. Untuk melihat paket fitur jangka panjang, lihat [Dynamics 365 dan rencana rilis Power Platform](/dynamics365/release-plans/).

Kami meluncurkan pembaruan pada basis kawasan per kawasan. Sehingga wilayah tertentu mungkin melihat fitur sebelum orang lain. Kecuali ditentukan secara berbeda, Anda tidak perlu mengambil tindakan apa pun, kami akan memperbarui aplikasi secara otomatis tanpa waktu henti.

> [!TIP]
> Untuk mengirimkan dan memilih permintaan fitur dan saran produk, buka [portal ide aplikasi Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="september-2022-updates"></a>Pembaruan September 2022

Pembaruan pada September 2022 mencakup fitur baru, peningkatan kinerja, dan perbaikan bug.

### <a name="export-data-to-hubspot"></a>Ekspor data ke HubSpot

Ekspor segmen profil pelanggan terpadu ke HubSpot dan gunakan untuk pemasaran email.

Untuk informasi selengkapnya, lihat [Mengekspor segmen ke HubSpot](export-hubspot.md).

### <a name="remove-a-unified-field-or-entity-from-data-unification"></a>Menghapus bidang atau entitas terpadu dari penyatuan data

Anda dapat menghapus bidang dan entitas dari proses penyatuan data.

Untuk informasi selengkapnya, lihat [Menghapus bidang terpadu](data-unification-update.md#remove-a-unified-field).

### <a name="manage-unknown-customer-profiles"></a>Mengelola profil pelanggan yang tidak dikenal

Personalisasi yang mudah diingat bergantung pada kekayaan dan kelengkapan data pelanggan Anda dan Customer Insights membantu Anda mencapai tujuan ini. Anda dapat mengelola profil pelanggan untuk pengguna yang tidak memiliki informasi apa pun selain ID.

Untuk informasi selengkapnya, lihat [Mengelola profil yang tidak dikenal dengan Customer Insights](manage-unknown-profiles.md).

## <a name="august-2022-updates"></a>Pembaruan Agustus 2022

Pembaruan pada Agustus 2022 mencakup fitur baru, peningkatan kinerja, dan perbaikan bug.

### <a name="contact-unification-in-b-to-b-environments"></a>Penyatuan kontak di lingkungan B-to-B

Lingkungan B-to-B di Customer Insights kini mendukung pengalaman penyatuan data yang disempurnakan.

Anda sekarang dapat menyatukan kontak selain akun untuk mendapatkan tampilan penuh dari kontak bisnis Anda. Kontak terpadu dikaitkan dengan akun terpadu dan sekarang tercantum di kartu pelanggan. 

Untuk informasi selengkapnya, lihat [Membuat profil kontak terpadu](data-unification-contacts.md).

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>Membuat dan mengekspor segmen berdasarkan kontak terpadu

Berkat penyatuan kontak baru, Anda dapat membuat segmen kontak menggunakan kriteria dari kontak, akun, atau keduanya. Segmen-segmen ini dapat diekspor untuk aktivasi di layanan lain.

Untuk informasi selengkapnya, lihat [Gambaran umum](export-destinations.md) ekspor.

### <a name="deployment-regions-aligned-with-microsoft-dataverse"></a>Wilayah penyebaran yang selaras dengan Microsoft Dataverse

Saat membuat lingkungan Customer Insights baru, Anda dapat memilih wilayah tempat Anda ingin layanan disebarkan dan dihosting. Kami telah memperbarui pemilihan wilayah untuk menyelaraskan dengan Microsoft Dataverse dan Power Platform.

Anda sekarang dapat dengan mudah memilih wilayah yang sama dengan lingkungan yang ada Microsoft Dataverse atau akun penyimpanan Azure Data Lake Anda (jika Anda memilih opsi itu), tergantung pada ketersediaan Customer Insights di wilayah tersebut.

Untuk informasi selengkapnya, lihat [Membuat lingkungan](create-environment.md) baru dan [Ketersediaan produk menurut geografi](https://dynamics.microsoft.com/availability-reports/).

## <a name="july-2022-updates"></a>Pembaruan Juli 2022

Pembaruan pada Juli 2022 mencakup fitur baru, peningkatan kinerja, dan perbaikan bug.

### <a name="export-to-moengage"></a>Ekspor ke MoEngage

Ekspor segmen profil pelanggan terpadu ke MoEngage dan gunakan untuk pemasaran email di MoEngage.

Untuk informasi selengkapnya, lihat [Mengekspor segmen ke MoEngage](export-moengage.md).

### <a name="ssh-support-for-sftp-based-exports"></a>Dukungan SSH untuk ekspor berbasis SFTP

Pilih apakah Anda ingin mengautentikasi melalui SSH atau nama pengguna/kata sandi untuk koneksi ke tujuan ekspor SFTP.

Untuk informasi selengkapnya, lihat [Mengekspor data ke host](export-sftp.md) SFTP.

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Personalisasi pengalaman dengan data tentang pengguna yang dikenal dan tidak dikenal

Mengelola data pelanggan bukanlah tantangan baru, tetapi semakin sulit karena pengguna menavigasi berbagai saluran digital yang ditawarkan merek. Pengguna yang dikenal (diautentikasi) di satu saluran menjadi tidak dikenal (tidak diautentikasi) di saluran lain jika tidak masuk. Masalahnya sering adalah bahwa pengguna yang tidak diautentikasi (tidak diketahui) tidak memiliki ID umum. Ini dapat digunakan untuk mengaitkan atribut profil yang bermakna dan menghasilkan profil pelanggan terpadu. Customer Insights membantu memecahkan masalah ini dengan menyerap data dari metode pelacakan pada sistem sumber Anda.

Untuk informasi selengkapnya, lihat [Mempersonalisasi pengalaman Anda dengan data tentang pengguna](unknown-to-known.md) yang dikenal dan tidak dikenal.

## <a name="june-2022-updates"></a>Pembaruan Juni 2022

Pembaruan pada Juni 2022 mencakup fitur baru, peningkatan kinerja, dan perbaikan bug.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Pengalaman pengguna yang diperbarui untuk sumber data dan penyerapan data

Mengimpor data dari berbagai sumber data adalah dasar untuk mengkonsolidasikan data pelanggan Anda dalam Dynamics 365 Customer Insights format. Kami telah meninjau kembali pengalaman pengguna untuk impor dan koneksi sumber data. Pembaruan ini bertujuan untuk memudahkan Anda menyerap data ke Customer Insights.

Untuk informasi selengkapnya, lihat [Gambaran](data-sources.md) umum sumber data.

### <a name="export-to-inmobi"></a>Ekspor ke InMobi

InMobi membantu merek memahami, mengidentifikasi, melibatkan, dan memperoleh konsumen. Anda dapat mengekspor segmen dan data lainnya ke layanan InMobi melalui akun Azure Blob Storage.

Untuk informasi selengkapnya, lihat [Mengekspor ke InMobi (pratinjau)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Dukungan Lockbox di Customer Insights

Customer Lockbox menyediakan antarmuka untuk meninjau dan menyetujui (atau menolak) permintaan akses data. Permintaan ini terjadi ketika akses data ke data pelanggan diperlukan untuk menyelesaikan kasus dukungan.

Untuk informasi selengkapnya, lihat [Mengakses data pelanggan dengan aman dengan Customer Lockbox (Pratinjau)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>Menyambungkan ke data Anda menggunakan Azure Private Link

Azure Private Link memungkinkan Customer Insights terhubung ke akun Anda melalui titik akhir privat di jaringan virtual Anda Azure Data Lake Storage. Untuk data di akun penyimpanan, yang tidak terekspos ke internet publik, Private Link memungkinkan koneksi ke jaringan terbatas tersebut.

Untuk informasi selengkapnya, lihat [Menggunakan Private Link di Customer Insights](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>Pembaruan Mei 2022

Pembaruan pada Mei 2022 mencakup fitur baru, peningkatan kinerja, dan perbaikan bug.

### <a name="updated-data-unification-experience"></a>Pengalaman penyatuan data yang diperbarui

 Penyatuan data memungkinkan Anda menyatukan sumber data yang sekali berbeda ke dalam satu himpunan data master yang menyediakan tampilan terpadu dari data tersebut. Data dapat disatukan pada satu entitas atau beberapa entitas. Pertama, Anda [memilih entitas dan bidang sumber, menghapus rekaman](map-entities.md) duplikat, menentukan aturan untuk [kondisi](remove-duplicates.md) yang cocok, [dan menentukan bidang](match-entities.md) mana yang [akan disertakan dalam profil](merge-entities.md) pelanggan terpadu.

Untuk informasi selengkapnya, lihat [Gambaran umum](data-unification.md) penyatuan data.

### <a name="refreshed-home-page-in-customer-insights"></a>Halaman beranda yang diperbarui di Customer Insights

**Home** memandu Anda melalui proses konfigurasi untuk fitur-fitur utama dan memberikan gambaran umum tentang segmen, ukuran, dan data pengayaan. Kami telah menyegarkan pengalaman untuk memberikan informasi yang lebih relevan secara sekilas.

Untuk informasi selengkapnya, lihat [Menjelajahi Customer Insights](home.md).

### <a name="track-usage-of-a-segment"></a>Melacak penggunaan segmen

Kini [Anda dapat melacak penggunaan segmen](segments.md#track-usage-of-a-segment) di aplikasi, yang didasarkan pada organisasi yang Dataverse terhubung dengan Customer Insights. Untuk [segmen Customer Insights yang digunakan dalam perjalanan pelanggan Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), sistem akan memberi tahu Anda tentang penggunaan segmen tersebut.

### <a name="export-to-criteo"></a>Ekspor ke Criteo

Criteo adalah platform online yang membantu pengguna mengelola iklan digital. Anda sekarang dapat mengekspor segmen profil pelanggan terpadu untuk menghasilkan kampanye, menyediakan pemasaran email, dan menggunakan grup pelanggan tertentu dengan Criteo.

Untuk informasi selengkapnya, lihat [Mengekspor segmen ke Criteo (pratinjau)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Struktur dokumentasi yang disempurnakan untuk pembuatan lingkungan

Kami telah meninjau kembali dokumen bantuan yang terkait dengan pembuatan dan pengelolaan lingkungan di Customer Insights. Artikel sekarang dikelompokkan di bawah node Lingkungan dalam daftar isi. Artikel yang direstrukturisasi memberikan lebih banyak panduan untuk berbagai cara mengatur lingkungan dan memiliki struktur yang lebih jelas. Jika Anda memiliki umpan balik untuk dibagikan, beri tahu kami melalui kontrol di akhir artikel bantuan.

Untuk informasi selengkapnya, lihat [Cara: Membuat lingkungan](create-environment.md) baru.

## <a name="april-2022-updates"></a>Pembaruan April 2022

Pembaruan pada April 2022 mencakup fitur baru, peningkatan kinerja, dan perbaikan bug.

### <a name="dun--bradstreet-enrichment-preview"></a>Pengayaan Dun & Bradstreet (Pratinjau)

Dun & Bradstreet menyediakan data komersial, analitik, dan wawasan untuk bisnis. Hal ini memungkinkan pelanggan dengan profil pelanggan terpadu untuk perusahaan untuk memperkaya data mereka. Pengayaan mencakup atribut seperti nomor DUNS, ukuran perusahaan, lokasi, industri, dan banyak lagi.

Untuk informasi selengkapnya, lihat [Pengayaan profil perusahaan dengan Dun & Bradstreet (Pratinjau)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Menentukan jenis pengukuran saat membuat pengukuran baru

Kini Anda dapat membedakan antara ukuran untuk profil individual dan ukuran di seluruh bisnis Anda. Sementara langkah-langkah bisnis ditampilkan di halaman beranda Customer Insights, langkah-langkah pelanggan diekspos pada tampilan pelanggan yang terperinci.

Untuk informasi selengkapnya, lihat [Menggunakan pembuat pengukuran untuk membuat pengukuran dari awal](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Konsolidasi dokumentasi Customer Insights

Kami telah meninjau kembali artikel dokumentasi kami dan menghapus penyebutan wawasan keterlibatan dan kemampuan wawasan audiens. Ke depannya, kami akan merujuk secara konsisten ke nama produk Customer Insights saat kami menulis tentang fitur inti aplikasi. Perubahan ini juga mengarah pada restrukturisasi yang signifikan dari daftar isi, struktur URL, dan jalur file dalam repositori dokumentasi yang mendasarinya. Semua bookmark atau tautan yang ada terus berfungsi dan dialihkan ke URL yang diperbarui.

Jika Anda ingin memberi tahu kami bagaimana Anda memandang perubahan itu atau melihat sesuatu yang tidak berfungsi seperti yang diharapkan, beri tahu kami dengan [mengirimkan umpan balik untuk halaman](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**) ini.

## <a name="march-2022-updates"></a>Pembaruan Maret 2022

Pembaruan pada Maret 2022 mencakup fitur baru, peningkatan kinerja, dan perbaikan bug.

### <a name="liveramp-abilitec-enrichment-preview"></a>Pengayaan LiveRamp AbiliTec (Pratinjau)

LiveRamp menyediakan resolusi identitas dan konsolidasi data pelanggan. Anda dapat memetakan pengidentifikasi pribadi dalam data pelanggan Anda ke grafik identitas AbiliTec dan menerima ID AbiliTec. Anda kemudian dapat menggunakan ID ini untuk penyatuan data pelanggan Anda dengan lebih baik.

Untuk informasi selengkapnya, lihat [Memperkaya profil pelanggan dengan data identitas dari LiveRamp (Pratinjau)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Mengatur segmen dan ukuran dengan tag dan filter

Jika organisasi Anda mempertahankan banyak segmen atau tindakan, menemukan yang tepat terkadang terasa menantang. Fitur baru ini memungkinkan Anda menata daftar menggunakan tag dan kolom. Ini membantu untuk menemukan data dengan cepat dan mudah dan menyesuaikan tampilan.

Untuk informasi selengkapnya, lihat [Bekerja dengan tag dan kolom](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Aktifkan berbagi data saat Dataverse menggunakan akun penyimpanan Anda sendiri

Jika lingkungan Anda menggunakan Azure Data Lake Storage untuk menyimpan data Customer Insights, berbagi data dengan Microsoft Dataverse memerlukan beberapa konfigurasi tambahan.
Sebelumnya, Anda hanya dapat mengaktifkan berbagi data saat Dataverse data Anda disimpan di data lake terkelola kami.

Untuk informasi selengkapnya, lihat [Mengaktifkan berbagi data dengan Dataverse dari milik Anda sendiri Azure Data Lake Storage (Pratinjau)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Tujuan ekspor baru: Iterable dan Braze

Kami terus memperluas ekosistem tujuan ekspor kami dengan koneksi baru. Anda sekarang dapat mengekspor segmen ke Iterable dan Braze untuk menggunakan layanan aktivasi mereka.

Untuk informasi selengkapnya, lihat [Mengekspor segmen ke Dapat Diulang (pratinjau)](export-iterable.md) dan [Mengekspor segmen ke Braze (pratinjau).](export-braze.md)

### <a name="improvements-to-marketo-and-google-ads-export"></a>Peningkatan pada ekspor Marketo dan Google Ads

Mengubah API dalam layanan yang terhubung menyebabkan pembaruan agar konektor berjalan dengan andal dan lancar. Kami telah merilis beberapa pembaruan untuk ekspor ke layanan Marketo dan Google Ads:

- Google Ads: Versi baru konektor ekspor Google Ads menyederhanakan pengalaman autentikasi dan kini memungkinkan Anda membuat audiens Google Ads baru secara otomatis. 
- Marketo: Versi baru konektor ekspor Marketo menyediakan dukungan untuk ID Marketo, memungkinkan Anda menghindari duplikasi data, memperbarui catatan yang ada, dan membuat catatan baru di Marketo. 

## <a name="february-2022-updates"></a>Pembaruan Februari 2022

Pembaruan pada Februari 2022 mencakup fitur baru, peningkatan kinerja, dan perbaikan bug.

### <a name="general-availability-for-prediction-models"></a>Ketersediaan umum untuk model prediksi

Model prediksi siap pakai, termasuk **churn langganan, churn** **transaksional,** dan **nilai umur pelanggan (CLV)** tersedia secara umum sebagai bagian dari Customer Insights. 

Untuk informasi selengkapnya, lihat [Gambaran umum prediksi](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Sumber data Baru: Integrasi dengan Azure Synapse Analytics (Pratinjau)

Azure Synapse Analytics adalah layanan analitik perusahaan yang mempercepat waktu untuk wawasan di seluruh gudang data dan sistem data besar.

Organisasi yang sudah menggunakan Azure Synapse Analytics dapat menyerap data tersebut ke Customer Insights. 

Untuk informasi selengkapnya, lihat [Menyambungkan Azure Synapse sumber data (Pratinjau)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Pengayaan LiveRamp (Pratinjau)

LiveRamp menyediakan resolusi identitas dan konsolidasi data pelanggan. Anda dapat memetakan pengidentifikasi pribadi dalam data pelanggan Anda ke grafik identitas AbiliTec dan menerima ID AbiliTec. Anda kemudian dapat menggunakan ID ini untuk penyatuan data pelanggan Anda dengan lebih baik.

Untuk informasi selengkapnya, lihat [Memperkaya profil pelanggan dengan data identitas dari LiveRamp (Pratinjau)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Pengayaan untuk sumber data (Pratinjau)

Gunakan data dari sumber seperti Microsoft dan mitra lain untuk memperkaya data pelanggan Anda sebelum penyatuan data. Pengayaan sumber data membantu menghasilkan kelengkapan dan kualitas data yang lebih tinggi yang dapat membantu mencapai hasil yang lebih baik setelah Anda menyatukan data Anda.

Untuk informasi selengkapnya, lihat [Pengayaan untuk sumber data (Pratinjau)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Ubah pemilik lingkungan

Meskipun beberapa pengguna dapat memiliki izin admin di Customer Insights, hanya satu pengguna yang merupakan pemilik lingkungan. Pengalaman yang lebih baik memungkinkan Anda mengubah pemilik lingkungan dan mengklaim kepemilikan jika pemilik sebelumnya meninggalkan organisasi. 

Untuk informasi selengkapnya, lihat [Mengubah pemilik lingkungan](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Proses persiapan data mencantumkan alasan kerusakan untuk catatan yang rusak

Persiapan data sekarang menunjukkan alasan kerusakan untuk semua bidang dengan data yang rusak. Informasi ini disediakan di tingkat catatan individu untuk memudahkan identifikasi.

Untuk informasi selengkapnya, lihat [Sumber](data-sources.md#corrupt-data-sources) data yang rusak.

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Akhir pratinjau untuk fitur pelaporan dalam kemampuan wawasan keterlibatan

Pratinjau Dynamics 365 Customer Insights kemampuan wawasan keterlibatan berakhir pada 15 Februari 2022.  
Perubahan ini berarti pengalaman uji coba Customer Insights tidak lagi mencakup kemampuan untuk membuat corong atau fungsi pelaporan lainnya.

Kami mengundang Anda untuk menjelajahi dan mengevaluasi banyak fitur lain dari [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), platform data pelanggan (CDP) Microsoft.    
 
Untuk periode transisi, peserta pratinjau yang ada masih memiliki akses ke beberapa kemampuan dan fungsionalitas pratinjau:

- Mendapatkan kode untuk instrumen situs web atau aplikasi ponsel 
- Melihat peristiwa dan properti peristiwa 
- Tingkatkan profil terpadu dengan peristiwa yang diserap dan disempurnakan untuk mendapatkan manfaat dari nilai penuh data pelanggan mereka
  
Selama masa transisi, peristiwa yang diambil masih dialirkan ke Data Lake yang terhubung. Setelah fungsi ini dinonaktifkan, berbagi data akan berhenti, dan tidak ada peristiwa baru yang dikirim ke penyimpanan yang terhubung.
Hubungi tim Akun Microsoft Anda secara langsung jika Anda memiliki pertanyaan tentang akhir pratinjau kemampuan. Tim Akun Anda akan terus memberi Anda informasi terbaru tentang peluncuran yang akan datang. 

## <a name="january-2022-updates"></a>Pembaruan Januari 2022

Pembaruan pada Januari 2022 mencakup fitur baru, peningkatan kinerja, dan perbaikan bug.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analisis sentimen umpan balik pelanggan Anda

Customer Insights menyediakan fitur baru yang didukung AI untuk mensintesis sentimen pelanggan dan mengidentifikasi aspek bisnis tertentu sebagai peluang untuk peningkatan yang ditargetkan. Dengan menganalisis umpan balik tertulis dari pelanggan Anda, Anda bisa mendapatkan wawasan yang akurat dengan biaya rendah. Analisis sentimen didukung oleh model Natural Language Processing (NLP) yang menghasilkan dua wawasan turunan untuk setiap ID pelanggan. Skor sentimen (dari –5 hingga 5) dan daftar aspek bisnis yang berlaku. 

Untuk informasi selengkapnya, lihat [Menganalisis sentimen dalam umpan balik pelanggan (Pratinjau)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]