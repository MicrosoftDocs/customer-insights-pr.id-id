---
title: Mengekspor segmen Customer Insights ke Adobe Standar Kampanye (pratinjau)
description: Pelajari cara menggunakan segmen Customer Insights di Adobe Standar Kampanye.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195524"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Mengekspor segmen Customer Insights ke Adobe Standar Kampanye (pratinjau)

Ekspor segmen yang menargetkan audiens yang relevan ke Adobe Standar Kampanye.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram proses dari langkah-langkah yang diuraikan dalam artikel ini.":::

## <a name="prerequisites"></a>Prasyarat

- Lisensi Adobe Standar Kampanye.
- Nama [akun](/azure/storage/blobs/create-data-lake-storage-account) dan kunci akun Azure Blob Storage. Untuk menemukan nama dan kunci, lihat [Mengelola pengaturan akun penyimpanan di portal Microsoft Azure](/azure/storage/common/storage-account-manage).
- Kontainer [Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Ikhtisar Kampanye

Untuk lebih memahami bagaimana Anda dapat menggunakan segmen dari Customer Insights di Adobe Experience Platform, mari kita lihat kampanye sampel fiktif.

Misalnya, perusahaan Anda menawarkan layanan berbasis langganan bulanan kepada pelanggan Anda di Amerika Serikat. Anda ingin mengidentifikasi pelanggan yang langganannya harus diperpanjang dalam delapan hari berikutnya tetapi belum memperbarui langganan mereka. Untuk menjaga pelanggan ini, Anda ingin mengirimkan penawaran promosi melalui email, menggunakan Adobe Campaign Standard.

Di contoh ini, kita ingin menjalankan kampanye email promosi sekali. Artikel ini tidak mencakup kasus penggunaan dalam menjalankan kampanye lebih dari satu kali. Namun, Customer Insights dan Adobe Standar Kampanye juga dapat dikonfigurasi agar berfungsi untuk skenario kampanye berulang.

## <a name="identify-your-target-audience"></a>Identifikasikan target audiens

Dalam skenario kami, kami berasumsi bahwa alamat email pelanggan tersedia di Customer Insights dan preferensi promosi mereka dianalisis untuk mengidentifikasi anggota segmen.

Segmen [yang Anda tentukan di Customer Insights](segments.md) disebut **ChurnProneCustomers** dan Anda berencana untuk mengirimkan promosi email kepada pelanggan ini.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Tangkapan layar halaman segmen dengan segmen ChurnProneCustomers dibuat.":::

Email penawaran yang ingin Anda kirim akan berisi nama depan, nama belakang, dan tanggal berakhir langganan pelanggan. Ini akan menginformasikan kepada pelanggan tentang diskon yang akan mereka dapatkan jika mereka memperpanjang langganan sebelum berakhir.

## <a name="export-your-target-audience"></a>Ekspor target audiens

### <a name="set-up-connection-to-adobe-campaign"></a>Menyiapkan koneksi ke Adobe Kampanye

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Adobe Kampanye**.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **Nama akun,** Kunci **akun**, dan **Kontainer** untuk akun Blob Storage Anda.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurasi akun penyimpanan. ":::

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

### <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. Di bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Adobe Campaign. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. Pilih segmen yang ingin Anda ekspor. Di contoh ini, itu adalah **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Tangkapan layar dari antarmuka pengguna pilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. Pilih **Selanjutnya**.

1. Petakan **bidang Sumber** dari segmen Customer Insights ke **nama bidang Target** dalam Adobe skema profil Standar Kampanye.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Pemetaan bidang untuk konektor Adobe Campaign Standard.":::

   Jika Anda ingin menambahkan atribut lainnya, pilih **Tambah atribut**. Nama target dapat berbeda dari nama bidang sumber sehingga Anda masih dapat memetakan output segmen dari Customer Insights ke Adobe Standar Kampanye jika bidang tidak memiliki nama yang sama di kedua sistem.

   > [!NOTE]
   > Alamat email digunakan sebagai bidang identitas, tetapi Anda dapat menggunakan pengidentifikasi lain dari profil pelanggan untuk memetakan data ke Adobe Standar Kampanye.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Pastikan jumlah rekaman dalam segmen yang diekspor berada dalam batas yang diizinkan untuk lisensi Adobe Campaign Standard Anda.

Data yang diekspor disimpan dalam wadah Azure Blob storage yang dikonfigurasi di atas. Jalur folder berikut secara otomatis dibuat di kontainer Anda: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurasikan Adobe Campaign Standard

Segmen yang diekspor berisi kolom yang Anda pilih saat mengonfigurasi ekspor. Data ini dapat digunakan untuk [membuat profil dalam Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Untuk menggunakan segmen di Adobe Standar Kampanye, perluas [skema](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) profil di Adobe Standar Kampanye untuk menyertakan dua kolom tambahan.

Dalam contoh kami, bidang ini adalah Nama Segmen dan Tanggal Segmen. Kita akan menggunakan bidang ini untuk mengidentifikasi profil dalam Adobe Campaign Standard yang akan ditargetkan untuk kampanye ini.

Jika tidak ada catatan lain di Adobe Standar Kampanye, selain yang akan Anda impor, lewati langkah ini.

## <a name="import-data-into-adobe-campaign-standard"></a>Mengimpor data ke Adobe Campaign Standard

Impor data audiens yang disiapkan dari Customer Insights ke dalam Adobe Standar Kampanye untuk [membuat profil menggunakan alur kerja](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

Alur kerja impor pada gambar di bawah ini telah dikonfigurasi untuk berjalan setiap delapan jam dan mencari segmen Customer Insights yang diekspor (.csv file di Azure Blob Storage). Alur kerja mengekstrak konten file .csv dalam urutan kolom yang ditentukan. Alur kerja ini telah dibuat untuk melakukan penanganan kesalahan dasar dan memastikan setiap rekaman memiliki alamat email sebelum menghidrasi data dalam Adobe Campaign Standard. Alur kerja juga mengekstrak nama segmen dari nama file sebelum melakukan upserting ke data profil Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Cuplikan layar alur kerja impor di antarmuka pengguna Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Mengambil audiens dalam Adobe Campaign Standard

Setelah data diimpor ke Adobe Standar Kampanye, [buat alur kerja](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) dan [kueri](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) pelanggan berdasarkan Nama Segmen dan Tanggal Segmen untuk memilih profil yang diidentifikasi untuk kampanye sampel kami.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Membuat dan mengirim email menggunakan Adobe Campaign Standard

Buat konten email, lalu [uji dan kirim](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email Anda.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Contoh email dengan penawaran perpanjangan dari Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
