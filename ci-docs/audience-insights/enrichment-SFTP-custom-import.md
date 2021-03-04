---
title: Pengayaan dengan impor kustom SFTP
description: Informasi umum tentang pengayaan impor kustom SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269610"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Memperkaya profil pelanggan dengan data kustom (pratinjau)

Impor kustom protokol transfer file aman (SFTP) memungkinkan Anda mengimpor data yang tidak harus melalui proses penyatuan data. Cara yang fleksibel, aman, dan mudah untuk membawa data Anda. Impor kustom SFTP dapat digunakan bersama dengan [ekspor SFTP](export-sftp.md) yang memungkinkan Anda mengekspor data profil pelanggan yang diperlukan untuk pengayaan. Data selanjutnya dapat diproses, diperkaya, dan impor kustom SFTP dapat digunakan untuk menghadirkan data yang diperkaya kembali ke kemampuan wawasan audiens Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasikan impor kustom SFTP, persyaratan berikut harus dipenuhi:

- Anda memiliki kredensial pengguna (nama pengguna dan sandi) untuk lokasi SFTP dengan data yang akan diimpor.
- Anda memiliki URL dan nomor port (biasanya 22) untuk host SFTP.
- Anda memiliki nama file dan lokasi file yang akan diimpor pada host SFTP.
- Ada file *model.JSON* yang menentukan skema untuk data yang akan diimpor. File ini harus berada di direktori yang sama dengan file yang akan diimpor.
- Anda memiliki izin [administratif](permissions.md#administrator).

## <a name="configuration"></a>Konfigurasi

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Di **petak impor kustom SFTP** pilih **Perkaya data**.

   > [!div class="mx-imgBorder"]
   > ![petak Impor Kustom SFTP](media/SFTP_Custom_Import_tile.png "petak Impor Kustom SFTP")

1. Pilih **Mulai** dan berikan kredensial dan alamat untuk server SFTP. Misalnya, sftp://mysftpserver.com:22.

1. Masukkan nama file yang berisi data dan jalur ke file di server SFTP jika tidak di dalam folder root.

1. Konfirmasikan semua input dengan memilih **Sambungkan ke impor kustom**.

   > [!div class="mx-imgBorder"]
   > ![Flyout konfigurasi impor kustom SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Flyout konfigurasi impor kustom SFTP")

## <a name="defining-field-mappings"></a>Menentukan pemetaan bidang 

Direktori yang berisi file yang akan diimpor pada server SFTP juga harus berisi file *model.JSON*. File ini mendefinisikan skema yang akan digunakan untuk mengimpor data. Skema harus menggunakan [Common Data Model](https://docs.microsoft.com/common-data-model/) untuk menentukan pemetaan bidang. Contoh sederhana dari file model.JSON terlihat seperti ini:

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
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
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

## <a name="enrichment-results"></a>Hasil pengayaan

Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah. Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab). Waktu pemrosesan tergantung pada ukuran data yang akan diimpor dan sambungan ke server SFTP.

Setelah proses pengayaan selesai, Anda dapat meninjau data pengayaan kustom yang baru diimpor dalam **pengayaan saya**. Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.

Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.

## <a name="next-steps"></a>Langkah berikutnya

Bangun di atas data pelanggan yang diperkaya. Buat [segmen](segments.md), [tindakan](measures.md), dan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan dengan pelanggan Anda.




[!INCLUDE[footer-include](../includes/footer-banner.md)]