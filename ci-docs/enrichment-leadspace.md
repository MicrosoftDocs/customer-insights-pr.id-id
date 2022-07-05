---
title: Perkaya profil perusahaan dengan Leadspace (pratinjau)
description: Informasi umum tentang pengayaan pihak ketiga Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b58532a541ee22a5e34d0af1a3334ccbd53627b2
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082366"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Perkaya profil perusahaan dengan Leadspace (pratinjau)

Leadspace adalah perusahaan ilmu data yang menyediakan Platform Data Pelanggan B-to-B. Ini memungkinkan lingkungan dengan profil pelanggan terpadu berdasarkan akun untuk memperkaya data mereka. Perkaya *profil pelanggan* dengan atribut seperti ukuran perusahaan, lokasi, atau industri. Perkaya *Profil kontak* dengan atribut seperti judul, persona, atau verifikasi email.

## <a name="prerequisites"></a>Prasyarat

- Lisensi Leadspace aktif.
- [Profil](customer-profiles.md) pelanggan terpadu berdasarkan akun.
- Koneksi [Leadspace](connections.md)[dikonfigurasi](#configure-the-connection-for-leadspace) oleh administrator. Hubungi [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) secara langsung untuk detail tentang produk mereka.

## <a name="configure-the-connection-for-leadspace"></a>Mengonfigurasi koneksi untuk Leadspace

Anda harus menjadi [administrator](permissions.md#admin) di Customer Insights dan memiliki "kunci abadi" (disebut sebagai **token** Leadspace).

1. Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan atau buka **Koneksi** > **Admin** dan pilih **Siapkan** di petak leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Halaman konfigurasi koneksi Leadspace.":::

1. Masukkan nama untuk koneksi dan token Leadspace yang valid.

1. Baca dan berikan persetujuan Anda untuk [privasi dan kesesuaian Data](#data-privacy-and-compliance) dengan memilih **Saya setuju**.

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi lalu pilih **Simpan**.

### <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Leadspace, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Leadspace memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data** saya pada **data** Perusahaan dari petak peta Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Tangkapan layar petak Leadspace.":::

1. Tinjau gambaran umum lalu pilih **Berikutnya**.

1. Pilih koneksi. Hubungi administrator jika tidak tersedia.

1. Pilih **Selanjutnya**.

1. **Pilih himpunan data** Pelanggan dan pilih profil atau segmen yang ingin Anda perkaya dengan data perusahaan dari Leadspace. Entitas Pelanggan *memperkaya semua profil pelanggan Anda sedangkan segmen hanya memperkaya profil pelanggan yang terkandung dalam segmen tersebut*.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Tangkapan layar saat memilih himpunan data pelanggan.":::

1. Tentukan jenis bidang mana dari profil terpadu Anda yang akan digunakan untuk pencocokan: alamat utama dan/atau sekunder. Anda dapat menentukan pemetaan bidang untuk kedua alamat dan memperkaya profil untuk kedua alamat secara terpisah. Misalnya, untuk alamat rumah dan alamat bisnis. Pilih **Selanjutnya**.

1. Petakan bidang Anda ke data perusahaan dari Leadspace. Bidang **Nama perusahaan** diperlukan. Untuk akurasi kecocokan yang lebih tinggi, hingga dua bidang lainnya, **situs web perusahaan** dan **lokasi perusahaan**, dapat ditambahkan.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Panel pemetaan bidang leadspace.":::

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Pilih kotak centang jika Anda memiliki *profil Kontak* yang akan di perkaya. Customer Insights akan secara otomatis memetakan bidang yang diperlukan.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Pengayaan rekaman kontak Leadspace.":::

1. Pilih **Selanjutnya**.

1. Berikan **Nama** untuk pengayaan dan **nama** entitas Output.

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

1. Pilih **Jalankan** untuk memulai proses pengayaan atau tutup untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Untuk informasi lebih lanjut, lihat [api leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
