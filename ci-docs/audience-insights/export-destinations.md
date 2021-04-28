---
title: Mengekspor data dari Customer Insights
description: Kelola ekspor untuk berbagi data.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896147"
---
# <a name="exports-preview-overview"></a>Gambaran umum Ekspor (pratinjau)

Halaman **Ekspor** memperlihatkan kepada Anda semua ekspor yang dikonfigurasi. Ekspor berbagi data tertentu dengan berbagai aplikasi. Mereka dapat menyertakan profil pelanggan atau entitas, skema, dan detail pemetaan. Setiap ekspor memerlukan [koneksi, yang disiapkan oleh administrator, untuk mengelola autentikasi dan akses](connections.md).

> [!NOTE]
> Hingga Maret 2021, ekspor membuat koneksi ke layanan yang sesuai secara otomatis. Ekspor sekarang memerlukan [koneksi, yang dibuat dan dibagikan oleh administrator](connections.md) sebelum Anda bisa membuatnya.

Buka **Data** > **Ekspor** untuk menampilkan halaman ekspor. Semua peran pengguna memiliki akses untuk melihat ekspor yang dikonfigurasi. Gunakan bidang pencarian di bilah perintah untuk menemukan ekspor menurut nama, nama koneksi, atau tipe koneksinya.

## <a name="set-up-a-new-export"></a>Konfigurasikan ekspor baru

Untuk menyiapkan atau mengedit ekspor, Anda harus memiliki koneksi yang tersedia untuk Anda. Koneksi bergantung pada [peran pengguna](permissions.md) Anda:
- Administrator memiliki akses ke semua koneksi. Mereka juga dapat membuat koneksi baru saat menyiapkan ekspor.
- Kontributor dapat memiliki akses ke koneksi tertentu. Mereka bergantung pada administrator untuk mengonfigurasi dan berbagi koneksi. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Pemirsa hanya dapat melihat ekspor yang ada tetapi tidak membuatnya.

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat tujuan ekspor baru.

1. Di panel **Konfigurasikan ekspor**, pilih koneksi mana yang akan digunakan. [Koneksi](connections.md) dikelola oleh administrator. 

1. Berikan detail yang diperlukan dan pilih **Simpan** untuk membuat ekspor.

### <a name="edit-an-export"></a>Edit ekspor

1. Pilih elipsis vertikal untuk tujuan ekspor yang akan diedit.

1. Dari menu tarik-turun, pilih **Edit**.

1. Ubah nilai yang ingin Anda perbarui dan pilih **Simpan**.

## <a name="view-exports-and-export-details"></a>Melihat ekspor dan mengekspor detail

Setelah membuat tujuan ekspor, mereka tercantum pada **Data** > **Ekspor**. Semua pengguna dapat melihat data mana yang dibagikan dan status terbarunya.

1. Buka **Data** > **Ekspor**.

1. Pengguna tanpa izin edit memilih **Lihat**, bukan **Edit** untuk melihat detail ekspor.

1. Panel samping ini memperlihatkan pengaturan ekspor ini. Tanpa izin edit, Anda tidak bisa mengubah nilai. Pilih **Tutup** untuk kembali ke halaman ekspor.

## <a name="run-exports-on-demand"></a>Menjalankan ekspor Atas Permintaan

Setelah mengonfigurasi ekspor, ekspor akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab) selama memiliki koneksi yang berfungsi.

Untuk mengekspor data tanpa menunggu refresh terjadwal, buka **Data** > **Ekspor**. Anda memiliki dua pilihan:

- Untuk menjalankan semua ekspor, pilih **Jalankan semua** di bilah perintah. 
- Untuk menjalankan ekspor tunggal, pilih elipsis (...) pada item daftar lalu pilih **Jalankan**.

## <a name="remove-an-export"></a>Menghapus ekspor

1. Buka **Data** > **Ekspor**.

1. Pilih elipsis vertikal untuk ekspor yang akan dihilangkan.

1. Dari menu dropdown, pilih **hilangkan**.

1. Konfirmasikan penghapusan dengan memilih **Hapus** di layar konfirmasi.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
