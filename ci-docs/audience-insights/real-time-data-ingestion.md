---
title: Konsumsi data real-time dan keterbatasan
description: Informasi umum tentang kemampuan real-time dalam wawasan audiens.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2fe5279eee1b3b30f5bc21464c85fe5f86d342a0
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355479"
---
# <a name="real-time-data-ingestion-preview"></a>Konsumsi data real-time (pratinjau)

Fungsi nyaris real-time memungkinkan Anda melihat, dalam hitungan detik, interaksi terbaru yang telah dibuat pelanggan dengan produk atau layanan Anda.

[Penyegaran terjadwal](system.md#schedule-tab) mencakup sejumlah besar rekaman dan beberapa operasi kompleks. Pertama, data ditarik dari sumber data. Selanjutnya, data disatukan, lalu diperkaya dengan informasi tambahan. Setiap proses ini dapat berlangsung selama beberapa menit.

Fungsi real-time menyediakan data segera untuk dikonsumsi, hingga penyegaran terjadwal berikutnya menarik data ini dari sumber data.

Pembaruan Real-time memiliki waktu kedaluwarsa yang setelahnya tidak lagi mengesampingkan nilai dari sumber data:

- Pembaruan profil akan disimpan selama 4 jam
- Aktivitas akan disimpan selama 30 hari

Nilai ini adalah parameter panggilan API yang dapat Anda ubah. Mereka bertujuan untuk memastikan bahwa data sumber Anda tetap menjadi sumber kebenaran. Jika anda ingin pembaruan real-time dimasukkan lebih lama, anda harus menambahkannya ke sumber data sehingga ditarik selama refresh terjadwal berikutnya.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Pembaruan real-time atas bidang profil pelanggan terpadu

Profil yang diperbarui akan ditampilkan di tampilan kartu pelanggan, atau visualisasi lainnya, dalam beberapa detik.

Karena operasi real-time terjadi setelah penyatuan data terjadi, itu hanya berlaku untuk profil pelanggan terpadu. Akibatnya, perubahan profil secara real-time tidak akan memperbarui tindakan, keanggotaan segmen, atau pengayaan.

### <a name="limitations"></a>Batasan

- Profil pelanggan dapat diperbarui, namun tidak dibuat atau dihapus.
- Mengekspor pembaruan real-time ke sistem eksternal, seperti Power BI, tidak dapat dilakukan saat ini.

## <a name="real-time-creation-of-activities"></a>Pembuatan real-time aktivitas

API real-time memungkinkan Anda mempublikasikan aktivitas baru dari sistem sumber (rekaman sumber individual) ke profil pelanggan terpadu. Aktivitas baru akan tersedia sebagai aktivitas terpadu dalam Timeline profil pelanggan terpadu dalam hitungan detik. Anda dapat melihat Timeline di tampilan kartu pelanggan atau integrasi Timeline lain yang Anda konfigurasikan.

> [!NOTE]
>
> - Aktivitas tidak dapat diubah. Mereka tidak berubah setelah dibuat.
> - Saat ini, segmen dan langkah tidak diperbarui berdasarkan aktivitas baru.
> - Aktivitas yang ditambahkan hanya melalui API real-time bukan bagian dari ekspor dan tidak akan ditampilkan di PowerBI.

Ada dua cara untuk menyambung ke API real-time:

- [secara tidak langsung](#connect-via-the-dynamics-365-customer-insights-connector), menggunakan [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)
- [secara langsung](#connect-directly-to-the-real-time-api), dengan kode

Kedua cara sama-sama memiliki prasyarat berikut:

- Lingkungan Customer Insights
- Profil pelanggan terpadu
- Aktivitas yang dikonfigurasi dan dijalankan
- Izin kontributor atau Administrator untuk mengotentikasi akun anda

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Sambungkan melalui Dynamics 365 Customer Insights connector

Real-Time API dapat menyerap data dari Power Platform connector khusus, [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), tanpa harus menulis dan menyebarkan kode apa pun.    
Konektor dapat melakukan tindakan real-time yang sama dengan API. Anda memerlukan lisensi yang valid untuk konektor Premium. Untuk informasi lebih lanjut, lihat [pertanyaan umum lisensi Power Automate dan Power Apps](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps dan/atau Power Automate](/connectors/)
- Azure [Aplikasi Logika](/azure/connectors/apis-list)

Untuk rincian tentang pembuatan alur, lihat [dokumentasi Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Terhubung langsung ke API real-time

Anda dapat menggunakan kemampuan real-time dengan membuat alur sendiri dan terhubung langsung ke API real-time.    
Anda dapat memposting aktivitas dalam format sistem sumber atau dalam format UnifiedActivity. Dapatkan format dengan membuat panggilan API ke /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Rincian API ini, termasuk parameter dan respons, dapat ditemukan di bagian **EntityData** di [referensi API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Untuk informasi lebih lanjut, lihat [bekerja dengan api Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Memahami penggunaan real-time Anda dengan telemetri

Dapatkan ikhtisar tentang volume permintaan ke API real-time dan informasi tentang masalah yang mungkin dihadapi sistem. Anda dapat [mengakses telemetri real-time](system.md#api-usage-tab). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]