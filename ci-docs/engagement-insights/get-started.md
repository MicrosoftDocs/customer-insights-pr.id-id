---
title: Memulai kemampuan wawasan keterlibatan
description: Ikhtisar sumber daya bantuan untuk memulai dengan cepat.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405362"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Memulai kemampuan wawasan keterlibatan Dynamics 365 Customer Insights (pratinjau umum)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Kemampuan wawasan keterlibatan memungkinkan Anda mengumpulkan dan mengukur perilaku pelanggan di situs web Anda. Analitik ini terintegrasi audiens kemampuan wawasan sehingga Anda dapat melihat analitik perilaku real-time kaya di samping laporan profil pelanggan. Link di artikel ini akan membantu Anda mengkonfigurasi dan mengatur lingkungan secara cepat.

## <a name="step-1-review-prerequisites"></a>Langkah 1: Lihat persyaratan

Pertama,Anda harus memiliki akun pengguna Microsoft Azure Active Directory aktif. Selanjutnya, baca artikel berikut sebelum menyiapkan ruang kerja wawasan keterlibatan.

- Tinjau dan setujui [Ketentuan Layanan](terms-of-service.md) Microsoft.  
- Baca artikel [Mengelola cookie dan persetujuan pengguna](user-consent-storage.md). Setelah memeriksa artikel ini, evaluasi apakah Anda perlu memperbarui pemberitahuan persetujuan pengguna Anda. Jika sebelumnya Anda tidak memiliki cookie "non-penting", kemungkinan Anda harus memperbarui kebijakan situs.
- Lihat [daftar istilah](glossary.md) untuk pengantar singkat istilah dan konsep utama.

## <a name="step-2-explore-engagement-insights"></a>Langkah 2: Jelajahi wawasan keterlibatan

Pertama kali anda mengunjungi wawasan keterlibatan, Anda dapat mengkonfigurasi pengaturan, meninjau kebijakan, dan menjelajahi produk.

1. Masuk ke [portal kemampuan wawasan keterlibatan](https://pi.dynamics.com) menggunakan akun pengguna Microsoft Azure Active Directory. (Dapat berupa akun sekolah atau kantor Anda.)

1. Pilih kawasan Anda, dan gunakan kotak centang untuk menunjukkan apakah Anda ingin menerima pembaruan dan penawaran melalui email.

1. Tinjau **Ketentuan penggunaan wawasan keterlibatan (pratinjau)** dan **Pernyataan Privasi**, lalu pilih **Jelajahi demo** untuk menerimanya.

1. Jelajahi produk menggunakan rangkaian data sampel.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Langkah 3: Siapkan ruang kerja dan tambahkan kode ke situs web Anda

Ruang kerja adalah tempat Anda dapat melihat aktivitas pengguna secara real time, serta menyimpan serta mengelola laporan. Tambahkan kode ke situs web Anda untuk mulai mengumpulkan *aktivitas*, data aktivitas yang berasal dari pengguna.

1. [Buat ruang kerja](create-workspace.md) dan tambahkan anggota.

1. [Tambahkan kode ke situs web](instrument-website.md) atau [aplikasi seluler](developer-resources.md#capture-events-from-mobile-apps) untuk melihat aktivitas pengguna yang masuk ke ruang kerja Anda.

1. Melihat [laporan real-time](view-reports.md) yang menampilkan pengguna aktif menurut browser, perangkat, sistem operasi, lokasi, dan bahasa. Anda juga dapat membuat [laporan kustom](custom-reports.md) untuk membuat visualisasi Sendiri.
    
## <a name="step-4-export-data-to-other-channels"></a>Langkah 4: Ekspor data ke saluran lain

Anda dapat membuat *aktivitas disempurnakan* (tampilan virtual) data analitik web. Kemudian filter dan ekspor data ke Azure Data Lake Storage. Anda dapat menyerap data yang diekspor sebagai sumber data. Untuk informasi lebih lanjut, lihat [Membuat tautan antara wawasan audiens dan wawasan keterlibatan](integrate-audience-insights-engagement-insights.md).

1. [Buat aktivitas disempurnakan](refined-events.md) untuk ekspor.

1. [Ekspor data](export-events.md) ke Data Lake Store.

1. Pelajari cara [Menghapus dan mengekspor data aktivitas yang berisi informasi pribadi](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Langkah 5: Tetap tersambung

Kami sangat mengapresiasi keterlibatan aktif Anda dan berencana mempertimbangkan semua tanggapan relevan dalam mengembangkan rilis yang akan datang. Bagikan tanggapan dan laporkan masalah Anda dengan salah satu saluran berikut:
- [Komunitas](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Berikan tanggapan](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Minta dukungan](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
