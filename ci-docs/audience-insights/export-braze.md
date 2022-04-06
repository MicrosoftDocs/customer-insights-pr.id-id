---
title: Mengekspor data Customer Insights ke Braze
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8d7cf95c1f157c771b2d655346464e5af03d73b9
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524600"
---
# <a name="export-segment-lists-to-braze-preview"></a>Mengekspor daftar segmen ke Braze (pratinjau)

Ekspor segmen profil pelanggan terpadu ke Braze dan gunakan untuk kegiatan pemasaran.

## <a name="prerequisites"></a>Prasyarat

-   Anda memiliki [akun](https://www.braze.com/) Braze dan kredensial administrator yang sesuai.
-   Anda telah [mengonfigurasikan segmen](segments.md) di wawasan audiens.
-   Profil pelanggan terpadu di segmen yang diekspor berisi bidang yang mewakili alamat email dan ID pelanggan Braze. 

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Mengekspor ke Braze terbatas pada segmen.
- Mengekspor hingga 1 juta profil pelanggan ke Braze dapat memakan waktu hingga 40 menit untuk menyelesaikannya. 
- Jumlah profil pelanggan yang dapat Anda ekspor ke Braze tergantung dan terbatas pada kontrak Anda dengan Braze.

## <a name="set-up-connection-to-braze"></a>Menyiapkan koneksi ke Braze

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Braze** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan kunci [API Braze Anda](https://www.braze.com/docs/api/basics/) untuk terus masuk. 

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **Hubungkan** untuk menginisialisasi koneksi ke Braze.

1. Pilih **Tambah diri Anda sebagai pengguna ekspor** dan berikan kredensial Customer Insights Anda.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Di bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian Braze. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.  

3. **Di bagian Pencocokan** data, di **bidang Email**, pilih bidang yang mewakili alamat email pelanggan, di bidang "ID Pelanggan", pilih bidang yang mewakili ID Braze pelanggan. Diperlukan untuk mengekspor segmen ke Braze. Segmen di Braze akan dibuat dengan nama segmen yang sama seperti di Dynamics 365 Customer Insights. Anda dapat memilih bidang opsional tambahan untuk mencocokkan data. 

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Saat Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Braze, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa Braze memenuhi kewajiban privasi atau keamanan apa pun yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.
