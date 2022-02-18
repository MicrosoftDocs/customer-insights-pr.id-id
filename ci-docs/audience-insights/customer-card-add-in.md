---
title: Add-in Kartu Pelanggan untuk aplikasi Dynamics 365 (berisi video)
description: Tampilkan data wawasan audiens di aplikasi Dynamics 365 dengan add-in ini.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: ce6c8fab84fd4c5dfc9f78b91dde3483a1d358c1
ms.sourcegitcommit: 11308ed275b4b25a35576eccfcae9dda9e2c2784
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/02/2022
ms.locfileid: "8085252"
---
# <a name="customer-card-add-in-preview"></a>Add-in Kartu Pelanggan (pratinjau)



Dapatkan tampilan 360 derajat pelanggan Anda secara langsung di aplikasi Dynamics 365. Dengan Add-in Kartu Pelanggan yang terinstal di aplikasi Dynamics 365 yang didukung, Anda dapat memilih untuk menampilkan bidang profil pelanggan, wawasan, dan timeline aktivitas. Add-in akan mengambil data dari Customer Insights tanpa mempengaruhi data dalam aplikasi Dynamics 365 yang tersambung.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Prasyarat

- Add-in hanya berfungsi dengan aplikasi yang diarahkan model Dynamics 365, seperti Sales, atau Customer Service, versi 9.0 dan versi yang lebih baru.
- Agar data Dynamics 365 Anda dipetakan ke audiens profil pelanggan insight, sebaiknya [data tersebut tertelan dari aplikasi Dynamics 365 menggunakan Microsoft Dataverse konektor](connect-power-query.md). Jika Anda menggunakan metode yang berbeda untuk menelan kontak Dynamics 365 (atau akun), Anda perlu memastikan `contactid` bidang (atau`accountid`) ditetapkan sebagai [kunci utama untuk sumber data tersebut dalam langkah peta proses penyatuan data](map-entities.md#select-primary-key-and-semantic-type-for-attributes). 
- Semua pengguna Add-in Kartu Pelanggan Dynamics 365 harus [ditambahkan sebagai pengguna](permissions.md) dalam wawasan audiens untuk melihat data.
- [Kemampuan pencarian dan filter yang dikonfigurasi](search-filter-index.md) di audiens wawasan diperlukan agar pencarian data dapat bekerja.
- Setiap kontrol add-in mengandalkan data tertentu dalam wawasan audiens. Beberapa data dan kontrol hanya tersedia di lingkungan dengan jenis tertentu. Konfigurasi add-in akan menginformasikan Anda jika kontrol tidak tersedia karena jenis lingkungan yang dipilih. Selengkapnya tentang [kasus penggunaan lingkungan](work-with-business-accounts.md).
  - **Kontrol ukuran**: Memerlukan [ukuran terkonfigurasi](measures.md) jenis atribut pelanggan.
  - **Kontrol kecerdasan**: Memerlukan data yang dihasilkan menggunakan [prediksi atau model](predictions-overview.md) kustom.
  - **Kontrol rincian pelanggan**: Semua bidang dari profil tersedia di profil pelanggan terpadu.
  - **Kontrol pengayaan**: memerlukan [pengayaan](enrichment-hub.md) aktif yang diterapkan ke profil pelanggan. Add-in kartu mendukung pengayaan ini: [Merek](enrichment-microsoft.md) yang disediakan oleh Microsoft, [Minat yang](enrichment-microsoft.md) disediakan oleh Microsoft, dan [data](enrichment-office.md) keterlibatan Office yang disediakan oleh Microsoft.
  - **Kontrol kontak**: Memerlukan definisi entitas semantis dari kontak jenis.
  - **Kontrol Timeline**: memerlukan [aktivitas yang dikonfigurasi](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instal Add-in Kartu Pelanggan

Add-in kartu pelanggan adalah solusi untuk aplikasi Customer Engagement di Dynamics 365. Untuk menginstal solusi, buka AppSource dan Cari **kartu pelanggan Dynamics**. Pilih [Add-in kartu pelanggan di AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) dan pilih **Dapatkan sekarang**.

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

Tergantung pada skenario Anda, Anda dapat memilih untuk menambahkan kontrol ke formulir **Kontak** atau formulir **Akun**. Jika lingkungan audiens Anda adalah untuk akun bisnis, sebaiknya tambahkan kontrol ke formulir Akun. Dalam hal ini, ganti "kontak" pada langkah-langkah di bawah dengan "akun".

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

1. Pastikan Anda mengonfigurasi Add-in Kartu sesuai dengan petunjuk: [Mengonfigurasi Add-in Kartu Pelanggan](#configure-the-customer-card-add-in) 

1. Tinjau konfigurasi konsumsi data. Edit sumber data untuk sistem Dynamics 365 yang berisi ID kontak GUID. Jika ID kontak GUID ditampilkan dengan karakter huruf besar di Power Query editor, coba hal berikut: 
    1. Edit sumber data untuk membuka sumber data di Power Query Editor.
    1. Pilih kolom ID kontak.
    1. Pilih **Ubah** di bilah header untuk melihat tindakan yang tersedia.
    1. Pilih **huruf kecil**. Validasi apakah GUID dalam tabel sekarang huruf kecil.
    1. Simpan Sumber Data.
    1. Jalankan proses konsumsi data, penyatuan, dan hilir untuk menyebarkan perubahan pada GUID. 

Setelah menyelesaikan refresh penuh, kontrol Add-in Kartu Pelanggan harus menampilkan data yang diharapkan. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
