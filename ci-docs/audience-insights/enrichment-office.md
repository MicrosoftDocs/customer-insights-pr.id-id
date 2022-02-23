---
title: Memperkaya profil pelanggan dengan data dari Microsoft Office 365
description: Gunakan data kepemilikan Microsoft Office untuk memperkaya profil pelanggan Anda dengan data keterlibatan.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a30e09b5ed491c8d36019b5f0d35e0a2f7a0199c
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/03/2021
ms.locfileid: "7889777"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Memperkaya profil pelanggan dengan data keterlibatan (pratinjau)

Gunakan data Microsoft Office 365 untuk memperkaya profil akun pelanggan Anda dengan wawasan tentang keterlibatan melalui Office 365 aplikasi. Data keterlibatan terdiri dari aktivitas email dan rapat, yang dikumpulkan pada tingkat akun. Misalnya, jumlah email dari akun bisnis atau jumlah pertemuan dengan akun. Tidak ada data tentang pengguna individu yang tersedia. 

Pengayaan ini tersedia di wilayah berikut: Inggris, Eropa, Amerika Utara.

## <a name="prerequisites"></a>Prasyarat

Untuk mengonfigurasi pengayaan, prasyarat berikut harus dipenuhi:

- Anda memiliki Office 365 lisensi cloud aktif.
- Anda memiliki [profil pelanggan terpadu berdasarkan akun](customer-profiles.md)[bisnis](work-with-business-accounts.md).
- Lingkungan Wawasan Pelanggan Anda harus memiliki [Microsoft Dataverse organisasi yang](create-environment.md#step-3-connect-to-microsoft-dataverse) terpasang.
- Anda memiliki [izin](permissions.md#administrator) administrator.
- Anda memiliki, atau bisa mendapatkan, persetujuan dari administrator penyewa Anda Office 365 untuk menggunakan data untuk memberikan Wawasan bagi Organisasi dalam aplikasi Dynamics Office 365 **365**.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Di wawasan audiens, buka **Data** > **pengayaan**.

1. Buka **tab Temukan dan pilih Memperkaya data saya di petak Keterlibatan** **·** **Akun**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Petak keterlibatan akun.":::
   
1. Pilih **Berikutnya dalam langkah Gambaran Umum dan masukkan alamat email dari organisasi Anda yang data Office akan** **dikumpulkan**. Hanya data dari alamat email yang terdaftar yang diproses untuk komunikasi yang relevan. Praktik terbaik adalah menggunakan grup email, misalnya, *tim Penjualan* AS, yang mudah Office 365 dikelola. Jumlah alamat email dalam grup diselesaikan dan ditampilkan. Jumlah total alamat email harus setidaknya 2 dan tidak dapat melebihi 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Alamat email keterlibatan akun.":::

1. Tinjau pernyataan persetujuan, pilih **kotak centang Yang Saya** setujui, dan pilih **Berikutnya**.

1. Pilih himpunan data pelanggan dan pilih **Berikutnya**.

1. Petakan bidang alamat email kontak dan pilih **Berikutnya**.

1. Tinjau konfigurasi pengayaan, berikan nama pengayaan, dan pilih **Simpan pengayaan untuk menyimpan** pengayaan.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 persetujuan administrator penyewa

Persetujuan dari Office 365 administrator penyewa diperlukan untuk mengaktifkan pengayaan. Email dikirim ke Office 365 administrator penyewa saat pengayaan disimpan, yang meminta mereka untuk meninjau dan menyetujui mengizinkan aplikasi Dynamics 365 menggunakan data perusahaan Anda Office 365 untuk memberikan Wawasan bagi **Organisasi**. Office 365 Administrator penyewa juga dapat menyetujui langsung di konsol admin Office 365 mereka, dengan memilih Wawasan untuk **Organisasi**.

## <a name="running-the-enrichment-for-the-first-time"></a>Menjalankan pengayaan untuk pertama kalinya

Ketika pengayaan dimulai untuk pertama kalinya, setelah Office 365 administrator penyewa memberikan persetujuan, pengunduhan data Office 365 dimulai. Proses ini membutuhkan waktu. Pengayaan pertama akan dijadwalkan terjadi dengan penundaan enam jam. Anda dapat melihat jumlah hari yang dicakup data pada halaman gambaran umum keterlibatan akun setelah pengayaan selesai. Dengan volume data yang besar, jalankan pengayaan lagi setelah beberapa hari. Ini memastikan data selesai untuk seluruh jendela waktu, yaitu satu tahun.

Untuk memulai proses, pilih **Jalankan pada halaman konfigurasi keterlibatan** Akun. Selain itu, Anda dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran](system.md#schedule-tab) terjadwal. Secara default, pengayaan berjalan sekali per minggu.

Tergantung pada ukuran data Office Anda, mungkin diperlukan beberapa jam untuk pengayaan berjalan untuk menyelesaikan.

Saat Anda menjalankan pengayaan, Microsoft akan memproses data dalam Office 365 batas kepatuhan untuk membuat wawasan agregat, yang kemudian ditambahkan ke lingkungan Wawasan Pelanggan Anda. Tidak ada data pada tingkat individu (misalnya, isi dari setiap e-mail atau kalender undangan) menjadi tersedia untuk pengguna Customer Insights. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Hasil pengayaan

Setelah menjalankan proses pengayaan, pergilah ke **pengayaan Saya untuk meninjau hasil** pengayaan. Anda akan menemukan jumlah total pelanggan yang diperkaya dan gambaran umum hasil pengayaan. Ini termasuk jumlah email dan rapat yang diproses, jumlah hari di mana data telah dikumpulkan, dan banyak lagi.

Anda juga akan menemukan bagan dengan jumlah pelanggan yang diperkaya dari waktu ke waktu dan pratinjau data pengayaan.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Pratinjau hasil setelah menjalankan proses pengayaan.":::

Semua data dikumpulkan hingga tingkat akun. Sistem menghitung skor keterlibatan, yang berkisar antara 0 hingga 100, untuk setiap akun. Skor keterlibatan memberikan ukuran gabungan dari keterlibatan akun di seluruh email dan rapat relatif terhadap akun Anda yang lain. Daftar berikut berisi data agregat yang disediakan oleh pengayaan keterlibatan akun:



| Data                                                                              | Nama kolom                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Skor keterlibatan                                                                  |  EngagementScore                         |
| Jumlah email ke akun                                                       |  NoOfEmails_ToAccount                    |
| Jumlah email dari akun                                                     |  NoOfEmails_FromAccount                  | 
| Jumlah pertemuan yang diprakarsai oleh akun                                           |  NoOfMeetings_FromAccount                | 
| Jumlah pertemuan yang diprakarsai oleh organisasi Anda                                 |  NoOfMeetings_ToAccount                  | 
| Jumlah orang dari organisasi Anda dalam rapat dengan akun                  |  NoOfContactsInvolved_Meetings           | 
| Jumlah orang dari organisasi Anda dalam percakapan email dengan akun       |  NoOfContactsInvolved_Emails             | 
| Jumlah orang dari akun dalam rapat dengan organisasi Anda                  |  NoOfAccountContactsInvolved_Meetings    | 
| Jumlah orang dari akun dalam percakapan email dengan organisasi Anda       |  NoOfAccountContactsInvolved_Emails      | 
| Tanggal mulai keterlibatan (email atau rapat pertama dalam data)                        |  EngagementStartdate                     | 
| Beberapa hari sejak email terakhir                                                             |  DaysSinceLastemail                      | 
| Beberapa hari sejak pertemuan terakhir                                                           |  DaysSinceLastMeeting                    | 
| Durasi rata-rata rapat                                                      |  AverageDuration_Of_Meetings             | 
| Durasi rata-rata balasan email dari akun                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Tanggal mulai agregasi                                                            |  AgregasiStartdate                    | 
| Tingkat agregasi (tahun, bulan, atau minggu)                                          |  AgregasiLevel                        | 


Tinjau data yang diperkaya dengan memilih **Lihat** selengkapnya di bagian pratinjau. Ini membuka *entitas* Office. Anda juga dapat menemukan entitas yang tercantum dalam **grup Pengayaan dalam Entitas** **·** > **Data**. Anda juga akan menemukan *Office_UserEntity*, yang berisi CD Active Directory untuk alamat email yang dipilih selama konfigurasi pengayaan. 

## <a name="see-enrichment-data-on-the-customer-card"></a>Melihat data pengayaan pada kartu pelanggan

Keterlibatan akun juga dapat dilihat pada masing-masing kartu pelanggan. Buka **pelanggan** dan pilih profil pelanggan. Dalam kartu pelanggan, Anda akan menemukan skor keterlibatan akun, jumlah total email, dan jumlah total pertemuan yang dikumpulkan selama setahun terakhir. Anda juga menemukan bagan yang menampilkan riwayat email dan rapat.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kartu pelanggan dengan data yang diperkaya.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Membuat segmen dan ukuran berdasarkan data yang diperkaya

Data yang diperkaya dapat digunakan untuk membuat segmen dan langkah-langkah seperti yang dijelaskan di bawah ini. Misalnya, segmen yang berisi semua pelanggan yang memiliki nilai lebih dari 60 selama *berhari-hari sejak email dan hari terakhir* *sejak pertemuan* terakhir. Segmen itu berisi akun basi yang dapat Anda coba aktifkan kembali. 

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
