---
title: Mengekspor segmen ke ActiveCampaign
description: Pelajari lebih lanjut cara mengkonfigurasi sambungan dan mengekspor ke ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: eb6f2bb69bb30c319e17390562b3f33512f33ff1
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054712"
---
# <a name="export-segments-to-activecampaign-preview"></a>Mengekspor segmen ke ActiveCampaign (pratinjau)

Mengekspor segmen profil pelanggan terpadu ke ActiveCampaign dan menggunakannya untuk aktivitas pemasaran.

## <a name="prerequisites"></a>Prasyarat

- Anda memiliki [akun ActiveCampaign](https://www.activecampaign.com/) dan kredensial administrator yang terkait.
- Anda telah [mengonfigurasi segmen](segments.md) di Customer Insights.
- Profil pelanggan terpadu di segmen yang diekspor berisi bidang dengan alamat email.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Anda dapat mengekspor hingga 1 juta profil pelanggan per ekspor ke ActiveCampaign dan dapat berlangsung hingga 90 menit.
- Mengekspor ke ActiveCampaign terbatas pada segmen.
- Jumlah profil pelanggan yang dapat Anda ekspor ke ActiveCampaign tergantung pada kontrak Anda dengan ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Siapkan sambungan ke ActiveCampaign

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambah koneksi** dan pilih **ActiveCampaign** untuk mengkonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Secara default hanya administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan [Hostname titik akhir REST dan Kunci API ActiveCampaign](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). Hostname titik akhir REST adalah hanya hostname, tanpa https://. 

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Sambungkan** untuk memulai koneksi ke ActiveCampaign.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Di bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian ActiveCampaign. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Masukkan [**ID daftar ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign) Anda.    

1. Di bagian **Pencocokan data**, di bidang **Email**, pilih bidang yang mewakili alamat email pelanggan. Mengekspor segmen ke ActiveCampaign harus dilakukan. Atau, Anda dapat mengekspor nama depan, nama belakang, dan Telepon untuk membuat email yang lebih dipersonalisasi. Pilih Tambah atribut untuk memetakan bidang ini.

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mentransmisikan data ke ActiveCampaign, Anda mengizinkan transfer data di luar batas kesesuaian untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mengalihkan data tersebut berdasarkan instruksi Anda, namun Anda bertanggung jawab untuk memastikan bahwa ActiveCampaign memenuhi privasi atau jaminan keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.
