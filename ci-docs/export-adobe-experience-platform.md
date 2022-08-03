---
title: Mengekspor segmen ke Adobe Experience Platform (pratinjau)
description: Pelajari cara menggunakan segmen Customer Insights di Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195294"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Mengekspor segmen ke Adobe Experience Platform (pratinjau)

Ekspor segmen yang menargetkan audiens yang relevan ke Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagram proses dari langkah-langkah yang diuraikan dalam artikel ini.":::

## <a name="prerequisites"></a>Prasyarat

- Lisensi Adobe Experience Platform.
- Lisensi Adobe Standar Kampanye.
- Nama [akun](/azure/storage/blobs/create-data-lake-storage-account) dan kunci akun Azure Blob Storage. Untuk menemukan nama dan kunci, lihat [Mengelola pengaturan akun penyimpanan di portal Microsoft Azure](/azure/storage/common/storage-account-manage).
- Kontainer [Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

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

Kami akan mengonfigurasi ekspor dari Customer Insights ke akun Azure Blob Storage.

### <a name="set-up-connection-to-azure-blob-storage"></a>Menyiapkan koneksi ke Azure Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Azure Blob Storage**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **nama Akun**, **Kunci akun**, dan **Wadah** untuk akun Penyimpanan Blob Anda yang ingin Anda ekspor segmennya.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurasi akun penyimpanan. ":::

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

### <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Penyimpanan Blob Azure. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Pilih segmen yang ingin Anda ekspor. Di contoh ini, itu adalah **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Tangkapan layar dari antarmuka pengguna pilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Pastikan jumlah rekaman dalam segmen yang diekspor berada dalam batas yang diizinkan untuk lisensi Adobe Campaign Standard Anda.

Data yang diekspor disimpan dalam kontainer Azure Blob Storage yang Anda konfigurasikan. Jalur folder berikut dibuat secara otomatis dalam penampung:

- Untuk entitas sumber dan entitas yang dihasilkan oleh sistem:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- *Model.json* untuk entitas yang diekspor berada di tingkat *%ExportDestinationName%*.

  Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Tentukan Model Data pengalaman (XDM) di Adobe Experience Platform

Sebelum data yang diekspor dari Customer Insights dapat digunakan di dalamnya Adobe Experience Platform, tentukan skema Model Data Pengalaman dan [konfigurasikan data untuk Profil](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) Pelanggan Real-time.

Ketahui [apa itu XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) dan pahami [dasar-dasar susunan skema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Impor Data ke Adobe Experience Platform

Impor data audiens yang disiapkan dari Customer Insights ke dalam Adobe Experience Platform file.

1. [Buat koneksi](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started) sumber Azure Blob Storage.

1. [Konfigurasikan aliran](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) data untuk koneksi batch penyimpanan cloud untuk mengimpor output segmen dari Customer Insights ke dalam Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Buat audiens dalam Adobe Campaign Standard

Untuk mengirim email tentang kampanye ini, kami akan menggunakan Adobe Campaign Standard.

1. [Buat audiens](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) di Adobe Standar Kampanye menggunakan data di Adobe Experience Platform.

1. [Gunakan pembuat](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) segmen di Adobe Standar Kampanye untuk menentukan audiens berdasarkan data di Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Membuat dan mengirim email menggunakan Adobe Campaign Standard

Buat konten email, lalu [uji dan kirim](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email Anda.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Contoh email dengan penawaran perpanjangan dari Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
