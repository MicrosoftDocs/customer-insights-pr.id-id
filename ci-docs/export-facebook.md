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
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195018"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Mengekspor segmen ke Facebook Pengelola Iklan (pratinjau)

Ekspor segmen profil pelanggan terpadu ke pengelola iklan Facebook untuk membuat kampanye di Facebook dan Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Prasyarat

- [Facebook Akun](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) Iklan yang [Facebook menyertakan Akun Bisnis](https://business.facebook.com/).
- Hak istimewa administrator di [Facebook Akun Iklan](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Pembatasan yang diketahui

- Hingga 10 juta profil pelanggan per ekspor ke Facebook Pengelola Iklan, yang dapat memakan waktu hingga 90 menit.
- Segmen saja.
- Facebook *jenis daftar* pelanggan hanya di [audiens](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) khusus.
  > [!NOTE]
  > Dalam beberapa kasus, Anda mungkin melihat pemirsa khusus dari berbagai jenis di daftar dropdown. Jika Anda memilih jenis yang berbeda selain *daftar* pelanggan, ekspor gagal.

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

1. **Di bidang Koneksi untuk ekspor**, pilih koneksi dari bagian Facebook Pengelola Iklan. Hubungi administrator jika tidak ada koneksi yang tersedia.

1. Masukkan nama untuk ekspor.

1. **Di bidang Hubungkan data**, pilih **Email**, **Nama dan alamat**, atau **Telepon** untuk dikirim ke Facebook Pengelola Iklan.

1. Petakan atribut yang terkait dari entitas pelanggan terpadu Anda untuk pengidentifikasi kunci yang dipilih.
   > [!TIP]
   > Peluang terbaik untuk kecocokan terjadi jika Anda memilih **email** sebagai pengidentifikasi utama. Menambahkan pengidentifikasi tambahan dapat meningkatkan pencocokan.

1. Pilih **Tambahkan atribut** untuk memetakan lebih banyak atribut untuk dikirim ke Facebook Ads Manager. Atribut dari manajer iklan Facebook melakukan pemetaan ke nama rumah pengguna berikut: **FN** = **Nama Depan**, **LN** = **Nama Belakang**, **FI** = **Inisial Depan**, **TELEPON** = **Telepon**, **GEN** = **Gender**, **DOB** = **Tanggal Lahir**, **ST** = **Negara Bagian**, **CT** = **Kota**, **ZIP** = **Kode pos/Zip**, **NEGARA** = **Negara/Wilayah**

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
