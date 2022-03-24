---
title: Pengayaan dengan impor kustom SFTP
description: Informasi umum tentang pengayaan impor kustom SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 042558af801a1d1fc365939d9aa42c09b98b2679
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376558"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Memperkaya profil pelanggan dengan data kustom (pratinjau)

Impor kustom protokol transfer file aman (SFTP) memungkinkan Anda mengimpor data yang tidak harus melalui proses penyatuan data. Cara yang fleksibel, aman, dan mudah untuk membawa data Anda. Impor kustom SFTP dapat digunakan bersama dengan [ekspor SFTP](export-sftp.md) yang memungkinkan Anda mengekspor data profil pelanggan yang diperlukan untuk pengayaan. Selanjutnya data dapat diproses dan diperkaya, dan impor kustom SFTP dapat digunakan untuk mengembalikan data yang diperkaya menjadi kemampuan wawasan audiens Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasikan impor kustom SFTP, persyaratan berikut harus dipenuhi:

- Anda memiliki nama file dan lokasi (jalur) file yang akan diimpor di host SFTP.
- Ada file *model.json* yang menentukan [skema Common Data Model](/common-data-model/) untuk data yang akan diimpor. File ini harus berada di direktori yang sama dengan file yang akan diimpor.
- Koneksi SFTP telah dikonfigurasi oleh administrator *atau* Anda memiliki izin [administrator](permissions.md#admin). Anda akan memerlukan kredensial pengguna, URL, dan nomor port untuk lokasi SFTP tempat Anda ingin mengimpor data.


## <a name="configure-the-import"></a>Mengonfigurasi impor

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data saya** di **petak impor kustom SFTP** lalu pilih **Mulai**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Petak Impor Kustom SFTP.":::

1. Pilih [koneksi](connections.md) dari daftar drop-down. Hubungi administrator jika tidak ada koneksi yang tersedia. Jika Anda administrator, Anda dapat membuat sambungan dengan memilih **Tambah sambungan** dan memilih **Impor Kustom SFTP** dari daftar dropdown.

1. Pilih **Sambungkan ke Impor Kustom** untuk mengonfirmasi koneksi yang dipilih.

1.  Pilih **Berikutnya**, lalu masukkan **Jalur** dan **Nama File** dari file data yang akan diimpor.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Cuplikan layar saat memasukkan lokasi data.":::

1. Pilih **Berikutnya**, lalu pilih rangkaian data pelanggan. Pilihan ini dapat berupa semua profil pelanggan atau satu segmen.

1. Pilih **Selanjutnya** dan berikan nama untuk pengayaan dan nama untuk entitas output. 

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Mengonfigurasi koneksi untuk Impor Kustom SFTP 

Anda perlu menjadi administrator untuk mengonfigurasi koneksi. Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan *atau* masuk ke **Admin** > **Koneksi** dan pilih **Konfigurasi** pada petak Impor Kustom.

1. Masukkan nama untuk koneksi dalam kotak **nama tampilan**.

1. Masukkan nama pengguna, sandi, dan URL host yang valid untuk server tempat SFTP yang datanya akan diimpor berada.

1. Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**.

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi.

1. Setelah verifikasi selesai, sambungan dapat disimpan dengan memilih **Simpan**.

   > [!div class="mx-imgBorder"]
   > ![halaman Panel Konfigurasi koneksi Experian.](media/enrichment-SFTP-connection.png "halaman Panel Konfigurasi koneksi Experian")


## <a name="defining-field-mappings"></a>Menentukan pemetaan bidang 

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

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
