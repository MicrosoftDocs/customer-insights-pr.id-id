---
title: Pengayaan dengan Experian pengayaan pihak ketiga
description: Informasi umum tentang pengayaan pihak ketiga Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896377"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Memperkaya profil pelanggan dengan demografi dari Experian (pratinjau)

Experian adalah pemimpin global dalam pelaporan kredit konsumen dan bisnis serta layanan pemasaran. Dengan layanan pengayaan data Experian, Anda dapat membangun pemahaman yang lebih mendalam tentang pelanggan Anda dengan memperkaya profil pelanggan Anda dengan data demografis seperti ukuran rumah tangga, pendapatan, dan lainnya.

## <a name="prerequisites"></a>Prasyarat

Untuk mengonfigurasikan Experian, prasyarat berikut harus dipenuhi:

- Anda memiliki langganan Experian aktif. Untuk mendapatkan langganan, [Hubungi Experian](https://www.experian.com/marketing-services/contact) secara langsung. [Pelajari selengkapnya tentang pengayaan data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Koneksi Experian telah dikonfigurasi oleh administrator *atau* Anda memiliki izin [administrator](permissions.md#administrator). Anda juga memerlukan ID Pengguna, ID Pesta, dan Nomor Model untuk akun Secure Transport (ST) berkemampuan SSH yang dibuat Experian untuk Anda.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data saya** di petak Experian.

   > [!div class="mx-imgBorder"]
   > ![petak Experian](media/experian-tile.png "petak Experian")
   > 

1. Pilih [koneksi](connections.md) dari menu tarik-turun. Hubungi administrator jika tidak ada koneksi yang tersedia. Jika Anda adalah administrator, Anda bisa membuat koneksi dengan memilih **Tambahkan koneksi** dan memilih Experian dari menu tarik-turun. 

1. Pilih **Sambungkan ke Experian** untuk mengonfirmasi pilihan koneksi.

1.  Pilih **Berikutnya** dan pilih **himpunan data Pelanggan** yang ingin Anda perkaya dengan data demografis dari Experian. Anda dapat memilih entitas **Pelanggan** untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Tangkapan layar saat memilih himpunan data pelanggan.":::

1. Pilih **Berikutnya** dan tentukan tipe bidang mana dari profil terpadu Anda yang harus digunakan untuk mencari data demografis yang cocok dari Experian. Setidaknya salah satu bidang **Nama dan alamat**, **Telepon**, atau **Email** diperlukan. Untuk akurasi pencocokan yang lebih tinggi, hingga dua bidang lain dapat ditambahkan. Pilihan ini akan memengaruhi bidang pemetaan yang dapat Anda akses di langkah berikutnya.

    > [!TIP]
    > Atribut pengidentifikasi kunci lainnya yang dikirim ke Experian kemungkinan menghasilkan tingkat kecocokan yang lebih tinggi.

1. Untuk memulai pemetaan bidang, pilih **berikutnya**.

1. Tentukan bidang mana dari profil terpadu Anda yang harus digunakan untuk mencari data demografis yang cocok dari Experian. Bidang yang diperlukan ditandai.

1. Berikan nama untuk pengayaan dan nama untuk entitas output.

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

## <a name="configure-the-connection-for-experian"></a>Mengonfigurasi koneksi untuk Experian 

Anda perlu menjadi administrator untuk mengonfigurasi koneksi. Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan *atau* masuk ke **Admin** > **Koneksi** dan pilih **Konfigurasi** pada petak Experian.

1. Pilih **Mulai**.

1. Masukkan nama untuk koneksi dalam kotak **nama tampilan**.

1. Masukkan ID pengguna, ID pesta, dan Nomor Model yang valid untuk akun Secure Transport Experian Anda.

1. Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi.

1. Setelah menyelesaikan verifikasi, pilih **Simpan**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Panel konfigurasi koneksi Experian.":::

## <a name="enrichment-results"></a>Hasil pengayaan

Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah. Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab). Waktu pemrosesan akan tergantung pada ukuran data pelanggan Anda dan proses pengayaan diatur untuk akun Anda oleh Experian.

Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan baru yang diperkaya di dalam **pengayaan saya**. Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.

Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.

## <a name="next-steps"></a>Langkah berikutnya

Bangun di atas data pelanggan yang diperkaya. Buat [segmen](segments.md), [tindakan](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan bagi pelanggan Anda.

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Experian, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Experian memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
