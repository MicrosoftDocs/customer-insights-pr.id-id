---
title: Ekspor data Customer Insights ke Facebook Ads Manager
description: Pelajari cara mengkonfigurasi sambungan ke pengelola iklan Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8260e3b5e529f3d54678d9d6e11aebb2795e27fd
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643687"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Konektor untuk pengelola iklan Facebook (pratinjau)

Ekspor segmen profil pelanggan terpadu ke pengelola iklan Facebook untuk membuat kampanye di Facebook dan Instagram.

## <a name="prerequisites"></a>Prasyarat

- Anda harus memiliki akun [**iklan Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) yang mencakup akun [**bisnis Facebook**](https://business.facebook.com/).
- Anda harus menjadi administrator pada akun [**iklan Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Terhubung ke pengelola iklan Facebook

1. Buka **Admin** > **Tujuan ekspor**.

1. Di **pengelola iklan Facebook**, pilih **konfigurasi**.

1. Beri tujuan ekspor nama yang dikenali di bidang **nama tampilan**.

1. Pilih **Lanjutkan dengan Facebook** untuk masuk ke akun iklan Facebook Anda.

1. Izinkan izin **ads_management** setelah mengautentikasi dengan Facebook.

1. Pilih **Akun Iklan Facebook** yang ingin Anda kerjakan.

1. Pilih **audiens kustom yang ada** dari daftar drop-down atau buat **audiens kustom baru**. Untuk informasi lebih lanjut, lihat [**audiens di pengelola iklan Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Pilih **saya setuju** untuk mengonfirmasi **privasi dan kepatuhan data**.

1. Pilih **berikutnya** untuk mengkonfigurasi ekspor.

## <a name="configure-the-connector"></a>Konfigurasikan konektor

1. Di bidang **Pilih pengidentifikasi utama Anda**, pilih **email**, **nama dan alamat**, atau **telepon** untuk dikirim ke pengelola iklan Facebook.

1. Petakan atribut yang terkait dari entitas pelanggan terpadu Anda untuk pengidentifikasi kunci yang dipilih.
   > [KIAT] Peluang terbaik untuk kecocokan terjadi jika Anda memilih **email** sebagai pengidentifikasi utama. Menambahkan pengidentifikasi tambahan dapat meningkatkan pencocokan.

1. Pilih **Tambah atribut** untuk memetakan atribut tambahan agar dapat dikirim ke pengelola iklan Facebook. Atribut dari manajer iklan Facebook melakukan pemetaan ke nama rumah pengguna berikut: **FN** = **Nama Depan**, **LN** = **Nama Belakang**, **FI** = **Inisial Depan**, **TELEPON** = **Telepon**, **GEN** = **Gender**, **DOB** = **Tanggal Lahir**, **ST** = **Negara Bagian**, **CT** = **Kota**, **ZIP** = **Kode pos/Zip**, **NEGARA** = **Negara/Wilayah**

1. Pilih segmen yang ingin diekspor.

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengekspor data

Anda dapat [mengekspor data sesuai permintaan](export-destinations.md). Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Facebook Ads Manager, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Facebook Ads memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.
