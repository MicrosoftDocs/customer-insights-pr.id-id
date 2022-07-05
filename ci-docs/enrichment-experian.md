---
title: Perkaya profil pelanggan dengan demografi dari Experian (pratinjau)
description: Informasi umum tentang pengayaan pihak ketiga Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: a30e98b06ed07590ab95cae1d8db8023e49ff7f9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053025"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Perkaya profil pelanggan dengan demografi dari Experian (pratinjau)

Experian adalah pemimpin global dalam pelaporan kredit konsumen dan bisnis serta layanan pemasaran. Dengan layanan pengayaan data Experian, Anda dapat membangun pemahaman yang lebih mendalam tentang pelanggan dengan memperkaya profil pelanggan dengan data demografis seperti ukuran rumah tangga, penghasilan, dan banyak lagi.

## <a name="supported-countriesregions"></a>Negara/kawasan yang didukung

Kami saat ini hanya mendukung pengayaan profil pelanggan di Amerika Serikat.

## <a name="prerequisites"></a>Prasyarat

- Langganan aktif Experian. Untuk mendapatkan langganan, [hubungi Experian](https://www.experian.com/marketing-services/contact) secara langsung. [Pelajari selengkapnya tentang Pengayaan data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Koneksi Experian [...](connections.md)[dikonfigurasi](#configure-the-connection-for-experian) oleh administrator.

- Experian ID Pengguna, ID Pihak, dan Nomor Model untuk akun Secure Transport (ST) berkemampuan SSH yang Experian dibuat untuk Anda.

## <a name="configure-the-connection-for-experian"></a>Mengonfigurasi koneksi untuk Experian

Anda harus menjadi [administrator](permissions.md#admin) di Customer Insights dan memiliki Experian ID Pengguna, ID Pihak, dan Nomor Model.

1. Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan, atau buka **Koneksi** > **Admin** dan pilih **Siapkan** di petak Experian peta.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Panel Konfigurasi koneksi Experian.":::

1. Masukkan nama untuk koneksi dan ID Pengguna, ID Pihak, dan Nomor Model yang valid untuk akun Transportasi Aman Anda Experian.

1. Baca dan berikan persetujuan Anda untuk [privasi dan kesesuaian Data](#data-privacy-and-compliance) dengan memilih **Saya setuju**.

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi lalu pilih **Simpan**.

### <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mentransmisikan data ke Experian, Anda mengizinkan transfer data di luar batas kesesuaian untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mengalihkan data tersebut berdasarkan instruksi Anda, namun Anda bertanggung jawab untuk memastikan bahwa Experian memenuhi privasi atau jaminan keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data** saya di **petak demografi** dari Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian ubin di halaman ikhtisar pengayaan.":::

1. Tinjau gambaran umum lalu pilih **Berikutnya**.

1. Pilih koneksi. Hubungi administrator jika tidak tersedia.

1. Pilih **Selanjutnya**.

1. **Pilih himpunan data** Pelanggan dan pilih profil atau segmen yang ingin Anda perkaya dengan data demografi dari Experian. Entitas Pelanggan *memperkaya semua profil pelanggan Anda sedangkan segmen hanya memperkaya profil pelanggan yang terkandung dalam segmen tersebut*.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Tangkapan layar saat memilih himpunan data pelanggan.":::

1. Tentukan jenis bidang mana dari profil terpadu Anda yang akan digunakan untuk mencocokkan data demografi dari Experian. Setidaknya salah satu bidang **Nama dan alamat**, **Telepon**, atau **Email** diperlukan. Untuk akurasi kecocokan yang lebih tinggi, tambahkan bidang lain. Pilih **Selanjutnya**.

1. Petakan bidang Anda ke data demografis dari Experian.

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Berikan **Nama** untuk pengayaan dan **nama** entitas Output.

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

1. Pilih **Jalankan** untuk memulai proses pengayaan atau tutup untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Jumlah **pelanggan yang diperkaya oleh lapangan** memberikan penelusuran ke dalam cakupan setiap bidang yang diperkaya.

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
