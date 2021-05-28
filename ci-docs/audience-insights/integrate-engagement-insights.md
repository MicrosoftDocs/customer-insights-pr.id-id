---
title: Mengintegrasikan data web dari wawasan keterlibatan dengan wawasan audiens
description: Bawa informasi web tentang pelanggan dari wawasan keterlibatan ke wawasan audiens.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a4cb77bb4c6ef0d88b3f00802f66baab5520a07
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896423"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Mengintegrasikan data web dari wawasan keterlibatan dengan wawasan audiens

Pelanggan sering melakukan transaksi sehari-hari secara online menggunakan situs web. Kemampuan wawasan keterlibatan di Dynamics 365 Customer Insights adalah solusi bermanfaat untuk mengintegrasikan data web sebagai sumber. Selain data transaksional, historis, atau data perilaku, kita dapat melihat aktivitas di web dalam profil pelanggan terpadu. Kita dapat menggunakan profil ini untuk mendapatkan wawasan tambahan seperti segmen, pengukuran, atau prediksi untuk aktivasi audiens.

Artikel ini menjelaskan ukuran untuk membawa data aktivitas web pelanggan dari wawasan keterlibatan ke lingkungan wawasan audiens yang ada.

Di contoh ini, kami mengasumsikan lingkungan yang berisi profil pelanggan terpadu. Profilnya disatukan dengan sumber dari survei, penjualan ritel, dan sistem tiket. Ini juga menunjukkan aktivitas terkait pelanggan. 

Kita sekarang ingin mengetahui apakah pelanggan mengunjungi properti web Kita dan memahami aktivitas mereka. Aktivitas mencakup, misalnya, situs web yang dikunjungi atau halaman produk yang dilihat dari tautan yang diterima dalam email.

## <a name="prerequisites"></a>Prasyarat

Untuk mengintegrasikan data dari wawasan keterlibatan, beberapa prasyarat harus dipenuhi: 

- Mengintegrasikan SDK wawasan keterlibatan dengan situs web Anda. Untuk informasi lebih lanjut, lihat [Memulai SDK web](../engagement-insights/instrument-website.md).
- Mengekspor aktivitas web dari wawasan keterlibatan memerlukan akses ke akun penyimpanan ADLS Gen 2 yang akan digunakan untuk menyerap data aktivitas web ke wawasan audiens. Untuk informasi lebih lanjut, lihat [Ekspor aktivitas](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Mengkonfigurasi aktivitas yang disempurnakan dalam wawasan keterlibatan

Setelah administrator menginstrumentasikan situs web dengan SDK wawasan keterlibatan, *aktivitas dasar* akan dikumpulkan bila pengguna melihat halaman web atau mengeklik di suatu tempat. Aktivitas dasar biasanya berisi banyak rincian. Tergantung pada kasus penggunaan, Anda hanya memerlukan subset data di aktivitas dasar. Wawasan keterlibatan memungkinkan Anda membuat *aktivitas yang disempurnakan* yang hanya berisi properti aktivitas dasar yang Anda pilih.     

Untuk informasi lebih lanjut, lihat [Membuat dan memodifikasi aktivitas yang disempurnakan](../engagement-insights/refined-events.md).

Pertimbangan saat membuat aktivitas yang disempurnakan: 

- Berikan nama yang memiliki arti untuk aktivitas yang disempurnakan. Itu akan digunakan sebagai nama aktivitas dalam wawasan audiens.
- Pilih sekurangnya properti berikut untuk membuat aktivitas di wawasan audiens: 
    - Signal.Action.Name - yang menunjukkan rincian aktivitas
    - Signal.User.Id - digunakan untuk memetakan dengan ID pelanggan
    - Signal.View.Uri - digunakan sebagai alamat web sebagai dasar untuk segmen atau ukuran
    - Signal.Export.Id - untuk digunakan sebagai kunci utama untuk aktivitas
    - Signal.Timestamp - untuk menentukan tanggal dan waktu aktivitas

Pilih filter untuk fokus pada aktivitas dan halaman yang penting untuk kasus penggunaan Anda. Di contoh ini, kami akan menggunakan nama tindakan "Promosi email".

## <a name="export-the-refined-web-events"></a>Mengekspor Aktivitas Web yang Disempurnakan 

Setelah aktivitas yang disempurnakan ditentukan, Anda harus mengkonfigurasi ekspor data aktivitas ke Azure Data Lake Storage, yang dapat ditetapkan sebagai sumber data untuk penyerapan dalam wawasan audiens. Ekspor terjadi secara terus-menerus sebagai alur aktivitas dari properti web.

Untuk informasi lebih lanjut, lihat [Ekspor aktivitas](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Serap aktivitas ke wawasan audiens

Setelah Anda menentukan aktivitas yang disempurnakan dan mengonfigurasi ekspor, kita akan beralih ke penyerapan data ke wawasan audiens. Anda harus membuat folder sumber data berdasarkan folder Common Data Model. Masukkan rincian untuk akun penyimpanan yang akan diekspor aktivitasnya. Di file *default.cdm.json*, pilih aktivitas disempurnakan untuk diserap dan buat entitas dalam wawasan audiens.

Untuk informasi lebih lanjut, lihat [Menyambung ke folder Common Data Model menggunakan akun Azure Data Lake](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Kaitkan data aktivitas yang disempurnakan sebagai aktivitas profil pelanggan

Setelah menyelesaikan proses pengaturan entitas, Anda dapat mengkonfigurasi aktivitas untuk profil pelanggan.

Untuk informasi lebih lanjut, lihat [Aktivitas pelanggan](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Halaman aktivitas dengan panel Edit aktivitas yang diperluas dan diisi dalam bidang.":::

Konfigurasikan aktivitas baru dengan pemetaan berikut: 

- **Kunci Utama:** Signal.Export.Id, ID unik yang tersedia untuk setiap rekaman aktivitas dalam wawasan keterlibatan. Properti ini akan secara otomatis dibuat.

- **Timestamp:** Signal.Timestamp di properti aktivitas.

- **Aktivitas:** Signal.Name, nama aktivitas yang akan dilacak.

- **Alamat web:** Signal.View.Uri mengacu pada url halaman yang membuat aktivitas.

- **Rincian:** Signal.Action.Name untuk menunjukkan informasi yang akan dikaitkan dengan aktivitas. Properti yang dipilih dalam kasus ini menunjukkan bahwa aktivitas adalah untuk promosi email.

- **Jenis aktivitas:** Dalam contoh ini, kami memilih jenis aktivitas yang ada, WebLog. Pilihan ini merupakan pilihan filter yang berguna untuk menjalankan prediksi model atau membuat segmen berdasarkan jenis aktivitas ini.

- **Mengkonfigurasi relasi:** Pengaturan penting ini mengatur hubungan aktivitas dengan profil pelanggan yang ada. **Signal.User.Id** adalah pengidentifikasi yang dikonfigurasi dalam SDK untuk dikumpulkan dan yang terkait dengan ID pengguna di sumber data lain yang dikonfigurasi dalam wawasan audiens. Di contoh ini, kami mengkonfigurasi relasi antara Signal.User.Id dan RetailCustomers:CustomerRetailId, yang merupakan kunci utama yang ditentukan dalam langkah pemetaan dari proses penyatuan data.


Setelah memproses aktivitas, Anda dapat meninjau rekaman pelanggan dan membuka kartu pelanggan untuk melihat aktivitas dari wawasan keterlibatan di timeline. 

> [!TIP]
> Untuk menemukan id pelanggan yang memiliki aktivitas wawasan keterlibatan, buka **Entitas** dan pratinjau data untuk entitas UnifiedActivity. ActivityTypeDisplay = WebLog berisi aktivitas wawasan keterlibatan yang dikonfigurasi dalam contoh di atas. Salin ID pelanggan untuk salah satu rekaman dan untuk ID tersebut pada halaman **Pelanggan**.

## <a name="next-steps"></a>Langkah-Langkah Berikutnya

Anda sekarang dapat membuat [segmen](segments.md), [ukuran](measures.md), dan [prediksi](predictions.md) untuk membuat sambungan yang berarti dengan pelanggan Anda.


[!INCLUDE[footer-include](../includes/footer-banner.md)]