---
title: Konektor LiveRamp
description: Pelajari cara mengonfigurasi koneksi dan ekspor ke LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: f9a0a88fb58897e4d279c181f4cdb4f6c852da60
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618939"
---
# <a name="export-segments-to-liverampreg-preview"></a>Mengekspor segmen ke LiveRamp&reg; (pratinjau)

Aktifkan data Anda di LiveRamp untuk terhubung dengan lebih dari 500 platform di seluruh digital, sosial, dan TV. Bekerja dengan data Anda di LiveRamp untuk menargetkan, menekan, dan mempersonalisasi kampanye iklan.

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk koneksi

- Anda memerlukan langganan LiveRamp untuk menggunakan konektor ini.
- Untuk mendapatkan langganan, [hubungi langsung LiveRamp](https://liveramp.com/contact/). [Pelajari lebih lanjut tentang LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Konfigurasikan koneksi ke LiveRamp

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **LiveRamp** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah Administrator. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Berikan **nama pengguna** dan **sandi** untuk akun LiveRamp Secure FTP (SFTP) Anda.
Kredensial ini mungkin berbeda dengan kredensial LiveRamp Onboarding Anda.

1. Pilih **Verifikasikan** untuk menguji sambungan ke LiveRamp.

1. Setelah verifikasi berhasil, berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Pada bidang **Koneksi untuk ekspor**, pilih koneksi dari bagian LiveRamp. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Di bidang **Pilih pengidentifikasi kunci Anda**, pilih **email**,  **nama dan alamat**, atau **telepon** untuk dikirim ke LiveRamp untuk resolusi identitas.
   > [!div class="mx-imgBorder"]
   > ![Konektor LiveRamp dengan pemetaan atribut.](media/export-liveramp-segments.png "Konektor LiveRamp dengan pemetaan atribut")

1. Petakan atribut yang sesuai dari entitas *Pelanggan* untuk pengidentifikasi utama yang dipilih.

1. Pilih **Tambahkan atribut** untuk memetakan lebih banyak atribut untuk dikirim ke LiveRamp.

   > [!TIP]
   > Mengirimkan lebih banyak atribut pengidentifikasi kunci ke LiveRamp kemungkinan akan memberi Anda tingkat kecocokan yang lebih tinggi.

1. Pilih segmen yang ingin Anda ekspor ke LiveRamp.

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Liveramp, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Liveramp memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
