---
title: Membuat dan mengelola lingkungan
description: Pelajari cara mendaftar ke layanan dan cara mengelola lingkungan.
ms.date: 10/14/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2d977ef4eb585e26b36139681552db22d84759c9
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673737"
---
# <a name="manage-environments"></a>Kelola lingkungan

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Alihkan Lingkungan

Pilih kontrol **lingkungan** di sudut kanan atas halaman untuk mengubah lingkungan.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Cuplikan layar kontrol untuk beralih lingkungan.":::

Administrator dapat [membuat](create-environment.md) dan mengelola lingkungan.

## <a name="edit-an-existing-environment"></a>Edit lingkungan yang ada

Anda dapat mengedit beberapa rincian lingkungan yang ada.

1.  Pilih pemilih **Lingkungan** di header aplikasi.

2.  Pilih ikon **Edit**.

3. Di kotak **Edit lingkungan**, Anda dapat memperbarui pengaturan lingkungan.

Untuk informasi lebih lanjut tentang pengaturan lingkungan, lihat [Membuat lingkungan baru](create-environment.md).

## <a name="copy-the-environment-configuration"></a>Salin konfigurasi lingkungan

Bila membuat lingkungan baru, Anda dapat memilih untuk menyalin konfigurasi dari lingkungan yang ada. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Cuplikan layar pilihan pengaturan di pengaturan lingkungan.":::

Anda akan melihat daftar semua lingkungan yang tersedia di organisasi tempat Anda dapat menyalin data.

Pengaturan konfigurasi berikut disalin:

- Sumber data yang diserap/diimpor
- Konfigurasi penyatuan data (petakan, cocokkan, gabungkan)
- Segmen
- Tindakan
- Relasi
- Aktivitas
- Indeks Pencarian & filter
- Tujuan ekspor
- Refresh terjadwal
- Pengayaan
- Manajemen model
- Penetapan peran

Data berikut ini *tidak* disalin:

- Profil pelanggan.
- Kredensial sumber data. Anda harus memberikan kredensial untuk setiap sumber data dan menyegarkan sumber data secara manual.

- Sumber data dari folder Common Data Model dan data lake terkelola Dataverse. Anda harus membuat sumber data secara manual dengan nama yang sama seperti di lingkungan sumber.

Bila Anda menyalin lingkungan, Anda akan melihat pesan konfirmasi bahwa lingkungan baru telah dibuat. Pilih **buka sumber data** untuk melihat daftar sumber data.

Semua sumber data akan menampilkan status **kredensial yang diperlukan**. Edit sumber data dan masukkan kredensial untuk me-refresh mereka.

:::image type="content" source="media/data-sources-copied.png" alt-text="Daftar sumber data yang disalin dan memerlukan otentikasi.":::

Setelah menyegarkan sumber data, buka **data** > **Satukan**. Di sini Anda akan menemukan pengaturan dari lingkungan sumber. Edit sesuai kebutuhan atau pilih **Jalankan** untuk memulai proses penyatuan data dan buat entitas pelanggan terpadu.

Bila penyatuan data selesai, buka **langkah** dan **segmen** untuk me-refresh juga.

## <a name="reset-an-existing-environment"></a>Mengatur ulang lingkungan yang ada

Sebagai administrator, Anda dapat mengatur ulang lingkungan ke status kosong jika Anda ingin menghapus semua konfigurasi dan menghapus data yang diserap.

1.  Pilih pemilih **Lingkungan** di header aplikasi. 

2.  Pilih lingkungan yang ingin Anda atur ulang dan pilih elipsis (**...**). 

3. Pilih opsi **Atur ulang**. 

4.  Untuk mengkonfirmasi penghapusan, masukkan nama lingkungan dan pilih **Atur ulang**.

## <a name="delete-an-existing-environment"></a>Menghapus lingkungan yang ada

Sebagai administrator, Anda dapat menghapus lingkungan yang dikelola.

1.  Pilih pemilih **Lingkungan** di header aplikasi.

2.  Pilih lingkungan yang ingin Anda atur ulang dan pilih elipsis (**...**). 

3. Pilih opsi **Hapus**. 

4.  Untuk mengonfirmasikan penghapusan, masukkan nama lingkungan dan pilih **Hapus**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
