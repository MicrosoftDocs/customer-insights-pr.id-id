---
title: Memperkaya profil pelanggan dengan data lokasi dari Azure Maps
description: Informasi umum tentang pengayaan pihak pertama Azure Maps.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 63f241c27ec86f357c83a301d6797f9ff87c2241
ms.sourcegitcommit: 2acda3c5adf40bc3f5bbb4b2b4b6c22f84371da7
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466766"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Pengayaan profil pelanggan dengan Azure Maps (pratinjau)

Azure Maps menyediakan data dan layanan berpusat lokasi untuk memberikan pengalaman berdasarkan data geospasial dengan inteligensi lokasi built-in. Layanan pengayaan data Azure Maps akan meningkatkan presisi informasi lokasi tentang pelanggan Anda. Ia memberikan kemampuan seperti normalisasi alamat dan ekstrak garis lintang dan garis bujur untuk Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi pengayaan data Azure Maps, prasyarat berikut harus dipenuhi:

- Anda memiliki langganan Azure Maps aktif. Untuk mendapatkan langganan, Anda dapat [mendaftar atau mendapatkan uji coba gratis](https://azure.microsoft.com/services/azure-maps/).

- [Sambungan](connections.md) Azure Maps tersedia, *atau* Anda memiliki izin [administrator](permissions.md#administrator) dan kunci API Azure Maps yang aktif.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka **Data** > **Pengayaan**. 

1. Pilih **Perkaya data saya** pada petak **Lokasi**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Petak Azure Maps.":::

1. Pilih [koneksi](connections.md) dari daftar drop-down. Hubungi administrator jika sambungan Azure Maps tidak tersedia. Jika Anda administrator, Anda dapat [mengkonfigurasi sambungan untuk Azure Maps](#configure-the-connection-for-azure-maps). 

1. Pilih **Berikutnya** untuk mengkonfirmasi pilihan.

1. Pilih **dataset Pelanggan** yang ingin Anda perkaya dengan data lokasi dari Azure Maps. Anda dapat memilih entitas **Pelanggan** untuk memperkaya semua profil pelanggan terpadu Anda, atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Screenshot saat memilih set data pelanggan.":::

1. Pilih apakah Anda ingin memetakan bidang ke alamat utama dan/atau kedua. Anda dapat menentukan pemetaan bidang untuk alamat dan memperkaya profil untuk kedua alamat secara terpisah&mdash;misalnya, untuk alamat rumah dan alamat bisnis. Pilih **Selanjutnya**.

1. Tentukan bidang dari profil terpadu yang digunakan untuk mencari data lokasi yang cocok dari Azure Maps. Bidang **Jalan 1** dan **Kode Zip/Pos** diperlukan untuk alamat utama atau kedua yang dipilih. Untuk keakuratan kecocokan yang lebih tinggi, Anda dapat menambahkan bidang lainnya.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Halaman konfigurasi pengayaan Azure Maps.":::

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Mengevaluasi apakah Anda ingin memodifikasi **Pengaturan Tingkat Lanjut**. Hal ini diberikan untuk memberikan fleksibilitas maksimum dalam menangani kasus penggunaan lanjutan, namun nilai default akan memadai di sebagian besar kasus:
   - **Jenis alamat**: Perilaku default adalah bahwa pengayaan akan mengembalikan kecocokan alamat terbaik meskipun tidak lengkap. Untuk mendapatkan hanya alamat lengkap&mdash;misalnya, alamat yang mencakup nomor rumah&mdash;kosongkan semua kotak centang kecuali **Alamat Titik**. 
   - **Bahasa**: Secara default, alamat akan dikembalikan dalam bahasa untuk kawasan yang ditentukan memiliki alamat tersebut. Untuk menerapkan bahasa alamat standar, pilih bahasa dari menu dropdown. Misalnya, memilih bahasa **Inggris** akan mengembalikan **Copenhagen, Denmark**, bukan **København, Danmark**.

1. Berikan nama untuk pengayaan.

1. Tinjau pilihan Anda, lalu pilih **Simpan pengayaan**.

## <a name="configure-the-connection-for-azure-maps"></a>Mengonfigurasi koneksi untuk Azure Maps

Anda harus menjadi administrator di wawasan audiens untuk mengkonfigurasi sambungan. Pilih **Tambah koneksi** saat mengkonfigurasi pengayaan atau buka **Admin** > **Koneksi**, lalu pilih **Atur** pada petak Azure Maps.

1. Di **nama tampilan**, masukkan nama untuk sambungan.

1. Berikan kunci API Azure Maps yang valid.

1. Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi.

1. Setelah menyelesaikan verifikasi, pilih **Simpan**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Halaman koneksi pengayaan Azure Maps.":::

## <a name="enrichment-results"></a>Hasil pengayaan

Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah. Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab). Waktu pemrosesan akan tergantung pada ukuran data pelanggan dan waktu respons API.

Setelah proses pengayaan selesai, Anda dapat memeriksa data profil pelanggan yang baru saja diperkaya dalam **Pengayaan Saya**. Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.

Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.

## <a name="next-steps"></a>Langkah berikutnya

Bangun di atas data pelanggan yang diperkaya. Buat [segmen](segments.md), [tindakan](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan bagi pelanggan Anda.

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mentransmisikan data ke Azure Maps, Anda mengizinkan transfer data di luar batas kesesuaian untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mengalihkan data tersebut berdasarkan instruksi Anda, namun Anda bertanggung jawab untuk memastikan Azure Maps memenuhi privasi atau jaminan keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, buka [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
