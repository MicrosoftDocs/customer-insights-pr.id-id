---
title: Pengayaan data identitas LiveRamp
description: Perkaya profil pelanggan dengan data LiveRamp.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e8a130865267b57c89157b44be3d4bba3dc2fb4e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953999"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Perkaya profil pelanggan dengan data identitas dari LiveRamp (pratinjau)

LiveRamp menyediakan resolusi identitas offline deterministik dan konsolidasi data pelanggan. Anda dapat memetakan pengidentifikasi pribadi dalam data pelanggan Anda ke grafik identitas AbiliTec dan menerima ID AbiliTec. Anda kemudian dapat menggunakan ID ini untuk penyatuan data pelanggan Anda dengan lebih baik.

## <a name="supported-countriesregions"></a>Negara/kawasan yang didukung

Saat ini kami mendukung pengayaan profil pelanggan dengan data LiveRamp di Amerika Serikat saja.

## <a name="prerequisites"></a>Prasyarat

- Langganan LiveRamp aktif. Untuk mendapatkan langganan, hubungi tim akun LiveRamp Anda atau untuk [dynamics@liveramp.com](mailto:dynamics@liveramp.com) informasi lebih lanjut.

- Langganan AbiliTec aktif dengan ID klien dan rahasia untuk mengakses API. Untuk informasi selengkapnya, lihat [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/).

- Koneksi [LiveRamp](connections.md)[dikonfigurasi](#configure-the-connection-for-liveramp) oleh administrator.

## <a name="configure-the-connection-for-liveramp"></a>Mengonfigurasi koneksi untuk LiveRamp

Anda harus menjadi [administrator](permissions.md#admin) di Customer Insights dan memiliki ID dan rahasia klien LiveRamp aktif.

1. Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan, atau buka **Koneksi** > **Admin** dan pilih **Siapkan** di ubin LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Panel konfigurasi untuk menyiapkan koneksi ke layanan LiveRamp AbiliTec.":::

1. Masukkan nama untuk koneksi dan ID klien LiveRamp yang valid serta rahasia.

1. Baca dan berikan persetujuan Anda untuk [privasi dan kesesuaian Data](#data-privacy-and-compliance) dengan memilih **Saya setuju**.

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi lalu pilih **Simpan**.

### <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke LiveRamp, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa LiveRamp memenuhi kewajiban privasi atau keamanan apa pun yang mungkin Anda miliki. Untuk informasi selengkapnya, tinjau [Pernyataan](https://go.microsoft.com/fwlink/?linkid=396732) Privasi Microsoft. Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data** saya di **petak peta Identitas** dari LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Petak identitas di halaman ringkasan pengayaan.":::

1. Tinjau gambaran umum lalu pilih **Berikutnya**.

1. Pilih koneksi. Hubungi administrator jika tidak tersedia.

1. Pilih **Selanjutnya**.

1. **Pilih himpunan data** Pelanggan dan pilih profil atau segmen yang ingin Anda perkaya dengan data identitas dari LiveRamp. Entitas Pelanggan *memperkaya semua profil pelanggan Anda sedangkan segmen hanya memperkaya profil pelanggan yang terkandung dalam segmen tersebut*.

1. Tentukan jenis bidang mana dari profil terpadu Anda yang akan digunakan untuk mencocokkan data identitas dari LiveRamp. Setidaknya salah satu bidang **Nama dan alamat**, **E-mail**, atau **Telepon** diperlukan. Untuk akurasi kecocokan yang lebih tinggi, tambahkan bidang lain. Pilih **Selanjutnya**.

1. Petakan bidang Anda ke data identifikasi dari LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opsi pemetaan data untuk pengayaan LiveRamp.":::

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Berikan **Nama** untuk pengayaan dan **nama** entitas Output.

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

1. Pilih **Jalankan** untuk memulai proses pengayaan atau tutup untuk kembali ke **halaman Pengayaan**.

## <a name="enrichment-results"></a>Hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Jumlah **pelanggan yang diperkaya oleh lapangan** memberikan penelusuran ke dalam cakupan setiap bidang yang diperkaya.

## <a name="next-steps"></a>Langkah berikutnya

Bangun di atas data pelanggan yang diperkaya. Gunakan ID AbiliTec untuk mengkonsolidasikan profil pelanggan ke dalam tampilan berbasis orang.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
