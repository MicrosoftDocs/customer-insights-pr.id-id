---
title: Mengekspor segmen ke Facebook Pengelola Iklan (pratinjau) (berisi video)
description: Pelajari cara mengonfigurasi koneksi dan mengekspor ke Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724603"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Mengekspor segmen ke Facebook Pengelola Iklan (pratinjau)

Ekspor segmen profil pelanggan terpadu ke pengelola iklan Facebook untuk membuat kampanye di Facebook dan Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Prasyarat

- [Facebook Akun Iklan yang](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) menyertakan Akun [Facebook Bisnis](https://business.facebook.com/).
- Hak istimewa administrator di [Facebook Akun Iklan](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Persyaratan audiens kustom harus diterima oleh pengguna yang menyiapkan koneksi di Customer Insights.

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 10 juta profil pelanggan per ekspor ke Facebook Pengelola Iklan, yang dapat memakan waktu hingga 90 menit.
- Segmen saja.
- Facebook Integrasi iklan tidak mendukung pengguna dengan lebih dari 25 akun iklan.
- Facebook *Tipe daftar* pelanggan hanya di [Audiens](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) Kustom.
  > [!NOTE]
  > Dalam beberapa kasus, Anda mungkin melihat audiens khusus dari berbagai jenis di daftar dropdown. Jika Anda memilih jenis lain selain *daftar* pelanggan, ekspor gagal.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Menyiapkan koneksi ke Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih **Facebook Pengelola** Iklan.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. [Izinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autentikasikan dengan Facebook Ads:

   1. Pilih **Lanjutkan dengan Facebook** untuk masuk ke akun Iklan Facebook Anda.

   1. Izinkan izin **ads_management** setelah mengautentikasi dengan Facebook.

   1. Pilih **Akun Iklan Facebook** yang ingin Anda kerjakan.

   1. Pilih **audiens kustom yang ada** dari daftar dropdown atau buat **audiens Kustom Baru**.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Simpan** untuk menyelesaikan koneksi.

## <a name="configure-an-export"></a>Mengonfigurasi ekspor

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor**.

1. **Di bidang Koneksi untuk ekspor**, pilih koneksi dari Facebook bagian Pengelola Iklan. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. **Di bidang Hubungkan data**, pilih **Email**, Nama dan alamat **,** atau **Telepon** untuk dikirim ke Facebook Pengelola Iklan.

1. Petakan atribut yang terkait dari entitas pelanggan terpadu Anda untuk pengidentifikasi kunci yang dipilih.
   > [!TIP]
   > Peluang terbaik untuk kecocokan terjadi jika Anda memilih **email** sebagai pengidentifikasi utama. Menambahkan pengidentifikasi tambahan dapat meningkatkan pencocokan.

1. Pilih **Tambahkan atribut** untuk memetakan lebih banyak atribut untuk dikirim ke Facebook Ads Manager. Atribut dari manajer iklan Facebook melakukan pemetaan ke nama rumah pengguna berikut: **FN** = **Nama Depan**, **LN** = **Nama Belakang**, **FI** = **Inisial Depan**, **TELEPON** = **Telepon**, **GEN** = **Gender**, **DOB** = **Tanggal Lahir**, **ST** = **Negara Bagian**, **CT** = **Kota**, **ZIP** = **Kode pos/Zip**, **NEGARA** = **Negara/Wilayah**

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
