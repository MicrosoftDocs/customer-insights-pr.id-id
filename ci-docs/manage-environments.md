---
title: Kelola lingkungan
description: Pelajari cara mengelola lingkungan Customer Insights yang ada sebagai admin.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 6d48f7088d722b27ca69cd591178651bdb6e2c23
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588816"
---
# <a name="manage-environments"></a>Kelola lingkungan

[Administrator membuat](create-environment.md) dan mengelola lingkungan. Mereka dapat mengubah beberapa pengaturan di lingkungan yang ada. Bisnis, jenis, wilayah, opsi penyimpanan, dan Dataverse pengaturan diperbaiki setelah membuat lingkungan. Jika Anda ingin mengubah pengaturan ini, [atur ulang lingkungan](#reset-an-existing-environment-preview) atau [buat lingkungan baru](create-environment.md).

## <a name="edit-an-existing-environment"></a>Edit lingkungan yang ada

Edit detail lingkungan yang ada seperti nama atau pengaturan lingkungan default.

1. Pilih pemilih **Lingkungan** di header aplikasi.

1. Pilih ikon **Edit**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikon untuk mengedit pengaturan lingkungan.":::

1. Di **panel Edit lingkungan**, perbarui pengaturan lingkungan.

1. Pilih **Tinjau dan selesaikan**, lalu **Perbarui** untuk menerapkan perubahan.

## <a name="change-the-owner-of-an-environment"></a>Mengubah pemilik lingkungan

Beberapa pengguna dapat memiliki izin admin tetapi hanya satu pengguna yang merupakan pemilik lingkungan. Secara default, adminlah yang membuat lingkungan pada awalnya. Sebagai admin lingkungan, Anda dapat menetapkan kepemilikan ke pengguna lain dengan izin admin.

1. Pilih pemilih **Lingkungan** di header aplikasi.

1. Pilih ikon **Edit**.

1. Di **panel Edit lingkungan**, buka **langkah Informasi** dasar.

1. Di **bidang Ubah pemilik lingkungan**, pilih pemilik baru lingkungan.  

1. Pilih **Tinjau dan selesaikan**, lalu **Perbarui** untuk menerapkan perubahan.

## <a name="claim-ownership-of-an-environment"></a>Mengklaim kepemilikan lingkungan

Jika akun pengguna pemilik dihapus atau ditangguhkan, lingkungan tidak akan memiliki pemilik. Setiap pengguna admin dapat mengklaim kepemilikan dan menjadi pemilik baru. Admin pemilik dapat terus memiliki lingkungan atau [mengubah kepemilikan ke admin](#change-the-owner-of-an-environment) lain.

Untuk mengklaim kepemilikan, pilih tombol **Ambil kepemilikan** yang ditampilkan di bagian atas setiap halaman di Customer Insights saat pemilik asli meninggalkan organisasi.

## <a name="reset-an-existing-environment-preview"></a>Mengatur ulang lingkungan yang ada (pratinjau)

Sebagai pemilik lingkungan, atur ulang lingkungan ke status kosong jika Anda ingin menghapus semua konfigurasi dan menghapus data yang diserap.

1. Pilih pemilih **Lingkungan** di header aplikasi.

1. Pilih lingkungan yang ingin Anda atur ulang dan pilih elipsis vertikal (&vellip;).

1. Pilih **Atur Ulang (pratinjau)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kontrol untuk mengatur ulang lingkungan.":::

1. Pilih apakah Anda ingin mengatur ulang seluruh lingkungan, semuanya kecuali sumber data, atau apa pun yang dikonfigurasi di atas profil pelanggan terpadu.

1. Untuk mengonfirmasi, masukkan nama lingkungan dan pilih **Atur Ulang**.

## <a name="delete-an-existing-environment"></a>Menghapus lingkungan yang ada

Sebagai pemilik lingkungan, Anda dapat menghapusnya.

> [!IMPORTANT]
> Menghapus lingkungan tidak menghapus koneksi ke Dataverse lingkungan. Jika Anda berencana untuk menghubungkan lingkungan yang sama Dataverse ke lingkungan Customer Insights baru di masa mendatang, Anda harus [menghapus koneksi tersebut ke lingkungan Dataverse tersebut](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Pilih pemilih **Lingkungan** di header aplikasi.

1. Pilih lingkungan yang ingin Anda hapus dan pilih elipsis vertikal (&vellip;). 

1. Pilih **Hapus**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kontrol untuk menghapus lingkungan.":::

1. Untuk mengonfirmasikan penghapusan, masukkan nama lingkungan dan pilih **Hapus**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
