---
title: Mengekspor data Customer Insights ke Adobe Experience Platform
description: Pelajari bagaimana menggunakan segmen wawasan audiens dalam Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760105"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Gunakan segmen Customer Insights dalam Adobe Experience Platform (pratinjau)

Sebagai pengguna wawasan audiens untuk Dynamics 365 Customer Insights, Anda mungkin telah membuat segmen untuk membuat kampanye pemasaran yang lebih efisien dengan menargetkan audiens yang relevan. Agar dapat menggunakan segmen audiens wawasan dalam Adobe Experience Platform dan aplikasi seperti Adobe Campaign Standard, Anda harus mengikuti beberapa langkah yang diuraikan dalam artikel ini.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram proses dari langkah-langkah yang diuraikan dalam artikel ini.":::

## <a name="prerequisites"></a>Prasyarat

-   Lisensi Dynamics 365 Customer Insights
-   Lisensi Adobe Experience Platform
-   Lisensi Adobe Campaign Standard
-   Akun Azure Blob Storage

## <a name="campaign-overview"></a>Ikhtisar Kampanye

Untuk lebih memahami bagaimana Anda dapat menggunakan segmen wawasan audiens dalam Adobe Experience Platform, lihat kampanye sampel fiktif.

Misalnya, perusahaan Anda menawarkan layanan berbasis langganan bulanan kepada pelanggan Anda di Amerika Serikat. Anda ingin mengidentifikasi pelanggan yang langganannya harus diperpanjang dalam delapan hari berikutnya tetapi belum memperbarui langganan mereka. Untuk menjaga pelanggan ini, Anda perlu mengirimkan penawaran promosi melalui email, menggunakan Adobe Experience Platform.

Di contoh ini, kita ingin menjalankan kampanye email promosi sekali. Artikel ini tidak mencakup kasus penggunaan dalam menjalankan kampanye lebih dari satu kali.

## <a name="identify-your-target-audience"></a>Identifikasikan target audiens

Dalam skenario kami, kami mengasumsikan bahwa alamat email pelanggan tersedia di wawasan audiens dan preferensi promosi mereka dianalisis untuk mengidentifikasi anggota segmen.

[Segmen yang Anda tentukan dalam wawasan audiens](segments.md) disebut **ChurnProneCustomers** dan Anda berencana mengirimkan promosi email kepada pelanggan ini.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Tangkapan layar halaman segmen dengan segmen ChurnProneCustomers dibuat.":::

Email penawaran yang ingin Anda kirim akan berisi nama depan, nama belakang, dan tanggal berakhir langganan pelanggan. Ini akan menginformasikan kepada pelanggan tentang diskon yang akan mereka dapatkan jika mereka memperpanjang langganan sebelum berakhir.

## <a name="export-your-target-audience"></a>Ekspor target audiens

Dengan target audiens, kita dapat mengkonfigurasi ekspor dari wawasan audiens ke akun Azure Blob Storage.

### <a name="configure-a-connection"></a>Mengonfigurasi koneksi

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Penyimpanan Blob Azure** atau pilih **Konfigurasi** di petak **Penyimpanan Blob Azure**:

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="petak konfigurasi untuk Azure Blob Storage."::: untuk mengonfigurasi koneksi.

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

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Penyimpanan Blob Azure. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Pilih segmen yang ingin Anda ekspor. Di contoh ini, itu adalah **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Tangkapan layar dari antarmuka pengguna pilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. Pilih **Simpan**.

Setelah menyimpan tujuan ekspor, Anda menemukannya di **Ekspor** > **Data**.

Anda sekarang dapat [mengekspor segmen sesuai permintaan](export-destinations.md#run-exports-on-demand). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md).

> [!NOTE]
> Pastikan jumlah rekaman dalam segmen yang diekspor berada dalam batas yang diizinkan untuk lisensi Adobe Campaign Standard.

Data yang diekspor disimpan dalam wadah Azure Blob storage yang dikonfigurasi di atas. Jalur folder berikut dibuat secara otomatis dalam wadah Anda:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

*Model.json* untuk entitas yang diekspor berada di tingkat *%ExportDestinationName%*.

Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Mendefinisikan Model Data Pengalaman (XDM) di Adobe Experience Platform

Sebelum data yang diekspor dari wawasan audiens dapat digunakan dalam Adobe Experience Platform, kita harus mendefinisikan skema Model Data Pengalaman dan [mengkonfigurasikan data untuk Profil Pelanggan Real-time](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Ketahui [apa itu XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) dan pahami [dasar-dasar susunan skema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Mengimpor data ke Adobe Experience Platform

Setelah semuanya tersedia, kita harus mengimpor data audiens yang disiapkan dari wawasan audiens ke Adobe Experience Platform.

Pertama, [buat sambungan sumber Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Setelah menentukan sambungan sumber, [konfigurasikan aliran data](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) untuk sambungan kumpulan penyimpanan cloud agar dapat mengimpor output segmen dari wawasan audiens ke Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Buat audiens di Adobe Campaign Standard

Untuk mengirim email tentang kampanye ini, kami akan menggunakan Adobe Campaign Standard. Setelah mengimpor data ke Adobe Experience Platform, kita harus [membuat audiens](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) di Adobe Campaign Standard menggunakan data di Adobe Experience Platform.

Pelajari cara [menggunakan pembuat segmen](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) di Adobe Campaign Standard untuk menentukan audiens berdasarkan data dalam Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Membuat dan mengirim email menggunakan Adobe Campaign Standard

Buat konten email, lalu [uji dan kirim](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email Anda.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Contoh email dengan penawaran perpanjangan dari Adobe Campaign Standard.":::