---
title: Pengayaan dengan pengayaan pihak ketiga Experian
description: Informasi umum tentang pengayaan pihak ketiga Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ad1023135516ca9c49818d19aa84df68d16b2e3c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229968"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Perkaya profil pelanggan dengan demografi dari Experian (pratinjau)

Experian adalah pemimpin global dalam pelaporan kredit konsumen dan bisnis serta layanan pemasaran. Dengan layanan pengayaan data Experian, Anda dapat membangun pemahaman yang lebih mendalam tentang pelanggan dengan memperkaya profil pelanggan dengan data demografis seperti ukuran rumah tangga, penghasilan, dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

Untuk mengonfigurasikan Experian, prasyarat berikut harus dipenuhi:

- Anda memiliki langganan Experian aktif. Untuk mendapatkan langganan, [hubungi Experian](https://www.experian.com/marketing-services/contact) secara langsung. [Pelajari selengkapnya tentang Pengayaan data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Koneksi Experian telah dikonfigurasi oleh administrator *atau* Anda memiliki izin [administrator](permissions.md#administrator). Anda juga memerlukan ID Pengguna, ID Pihak, dan Nomor Model untuk akun ST (Secure Transport) berkemampuan SSH yang dibuat Experian untuk Anda.

## <a name="supported-countriesregions"></a>Negara/kawasan yang didukung

Kami saat ini hanya mendukung pengayaan profil pelanggan di Amerika Serikat.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data saya** pada petak Experian.

   > [!div class="mx-imgBorder"]
   > ![petak Experian.](media/experian-tile.png "Experian tile")
   > 

1. Pilih [koneksi](connections.md) dari daftar drop-down. Hubungi administrator jika tidak ada koneksi yang tersedia. Jika Anda administrator, Anda dapat membuat sambungan dengan memilih **Tambah sambungan** dan memilih Experian dari daftar dropdown. 

1. Pilih **Sambungkan ke Experian** untuk mengkonfirmasi pilihan koneksi.

1.  Pilih **Berikutnya** dan pilih **himpunan data Pelanggan** yang ingin Anda perkaya dengan data demografi dari Experian. Anda dapat memilih entitas **Pelanggan** untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Tangkapan layar saat memilih himpunan data pelanggan.":::

1. Pilih **Berikutnya** dan tentukan jenis bidang dari profil terpadu yang akan digunakan untuk mencari data historis yang cocok dari Experian. Setidaknya salah satu bidang **Nama dan alamat**, **Telepon**, atau **Email** diperlukan. Untuk akurasi pencocokan yang lebih tinggi, hingga dua bidang lain dapat ditambahkan. Pilihan ini akan memengaruhi bidang pemetaan yang dapat Anda akses di langkah berikutnya.

    > [!TIP]
    > Atribut pengidentifikasi utama lainnya yang dikirim ke Experian cenderung menghasilkan tingkat kecocokan yang lebih tinggi.

1. Untuk memulai pemetaan bidang, pilih **berikutnya**.

1. Tentukan bidang dari profil terpadu yang akan digunakan untuk mencari data historis yang cocok dari Experian. Bidang yang diperlukan ditandai.

1. Berikan nama untuk pengayaan dan nama untuk entitas output.

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

## <a name="configure-the-connection-for-experian"></a>Mengonfigurasi koneksi untuk Experian 

Anda perlu menjadi administrator untuk mengonfigurasi koneksi. Pilih **Tambah koneksi** saat mengkonfigurasi pengayaan *atau* buka **Admin** > **Koneksi**, lalu pilih **Atur** pada petak Experian.

1. Pilih **Mulai**.

1. Masukkan nama untuk koneksi dalam kotak **nama tampilan**.

1. Masukkan ID Pengguna, ID Pihak, dan Nomor Model yang valid untuk akun Secure Transport Experian Anda.

1. Baca dan berikan persetujuan Anda untuk **privasi dan kesesuaian Data** dengan memilih **Saya setuju**.

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi.

1. Setelah menyelesaikan verifikasi, pilih **Simpan**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Panel Konfigurasi koneksi Experian.":::

## <a name="enrichment-results"></a>Hasil pengayaan

Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah. Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab). Waktu pemrosesan akan tergantung pada ukuran data pelanggan dan proses pengayaan yang disiapkan untuk akun Anda oleh Experian.

Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan baru yang diperkaya di dalam **pengayaan saya**. Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.

Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mentransmisikan data ke Experian, Anda mengizinkan transfer data di luar batas kesesuaian untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mengalihkan data tersebut berdasarkan instruksi Anda, namun Anda bertanggung jawab untuk memastikan bahwa Experian memenuhi privasi atau jaminan keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
