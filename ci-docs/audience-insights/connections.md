---
title: Koneksi ke layanan lain dari Customer Insights.
description: Bagikan data ke layanan lain.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e78e18b75ee9797b5fc76486615992e301e4c650
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977741"
---
# <a name="connections-preview-overview"></a>Ikhtisar koneksi (pratinjau)

Koneksi adalah kunci untuk memungkinkan berbagi data ke dan dari Customer Insights. Setiap koneksi menetapkan berbagi data dengan layanan tertentu. Koneksi adalah fondasi untuk [mengkonfigurasi pengayaan pihak ketiga](enrichment-hub.md) dan [mengonfigurasi ekspor](export-destinations.md). Sambungan yang sama dapat digunakan beberapa kali. Misalnya, satu koneksi ke Dynamics 365 Marketing berfungsi untuk beberapa ekspor dan satu koneksi Leadspace dapat digunakan untuk beberapa pengayaan.

Buka **Admin** > **Koneksi** untuk membuat dan melihat koneksi.

Tab **Koneksi** memperlihatkan semua koneksi aktif. Daftar memperlihatkan baris untuk setiap koneksi. 

Dapatkan gambaran umum, deskripsi, dan cari tahu apa yang bisa Anda lakukan dengan setiap opsi ekstensibilitas pada tab **Temukan**.

### <a name="exports"></a>Ekspor

Hanya administrator yang dapat mengonfigurasi koneksi baru, tetapi mereka dapat memberikan akses ke kontributor untuk menggunakan koneksi yang ada. Administrator mengontrol ke mana data dapat pergi, kontributor menentukan muatan dan frekuensi yang sesuai dengan kebutuhan mereka. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Pengayaan

Hanya administrator yang dapat mengonfigurasi koneksi baru tetapi koneksi yang dibuat selalu tersedia untuk administrator dan kontributor. Administrator mengelola kredensial dan memberikan persetujuan untuk transfer data. Koneksi kemudian dapat digunakan untuk pengayaan oleh administrator dan kontributor.

## <a name="add-a-new-connection"></a>Tambah koneksi baru

Untuk menambahkan koneksi, Anda perlu memiliki [izin administrator](permissions.md). Jika Anda tersambung ke layanan Microsoft lainnya, kami menganggap kedua layanan berada dalam organisasi yang sama.

1. Buka **Admin** > **Koneksi (pratinjau)**.

1. Buka tab **Koneksi**.

1. Pilih **Tambahkan Koneksi** untuk membuat koneksi baru. Pilih dari menu dropdown jenis sambungan yang akan dibuat.

1. Di panel **Siapkan koneksi**, berikan detail yang diperlukan. 
   1. **Nama tampilan** dan tipe koneksi menjelaskan koneksi. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi ini.
   1. Bidang yang tepat tergantung pada layanan apa yang Anda sambungkan. Anda dapat mempelajari detail jenis koneksi tertentu di artikel tentang layanan target.
   1. Jika Anda [menggunakan Key Vault](use-azure-key-vault.md) untuk menyimpan rahasia, aktifkan **Gunakan Key Vault** dan pilih rahasia dari daftar.

1. Pilih **Simpan** untuk membuat koneksi.

Anda juga dapat memilih **konfigurasi** di ubin pada tab **temukan**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Izinkan kontributor menggunakan koneksi untuk ekspor

Saat menyiapkan atau mengedit koneksi ekspor, Anda memilih pengguna mana yang diizinkan menggunakan koneksi khusus ini untuk menentukan [ekspor](export-destinations.md). Secara default koneksi tersedia untuk pengguna dengan peran administrator. Anda bisa mengubah pengaturan ini di **Pilih siapa yang bisa menggunakan koneksi ini** dan mengizinkan pengguna dengan peran kontributor untuk menggunakan koneksi ini.

- Kontributor tidak akan dapat melihat atau mengedit koneksi. Mereka hanya akan melihat nama tampilan dan jenisnya ketika membuat ekspor.
- Dengan berbagi koneksi, Anda memperbolehkan kontributor menggunakan koneksi. Kontributor akan melihat koneksi bersama saat mereka menyiapkan ekspor. Mereka dapat mengelola setiap ekspor yang menggunakan koneksi khusus ini.
- Anda dapat mengubah pengaturan ini sambil mempertahankan ekspor yang telah ditentukan oleh kontributor.

## <a name="edit-a-connection"></a>Edit koneksi

1. Buka **Admin** > **Koneksi (pratinjau)**.

1. Buka tab **Koneksi**.

1. Pilih elipsis vertikal untuk koneksi yang ingin diedit.

1. Pilih **Edit**.

1. Ubah nilai yang ingin Anda perbarui dan pilih **Simpan**.

## <a name="remove-a-connection"></a>Hapus koneksi

Jika koneksi yang Anda hapus digunakan oleh pengayaan atau ekspor, Pertama-tama Anda harus melepaskan atau menghapusnya. Dialog hapus akan memandu Anda ke pengayaan atau ekspor yang relevan. 

Pengayaan dan ekspor terpisah menjadi tidak aktif. Anda mengaktifkannya kembali dengan menambahkan koneksi lain ke koneksi tersebut di halaman [Pengayaan](enrichment-hub.md) atau [Ekspor](export-destinations.md).

1. Buka **Admin** > **Koneksi (pratinjau)**.

1. Buka tab **Koneksi**.

1. Pilih elipsis vertikal untuk koneksi yang ingin dihapus.

1. Dari menu dropdown, pilih **hilangkan**. Dialog konfirmasi akan ditampilkan.

   1. Jika ada pengayaan atau ekspor menggunakan koneksi ini, pilih tombol untuk melihat apa yang menggunakan koneksi.
      - **Ekspor:** Anda dapat memilih untuk menghapus atau memutuskan sambungan ekspor agar dapat menghapus koneksi. Untuk memutuskan sambungan ekspor, administrator bisa menggunakan tindakan **Putuskan sambungan**. Tindakan ini tersedia untuk ekspor individual dan beberapa ekspor yang dipilih. Dengan memutuskan sambungan, Anda menyimpan konfigurasi ekspor, tetapi tidak akan dijalankan hingga koneksi lain ditambahkan ke konfigurasi tersebut.
      - **Pengayaan:** Anda dapat memilih untuk menghapus atau menonaktifkan pengayaan agar dapat menghapus koneksi. 
   1. Setelah koneksi tidak memiliki dependensi lagi, kembali ke **Admin** > **Koneksi** dan coba hapus koneksi lagi.

1. Pilih **Hapus**, untuk mengonfirmasi penghapusan tersebut.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Mengkonfigurasikan sambungan dengan rahasia yang dikelola oleh Key Vault Anda sendiri

Beberapa sambungan memerlukan rahasia seperti kunci API atau sandi. Beberapa sambungan mendukung rahasia yang tersimpan di Key Vault Anda sendiri. Pelajari lebih lanjut tentang sambungan yang didukung dan cara mengkonfigurasi [Key Vault anda sendiri wawasan audiens](use-azure-key-vault.md).
