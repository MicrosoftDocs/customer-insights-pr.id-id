---
title: Mengekspor data Customer Insights ke Adobe Campaign Standard
description: Pelajari bagaimana menggunakan segmen wawasan audiens dalam Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596319"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Gunakan segmen Customer Insights dalam Adobe Campaign Standard (pratinjau)

Sebagai pengguna wawasan audiens untuk Dynamics 365 Customer Insights, Anda mungkin telah membuat segmen untuk membuat kampanye pemasaran yang lebih efisien dengan menargetkan audiens yang relevan. Agar dapat menggunakan segmen audiens wawasan dalam Adobe Experience Platform dan aplikasi seperti Adobe Campaign Standard, Anda harus mengikuti beberapa langkah yang diuraikan dalam artikel ini.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram proses dari langkah-langkah yang diuraikan dalam artikel ini.":::

## <a name="prerequisites"></a>Prasyarat

-   Lisensi Dynamics 365 Customer Insights
-   Lisensi Adobe Campaign Standard
-   Akun Azure Blob Storage

## <a name="campaign-overview"></a>Ikhtisar Kampanye

Untuk lebih memahami bagaimana Anda dapat menggunakan segmen wawasan audiens dalam Adobe Experience Platform, lihat kampanye sampel fiktif.

Misalnya, perusahaan Anda menawarkan layanan berbasis langganan bulanan kepada pelanggan Anda di Amerika Serikat. Anda ingin mengidentifikasi pelanggan yang langganannya harus diperpanjang dalam delapan hari berikutnya tetapi belum memperbarui langganan mereka. Untuk menjaga pelanggan ini, Anda perlu mengirimkan penawaran promosi melalui email, menggunakan Adobe Campaign Standard.

Di contoh ini, kita ingin menjalankan kampanye email promosi sekali. Artikel ini tidak mencakup kasus penggunaan dalam menjalankan kampanye lebih dari satu kali. Namun, audiens dan Adobe Campaign Standard juga dapat dikonfigurasi untuk mengerjakan skenario kampanye berulang.

## <a name="identify-your-target-audience"></a>Identifikasikan target audiens

Dalam skenario kami, kami mengasumsikan bahwa alamat email pelanggan tersedia di wawasan audiens dan preferensi promosi mereka dianalisis untuk mengidentifikasi anggota segmen.

[Segmen yang Anda tentukan dalam wawasan audiens](segments.md) disebut **ChurnProneCustomers** dan Anda berencana mengirimkan promosi email kepada pelanggan ini.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Tangkapan layar halaman segmen dengan segmen ChurnProneCustomers dibuat.":::

Email penawaran yang ingin Anda kirim akan berisi nama depan, nama belakang, dan tanggal berakhir langganan pelanggan. Ini akan menginformasikan kepada pelanggan tentang diskon yang akan mereka dapatkan jika mereka memperpanjang langganan sebelum berakhir.

## <a name="export-your-target-audience"></a>Ekspor target audiens

Dengan target audiens, kita dapat mengkonfigurasi ekspor dari wawasan audiens ke akun Azure Blob Storage.

1. Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.

1. Di petak **Adobe Campaign** pilih **Konfigurasi**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Petak konfigurasi untuk Adobe Campaign Standard.":::

1. Berikan **nama tampilan** untuk tujuan ekspor baru ini, lalu masukkan **nama Akun**, **Kunci akun**, dan **Wadah** akun Azure Blob Storage untuk tempat mengekspor segmen.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurasi akun penyimpanan. "::: 

   - Untuk mempelajari lebih lanjut tentang cara menemukan kunci akun dan nama akun penyimpanan Azure Blob, lihat [mengelola pengaturan akun penyimpanan di portal Azure](/azure/storage/common/storage-account-manage).

   - Untuk mempelajari cara membuat penampung, lihat [membuat penampung](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pilih **Selanjutnya**.

1. Pilih segmen yang ingin Anda ekspor. Di contoh ini, itu adalah **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Tangkapan layar dari antarmuka pengguna pilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. Pilih **Selanjutnya**.

1. Sekarang kami memetakan bidang **Sumber** dari segmen wawasan audiens ke nama bidang **Target** dalam skema profil Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Pemetaan bidang untuk konektor Adobe Campaign Standard.":::

   Jika Anda ingin menambahkan atribut lainnya, pilih **Tambah atribut**. Nama target dapat berbeda dari nama bidang sumber, sehingga Anda tetap dapat memetakan output segmen dari wawasan audiens ke Adobe Campaign Standard jika bidang tidak memiliki nama yang sama di kedua sistem.

   > [!NOTE]
   > Alamat email digunakan sebagai bidang identitas, namun Anda dapat menggunakan pengidentifikasi lainnya dari profil pelanggan wawasan audiens untuk memetakan data ke Adobe Campaign Standard.

1. Pilih **Simpan**.

Setelah menyimpan tujuan ekspor, Anda dapat menemukannya di **Admin** > **Ekspor** > **Tujuan ekspor Saya**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Tangkapan layar dengan daftar ekspor dan segmen sampel disorot.":::

Anda sekarang dapat [mengekspor segmen sesuai permintaan](export-destinations.md#export-data-on-demand). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md).

> [!NOTE]
> Pastikan jumlah rekaman dalam segmen yang diekspor berada dalam batas yang diizinkan untuk lisensi Adobe Campaign Standard.

Data yang diekspor disimpan dalam wadah Azure Blob storage yang dikonfigurasi di atas. Jalur folder berikut dibuat secara otomatis dalam wadah Anda:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurasikan Adobe Campaign Standard

Bila segmen dari wawasan audiens diekspor, segmen tersebut berisi kolom yang Anda pilih saat menentukan tujuan ekspor pada langkah sebelumnya. Data ini dapat digunakan untuk [membuat profil di Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Agar dapat menggunakan segmen dalam Adobe Campaign Standard, kita harus memperluas skema profil di Adobe Campaign Standard agar dapat mencakup dua bidang tambahan. Pelajari lebih lanjut cara [memperluas sumber daya profil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) dengan bidang baru di Adobe Campaign Standard.

Di contoh kami, bidang ini adalah *Nama Segmen dan Tanggal Segmen (opsional).*

Kita akan menggunakan bidang ini untuk mengidentifikasi profil dalam Adobe Campaign Standard yang akan ditargetkan untuk kampanye ini.

Jika tidak ada rekaman lain dalam Adobe Campaign Standard, selain yang akan diimpor, Anda dapat melewatkan langkah ini.

## <a name="import-data-into-adobe-campaign-standard"></a>Mengimpor data ke Adobe Campaign Standard

Setelah semuanya tersedia, kita harus mengimpor data audiens yang disiapkan dari wawasan audiens ke Adobe Campaign Standard untuk membuat profil. Pelajari [cara mengimpor profil di Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) menggunakan alur kerja.

Alur kerja impor pada gambar di bawah ini telah dikonfigurasi untuk dijalankan setiap 8 jam dan mencari segmen wawasan audiens yang diekspor (file .csv dalam Azure Blob Storage). Alur kerja mengekstrak konten file .csv dalam urutan kolom yang ditentukan. Alur kerja ini telah dibuat untuk melakukan penanganan kesalahan dasar dan memastikan setiap rekaman memiliki alamat email sebelum menghidrasi data di Adobe Campaign Standard. Alur kerja juga mengekstrak nama segmen dari nama file sebelum melakukan upserting ke data Profil ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Cuplikan layar alur kerja impor di antarmuka pengguna Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Mengambil audiens di Adobe Campaign Standard

Setelah data diimpor ke Adobe Campaign Standard, Anda dapat [membuat alur kerja](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) dan [mengkueri](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) pelanggan berdasarkan *Nama Segmen* dan *Tanggal Segmen* untuk memilih profil yang diidentifikasi untuk kampanye sampel kita.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Membuat dan mengirim email menggunakan Adobe Campaign Standard

Buat konten email, lalu [uji dan kirim](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email Anda.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Contoh email dengan penawaran perpanjangan dari Adobe Campaign Standard.":::