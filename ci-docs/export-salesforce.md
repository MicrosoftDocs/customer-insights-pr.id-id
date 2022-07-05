---
title: Ekspor data ke Salesforce Marketing Cloud (pratinjau)
description: Pelajari lebih lanjut cara mengkonfigurasi sambungan dan mengekspor ke Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c3a6a40d9b9f08c8ebca8cb4a9196a1a79f03afa
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082618"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Ekspor data ke Salesforce Marketing Cloud (pratinjau)

Gunakan data pelanggan Anda di Salesforce Marketing Cloud dengan mengekspornya melalui lokasi SFTP (Secure File Transfer Protocol).

## <a name="prerequisites-for-connection"></a>Prasyarat untuk koneksi

- Ketersediaan host SFTP dan kredensial admin yang terkait. [Cara mengkonfigurasi lokasi SFTP untuk Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Mengkonfigurasikan sambungan ke Salesforce Marketing Cloud

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambah koneksi** dan pilih **Salesforce Marketing Cloud** untuk mengkonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan **nama pengguna**, **sandi**, **nama host**, dan **folder Ekspor** untuk akun SFTP Anda.

1. Pilih **Verifikasi** untuk menguji koneksi.

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian SFTP. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Pilih jika Anda ingin mengekspor data **dengan di-zip** atau **tidak di-zip** dan **pembatas bidang** untuk file yang diekspor.

1. Pilih entitas, misalnya segmen, yang akan diekspor.

   > [!NOTE]
   > Setiap entitas yang dipilih akan dibagi menjadi hingga lima file output saat diekspor. 

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Mengimpor data Customer Insights dari lokasi SFTP ke Salesforce Marketing Cloud

1. Buat [ekstensi data di Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) untuk mengimpor file data Customer Insights dari lokasi SFTP.

2. [Impor data dari lokasi SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) ke ekstensi data Salesforce Marketing Cloud. 

3. Mengkonfigurasikan otomatisasi untuk mengimpor data ke ekstensi data. Pelajari lebih lanjut tentang [otomatisasi peletakan file dan otomatisasi terjadwal](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Menentukan [otomatisasi peletakan file](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) atau  [otomatisasi terjadwal](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Berikut adalah contoh [otomatisasi dengan SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan melalui SFTP, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa tujuan ekspor memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.

[!INCLUDE [footer-include](includes/footer-banner.md)]
