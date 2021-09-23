---
title: Memulai kemampuan wawasan keterlibatan
description: Ikhtisar sumber daya bantuan untuk memulai dengan cepat.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494598"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Memulai kemampuan wawasan keterlibatan Dynamics 365 Customer Insights (pratinjau umum)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Kemampuan wawasan keterlibatan memungkinkan Anda mengumpulkan dan mengukur perilaku pelanggan di situs web Anda. Analitik ini terintegrasi audiens kemampuan wawasan sehingga Anda dapat melihat analitik perilaku real-time kaya di samping laporan profil pelanggan. Link di artikel ini akan membantu Anda mengkonfigurasi dan mengatur lingkungan secara cepat.

## <a name="step-1-review-prerequisites"></a>Langkah 1: Lihat persyaratan

Pertama,Anda harus memiliki akun pengguna Microsoft Azure Active Directory (AAD) aktif. Selanjutnya, baca artikel berikut sebelum menyiapkan ruang kerja wawasan keterlibatan.

- Tinjau dan setujui [Ketentuan Layanan](terms-of-service.md) Microsoft.  
- Baca artikel [Mengelola cookie dan persetujuan pengguna](user-consent-storage.md). Setelah itu, evaluasi apakah Anda perlu memperbarui pemberitahuan persetujuan pengguna Anda. Jika sebelumnya Anda tidak memiliki cookie "non-penting", kemungkinan Anda harus memperbarui kebijakan situs.
- Lihat [daftar istilah](glossary.md) untuk pengantar singkat istilah dan konsep utama.

## <a name="step-2-explore-engagement-insights"></a>Langkah 2: Jelajahi wawasan keterlibatan

Pertama kali masuk ke wawasan keterlibatan, Anda dapat mengkonfigurasi pengaturan, meninjau kebijakan, dan menjelajahi kemampuan.

1. Masuk ke [portal kemampuan wawasan keterlibatan](https://home.ci.ai.dynamics.com/app/engagement-insights) menggunakan akun pengguna Microsoft AAD (sekolah atau kantor).

1. Pilih kawasan Anda, lalu centang kotak jika Anda ingin menerima pembaruan dan penawaran email.

1. Tinjau **Persyaratan penggunaan wawasan keterlibatan (pratinjau)** dan **pernyataan Privasi**, lalu pilih **Jelajahi demo** untuk menerima pengaturan ini.

1. Jelajahi produk menggunakan rangkaian data sampel.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Langkah 3: Siapkan ruang kerja dan tambahkan kode ke situs web Anda

Ruang kerja adalah tempat Anda dapat melihat aktivitas pengguna secara real time, serta menyimpan dan mengelola laporan. Tambahkan kode ke situs web Anda untuk mulai mengumpulkan *aktivitas*, data aktivitas yang berasal dari pengguna.

1. [Buat ruang kerja](create-workspace.md) dan tambahkan anggota.

1. [Tambahkan kode ke situs web](instrument-website.md) atau [aplikasi seluler](developer-resources.md#capture-events-from-mobile-apps) untuk melihat aktivitas pengguna yang masuk ke ruang kerja Anda.

1. Melihat [laporan real-time](view-reports.md) yang menunjukkan pengguna aktif berdasarkan browser, perangkat, sistem operasi, lokasi, dan bahasa. Anda juga dapat membuat [laporan kustom](custom-reports.md) untuk membuat visualisasi Sendiri.
    
## <a name="step-4-export-data-to-other-channels"></a>Langkah 4: Ekspor data ke saluran lain

Anda dapat membuat *aktivitas disempurnakan* (tampilan virtual) data analitik web. Kemudian filter dan ekspor data ke Azure Data Lake Storage. Anda dapat menyerap data yang diekspor sebagai sumber data. Untuk informasi lebih lanjut, lihat [Membuat tautan antara wawasan audiens dan wawasan keterlibatan](integrate-audience-insights-engagement-insights.md).

1. [Buat aktivitas disempurnakan](refined-events.md) untuk ekspor.

1. [Ekspor data](export-events.md) ke Data Lake Store.

1. [Buat tautan antara wawasan audiens dan wawasan keterlibatan](integrate-audience-insights-engagement-insights.md) untuk berbagi data antara kedua kemampuan.

1. Pelajari cara [Menghapus dan mengekspor data aktivitas yang berisi informasi pribadi](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Langkah 5: Tetap tersambung

Kami sangat mengapresiasi partisipasi aktif Anda, dan mempertimbangkan semua tanggapan relevan dalam mengembangkan rilis yang akan datang. Bagikan tanggapan dan laporkan masalah Anda dengan salah satu saluran berikut:
- [Komunitas](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Berikan tanggapan](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Minta dukungan](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
