---
title: Lihat laporan data
description: Gunakan laporan yang tersedia untuk melihat aktivitas real-time di situs Anda.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 5ccdcb47db597154cf79b9f2e8fc238ab75dfde9
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582926"
---
# <a name="view-reports"></a>Lihat laporan

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Laporan adalah kumpulan visualisasi data, menggunakan data yang dikumpulkan melalui SDK, yang membantu Anda mengukur dan memahami perilaku pengguna. Wawasan keterlibatan Dynamics 365 Customer Insights mencakup laporan OOB (siap pakai) untuk proyek web dan perangkat bergerak.  

## <a name="web-reports"></a>Laporan web

Anda dapat mengakses laporan web dalam **Temukan** di panel navigasi kiri.

:::image type="content" source="media/report-menu.png" alt-text="Navigasi yang menampilkan daftar laporan yang tersedia.":::

### <a name="real-time-usage-report"></a>Laporan penggunaan real-time

Laporan  **penggunaan Real-time** memberikan ikhtisar aktivitas saat ini di situs Anda yang secara otomatis me-refresh setiap menit. Gunakan penggunaan real-time untuk memantau dampak kampanye pemasaran, aktivitas pers, dan skenario lain pada lalu lintas situs Anda.

### <a name="key-metrics-reports"></a>Laporan metrik kunci

- **Tampilan halaman** mencantumkan tampilan halaman untuk masing-masing halaman beserta jumlah tayangan halaman total selama jangka waktu yang dipilih.

- **Kunjungan** menampilkan informasi tentang jumlah kunjungan dan durasi kunjungan.

- **Pengunjung** menginformasikan tentang pengunjung unik yang baru dan kembali ke situs Anda.

### <a name="content-reports"></a>Laporkan konten

- **Tautan** menampilkan informasi tentang nomor dan jenis klik.

- **Halaman keluar** akan mencantumkan tautan yang diklik pengunjung untuk keluar dari situs Anda.

### <a name="traffic-sources-reports"></a>Laporan sumber lalu lintas

- **Pereferensi** mencantumkan domain dan URL yang mereferensikan pengunjung ke situs Anda.

- **Kode pelacakan** memberikan rincian tentang kode pelacakan pada tautan yang mendatangkan pengunjung ke situs Anda.

### <a name="visitor-profiles-reports"></a>Laporan profil pengunjung

- **Perangkat** mencantumkan perangkat fisik yang digunakan untuk mengakses situs Anda.

- **OS & Browser** memberikan wawasan tentang sistem operasi dan browser yang berjalan saat mengakses situs Anda.

- **Lokasi** menampilkan informasi tentang pengunjung berdasarkan negara, kawasan, dan kota.

- **Bahasa** mencantumkan tayangan halaman berdasarkan bahasa pilihan pengunjung.

## <a name="mobile-reports"></a>Laporan seluler

Laporan seluler dikelompokkan dalam kategori penggunaan, aplikasi, dan pengguna real-time. Anda dapat mengakses laporan seluler dalam **Temukan** di panel navigasi kiri.   

:::image type="content" source="media/mobile-reports.png" alt-text="Antarmuka pengguna dari wawasan keterlibatan yang menunjukkan laporan penggunaan real-time yang menampilkan data dalam diagram dan daftar.":::   

### <a name="real-time-usage"></a>Penggunaan real-time

**Penggunaan real-time** memberikan ikhtisar aktivitas saat ini dalam aplikasi seluler Anda yang secara otomatis me-refresh setiap menit. Gunakan penggunaan real-time untuk memantau jumlah pengguna dan sesi yang saat ini aktif dalam aplikasi dan tampilan layar atas.

### <a name="app-reports"></a>Laporan aplikasi

- **Tampilan layar** mencantumkan tayangan layar untuk setiap layar dalam aplikasi dan total jumlah tayangan layar selama jangka waktu yang dipilih. Anda dapat melihat tayangan layar berdasarkan nama layar atau judul layar.

- **Sesi** menampilkan informasi tentang jumlah sesi dan durasi sesi.

- **Frekuensi kembali** Jumlah sesi grup berdasarkan jumlah hari sejak sesi terakhir.

- **Pengguna** menampilkan pengguna baru dan kembali dalam aplikasi seluler Anda.

- **Aktivitas** mencantumkan semua aktivitas yang dikumpulkan dari aplikasi Anda, ditambah jumlah total untuk setiap aktivitas.

### <a name="user-reports"></a>Laporan pengguna

- **Versi aplikasi** mencantumkan versi aplikasi seluler yang digunakan oleh basis pengguna Anda.

- **Versi Perangkat & OS** memberikan wawasan tentang perangkat dan sistem operasi yang menjalankan aplikasi seluler Anda.

- **Lokasi** menampilkan informasi tentang pengguna aplikasi berdasarkan negara, kawasan, dan kota.

## <a name="filter-by-time-or-date-range"></a>Filter berdasarkan waktu atau rentang tanggal

Anda dapat memilih jangka waktu atau rentang tanggal dalam laporan web atau seluler untuk fokus pada nilai atau periode waktu. 

- Untuk memilih jangka waktu, di sudut kanan atas tampilan laporan, pilih nilai dari daftar dropdown laporan. Anda juga dapat memilih **Rentang tanggal tetap**. 

  :::image type="content" source="media/filter-by-time.png" alt-text="Filter berdasarkan waktu atau rentang tanggal.":::   

- Untuk sebagian besar laporan, pilih nilai dalam diagram atau daftar untuk memfilter laporan.

> [!NOTE]
> Pilihan rentang waktu dinonaktifkan untuk laporan penggunaan real-time; rentang waktu untuk laporan penggunaan real-time adalah "sekarang".


[!INCLUDE[footer-include](../includes/footer-banner.md)]
