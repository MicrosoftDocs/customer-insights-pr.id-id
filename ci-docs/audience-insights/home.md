---
title: Halaman beranda di wawasan audiens
description: Mulai eksplorasi aplikasi pada halaman beranda.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406065"
---
# <a name="create-a-new-environment"></a>Buat lingkungan baru

## <a name="create-a-trial-environment"></a>Buat lingkungan uji coba

Anda dapat mendaftar uji coba di halaman [pendaftaran uji coba](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Uji coba berakhir setelah 30 hari.

1. Pilih **Mendaftar untuk pilihan uji coba gratis** dan pilih **Mendaftar sekarang**.

1. Sediakan alamat email kantor atau sekolah Anda, beri tahu kami tentang diri Anda dan pilih **berikutnya**.

1. Berikan **nama** untuk lingkungan baru Anda. 

1. Pilih jenis uji coba.

1. Harap pilih **wilayah** untuk lingkungan Anda.

1. Opsional, untuk admin organisasi Dynamics 365: pilih **pengaturan lanjutan** dan berikan URL organisasi Anda untuk menggunakan fitur prediksi seperti kehilangan pelanggan.

1. Pilih **Buat**. 

Setelah lingkungan dibuat, Anda akan melihat lingkungan **demo** yang memungkinkan Anda menjelajahi aplikasi dengan data fiktif. Anda dapat mengubah data sampel untuk mencocokkan industri Anda. Pilih ikon **pengaturan** di header dan pilih **pengaturan demo**. Selain itu, Anda dapat mengubah tema visual. 

Anda [beralih ke lingkungan](#change-between-environments) yang Anda buat selama proses pendaftaran untuk bekerja dengan data Anda sendiri.

## <a name="create-a-new-production-or-sandbox-environment"></a>Buat lingkungan sandbox atau produksi baru

Di lingkungan Anda, pilih ikon **pengaturan** di header dan pilih **lingkungan baru**.

Ikuti langkah-langkah seolah Anda [membuat lingkungan uji coba](#create-a-trial-environment). Anda mendapatkan pilihan tambahan saat memilih **pengaturan lanjutan** untuk menyimpan data di Azure Data Lake Anda sendiri. Berikan nama akun dan kunci akun untuk membuat sambungan ke Azure Data Lake Anda. Secara default, data disimpan di data lake yang dikelola Customer Insights.

> [!IMPORTANT]
> Dengan menyimpan data ke Azure Data Lake Storage, Anda setuju bahwa data akan ditransfer dan disimpan di lokasi geografis yang sesuai untuk akun penyimpanan Azure tersebut, yang mungkin berbeda dengan tempat data disimpan di Dynamics 365 Customer Insights. [Pelajari lebih lanjut di pusat kepercayaan Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Mengeksplorasi halaman beranda

Anda dapat [mengakses lingkungan Customer Insights Anda](https://home.ci.ai.dynamics.com/) pada URL berikut: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
Halaman **Beranda** menampilkan ikhtisar tentang basis pelanggan dan metrik kunci untuk melacak kesehatan bisnis Anda.

> [!div class="mx-imgBorder"] 
> ![Wawasan di Halaman Beranda](media/home-page-insights.png "Wawasan di Halaman Beranda")

Dalam **segmen terkini**, Anda melihat grup pelanggan berdasarkan atribut demografis, perilaku, atau transaksional yang telah Anda tetapkan. [Membuat segmen](segments.md) akan membantu Anda menargetkan aktivitas bisnis dengan lebih baik.

**Ukuran terbaru** menunjukkan ubin dengan [ukuran](measures.md). Ukuran adalah KPI (indikator performa utama) yang telah Anda tetapkan. Contohnya, kemungkinan rata-rata kehilangan pelanggan atau rata-rata pembelanjaan online per pelanggan.

Bagian **pengayaan baru-baru ini** berisi daftar hasil dari rangkaian pengayaan yang diselesaikan baru-baru ini. Pengayaan menambahkan informasi tentang basis pelanggan Anda. Misalnya, dengan memahami minat dan merek yang mereka miliki afinitasnya. Informasi ini dapat dibuka dengan menggunakan [kemampuan pengayaan](enrichment-microsoft-graph.md), setelah menyelesaikan fase [pemetaan](map-entities.md), [pencocokan](match-entities.md), dan [penggabungan](merge-entities.md).

## <a name="change-between-environments"></a>Perubahan di antara lingkungan

Setelah mengkonfigurasi dan menyiapkan [sumber data](data-sources.md), Anda akan ingin beralih dari lingkungan demo ke lingkungan aktif. Menggunakan lingkungan produksi memungkinkan Anda bekerja dengan data pelanggan Anda sendiri. Pilih kontrol **lingkungan** di sudut kanan atas halaman untuk mengubah lingkungan.

> [!div class="mx-imgBorder"] 
> ![Alihkan lingkungan](media/home-page-environment-switcher.png "Alihkan lingkungan")

Administrator dapat membuat dan mengelola [beberapa lingkungan](manage-environments.md). Mengelola lebih dari satu lingkungan mungkin berguna jika, misalnya, organisasi Anda beroperasi secara internasional dan Anda perlu memisahkan data dan wawasan dengan cara yang berbeda.

## <a name="next-step"></a>Langkah berikutnya

Untuk melihat wawasan Anda sendiri di halaman Beranda, Anda harus terlebih dulu [menambahkan sumber data](data-sources.md) dan [menyatukan](data-unification.md) data Anda untuk membangun profil pelanggan.
