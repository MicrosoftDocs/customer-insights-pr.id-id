---
title: Add-in Kartu Pelanggan untuk aplikasi Dynamics 365
description: Tampilkan data wawasan audiens di aplikasi Dynamics 365 dengan add-in ini.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059592"
---
# <a name="customer-card-add-in-preview"></a>Add-in Kartu Pelanggan (pratinjau)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dapatkan tampilan 360 derajat pelanggan Anda secara langsung di aplikasi Dynamics 365. Dengan Add-in Kartu Pelanggan yang terinstal di aplikasi Dynamics 365 yang didukung, Anda dapat memilih untuk menampilkan demografi, wawasan, dan timeline aktivitas. Add-in akan mengambil data dari Customer Insights tanpa mempengaruhi data dalam aplikasi Dynamics 365 yang tersambung. 

## <a name="prerequisites"></a>Prasyarat

- Add-in hanya berfungsi dengan aplikasi yang diarahkan model Dynamics 365, seperti Sales, atau Customer Service, versi 9.0 dan versi yang lebih baru.
- Agar data Dynamics 365 Anda dapat memetakan ke profil pelanggan wawasan audiens, mereka perlu [diserap dari aplikasi Dynamics 365 menggunakan konektor Common Data Service](connect-power-query.md).
- Semua pengguna Add-in Kartu Pelanggan Dynamics 365 harus [ditambahkan sebagai pengguna](permissions.md) dalam wawasan audiens untuk melihat data.
- [Kemampuan pencarian dan filter yang dikonfigurasi](search-filter-index.md) di audiens wawasan diperlukan agar pencarian data dapat bekerja.
- Setiap kontrol add-in mengandalkan data tertentu dalam wawasan audiens:
  - Kontrol pengukuran: memerlukan [tindakan yang dikonfigurasi](measures.md).
  - Kontrol inteligensi: Memerlukan data yang dihasilkan menggunakan [prediksi](predictions.md) atau [model kustom](custom-models.md).
  - Kontrol demografis: bidang demografis, (seperti usia atau jenis kelamin) tersedia di profil pelanggan terpadu.
  - Kontrol pengayaan: memerlukan [pengayaan](enrichment-hub.md) aktif yang diterapkan ke profil pelanggan.
  - Kontrol Timeline: memerlukan [aktivitas yang dikonfigurasi](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instal Add-in Kartu Pelanggan

Add-in kartu pelanggan adalah solusi untuk aplikasi Customer Engagement di Dynamics 365. Untuk menginstal solusi, buka AppSource dan Cari **kartu pelanggan Dynamics**. Pilih [Add-in kartu pelanggan di AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) dan pilih **Dapatkan sekarang**.

Anda mungkin harus masuk dengan kredensial admin Anda agar aplikasi Dynamics 365 menginstal solusi.

Bisa diperlukan beberapa waktu agar solusi dapat diinstal ke lingkungan Anda.

## <a name="configure-the-customer-card-add-in"></a>Mengkonfigurasi Add-in kartu pelanggan

1. Sebagai admin, buka bagian **pengaturan** dalam Dynamics 365, lalu pilih **solusi**.

1. Pilih tautan **nama tampilan** untuk solusi **Add-in Kartu Pelanggan Dynamics 365 Customer Insights (Pratinjau)**.

   > [!div class="mx-imgBorder"]
   > ![pilih Nama tampilan](media/select-display-name.png "pilih Nama tampilan")

1. Pilih **Masuk** dan masukkan kredensial untuk akun admin yang Anda gunakan untuk mengkonfigurasi Customer Insights.

   > [!NOTE]
   > Periksa apakah Pemblokir pop-up browser tidak memblokir jendela autentikasi saat Anda memilih tombol **Masuk**.

1. pilih lingkungan Customer Insights yang ingin Anda ambil datanya.

1. Tentukan pemetaan bidang untuk rekaman di aplikasi Dynamics 365. Tergantung pada data dalam Customer Insights, Anda dapat memilih untuk memetakan pilihan berikut:
   - Untuk memetakan dengan kontak, pilih bidang di entitas Pelanggan yang sesuai dengan ID entitas kontak Anda.
   - Untuk memetakan dengan akun, pilih bidang di entitas Pelanggan yang sesuai dengan ID entitas akun Anda.

   > [!div class="mx-imgBorder"]
   > ![Bidang id kontak](media/contact-id-field.png "Bidang id kontak")

1. Pilih **Simpan konfigurasi** untuk menyimpan pengaturan.

1. Selanjutnya, Anda harus menetapkan peran keamanan di Dynamics 365 agar pengguna dapat menyesuaikan dan melihat kartu pelanggan. Di Dynamics 365, pergi ke **pengaturan** > **keamanan** > **pengguna**. Pilih pengguna untuk mengedit peran pengguna dan pilih **Kelola peran**.

1. Tetapkan **peran Penyesuai kartu Customer Insights** kepada pengguna yang akan menyesuaikan konten untuk ditampilkan pada kartu untuk seluruh organisasi.

## <a name="add-customer-card-controls-to-forms"></a>Tambahkan kontrol Kartu Pelanggan ke formulir
  
1. Untuk menambahkan kontrol kartu pelanggan ke formulir kontak, buka **pengaturan** > **penyesuaian** di Dynamics 365.

1. Pilih **Sesuaikan sistem**.

1. Telusuri entitas **kontak**, perluas lalu pilih **formulir**.

1. Pilih formulir kontak yang ingin ditambahkan kontrol kartu pelanggan.

    > [!div class="mx-imgBorder"]
    > ![Pilih formulir kontak](media/contact-active-forms.png "Pilih formulir kontak")

1. Untuk menambahkan kontrol, di editor formulir, tarik bidang apa pun dari **penjelajah bidang** ke tempat Anda ingin kontrol ditampilkan.

1. Pilih bidang di formulir yang baru saja ditambahkan, lalu pilih **Ubah properti**.

1. Buka tab **Kontrol** dan pilih **Tambahkan kontrol**. Pilih salah satu kontrol kustom yang tersedia dan pilih **Tambah**.

1. Di dialog **properti bidang**, kosongkan kotak centang **label tampilan di formulir**.

1. Pilih opsi **web** untuk kontrol. Untuk kontrol pengayaan, pilih jenis pengayaan yang akan ditampilkan dengan mengonfigurasi bidang **enrichmenttype**. Tambahkan kontrol pengayaan terpisah untuk setiap jenis pengayaan.

1. Pilih **Simpan** dan **publikasikan** untuk mempublikasikan formulir kontak yang diperbarui.

1. Buka formulir kontak yang dipublikasikan. Anda akan melihat kontrol yang baru ditambahkan. Anda mungkin harus masuk saat pertama kali menggunakannya.

1. Untuk menyesuaikan yang ingin Anda Tampilkan pada kontrol kustom, pilih tombol Edit di sudut kanan atas.

## <a name="upgrade-customer-card-add-in"></a>Tingkatkan Add-in Kartu Pelanggan
Add-in Kartu Pelanggan tidak ditingkatkan secara otomatis. Untuk meningkatkan ke versi terbaru, ikuti prosedur ini dalam aplikasi Dynamics 365 yang telah terinstal Add-in.

1. Dalam aplikasi Dynamics 365, buka **Pengaturan** > **Penyesuaian** dan pilih **Solusi**.

1. Pada tabel add-in, cari **CustomerInsightsCustomerCard** dan pilih baris.

1. Pilih **Terapkan Peningkatan Solusi** pada bilah tindakan.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Tingkatkan solusi di area Penyesuaian aplikasi Dynamics 365":::

1. Setelah memulai proses peningkatan, Anda akan melihat indikator pemuatan hingga peningkatan selesai. Jika tidak ada versi yang lebih baru, peningkatan akan menampilkan pesan kesalahan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
