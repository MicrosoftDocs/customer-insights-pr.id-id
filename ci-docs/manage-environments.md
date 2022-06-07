---
title: Cara - Mengelola lingkungan
description: Pelajari cara mengelola lingkungan Customer Insights yang ada sebagai admin."
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833496"
---
# <a name="how-to-manage-environments"></a>Cara: Mengelola lingkungan

[Administrator membuat](create-environment.md) dan mengelola lingkungan. Mereka dapat mengubah beberapa pengaturan di lingkungan yang ada. Bisnis, jenis, wilayah, opsi penyimpanan, dan Dataverse pengaturan diperbaiki setelah membuat lingkungan. Jika Anda ingin mengubah pengaturan ini, atur ulang lingkungan atau buat lingkungan baru.

## <a name="edit-an-existing-environment"></a>Edit lingkungan yang ada

Anda dapat mengedit beberapa rincian lingkungan yang ada.

1. Pilih pemilih **Lingkungan** di header aplikasi.

1. Pilih ikon **Edit**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikon untuk mengedit pengaturan lingkungan.":::

1. Di kotak **Edit lingkungan**, Anda dapat memperbarui pengaturan lingkungan.

Untuk memulai dengan lingkungan baru, lihat [Membuat lingkungan baru](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Mengubah pemilik lingkungan

Beberapa pengguna dapat memiliki izin admin tetapi hanya satu pengguna yang merupakan pemilik lingkungan. Secara default, adminlah yang membuat lingkungan pada awalnya. Sebagai admin lingkungan, Anda dapat menetapkan kepemilikan ke pengguna lain dengan izin admin.

1. Pilih pemilih **Lingkungan** di header aplikasi.

1. Pilih ikon **Edit**.

1. Dalam kotak **Edit lingkungan**, buka **langkah Informasi** dasar.

1. Di **bidang Ubah pemilik lingkungan**, pilih pemilik baru lingkungan.  

1. Pilih **Tinjau dan selesaikan**, lalu **Perbarui** untuk menerapkan perubahan.

## <a name="claim-ownership-of-an-environment"></a>Mengklaim kepemilikan lingkungan

Jika akun pengguna pemilik dihapus atau ditangguhkan, lingkungan tidak akan memiliki pemilik. Setiap pengguna admin dapat mengklaim kepemilikan dan menjadi pemilik baru. Mereka dapat terus memiliki lingkungan atau [mengubah kepemilikan ke admin](#change-the-owner-of-an-environment) lain.

Untuk mengklaim kepemilikan, pilih tombol **Ambil kepemilikan** yang ditampilkan di bagian atas setiap halaman di Customer Insights saat pemilik asli meninggalkan organisasi.

## <a name="reset-an-existing-environment-preview"></a>Mereset lingkungan yang ada (Pratinjau)

Sebagai pemilik lingkungan, Anda dapat mengatur ulang lingkungan ke status kosong jika Anda ingin menghapus semua konfigurasi dan menghapus data yang diserap.

1. Pilih pemilih **Lingkungan** di header aplikasi.

1. Pilih lingkungan yang ingin Anda atur ulang dan pilih elipsis vertikal (&vellip;).

1. Pilih opsi **Atur ulang**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontrol untuk mengatur ulang lingkungan.":::

1. Pilih apakah Anda ingin mengatur ulang seluruh lingkungan, semuanya kecuali sumber data, atau apa pun yang dikonfigurasi di atas profil pelanggan terpadu.

1. Untuk mengonfirmasi, masukkan nama lingkungan dan pilih **Atur Ulang**.

## <a name="delete-an-existing-environment"></a>Menghapus lingkungan yang ada

Sebagai pemilik lingkungan, Anda dapat menghapus lingkungan yang Anda kelola.

1. Pilih pemilih **Lingkungan** di header aplikasi.

1. Pilih lingkungan yang ingin Anda atur ulang dan pilih elipsis vertikal (&vellip;). 

1. Pilih opsi **Hapus**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontrol untuk menghapus lingkungan.":::

1. Untuk mengonfirmasikan penghapusan, masukkan nama lingkungan dan pilih **Hapus**.

> [!IMPORTANT]
> Menghapus lingkungan tidak menghapus koneksi ke Dataverse lingkungan. Jika Anda berencana untuk menghubungkan lingkungan yang sama Dataverse ke lingkungan Customer Insights baru di masa mendatang, Anda harus menghapus koneksi tersebut Pelajari cara [menghapus koneksi yang ada ke Dataverse lingkungan](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
