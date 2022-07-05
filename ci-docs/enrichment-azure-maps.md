---
title: Perkaya profil pelanggan dengan data lokasi dari Azure Maps (pratinjau)
description: Informasi umum tentang pengayaan pihak pertama Azure Maps.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: dfadc08f67beac3fded1a97e557ee9e1880664e0
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052611"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Perkaya profil pelanggan dengan data lokasi dari Azure Maps (pratinjau)

Azure Maps menyediakan data dan layanan yang berpusat pada lokasi untuk memberikan pengalaman berdasarkan data geospasial dengan kecerdasan lokasi bawaan. Layanan pengayaan data Azure Maps akan meningkatkan presisi informasi lokasi tentang pelanggan Anda. Ia memberikan kemampuan seperti normalisasi alamat dan ekstrak garis lintang dan garis bujur untuk Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prasyarat

- Langganan Azure Maps aktif. Untuk mendapatkan langganan, [daftar atau dapatkan uji coba gratis](https://azure.microsoft.com/services/azure-maps/).

- Koneksi Azure [Maps](connections.md)[dikonfigurasi](#configure-the-connection-for-azure-maps) oleh administrator.

## <a name="configure-the-connection-for-azure-maps"></a>Mengonfigurasi koneksi untuk Azure Maps

Anda harus menjadi [administrator](permissions.md#admin) di Customer Insights dan memiliki kunci Azure Maps API aktif.

1. Pilih **Tambah koneksi** saat mengkonfigurasi pengayaan atau buka **Admin** > **Koneksi**, lalu pilih **Atur** pada petak Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Halaman koneksi pengayaan Azure Maps.":::

1. Masukkan nama untuk koneksi dan kunci Azure Maps API yang valid.

1. Baca dan berikan persetujuan Anda untuk [privasi dan kesesuaian Data](#data-privacy-and-compliance) dengan memilih **Saya setuju**.

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi lalu pilih **Simpan**.

### <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mentransmisikan data ke Azure Maps, Anda mengizinkan transfer data di luar batas kesesuaian untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa Azure Maps memenuhi kewajiban privasi atau keamanan apa pun yang mungkin Anda miliki. Untuk informasi lebih lanjut, buka [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data** saya di petak **peta Lokasi** dari Microsoft Azure Peta.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Petak Azure Maps.":::

1. Tinjau gambaran umum lalu pilih **Berikutnya**.

1. Pilih koneksi. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Pilih **Selanjutnya**.

1. **Pilih himpunan data** Pelanggan dan pilih profil atau segmen yang ingin Anda perkaya dengan data dari Microsoft. Entitas Pelanggan *memperkaya semua profil pelanggan Anda sedangkan segmen hanya memperkaya profil pelanggan yang terkandung dalam segmen tersebut*.

1. Tentukan jenis bidang mana dari profil terpadu Anda yang akan digunakan untuk pencocokan: alamat utama dan/atau sekunder. Anda dapat menentukan pemetaan bidang untuk kedua alamat dan memperkaya profil untuk kedua alamat secara terpisah. Misalnya, untuk alamat rumah dan alamat bisnis. Pilih **Selanjutnya**.

1. Petakan bidang Anda ke data lokasi dari Azure Maps. Bidang **jalan 1** dan **Kode Zip/Pos** diperlukan untuk alamat utama dan/atau sekunder yang dipilih. Untuk akurasi kecocokan yang lebih tinggi, tambahkan lebih banyak bidang.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Pemetaan atribut Azure Maps.":::

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Tinjau **Pengaturan** Lanjutan yang menawarkan fleksibilitas maksimum untuk menangani kasus penggunaan tingkat lanjut. Namun, nilai default berikut biasanya tidak perlu diubah.

   - **Jenis alamat**: Kecocokan alamat terbaik kembali meskipun tidak lengkap. Untuk mendapatkan hanya alamat lengkap&mdash;misalnya, alamat yang mencakup nomor rumah&mdash;kosongkan semua kotak centang kecuali **Alamat Titik**.
   - **Bahasa**: Alamat kembali dalam bahasa berdasarkan wilayah alamat. Untuk menerapkan bahasa alamat standar, pilih bahasa dari menu dropdown. Misalnya, memilih **bahasa Inggris** mengembalikan **Kopenhagen, Denmark** alih-alih **København, Danmark**.
   - **Jumlah** hasil maksimum: Jumlah hasil per alamat.

1. Pilih **Selanjutnya**.

1. Berikan **Nama** untuk pengayaan dan **nama** entitas Output.

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

1. Pilih **Jalankan** untuk memulai proses pengayaan atau tutup untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Jumlah **pelanggan yang diperkaya oleh lapangan** memberikan penelusuran ke dalam cakupan setiap bidang yang diperkaya.

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
