---
title: Perkaya profil pelanggan dengan impor kustom SFTP (pratinjau)
description: Informasi umum tentang pengayaan impor kustom SFTP.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 831d1d3d3045379bbc5bcdcd4b05b8a147221f31
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237770"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Perkaya profil pelanggan dengan impor kustom SFTP (pratinjau)

Impor kustom protokol transfer file aman (SFTP) memungkinkan Anda mengimpor data yang tidak harus melalui proses penyatuan data. Cara yang fleksibel, aman, dan mudah untuk membawa data Anda. Impor kustom SFTP dapat digunakan bersama dengan [ekspor SFTP](export-sftp.md) yang memungkinkan Anda mengekspor data profil pelanggan yang diperlukan untuk pengayaan. Data kemudian dapat diproses dan diperkaya, dan impor kustom SFTP dapat digunakan untuk mengembalikan data yang diperkaya ke Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prasyarat

- Nama file dan lokasi (jalur) file yang akan diimpor pada host SFTP diketahui.

- File *model.json* yang menentukan skema Common Data Model untuk data yang akan diimpor tersedia. File ini harus berada di direktori yang sama dengan file yang akan diimpor.

- Koneksi [SFTP](connections.md)[dikonfigurasi](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Contoh skema file

Direktori yang berisi file yang akan diimpor pada server SFTP juga harus berisi file *model.JSON*. File ini mendefinisikan skema yang akan digunakan untuk mengimpor data. Skema harus menggunakan [Common Data Model](/common-data-model/) untuk menentukan pemetaan bidang. Contoh sederhana dari file model.JSON terlihat seperti ini:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="configure-the-connection-for-sftp-custom-import"></a>Mengonfigurasi koneksi untuk Impor Kustom SFTP

Anda harus menjadi [administrator](permissions.md#admin) di Customer Insights dan memiliki kredensial pengguna, URL, dan nomor port untuk lokasi SFTP tempat Anda ingin mengimpor data.

1. Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan atau buka **Koneksi** > **Admin** dan pilih **Siapkan** pada petak peta Impor Kustom.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Halaman konfigurasi koneksi Impor Kustom.":::

1. Masukkan nama untuk koneksi.

1. Masukkan nama pengguna, sandi, dan URL host yang valid untuk server tempat SFTP yang datanya akan diimpor berada.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi lalu pilih **Simpan**.

## <a name="configure-the-import"></a>Mengonfigurasi impor

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data** saya di petak **peta impor** kustom SFTP.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Petak Impor Kustom SFTP.":::

1. Tinjau gambaran umum lalu pilih **Berikutnya**.

1. Pilih koneksi. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. **Pilih himpunan data** Pelanggan dan pilih profil atau segmen yang ingin Anda perkaya. Entitas Pelanggan *memperkaya semua profil pelanggan Anda sedangkan segmen hanya memperkaya profil pelanggan yang terkandung dalam segmen tersebut*.

1. Pilih **Selanjutnya**.

1. Masukkan **Jalur** dan **Nama** File dari file data yang ingin Anda impor.

1. Pilih **Selanjutnya**.

1. Berikan **Nama** untuk pengayaan dan **nama** entitas Output.

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

1. Pilih **Jalankan** untuk memulai proses pengayaan atau tutup untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
