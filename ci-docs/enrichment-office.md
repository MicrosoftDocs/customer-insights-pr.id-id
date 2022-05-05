---
title: Memperkaya profil pelanggan dengan data dari Microsoft Office 365
description: Gunakan data kepemilikan untuk Microsoft Office memperkaya profil pelanggan Anda dengan data keterlibatan.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 782042ff643bd0cc70ac53e5680bfd0c68944d84
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642719"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Memperkaya profil pelanggan dengan data keterlibatan (pratinjau)

Gunakan data dari Microsoft Office 365 untuk memperkaya profil akun pelanggan Anda dengan wawasan tentang keterlibatan melalui Office 365 aplikasi. Data keterlibatan terdiri dari aktivitas email dan rapat, yang dikumpulkan pada tingkat akun. Misalnya, jumlah email dari akun bisnis atau jumlah rapat dengan akun tersebut. Tidak ada data tentang pengguna individu yang tersedia. 

Pengayaan ini tersedia di wilayah berikut: Inggris, Eropa, Amerika Utara.

## <a name="prerequisites"></a>Prasyarat

Untuk mengonfigurasi pengayaan, prasyarat berikut harus dipenuhi:

- Anda memiliki lisensi cloud aktif Office 365.
- Anda memiliki [profil](customer-profiles.md) pelanggan terpadu berdasarkan [akun bisnis](work-with-business-accounts.md).
- Lingkungan Wawasan Pelanggan Anda harus memiliki organisasi yang [Microsoft Dataverse dilampirkan](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Anda memiliki [izin administrator](permissions.md#admin).
- Anda memiliki, atau bisa mendapatkan, persetujuan dari administrator penyewa untuk Office 365 menggunakan Office 365 data untuk memberikan **Wawasan bagi Organisasi** dalam aplikasi Dynamics 365.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka **Data** > **Pengayaan**.

1. Buka tab **Temukan** dan pilih **Memperkaya data** saya di **petak Keterlibatan** Akun.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Petak keterlibatan akun.":::
   
1. Pilih **Berikutnya** di **langkah Gambaran Umum** dan masukkan alamat email dari organisasi Anda yang data Office-nya akan dikumpulkan. Hanya data dari alamat email yang terdaftar yang diproses untuk komunikasi yang relevan. Praktik terbaik adalah menggunakan grup email, misalnya, *tim* Penjualan AS, yang mudah dikelola di Office 365. Jumlah alamat email dalam grup diselesaikan dan ditampilkan. Jumlah total alamat email harus minimal 2 dan tidak boleh melebihi 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Alamat email keterlibatan akun.":::

1. Tinjau pernyataan persetujuan, pilih **kotak centang Saya setuju**, dan pilih **Berikutnya**.

1. Pilih himpunan data pelanggan dan pilih **Berikutnya**.

1. Petakan bidang alamat email kontak dan pilih **Berikutnya**.

1. Tinjau konfigurasi pengayaan, beri nama pengayaan, dan pilih **Simpan pengayaan** untuk menyimpan pengayaan.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 persetujuan administrator penyewa

Persetujuan dari Office 365 administrator penyewa diperlukan untuk mengaktifkan pengayaan. Email dikirim ke Office 365 administrator penyewa saat pengayaan disimpan, yang meminta mereka untuk meninjau dan menyetujui untuk mengizinkan aplikasi Dynamics 365 menggunakan data perusahaan Office 365 Anda untuk memberikan **Wawasan bagi Organisasi**. Administrator Office 365 penyewa juga dapat menyetujui secara langsung di konsol admin mereka Office 365, dengan **memilih Wawasan untuk Organisasi**.

## <a name="running-the-enrichment-for-the-first-time"></a>Menjalankan pengayaan untuk pertama kalinya

Ketika pengayaan dimulai untuk pertama kalinya, setelah Office 365 administrator penyewa memberikan persetujuan, unduhan data dimulai Office 365. Proses ini membutuhkan waktu. Pengayaan pertama akan dijadwalkan berlangsung dengan penundaan enam jam. Anda dapat melihat jumlah hari yang dicakup data pada halaman ringkasan keterlibatan akun setelah pengayaan selesai. Dengan volume data yang besar, jalankan pengayaan lagi setelah beberapa hari. Itu memastikan data lengkap untuk seluruh jendela waktu, yaitu satu tahun.

Untuk memulai proses, pilih **Jalankan** di halaman Konfigurasi keterlibatan akun. Selain itu, Anda dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari refresh [terjadwal](system.md#schedule-tab). Secara default, pengayaan berjalan seminggu sekali.

Bergantung pada ukuran data Office Anda, mungkin diperlukan beberapa jam agar pengayaan selesai.

Saat Anda menjalankan pengayaan, Microsoft akan memproses data dalam Office 365 batas kepatuhan untuk membuat wawasan agregat, yang kemudian ditambahkan ke lingkungan Wawasan Pelanggan Anda. Tidak ada data pada tingkat individu (misalnya, isi email atau undangan kalender apa pun) yang tersedia untuk pengguna Wawasan Pelanggan. 

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Hasil pengayaan

Setelah menjalankan proses pengayaan, buka **Pengayaan saya** untuk meninjau hasil pengayaan. Anda akan menemukan jumlah total pelanggan yang diperkaya dan ikhtisar hasil pengayaan. Ini termasuk jumlah email dan rapat yang diproses, jumlah hari di mana data telah dikumpulkan, dan banyak lagi.

Anda juga akan menemukan bagan dengan jumlah pelanggan yang diperkaya dari waktu ke waktu dan pratinjau data pengayaan.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Pratinjau hasil setelah menjalankan proses pengayaan.":::

Semua data dikumpulkan hingga ke tingkat akun. Sistem ini menghitung skor keterlibatan, yang berkisar dari 0 hingga 100, untuk setiap akun. Skor keterlibatan memberikan ukuran gabungan dari keterlibatan akun di seluruh email dan rapat relatif terhadap akun Anda yang lain. Daftar berikut berisi data agregat yang disediakan pengayaan keterlibatan akun:



| Data                                                                              | Nama kolom                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Skor keterlibatan                                                                  |  EngagementScore                         |
| Jumlah email ke akun                                                       |  NoOfEmails_ToAccount                    |
| Jumlah email dari akun                                                     |  NoOfEmails_FromAccount                  | 
| Jumlah rapat yang dimulai oleh akun                                           |  NoOfMeetings_FromAccount                | 
| Jumlah rapat yang diinisiasi oleh organisasi Anda                                 |  NoOfMeetings_ToAccount                  | 
| Jumlah orang dari organisasi Anda dalam rapat dengan akun                  |  NoOfContactsInvolved_Meetings           | 
| Jumlah orang dari organisasi Anda dalam percakapan email dengan akun       |  NoOfContactsInvolved_Emails             | 
| Jumlah orang dari akun dalam rapat dengan organisasi Anda                  |  NoOfAccountContactsInvolved_Meetings    | 
| Jumlah orang dari akun dalam percakapan email dengan organisasi Anda       |  NoOfAccountContactsInvolved_Emails      | 
| Tanggal mulai keterlibatan (email atau rapat pertama dalam data)                        |  EngagementStartDate                     | 
| Beberapa hari sejak email terakhir                                                             |  DaysSinceLastemail                      | 
| Beberapa hari sejak pertemuan terakhir                                                           |  DaysSinceLastMeeting                    | 
| Durasi rata-rata rapat                                                      |  AverageDuration_Of_Meetings             | 
| Durasi rata-rata balasan email dari akun                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Tanggal mulai agregasi                                                            |  AggregationStartDate                    | 
| Tingkat agregasi (tahun, bulan, atau minggu)                                          |  Tingkat Agregasi                        | 


Tinjau data yang diperkaya dengan **memilih Lihat selengkapnya** di bagian pratinjau. Ini membuka *entitas Office*. Anda juga dapat menemukan entitas yang tercantum dalam **grup Pengayaan** di **DataEntities** > **·**. Anda juga akan menemukan *Office_UserEntity*, yang berisi ID Direktori Aktif untuk alamat email yang dipilih selama konfigurasi pengayaan 

## <a name="see-enrichment-data-on-the-customer-card"></a>Melihat data pengayaan pada kartu pelanggan

Keterlibatan akun juga dapat dilihat pada masing-masing kartu pelanggan. Buka **pelanggan** dan pilih profil pelanggan. Di kartu pelanggan, Anda akan menemukan skor keterlibatan akun, jumlah total email, dan jumlah total rapat yang dikumpulkan selama setahun terakhir. Anda juga menemukan bagan yang menampilkan email dan riwayat rapat.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kartu pelanggan dengan data yang diperkaya.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Membuat segmen dan ukuran berdasarkan data yang diperkaya

Data yang diperkaya dapat digunakan untuk membuat segmen dan ukuran seperti yang dijelaskan di bawah ini. Misalnya, segmen yang berisi semua pelanggan yang memiliki nilai lebih dari 60 selama berhari-hari *sejak email* dan *hari terakhir sejak rapat* terakhir. Segmen itu berisi akun basi yang dapat Anda coba aktifkan kembali. 

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
