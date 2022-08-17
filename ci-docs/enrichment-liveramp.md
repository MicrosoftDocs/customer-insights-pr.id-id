---
title: Perkaya profil pelanggan dengan data identitas dari LiveRamp (pratinjau)
description: Perkaya profil pelanggan dengan data LiveRamp.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0aa6dc144602741b87843a5373779855ee3e334c
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237816"
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

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi lalu pilih **Simpan**.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data** saya di **petak peta Identitas** dari LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Petak identitas di halaman ringkasan pengayaan.":::

1. Tinjau gambaran umum lalu pilih **Berikutnya**.

1. Pilih koneksi. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Pilih **Selanjutnya**.

1. **Pilih himpunan data** Pelanggan dan pilih profil atau segmen yang ingin Anda perkaya dengan data identitas dari LiveRamp. Entitas Pelanggan *memperkaya semua profil pelanggan Anda sedangkan segmen hanya memperkaya profil pelanggan yang terkandung dalam segmen tersebut*.

1. Tentukan jenis bidang mana dari profil terpadu Anda yang akan digunakan untuk mencocokkan data identitas dari LiveRamp. Setidaknya salah satu bidang **Nama dan alamat**, **E-mail**, atau **Telepon** diperlukan. Untuk akurasi kecocokan yang lebih tinggi, tambahkan bidang lain. Pilih **Selanjutnya**.

1. Petakan bidang Anda ke data identifikasi dari LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opsi pemetaan data untuk pengayaan LiveRamp.":::

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Berikan **Nama** untuk pengayaan dan **nama** entitas Output.

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

1. Pilih **Jalankan** untuk memulai proses pengayaan atau tutup untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Jumlah **pelanggan yang diperkaya oleh lapangan** memberikan penelusuran ke dalam cakupan setiap bidang yang diperkaya.

## <a name="next-steps"></a>Langkah berikutnya

Bangun di atas data pelanggan yang diperkaya. Gunakan ID AbiliTec untuk mengkonsolidasikan profil pelanggan ke dalam tampilan berbasis orang.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
