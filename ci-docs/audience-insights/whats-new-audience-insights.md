---
title: Fitur baru dan mendatang
description: Informasi tentang fitur, peningkatan, dan perbaikan bug baru.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 2f081306271a170cf3e250fc1a193cedb70aeec6
ms.sourcegitcommit: 0363559a1af7ae16da2a96b09d6a4a8a53a8cbb8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547676"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Yang baru di kemampuan audiens wawasan Dynamics 365 Customer Insights

Kami sangat senang mengumumkan pembaruan terbaru kami! Artikel ini merangkum fitur pratinjau umum, fitur pratinjau, penyempurnaan ketersediaan umum, dan pembaruan fitur. Untuk melihat paket fitur jangka panjang, lihat [Dynamics 365 dan rencana rilis Power Platform](/dynamics365/release-plans/).

Kami meluncurkan pembaruan pada basis kawasan per kawasan. Sehingga wilayah tertentu mungkin melihat fitur sebelum orang lain. Kecuali ditentukan berbeda, Anda tidak perlu melakukan tindakan apa pun dan kami akan memperbarui aplikasi secara otomatis tanpa waktu henti.

> [!TIP]
> Untuk mengirimkan dan memilih permintaan fitur dan saran produk, buka [portal ide aplikasi Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Pembaruan Maret 2022

Pembaruan pada Maret 2022 mencakup fitur baru, peningkatan kinerja, dan perbaikan bug.

### <a name="liveramp-abilitec-enrichment-preview"></a>Pengayaan LiveRamp AbiliTec (Pratinjau)

LiveRamp menyediakan resolusi identitas dan konsolidasi data pelanggan. Anda dapat memetakan pengidentifikasi pribadi dalam data pelanggan Anda ke grafik identitas AbiliTec dan menerima ID AbiliTec. Anda kemudian dapat menggunakan DAFTAR ini untuk penyatuan data pelanggan Anda dengan lebih baik.

Untuk informasi selengkapnya, lihat [Memperkaya profil pelanggan dengan data identitas dari LiveRamp (Pratinjau)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Mengatur segmen dan ukuran dengan tag dan filter
Jika organisasi Anda mempertahankan banyak segmen atau ukuran, menemukan yang tepat terkadang bisa terasa menantang. Fitur baru ini memungkinkan Anda mengatur daftar menggunakan tag dan kolom. Ini membantu menemukan data dengan cepat dan mudah dan menyesuaikan tampilan.

Untuk informasi selengkapnya, lihat [Bekerja dengan tag dan kolom](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Aktifkan berbagi data saat Dataverse menggunakan akun penyimpanan Anda sendiri

Jika lingkungan Anda digunakan Azure Data Lake Storage untuk menyimpan data Wawasan Pelanggan, berbagi data dengan Microsoft Dataverse memerlukan konfigurasi tambahan.
Sebelumnya, Anda hanya dapat mengaktifkan berbagi data saat Dataverse data Anda disimpan di danau data terkelola kami. 

Untuk informasi selengkapnya, lihat [Mengaktifkan berbagi data dari Dataverse Anda sendiri Azure Data Lake Storage (Pratinjau)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Tujuan ekspor baru: Iterable dan Braze

Kami terus memperluas ekosistem tujuan ekspor kami dengan koneksi baru. Anda sekarang dapat mengekspor segmen ke Iterable dan Braze untuk menggunakan layanan aktivasi mereka.

Untuk informasi selengkapnya, lihat [Mengekspor segmen ke segmen Iterable (pratinjau)](export-iterable.md) dan [Ekspor ke Braze (pratinjau)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Peningkatan ekspor Marketo dan Google Ads

Mengubah API dalam layanan yang terhubung menyebabkan pembaruan agar konektor berjalan dengan andal dan lancar. Kami telah merilis beberapa pembaruan untuk ekspor ke layanan Marketo dan Google Ads:

- Google Ads: Versi baru konektor ekspor Google Ads menyederhanakan pengalaman autentikasi dan sekarang memungkinkan Anda membuat audiens Google Ads baru secara otomatis. 
- Marketo: Versi baru konektor ekspor Marketo memberikan dukungan untuk ID Marketo, memungkinkan Anda untuk menghindari duplikasi data, memperbarui catatan yang ada, dan membuat catatan baru di Marketo. 


## <a name="february-2022-updates"></a>Pembaruan Februari 2022

Pembaruan pada Februari 2022 mencakup fitur baru, peningkatan kinerja, dan perbaikan bug.

### <a name="general-availability-for-prediction-models"></a>Ketersediaan umum untuk model prediksi

Model prediksi out-of-the-box, termasuk **churn** berlangganan, **churn** transaksional, dan **nilai masa pakai pelanggan (CLV)** menjadi tersedia secara umum sebagai bagian dari Customer Insights. 

Untuk informasi selengkapnya, lihat [Ikhtisar](predictions-overview.md) Prediksi.

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Sumber data Baru: Integrasi dengan Azure Synapse Analytics (Pratinjau)

Azure Synapse Analytics adalah layanan analitik perusahaan yang mempercepat waktu untuk wawasan di seluruh gudang data dan sistem data besar.

Organisasi yang sudah menggunakan Azure Synapse Analytics dapat menelan data tersebut ke Customer Insights. 

Untuk informasi selengkapnya, lihat [Menyambungkan Azure Synapse sumber data (Pratinjau)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Pengayaan LiveRamp (Pratinjau)

LiveRamp menyediakan resolusi identitas dan konsolidasi data pelanggan. Anda dapat memetakan pengidentifikasi pribadi dalam data pelanggan Anda ke grafik identitas AbiliTec dan menerima ID AbiliTec. Anda kemudian dapat menggunakan DAFTAR ini untuk penyatuan data pelanggan Anda dengan lebih baik.

Untuk informasi selengkapnya, lihat [Memperkaya profil pelanggan dengan data identitas dari LiveRamp (Pratinjau)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Pengayaan untuk sumber data (Pratinjau)

Gunakan data dari sumber seperti Microsoft dan mitra lainnya untuk memperkaya data pelanggan Anda sebelum penyatuan data. Sumber data membantu menghasilkan kelengkapan dan kualitas data yang lebih tinggi yang dapat membantu mencapai hasil yang lebih baik setelah Anda menyatukan data Anda.

Untuk informasi selengkapnya, lihat [Pengayaan untuk sumber data (Pratinjau)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Ubah pemilik lingkungan

Sementara beberapa pengguna dapat memiliki izin admin di Customer Insights, hanya satu pengguna yang merupakan pemilik lingkungan. Pengalaman yang ditingkatkan memungkinkan Anda mengubah pemilik lingkungan dan mengklaim kepemilikan jika mantan pemilik meninggalkan organisasi. 

Untuk informasi selengkapnya, lihat [Mengubah pemilik lingkungan](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Proses persiapan data mencantumkan alasan korupsi untuk catatan yang rusak

Persiapan data sekarang menunjukkan alasan korupsi untuk semua bidang dengan data yang rusak. Informasi diberikan pada tingkat catatan individu untuk identifikasi yang mudah. 

Untuk informasi selengkapnya, lihat [Sumber](entities.md#corrupted-data-sources) data yang rusak.

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Akhir pratinjau untuk melaporkan fitur dalam kemampuan wawasan keterlibatan

Pratinjau Dynamics 365 Customer Insights kemampuan wawasan keterlibatan berakhir 15 Februari 2022.  
Perubahan ini berarti pengalaman uji coba Customer Insights tidak lagi mencakup kemampuan untuk membuat corong atau fungsi pelaporan lainnya.

Kami mengundang Anda untuk menjelajahi dan mengevaluasi banyak fitur lain dari [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), platform data pelanggan Microsoft (CDP).    
 
Untuk masa transisi, peserta pratinjau yang ada masih memiliki akses ke beberapa kemampuan dan fungsionalitas pratinjau:

- Mendapatkan kode untuk instrumen situs web atau aplikasi ponsel 
- Melihat properti acara dan acara 
- Tingkatkan profil terpadu dengan peristiwa yang dicerna dan disempurnakan untuk mendapatkan manfaat dari nilai penuh data pelanggan mereka
  
Selama masa transisi, peristiwa yang ditangkap masih dialirkan ke Danau Data yang terhubung. Setelah fungsi ini dimatikan, berbagi data antara wawasan keterlibatan dan wawasan audiens akan berhenti dan tidak ada peristiwa baru yang dikirim ke penyimpanan yang terhubung.
Hubungi tim Akun Microsoft Anda secara langsung jika Anda memiliki pertanyaan tentang akhir pratinjau kemampuan. Tim Akun Anda akan membuat Anda tetap up-to-date pada peluncuran mendatang. 

## <a name="january-2022-updates"></a>Pembaruan Januari 2022

Pembaruan pada Januari 2022 mencakup fitur baru, peningkatan kinerja, dan perbaikan bug.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Analisis sentimen dari umpan balik pelanggan Anda

Customer Insights menyediakan fitur baru bertenaga AI untuk mensintesis sentimen pelanggan dan mengidentifikasi aspek bisnis tertentu sebagai peluang untuk peningkatan yang ditargetkan. Dengan menganalisis umpan balik tertulis dari pelanggan Anda, Anda bisa mendapatkan wawasan yang akurat dengan biaya rendah. Analisis sentimen didukung oleh model Natural Language Processing (NLP) yang menghasilkan dua wawasan turunan untuk setiap ID pelanggan. Skor sentimen (dari -5 hingga 5) dan daftar aspek bisnis yang berlaku. 

Untuk informasi selengkapnya, lihat [Menganalisis sentimen dalam umpan balik pelanggan (Pratinjau)](sentiment-analysis.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]