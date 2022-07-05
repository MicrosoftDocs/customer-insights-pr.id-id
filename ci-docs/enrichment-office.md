---
title: Perkaya profil pelanggan dengan data dari Microsoft Office 365 (pratinjau)
description: Gunakan data kepemilikan dari Microsoft Office untuk memperkaya profil pelanggan Anda dengan data keterlibatan.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 75762afb70814c8a81c1574ee7ea1553a2048737
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055678"
---
# <a name="enrich-customer-profiles-with-data-from-microsoft-office-365-preview"></a>Perkaya profil pelanggan dengan data dari Microsoft Office 365 (pratinjau)

Gunakan data dari Microsoft Office 365 untuk memperkaya profil akun pelanggan Anda dengan wawasan tentang keterlibatan melalui Office 365 aplikasi. Data keterlibatan terdiri dari email dan aktivitas rapat, yang dikumpulkan pada tingkat akun. Misalnya, jumlah email dari akun bisnis atau jumlah rapat dengan akun tersebut. Tidak ada data tentang pengguna individu yang tersedia.

## <a name="supported-countries-or-regions"></a>Negara atau kawasan yang didukung

Saat ini kami mendukung wilayah berikut: Inggris, Eropa, Amerika Utara.

## <a name="prerequisites"></a>Prasyarat

- Lisensi cloud aktif Office 365.
- [Profil](customer-profiles.md) pelanggan terpadu berdasarkan [akun bisnis](work-with-business-accounts.md).
- Organisasi yang [Microsoft Dataverse terlampir](create-environment.md#step-3-connect-to-microsoft-dataverse) di lingkungan Customer Insights Anda.
- [Izin](permissions.md#admin) administrator.
- Persetujuan dari administrator penyewa Anda Office 365 untuk menggunakan Office 365 data guna memberikan **Wawasan untuk Organisasi** dalam aplikasi Dynamics 365.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data** saya di petak **peta Keterlibatan** Akun.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Ubin keterlibatan akun.":::

1. Tinjau gambaran umum lalu pilih **Berikutnya**.

1. Masukkan alamat email dari organisasi Anda yang data Office-nya akan dikumpulkan. Hanya data dari alamat email yang tercantum yang akan diproses untuk komunikasi yang relevan. Praktik terbaik adalah menggunakan grup email, misalnya, *tim* Penjualan AS, yang dapat Anda kelola di Office 365. Jumlah alamat email dalam grup diselesaikan dan ditampilkan. Jumlah total alamat email harus minimal 2 dan tidak boleh melebihi 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Alamat email keterlibatan akun.":::

1. Tinjau dan berikan persetujuan Anda untuk [Office 365 persetujuan](#office-365-tenant-administrator-consent) administrator penyewa dengan **memilih Saya setuju**.

1. Pilih **Selanjutnya**.

1. **Pilih himpunan data** Kontak dan pilih profil yang ingin Anda perkaya. Pilih **Selanjutnya**.

1. Petakan bidang alamat email kontak dan pilih **Berikutnya**.

1. Berikan **Nama** untuk pengayaan dan **entitas** Output.

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

1. Pilih **Tutup** untuk kembali ke **halaman Pengayaan**.

### <a name="office-365-tenant-administrator-consent"></a>Office 365 persetujuan administrator penyewa

Persetujuan dari Office 365 administrator penyewa diperlukan untuk mengaktifkan pengayaan. Email dikirim ke Office 365 administrator penyewa saat pengayaan disimpan, yang meminta mereka untuk meninjau dan menyetujui untuk mengizinkan aplikasi Dynamics 365 menggunakan data perusahaan Office 365 Anda untuk memberikan **Wawasan bagi Organisasi**. Administrator Office 365 penyewa juga dapat menyetujui langsung di konsol admin mereka Office 365, dengan **memilih Insights for the Organization**.

## <a name="running-the-enrichment-for-the-first-time"></a>Menjalankan pengayaan untuk pertama kalinya

Ketika pengayaan dimulai untuk pertama kalinya, setelah Office 365 administrator penyewa memberikan persetujuan, unduhan data dimulai Office 365. Proses ini membutuhkan waktu. Pengayaan pertama akan dijadwalkan terjadi dengan penundaan enam jam. Anda dapat melihat jumlah hari yang dicakup data di halaman ringkasan keterlibatan akun setelah pengayaan selesai. Dengan volume data yang besar, jalankan pengayaan lagi setelah beberapa hari. Ini memastikan data lengkap untuk seluruh jendela waktu, yaitu satu tahun.

Bergantung pada ukuran data Office Anda, mungkin diperlukan waktu beberapa jam agar pengayaan berjalan selesai.

Saat Anda menjalankan pengayaan, Microsoft akan memproses data dalam Office 365 batas kepatuhan untuk membuat wawasan agregat, yang kemudian ditambahkan ke lingkungan Customer Insights Anda. Tidak ada data pada tingkat individu (misalnya, isi email atau undangan kalender apa pun) yang tersedia untuk pengguna Customer Insights.

Pilih **Jalankan** untuk memulai proses pengayaan.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Ini adalah *entitas Office*. Office_UserEntity *berisi* ID Direktori Aktif untuk alamat email yang dipilih selama konfigurasi pengayaan.

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Pratinjau hasil setelah menjalankan proses pengayaan.":::

Semua data dikumpulkan hingga tingkat akun. Sistem menghitung skor keterlibatan, yang berkisar antara 0 hingga 100, untuk setiap akun. Skor keterlibatan memberikan ukuran gabungan dari keterlibatan akun di seluruh email dan rapat relatif terhadap akun Anda yang lain. Daftar berikut berisi data agregat yang disediakan pengayaan keterlibatan akun:

| Data                                                                              | Nama kolom                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Skor keterlibatan                                                                  |  Garis Keterlibatan                         |
| Jumlah email ke akun                                                       |  NoOfEmails_ToAccount                    |
| Jumlah email dari akun                                                     |  NoOfEmails_FromAccount                  |
| Jumlah rapat yang dimulai oleh akun                                           |  NoOfMeetings_FromAccount                |
| Jumlah rapat yang dimulai oleh organisasi Anda                                 |  NoOfMeetings_ToAccount                  |
| Jumlah orang dari organisasi Anda dalam rapat dengan akun                  |  NoOfContactsInvolved_Meetings           |
| Jumlah orang dari organisasi Anda dalam percakapan email dengan akun       |  NoOfContactsInvolved_Emails             |
| Jumlah orang dari akun dalam rapat dengan organisasi Anda                  |  NoOfAccountContactsInvolved_Meetings    |
| Jumlah orang dari akun dalam percakapan email dengan organisasi Anda       |  NoOfAccountContactsInvolved_Emails      |
| Tanggal mulai keterlibatan (email pertama atau rapat dalam data)                        |  EngagementStartDate                     |
| Hari sejak email terakhir                                                             |  HariSinceLastEmail                      |
| Hari sejak pertemuan terakhir                                                           |  DaysSinceLastMeeting                    |
| Durasi rata-rata rapat                                                      |  AverageDuration_Of_Meetings             |
| Durasi rata-rata balasan email dari akun                                    |  AverageDuration_Of_AccountEmailReplies  |
| Tanggal mulai agregasi                                                            |  AgregasiStartDate                    |
| Tingkat agregasi (tahun, bulan, atau minggu)                                          |  AgregasiLevel                        |

## <a name="see-enrichment-data-on-the-customer-card"></a>Melihat data pengayaan pada kartu pelanggan

Keterlibatan akun juga dapat dilihat pada kartu pelanggan individu. Buka **pelanggan** dan pilih profil pelanggan. Di kartu pelanggan, Anda akan menemukan skor keterlibatan akun, jumlah total email, dan jumlah total rapat yang dikumpulkan selama setahun terakhir. Anda juga menemukan bagan yang memperlihatkan email dan riwayat rapat.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kartu pelanggan dengan data yang diperkaya.":::

## <a name="next-steps"></a>Langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Misalnya, segmen yang berisi semua pelanggan yang memiliki nilai lebih dari 60 untuk *hari sejak email* terakhir dan *hari sejak rapat* terakhir. Segmen tersebut berisi akun basi yang dapat Anda coba aktifkan kembali.

[!INCLUDE [footer-include](includes/footer-banner.md)]
