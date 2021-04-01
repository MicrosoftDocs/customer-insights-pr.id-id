---
title: Halaman beranda di wawasan audiens
description: Mulai eksplorasi aplikasi pada halaman beranda.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597239"
---
# <a name="create-a-new-environment"></a>Buat lingkungan baru

## <a name="create-a-trial-environment"></a>Buat lingkungan uji coba

Anda dapat mendaftar uji coba di halaman [pendaftaran uji coba](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Uji coba berakhir setelah 30 hari.

1. Pilih **Mendaftar untuk pilihan uji coba gratis** dan pilih **Mendaftar sekarang**.

1. Sediakan alamat email kantor atau sekolah Anda, beri tahu kami tentang diri Anda dan pilih **berikutnya**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Dialog untuk mendaftar ke instans uji coba":::

1. Berikan **nama** untuk lingkungan baru Anda. 

1. Pilih jenis uji coba.

1. Harap pilih **wilayah** untuk lingkungan Anda.

1. Opsional, untuk admin organisasi Dynamics 365: pilih **pengaturan lanjutan** dan berikan URL organisasi Anda untuk menggunakan fitur prediksi seperti kehilangan pelanggan.

1. Pilih **Buat**. 

Setelah lingkungan dibuat, Anda akan melihat lingkungan **demo** yang memungkinkan Anda menjelajahi aplikasi dengan data fiktif. Anda dapat mengubah data sampel untuk mencocokkan industri Anda. Pilih ikon **pengaturan** di header dan pilih **pengaturan demo**. Selain itu, Anda dapat mengubah tema visual. 

Anda [beralih ke lingkungan](#switch-environments) yang Anda buat selama proses pendaftaran untuk bekerja dengan data Anda sendiri.

## <a name="create-a-new-production-or-sandbox-environment"></a>Buat lingkungan sandbox atau produksi baru

Di lingkungan Anda, pilih pemilih **Lingkungan** pada header aplikasi, lalu pilih **Baru**.

Ikuti langkah-langkah seolah Anda [membuat lingkungan uji coba](#create-a-trial-environment). Secara default, data disimpan di data lake yang dikelola Customer Insights. Anda mendapatkan pilihan tambahan saat memilih **pengaturan lanjutan** untuk menyimpan data di Azure Data Lake Anda sendiri. Berikan nama akun dan kunci akun untuk membuat sambungan ke Azure Data Lake Anda. 

> [!IMPORTANT]
> Dengan menyimpan data ke Azure Data Lake Storage, Anda setuju bahwa data akan ditransfer dan disimpan di lokasi geografis yang sesuai untuk akun penyimpanan Azure tersebut, yang mungkin berbeda dengan tempat data disimpan di Dynamics 365 Customer Insights. [Pelajari lebih lanjut di pusat kepercayaan Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Mengeksplorasi halaman beranda

Anda dapat [mengakses wawasan audiens dari Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) di URL berikut: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
Halaman **Beranda** menampilkan ikhtisar segmen, pengukuran, dan data pengayaan (jika dikonfigurasi)setelah menyelesaikan fase [petakan](map-entities.md), [cocokkan](match-entities.md), dan [gabungkan](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Wawasan di Halaman Beranda](media/home-page-insights.png "Wawasan di Halaman Beranda")

Dalam **segmen terkini**, Anda melihat grup pelanggan berdasarkan atribut demografis, perilaku, atau transaksional yang telah Anda tetapkan. [Membuat segmen](segments.md) akan membantu Anda mengelompokkan basis pelanggan dan menargetkan aktivitas bisnis dengan lebih baik.

**Ukuran terbaru** menampilkan petak dengan [KPI (indikator performa utama)](measures.md) yang Anda tetapkan. Misalnya, rata-rata kemungkinan pelanggan untuk pergi atau rata-rata yang dihabiskan secara online per pelanggan.

Bagian **pengayaan baru-baru ini** berisi daftar hasil dari rangkaian pengayaan yang diselesaikan baru-baru ini. [Pengayaan](enrichment-hub.md) menambahkan informasi tentang basis pelanggan Anda. Misalnya, dengan memahami minat dan merek yang mereka miliki afinitasnya.

## <a name="switch-environments"></a>Alihkan Lingkungan

Pilih kontrol **lingkungan** di sudut kanan atas halaman untuk mengubah lingkungan.

> [!div class="mx-imgBorder"] 
> ![Alihkan lingkungan](media/home-page-environment-switcher.png "Alihkan lingkungan")

Administrator dapat membuat dan mengelola [beberapa lingkungan](manage-environments.md). Mengelola lebih dari satu lingkungan mungkin berguna jika, misalnya, organisasi Anda beroperasi secara internasional dan Anda perlu memisahkan data dan wawasan dengan cara yang berbeda.

## <a name="next-step"></a>Langkah berikutnya

Untuk melihat wawasan Anda sendiri di halaman Beranda, Anda harus terlebih dulu [menambahkan sumber data](data-sources.md) dan [menyatukan](data-unification.md) data Anda untuk membangun profil pelanggan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]