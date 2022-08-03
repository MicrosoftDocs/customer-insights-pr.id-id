---
title: Ekspor data ke Salesforce Marketing Cloud (pratinjau)
description: Pelajari lebih lanjut cara mengkonfigurasi sambungan dan mengekspor ke Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197042"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Ekspor data ke Salesforce Marketing Cloud (pratinjau)

Gunakan data pelanggan Anda di Salesforce Marketing Cloud dengan mengekspornya melalui lokasi SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Prasyarat

- Host [SFTP untuk Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) dan kredensial admin yang sesuai.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Menyiapkan koneksi ke Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Salesforce Marketing Cloud**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan **nama pengguna**, **sandi**, **nama host**, dan **folder Ekspor** untuk akun SFTP Anda.

1. Pilih **Verifikasi** untuk menguji koneksi.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian SFTP. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Pilih jika Anda ingin mengekspor data **dengan di-zip** atau **tidak di-zip** dan **pembatas bidang** untuk file yang diekspor.

1. Pilih entitas, misalnya segmen, yang ingin Anda ekspor.

   > [!NOTE]
   > Setiap entitas yang dipilih akan dibagi menjadi maksimal lima file output saat diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Mengimpor data Customer Insights dari lokasi SFTP ke Salesforce Marketing Cloud

1. Buat [ekstensi data di Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) untuk mengimpor file data Customer Insights dari lokasi SFTP.

2. [Impor data dari lokasi SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) ke ekstensi data Salesforce Marketing Cloud.

3. Mengkonfigurasikan otomatisasi untuk mengimpor data ke ekstensi data. Pelajari lebih lanjut tentang [otomatisasi peletakan file dan otomatisasi terjadwal](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Menentukan [otomatisasi peletakan file](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) atau  [otomatisasi terjadwal](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Berikut adalah contoh [otomatisasi dengan SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
