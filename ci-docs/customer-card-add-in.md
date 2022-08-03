---
title: Add-in Kartu Pelanggan untuk aplikasi Dynamics 365 (pratinjau) (berisi video)
description: Tampilkan data profil pelanggan dari Customer Insights di aplikasi Dynamics 365 dengan add-in ini.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8b3b6a0d54b80d7df454e9dc925f14cc3c39684c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194927"
---
# <a name="customer-card-add-in-for-dynamics-365-apps-preview"></a>Add-in Kartu Pelanggan untuk aplikasi Dynamics 365 (pratinjau)

Dapatkan tampilan 360 derajat pelanggan Anda secara langsung di aplikasi Dynamics 365. Dengan Add-in Kartu Pelanggan yang terinstal di aplikasi Dynamics 365 yang didukung, Anda dapat memilih untuk menampilkan bidang profil pelanggan, wawasan, dan timeline aktivitas. Add-in akan mengambil data dari Customer Insights tanpa mempengaruhi data dalam aplikasi Dynamics 365 yang tersambung.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Prasyarat

- Aplikasi berbasis model Dynamics 365, seperti Sales atau layanan pelanggan, versi 9.0, dan yang lebih baru.
- Agar data Dynamics 365 Anda dapat [dipetakan ke profil pelanggan Customer Insights, kami sarankan data tersebut diserap dari aplikasi Dynamics 365 menggunakan Microsoft Dataverse konektor](connect-power-query.md). Jika Anda menggunakan metode yang berbeda untuk menyerap kontak (atau akun) Dynamics 365, pastikan `contactid` bidang (atau `accountid`) ditetapkan sebagai [kunci utama untuk sumber data tersebut selama proses penyatuan data](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Semua pengguna Dynamics 365 dari Customer Card Add-in harus [ditambahkan sebagai pengguna](permissions.md) di Customer Insights untuk melihat data.
- [Kemampuan pencarian dan filter yang dikonfigurasi](search-filter-index.md) di Customer Insights.
- Setiap kontrol add-in bergantung pada data tertentu di Customer Insights. Beberapa data dan kontrol hanya tersedia di lingkungan dengan jenis tertentu. Konfigurasi add-in akan memberi tahu Anda jika kontrol tidak tersedia karena jenis lingkungan yang dipilih. Selengkapnya tentang [kasus penggunaan lingkungan](work-with-business-accounts.md).
  - **Kontrol pengukuran** memerlukan pengukuran [atribut pelanggan yang](measures.md) dikonfigurasi.
  - **Kontrol kecerdasan** memerlukan data yang dihasilkan menggunakan [prediksi atau model](predictions-overview.md) kustom.
  - **Kontrol** detail pelanggan menunjukkan semua bidang dari profil yang tersedia di profil pelanggan terpadu.
  - **Kontrol** pengayaan membutuhkan pengayaan aktif [yang](enrichment-hub.md) diterapkan pada profil pelanggan. Add-in kartu mendukung pengayaan ini: [Merek](enrichment-microsoft.md) yang disediakan oleh Microsoft, [Minat](enrichment-microsoft.md) yang disediakan oleh Microsoft, dan [data](enrichment-office.md) keterlibatan Office yang disediakan oleh Microsoft.
  - **Kontrol kontak** memerlukan jenis entitas semantik kontak.
  - **Kontrol** linimasa memerlukan aktivitas [yang](activities.md) dikonfigurasi.

## <a name="install-the-customer-card-add-in"></a>Instal Add-in Kartu Pelanggan

Add-in kartu pelanggan adalah solusi untuk aplikasi Customer Engagement di Dynamics 365. Untuk menginstal solusi:

1. AppSource Buka dan cari **Dynamics Customer Card**.

1. Pilih [Add-in kartu pelanggan di AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) dan pilih **Dapatkan sekarang**.

Anda mungkin harus masuk dengan kredensial admin Anda agar aplikasi Dynamics 365 menginstal solusi. Bisa diperlukan beberapa waktu agar solusi dapat diinstal ke lingkungan Anda.

## <a name="configure-the-customer-card-add-in"></a>Mengkonfigurasi Add-in kartu pelanggan

1. Sebagai admin, buka bagian **pengaturan** dalam Dynamics 365, lalu pilih **solusi**.

1. Pilih tautan **nama tampilan** untuk solusi **Add-in Kartu Pelanggan Dynamics 365 Customer Insights (Pratinjau)**.

   > [!div class="mx-imgBorder"]
   > ![pilih Nama tampilan.](media/select-display-name.png "pilih Nama tampilan.")

1. Pilih **Masuk** dan masukkan kredensial untuk akun admin yang Anda gunakan untuk mengkonfigurasi Customer Insights.

   > [!NOTE]
   > Periksa apakah Pemblokir pop-up browser tidak memblokir jendela autentikasi saat Anda memilih tombol **Masuk**.

1. pilih lingkungan Customer Insights yang ingin Anda ambil datanya.

1. Tentukan pemetaan bidang untuk rekaman di aplikasi Dynamics 365. Tergantung pada data dalam Customer Insights, Anda dapat memilih untuk memetakan pilihan berikut:
   - Untuk memetakan dengan kontak, pilih bidang di entitas Pelanggan yang sesuai dengan ID entitas kontak Anda.
   - Untuk memetakan dengan akun, pilih bidang di entitas Pelanggan yang sesuai dengan ID entitas akun Anda.

   > [!div class="mx-imgBorder"]
   > ![Bidang id kontak.](media/contact-id-field.png "Bidang id kontak.")

1. Pilih **Simpan konfigurasi** untuk menyimpan pengaturan.

1. Selanjutnya, Anda harus menetapkan peran keamanan di Dynamics 365 agar pengguna dapat menyesuaikan dan melihat kartu pelanggan. Di Dynamics 365, pergi ke **pengaturan** > **keamanan** > **pengguna**. Pilih pengguna untuk mengedit peran pengguna dan pilih **Kelola peran**.

1. Tetapkan **peran Penyesuai kartu Customer Insights** kepada pengguna yang akan menyesuaikan konten untuk ditampilkan pada kartu untuk seluruh organisasi.

## <a name="add-customer-card-controls-to-forms"></a>Tambahkan kontrol Kartu Pelanggan ke formulir

Tergantung pada skenario Anda, Anda dapat memilih untuk menambahkan kontrol ke formulir **Kontak** atau formulir **Akun**. Jika lingkungan Customer Insights Anda adalah untuk akun bisnis, sebaiknya tambahkan kontrol ke formulir Akun. Dalam hal ini, ganti "kontak" pada langkah-langkah di bawah dengan "akun".

1. Untuk menambahkan kontrol kartu pelanggan ke formulir kontak, buka **pengaturan** > **penyesuaian** di Dynamics 365.

1. Pilih **Sesuaikan sistem**.

1. Telusuri entitas **kontak**, perluas lalu pilih **formulir**.

1. Pilih formulir kontak yang ingin ditambahkan kontrol kartu pelanggan.

    > [!div class="mx-imgBorder"]
    > ![Pilih formulir kontak.](media/contact-active-forms.png "Pilih formulir kontak.")

1. Untuk menambahkan kontrol, di editor formulir, tarik bidang apa pun dari **penjelajah bidang** ke tempat Anda ingin kontrol ditampilkan.

1. Pilih bidang di formulir yang baru saja ditambahkan, lalu pilih **Ubah properti**.

1. Buka tab **Kontrol** dan pilih **Tambahkan kontrol**. Pilih salah satu kontrol kustom yang tersedia dan pilih **Tambah**.

1. Di dialog **properti bidang**, kosongkan kotak centang **label tampilan di formulir**.

1. Pilih opsi **web** untuk kontrol. Untuk kontrol pengayaan, pilih jenis pengayaan yang akan ditampilkan dengan mengonfigurasi bidang **enrichmenttype**. Tambahkan kontrol pengayaan terpisah untuk setiap jenis pengayaan.

1. Pilih **Simpan** dan **publikasikan** untuk mempublikasikan formulir kontak yang diperbarui.

1. Buka formulir kontak yang dipublikasikan. Anda akan melihat kontrol yang baru ditambahkan. Anda mungkin harus masuk saat pertama kali menggunakannya.

1. Untuk menyesuaikan yang ingin Anda Tampilkan pada kontrol kustom, pilih tombol Edit di sudut kanan atas.

## <a name="upgrade-customer-card-add-in"></a>Tingkatkan Add-in Kartu Pelanggan

Add-in Kartu Pelanggan tidak ditingkatkan secara otomatis. Untuk meningkatkan ke versi terbaru, ikuti langkah-langkah berikut di aplikasi Dynamics 365 yang telah terinstal add-in.

1. Dalam aplikasi Dynamics 365, buka **Pengaturan** > **Penyesuaian** dan pilih **Solusi**.

1. Pada tabel add-in, cari **CustomerInsightsCustomerCard** dan pilih baris.

1. Pilih **Terapkan Peningkatan Solusi** pada bilah tindakan.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Tingkatkan solusi di area Penyesuaian aplikasi Dynamics 365.":::

1. Setelah memulai proses peningkatan, Anda akan melihat indikator pemuatan hingga peningkatan selesai. Jika tidak ada versi yang lebih baru, peningkatan akan menampilkan pesan kesalahan.

## <a name="troubleshooting"></a>Mengatasi Masalah

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Kontrol dari Add-in Kartu Pelanggan tidak menemukan data

**Masalah:**

Bahkan dengan bidang ID yang dikonfigurasi dengan benar, kontrol tidak dapat menemukan data untuk pelanggan mana pun.  

**Resolusi:**

1. Pastikan Anda mengonfigurasi Add-in Kartu sesuai dengan instruksi: [Mengonfigurasi Add-in Kartu Pelanggan](#configure-the-customer-card-add-in)

1. Tinjau konfigurasi penyerapan data. Edit sumber data untuk sistem Dynamics 365 yang berisi GUID ID kontak. Jika GUID ID kontak diperlihatkan dengan karakter huruf besar di Power Query editor, coba langkah-langkah berikut:
    1. Edit sumber data untuk membuka sumber data di Power Query Editor.
    1. Pilih kolom ID kontak.
    1. Pilih **Transformasi** di bilah header untuk melihat tindakan yang tersedia.
    1. Pilih **huruf kecil**. Validasi apakah GUID dalam tabel sekarang huruf kecil.
    1. Simpan Sumber Data.
    1. Jalankan penyerapan data, penyatuan, dan proses hilir untuk menyebarkan perubahan ke GUID.

Setelah sistem menyelesaikan penyegaran penuh, kontrol Add-in Kartu Pelanggan akan menampilkan data yang diharapkan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
