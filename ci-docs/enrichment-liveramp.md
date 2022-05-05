---
title: Pengayaan data identitas LiveRamp
description: Memperkaya profil pelanggan dengan data LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642569"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Memperkaya profil pelanggan dengan data identitas dari LiveRamp (Pratinjau) 

LiveRamp menyediakan resolusi identitas offline deterministik dan konsolidasi data pelanggan. Anda dapat memetakan pengidentifikasi pribadi dalam data pelanggan Anda ke grafik identitas AbiliTec dan menerima ID AbiliTec. Anda kemudian dapat menggunakan ID ini untuk penyatuan data pelanggan Anda dengan lebih baik. 

## <a name="prerequisites"></a>Prasyarat 

Untuk mengonfigurasi pengayaan, prasyarat berikut harus dipenuhi: 

- Anda memiliki langganan LiveRamp aktif. Untuk mendapatkan langganan, hubungi tim akun LiveRamp Anda atau untuk [dynamics@liveramp.com](mailto:dynamics@liveramp.com) informasi lebih lanjut.   

- Langganan AbiliTec aktif dengan ID klien dan rahasia untuk mengakses API. Untuk informasi selengkapnya, lihat [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Negara/kawasan yang didukung 

Saat ini kami mendukung pengayaan profil pelanggan dengan data LiveRamp di Amerika Serikat saja. 

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan 

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**. 

1. Pilih **Perkaya data** saya di **petak Identitas**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Petak identitas di halaman gambaran umum pengayaan.":::

1. Pilih [koneksi](connections.md) dari daftar drop-down. Hubungi administrator jika tidak ada koneksi yang tersedia. Jika Anda seorang administrator, Anda dapat membuat koneksi dengan **memilih Tambahkan koneksi**. Pilih **LiveRamp** dari daftar tarik-turun. 

1. Pilih **Berikutnya** dan pilih **Pelanggan himpunan data** ingin Anda perkaya dengan data identitas dari LiveRamp. Anda dapat memilih entitas Pelanggan *untuk memperkaya semua profil pelanggan Anda atau memilih* entitas segmen *untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut*. 

1. Pilih **Berikutnya** dan tentukan jenis bidang dari profil terpadu Anda yang harus digunakan untuk mencari data identitas yang cocok dari LiveRamp. Setidaknya salah satu bidang **Nama dan alamat**, **Telepon**, atau **Email** diperlukan. 

   > [!TIP]
   > Semakin banyak pengidentifikasi dan bidang kunci yang Anda petakan, semakin besar kemungkinan tingkat kecocokan yang lebih tinggi 

1. Petakan bidang dari entitas Pelanggan *terpadu* Anda yang akan digunakan untuk mencocokkan dengan grafik ID AbiliTec LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opsi pemetaan data untuk pengayaan LiveRamp.":::

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**. 

1. **Berikan Nama** untuk pengayaan dan **entitas** Output. 

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda. 

## <a name="configure-the-connection-for-liveramp"></a>Mengonfigurasi koneksi untuk LiveRamp 

Anda harus menjadi administrator untuk [mengonfigurasi koneksi](connections.md). Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan atau buka **AdminConnections** > **dan** pilih **Siapkan** pada petak **LiveRamp**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Panel konfigurasi untuk menyiapkan koneksi ke layanan LiveRamp AbiliTec.":::

1. Untuk **nama tampilan**, masukkan nama koneksi. 

1. Berikan ID klien LiveRamp yang valid dan rahasia. 

1. Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**. 

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi. 

1. Untuk menyelesaikan koneksi, pilih **Simpan**. 

## <a name="enrichment-results"></a>Hasil pengayaan 

Untuk memulai proses pengayaan, pilih Jalankan dari bilah perintah. Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran](system.md#schedule-tab) terjadwal. Waktu pemrosesan tergantung pada ukuran data pelanggan Anda. 

Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**. Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya. 

Anda dapat mengakses tampilan terperinci dari setiap profil yang diperkaya dengan **memilih Data yang** diperkayaView. 

## <a name="next-steps"></a>Langkah berikutnya

Bangun di atas data pelanggan yang diperkaya. Gunakan ID AbiliTec untuk mengkonsolidasikan profil pelanggan menjadi tampilan berbasis orang. 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data 

Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke LiveRamp, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa LiveRamp memenuhi kewajiban privasi atau keamanan apa pun yang mungkin Anda miliki. Untuk informasi selengkapnya, tinjau [Pernyataan](https://go.microsoft.com/fwlink/?linkid=396732) Privasi Microsoft. Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini. 


[!INCLUDE [footer-include](includes/footer-banner.md)]
