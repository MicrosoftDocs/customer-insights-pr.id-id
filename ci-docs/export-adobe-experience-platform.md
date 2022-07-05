---
title: Mengekspor segmen ke Adobe Experience Platform (pratinjau)
description: Pelajari cara menggunakan segmen Customer Insights di Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: c29b8264019669ffd954a298ce3a633c852477fa
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052515"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Mengekspor segmen ke Adobe Experience Platform (pratinjau)

Sebagai pengguna Dynamics 365 Customer Insights, Anda mungkin telah membuat segmen untuk membuat kampanye pemasaran Anda lebih efisien dengan menargetkan audiens yang relevan. Untuk menggunakan segmen dari Customer Insights dan Adobe Experience Platform aplikasi seperti Adobe Standar Kampanye, Anda harus mengikuti beberapa langkah yang diuraikan dalam artikel ini.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram proses dari langkah-langkah yang diuraikan dalam artikel ini.":::

## <a name="prerequisites"></a>Prasyarat

-   Lisensi Dynamics 365 Customer Insights
-   Lisensi Adobe Experience Platform
-   Lisensi Adobe Campaign Standard
-   Akun Azure Blob Storage

## <a name="campaign-overview"></a>Ikhtisar Kampanye

Untuk lebih memahami bagaimana Anda dapat menggunakan segmen dari Customer Insights di Adobe Experience Platform, mari kita lihat kampanye sampel fiktif.

Misalnya, perusahaan Anda menawarkan layanan berbasis langganan bulanan kepada pelanggan Anda di Amerika Serikat. Anda ingin mengidentifikasi pelanggan yang langganannya harus diperpanjang dalam delapan hari berikutnya tetapi belum memperbarui langganan mereka. Untuk menjaga pelanggan ini, Anda ingin mengirimkan penawaran promosi melalui email, menggunakan Adobe Experience Platform.

Di contoh ini, kita ingin menjalankan kampanye email promosi sekali. Artikel ini tidak mencakup kasus penggunaan dalam menjalankan kampanye lebih dari satu kali.

## <a name="identify-your-target-audience"></a>Identifikasikan target audiens

Dalam skenario kami, kami berasumsi bahwa alamat email pelanggan tersedia di Customer Insights dan preferensi promosi mereka dianalisis untuk mengidentifikasi anggota segmen.

Segmen [yang Anda tentukan di Customer Insights](segments.md) disebut **ChurnProneCustomers** dan Anda berencana untuk mengirimkan promosi email kepada pelanggan ini.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Tangkapan layar halaman segmen dengan segmen ChurnProneCustomers dibuat.":::

Email penawaran yang ingin Anda kirim akan berisi nama depan, nama belakang, dan tanggal berakhir langganan pelanggan. Ini akan menginformasikan kepada pelanggan tentang diskon yang akan mereka dapatkan jika mereka memperpanjang langganan sebelum berakhir.

## <a name="export-your-target-audience"></a>Ekspor target audiens

Dengan target kami audiens diidentifikasi, kami dapat mengonfigurasi ekspor dari Customer Insights ke akun Azure Blob Storage.

### <a name="configure-a-connection"></a>Mengonfigurasi koneksi

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambah koneksi** dan pilih **Penyimpanan Blob Azure** untuk mengkonfigurasi **Konfigurasi** dalam petak **Penyimpanan Blob Adobe** untuk mengonfigurasikan koneksi.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="petak konfigurasi untuk Azure Blob Storage."::: 

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **nama Akun**, **Kunci akun**, dan **Wadah** untuk akun Penyimpanan Blob Anda yang ingin Anda ekspor segmennya.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurasi akun penyimpanan. "::: 
   
    - Untuk mempelajari selengkapnya tentang cara menemukan nama akun penyimpanan Blob dan kunci akun, lihat [Mengelola pengaturan akun penyimpanan di portal Azure](/azure/storage/common/storage-account-manage).
    - Untuk mempelajari cara membuat penampung, lihat [membuat penampung](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pilih **Simpan** untuk menyelesaikan koneksi. 

### <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Penyimpanan Blob Azure. Jika Anda tidak melihat nama bagian ini, maka tidak ada sambungan dari jenis ini yang tersedia untuk Anda.

1. Pilih segmen yang ingin Anda ekspor. Di contoh ini, itu adalah **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Tangkapan layar dari antarmuka pengguna pilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. Pilih **Simpan**.

Setelah menyimpan tujuan ekspor, Anda menemukannya di **Ekspor** > **Data**.

Anda sekarang dapat [mengekspor segmen sesuai permintaan](export-destinations.md#run-exports-on-demand). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md).

> [!NOTE]
> Pastikan jumlah rekaman dalam segmen yang diekspor berada dalam batas yang diizinkan untuk lisensi Adobe Campaign Standard Anda.

Data yang diekspor disimpan dalam wadah Azure Blob storage yang dikonfigurasi di atas. Jalur folder berikut dibuat secara otomatis dalam wadah Anda:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*Model.json* untuk entitas yang diekspor berada di tingkat *%ExportDestinationName%*.

Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Tentukan Model Data pengalaman (XDM) di Adobe Experience Platform

Sebelum data yang diekspor dari Customer Insights dapat digunakan di dalamnya Adobe Experience Platform, kita perlu menentukan skema Model Data Pengalaman dan [mengonfigurasi data untuk Profil](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) Pelanggan Real-time.

Ketahui [apa itu XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) dan pahami [dasar-dasar susunan skema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Impor Data ke Adobe Experience Platform

Sekarang semuanya sudah ada, kita perlu mengimpor data audiens yang disiapkan dari Customer Insights ke dalam Adobe Experience Platform.

Pertama, [buat sambungan sumber Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Setelah menentukan koneksi sumber, [konfigurasikan aliran](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) data untuk koneksi batch penyimpanan cloud untuk mengimpor output segmen dari Customer Insights ke dalam Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Buat audiens dalam Adobe Campaign Standard

Untuk mengirim email tentang kampanye ini, kami akan menggunakan Adobe Campaign Standard. Setelah mengimpor data ke dalam Adobe Experience Platform, kita harus [membuat audiens](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) di Adobe Campaign Standard menggunakan data di Adobe Experience Platform.


Pelajari cara [menggunakan pembuat segmen](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) dalam Adobe Campaign Standard untuk audiens berdasarkan data dalam Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Membuat dan mengirim email menggunakan Adobe Campaign Standard

Buat konten email, lalu [uji dan kirim](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email Anda.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Contoh email dengan penawaran perpanjangan dari Adobe Campaign Standard.":::