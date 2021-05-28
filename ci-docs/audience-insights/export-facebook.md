---
title: Ekspor data Customer Insights ke Facebook Ads Manager
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976046"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Mengekspor daftar segmen ke Facebook Ads Manager (pratinjau)

Ekspor segmen profil pelanggan terpadu ke pengelola iklan Facebook untuk membuat kampanye di Facebook dan Instagram.

## <a name="prerequisites-for-connection"></a>Prasyarat untuk koneksi

- Anda harus memiliki [**Akun Iklan Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) yang mencakup [**Akun Bisnis Facebook**](https://business.facebook.com/).
- Anda harus menjadi administrator pada akun [**iklan Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 10 juta profil pelanggan per ekspor ke Facebook Ads Manager.
- Mengekspor ke Facebook Ads Manager terbatas untuk segmen.
- Buat atau perbarui audiens kustom dalam Facebook dengan jenis *daftar pelanggan* saja.
- Mengekspor segmen dengan total 10 juta profil dapat memakan waktu hingga 90 menit untuk diselesaikan.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Menyiapkan koneksi ke Facebook Ads Manager

Sebelum pengguna dapat membuat ekspor, administrator harus mengonfigurasi koneksi ke layanan dan mengizinkan kontributor untuk menggunakan koneksi.

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Facebook Ads Manager** untuk mengonfigurasi koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Pilih siapa saja yang dapat menggunakan sambungan ini. Jika Anda tidak mengambil tindakan, defaultnya adalah **Administrator**. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autentikasikan dengan Facebook Ads: 

   1. Pilih **Lanjutkan dengan Facebook** untuk masuk ke akun iklan Facebook Anda.

   1. Izinkan izin **ads_management** setelah mengautentikasi dengan Facebook.

   1. Pilih **Akun Iklan Facebook** yang ingin Anda kerjakan.

   1. Pilih **audiens kustom yang ada** dari daftar drop-down atau buat **audiens kustom baru**. Untuk informasi lebih lanjut, lihat [**audiens di pengelola iklan Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Anda hanya dapat membuat atau memperbarui audiens kustom di Facebook dengan jenis *daftar pelanggan* dengan ekspor ini. Dalam beberapa kasus, Anda akan melihat pemirsa kustom dari berbagai tipe di daftar tarik-turun. Memilih tipe yang berbeda dari *daftar pelanggan* akan mengakibatkan kegagalan ekspor. 

1. Tinjau **privasi dan kepatuhan Data** dan pilih **Saya setuju**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

Anda bisa mengonfigurasi ekspor ini jika Anda memiliki akses ke sambungan tipe ini. Untuk informasi selengkapnya, lihat [Izin yang diperlukan untuk mengonfigurasi ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru. 

1. Pada **Koneksi untuk ekspor**, pilih koneksi dari bagian **Facebook Ads Manager**. Jika Anda tidak melihat nama bagian ini, tidak ada koneksi tipe ini yang tersedia untuk Anda.

1. Di bidang **Pilih pengidentifikasi utama Anda**, pilih **email**, **nama dan alamat**, atau **telepon** untuk dikirim ke pengelola iklan Facebook. 

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**.

1. Petakan atribut yang terkait dari entitas pelanggan terpadu Anda untuk pengidentifikasi kunci yang dipilih.
   > [KIAT] Peluang terbaik untuk kecocokan terjadi jika Anda memilih **email** sebagai pengidentifikasi utama. Menambahkan pengidentifikasi tambahan dapat meningkatkan pencocokan.

1. Pilih **Tambahkan atribut** untuk memetakan lebih banyak atribut untuk dikirim ke Facebook Ads Manager. Atribut dari manajer iklan Facebook melakukan pemetaan ke nama rumah pengguna berikut: **FN** = **Nama Depan**, **LN** = **Nama Belakang**, **FI** = **Inisial Depan**, **TELEPON** = **Telepon**, **GEN** = **Gender**, **DOB** = **Tanggal Lahir**, **ST** = **Negara Bagian**, **CT** = **Kota**, **ZIP** = **Kode pos/Zip**, **NEGARA** = **Negara/Wilayah**

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

Menyimpan ekspor tidak segera menjalankan ekspor.

Ekspor berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab). Anda juga dapat [mengekspor data sesuai permintaan](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Facebook Ads Manager, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Facebook Ads memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]