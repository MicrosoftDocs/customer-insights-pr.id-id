---
title: Perkaya profil pelanggan dengan HERE Technologies (pratinjau)
description: Informasi umum tentang pengayaan pihak ketiga HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d88085b6be156dd1c895e9e5b38cc9d77acbdb95
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052055"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Perkaya profil pelanggan dengan HERE Technologies (pratinjau)

HERE Technologies adalah perusahaan platform lokasi yang menyediakan data dan layanan yang berpusat lokasi. Layanan pengayaan data HERE Technologies meningkatkan presisi informasi lokasi tentang pelanggan Anda. Ini memberikan normalisasi alamat, ekstraksi lintang dan bujur, dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

- Langganan HERE Technologies yang aktif. Untuk mendapatkan langganan, [daftar di sini](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) atau [hubungi HERE Technologies secara](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) langsung. [Selengkapnya tentang pengayaan lokasi HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Koneksi [HERE](connections.md)[dikonfigurasi](#configure-the-connection-for-here-technologies) oleh administrator.

## <a name="configure-the-connection-for-here-technologies"></a>Mengonfigurasi koneksi untuk HERE Technologies

Anda harus menjadi [administrator](permissions.md#admin) di Customer Insights dan memiliki kunci HERE Technologies API yang aktif.

1. Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan, atau buka **Koneksi** > **Admin** dan pilih **Siapkan** di ubin HERE Technologies.

1. Masukkan nama untuk koneksi dan kunci API HERE Technologies yang valid.

1. Baca dan berikan persetujuan Anda untuk [privasi dan kesesuaian Data](#data-privacy-and-compliance) dengan memilih **Saya setuju**.

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi lalu pilih **Simpan**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Halaman konfigurasi koneksi HERE technologies.":::

### <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke HERE Technologies, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa HERE Technologies memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data** saya di **petak peta Lokasi** dari HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Petak HERE Technologies.":::

1. Tinjau gambaran umum lalu pilih **Berikutnya**.

1. Pilih koneksi. Hubungi administrator jika tidak tersedia.

1. Pilih **Selanjutnya**.

1. **Pilih himpunan data** Pelanggan dan pilih profil atau segmen yang ingin Anda perkaya dengan data dari HERE Technologies. Entitas Pelanggan *memperkaya semua profil pelanggan Anda sedangkan segmen hanya memperkaya profil pelanggan yang terkandung dalam segmen tersebut*.

1. Tentukan jenis bidang mana dari profil terpadu Anda yang akan digunakan untuk pencocokan: alamat utama dan/atau sekunder. Anda dapat menentukan pemetaan bidang untuk kedua alamat dan memperkaya profil untuk kedua alamat secara terpisah. Misalnya, untuk alamat rumah dan alamat bisnis. Pilih **Selanjutnya**.

1. Petakan bidang Anda ke data dari HERE Technologies. Bidang **jalan 1** dan **Kode Zip/Pos** diperlukan untuk alamat utama dan/atau sekunder yang dipilih. Untuk akurasi kecocokan yang lebih tinggi, tambahkan lebih banyak bidang.

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