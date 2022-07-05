---
title: Mengekspor segmen Customer Insights ke Adobe Standar Kampanye (pratinjau)
description: Pelajari cara menggunakan segmen Customer Insights di Adobe Standar Kampanye.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9915591cd969bf825f5d1669de43ed4f9953f898
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082345"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Mengekspor segmen Customer Insights ke Adobe Standar Kampanye (pratinjau)

Sebagai pengguna Dynamics 365 Customer Insights, Anda mungkin telah membuat segmen untuk membuat kampanye pemasaran Anda lebih efisien dengan menargetkan audiens yang relevan. Untuk menggunakan segmen dari Customer Insights dan Adobe Experience Platform aplikasi seperti Adobe Standar Kampanye, Anda harus mengikuti beberapa langkah yang diuraikan dalam artikel ini.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagram proses dari langkah-langkah yang diuraikan dalam artikel ini.":::

## <a name="prerequisites"></a>Prasyarat

- Lisensi Dynamics 365 Customer Insights
- Lisensi Adobe Campaign Standard
- Akun Azure Blob Storage

## <a name="campaign-overview"></a>Ikhtisar Kampanye

Untuk lebih memahami bagaimana Anda dapat menggunakan segmen dari Customer Insights di Adobe Experience Platform, mari kita lihat kampanye sampel fiktif.

Misalnya, perusahaan Anda menawarkan layanan berbasis langganan bulanan kepada pelanggan Anda di Amerika Serikat. Anda ingin mengidentifikasi pelanggan yang langganannya harus diperpanjang dalam delapan hari berikutnya tetapi belum memperbarui langganan mereka. Untuk menjaga pelanggan ini, Anda ingin mengirimkan penawaran promosi melalui email, menggunakan Adobe Campaign Standard.

Di contoh ini, kita ingin menjalankan kampanye email promosi sekali. Artikel ini tidak mencakup kasus penggunaan dalam menjalankan kampanye lebih dari satu kali. Namun, Customer Insights dan Adobe Standar Kampanye juga dapat dikonfigurasi agar berfungsi untuk skenario kampanye berulang.

## <a name="identify-your-target-audience"></a>Identifikasikan target audiens

Dalam skenario kami, kami berasumsi bahwa alamat email pelanggan tersedia dan preferensi promosi mereka dianalisis untuk mengidentifikasi anggota segmen.

Segmen [yang Anda tentukan di Customer Insights](segments.md) disebut **ChurnProneCustomers** dan Anda berencana untuk mengirimkan promosi email kepada pelanggan ini.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Tangkapan layar halaman segmen dengan segmen ChurnProneCustomers dibuat.":::

Email penawaran yang ingin Anda kirim akan berisi nama depan, nama belakang, dan tanggal berakhir langganan pelanggan. Ini akan menginformasikan kepada pelanggan tentang diskon yang akan mereka dapatkan jika mereka memperpanjang langganan sebelum berakhir.

## <a name="export-your-target-audience"></a>Ekspor target audiens

### <a name="configure-a-connection"></a>Mengonfigurasi koneksi

Dengan target kami audiens diidentifikasi, kami dapat mengonfigurasi ekspor ke akun Azure Blob Storage.

1. Di Customer Insights, buka **Koneksi Admin** > **·**.

1. Pilih **Tambah koneksi** dan pilih **Adobe Campaign** untuk mengkonfigurasi koneksi atau pilih **Konfigurasi** dalam petak **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="petak konfigurasi untuk Adobe Campaign Standard.":::

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Masukkan **nama Akun**, **Kunci akun**, dan **Wadah** akun Penyimpanan Blob Azure untuk diekspor segmennya.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Screenshot konfigurasi akun penyimpanan. "::: 

   - Untuk mempelajari lebih lanjut tentang cara menemukan kunci akun dan nama akun penyimpanan Azure Blob, lihat [mengelola pengaturan akun penyimpanan di portal Azure](/azure/storage/common/storage-account-manage).

   - Untuk mempelajari cara membuat penampung, lihat [membuat penampung](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Pilih **Simpan** untuk menyelesaikan koneksi.

### <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Di bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Adobe Campaign. Jika Anda tidak melihat nama bagian ini, maka tidak ada sambungan dari jenis ini yang tersedia untuk Anda.

1. Pilih segmen yang ingin Anda ekspor. Di contoh ini, itu adalah **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Tangkapan layar dari antarmuka pengguna pilihan segmen dengan segmen ChurnProneCustomers dipilih.":::

1. Pilih **Selanjutnya**.

1. Sekarang kita memetakan **bidang Sumber** dari segmen Customer Insights ke **nama bidang Target** dalam Adobe skema profil Standar Kampanye.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Pemetaan bidang untuk konektor Adobe Campaign Standard.":::

   Jika Anda ingin menambahkan atribut lainnya, pilih **Tambah atribut**. Nama target dapat berbeda dari nama bidang sumber sehingga Anda masih dapat memetakan output segmen dari Customer Insights ke Adobe Standar Kampanye jika bidang tidak memiliki nama yang sama di kedua sistem.

   > [!NOTE]
   > Alamat email digunakan sebagai bidang identitas, tetapi Anda dapat menggunakan pengidentifikasi lain dari profil pelanggan untuk memetakan data ke Adobe Standar Kampanye.

1. Pilih **Simpan**.

Setelah menyimpan tujuan ekspor, Anda menemukannya di **Ekspor** > **Data**.

Anda sekarang dapat [mengekspor segmen sesuai permintaan](export-destinations.md#run-exports-on-demand). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md).

> [!NOTE]
> Pastikan jumlah rekaman dalam segmen yang diekspor berada dalam batas yang diizinkan untuk lisensi Adobe Campaign Standard Anda.

Data yang diekspor disimpan dalam wadah Azure Blob storage yang dikonfigurasi di atas. Jalur folder berikut dibuat secara otomatis dalam wadah Anda:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Contoh: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigurasikan Adobe Campaign Standard

Segmen yang diekspor berisi kolom yang Anda pilih saat menentukan tujuan ekspor di langkah sebelumnya. Data ini dapat digunakan untuk [membuat profil dalam Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Agar dapat menggunakan segmen dalam Adobe Campaign Standard, kami harus memperluas skema profil di Adobe Campaign Standard agar dapat mencakup dua bidang tambahan. Pelajari lebih lanjut cara [memperluas sumber daya profil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) dengan bidang baru di Adobe Campaign Standard.

Di contoh kami, bidang ini adalah *Nama Segmen dan Tanggal Segmen (opsional)*.

Kita akan menggunakan bidang ini untuk mengidentifikasi profil dalam Adobe Campaign Standard yang akan ditargetkan untuk kampanye ini.

Jika tidak ada rekaman lain dalam Adobe Campaign Standard, selain yang akan diimpor, Anda dapat melewatkan langkah ini.

## <a name="import-data-into-adobe-campaign-standard"></a>Mengimpor data ke Adobe Campaign Standard

Sekarang semuanya sudah siap, kita perlu mengimpor data audiens yang disiapkan dari Customer Insights ke dalam Adobe Standar Kampanye untuk membuat profil. Pelajari lebih lanjut [cara mengimpor profil dalam Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) menggunakan alur kerja.

Alur kerja impor pada gambar di bawah ini telah dikonfigurasi untuk berjalan setiap delapan jam dan mencari segmen Customer Insights yang diekspor (.csv file di Azure Blob Storage). Alur kerja mengekstrak konten file .csv dalam urutan kolom yang ditentukan. Alur kerja ini telah dibuat untuk melakukan penanganan kesalahan dasar dan memastikan setiap rekaman memiliki alamat email sebelum menghidrasi data dalam Adobe Campaign Standard. Alur kerja juga mengekstrak nama segmen dari nama file sebelum melakukan upserting ke data profil Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Cuplikan layar alur kerja impor di antarmuka pengguna Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Mengambil audiens dalam Adobe Campaign Standard

Setelah data diimpor ke Adobe Campaign Standard, Anda [dapat membuat alur kerja](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) dan [mengkueri](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) pelanggan berdasarkan *Nama Segmen* dan *Tanggal Segmen* untuk memilih profil yang diidentifikasi untuk kampanye sampel kita.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Membuat dan mengirim email menggunakan Adobe Campaign Standard

Buat konten email, lalu [uji dan kirim](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) email Anda.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Contoh email dengan penawaran perpanjangan dari Adobe Campaign Standard.":::
