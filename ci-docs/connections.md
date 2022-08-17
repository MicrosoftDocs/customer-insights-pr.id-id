---
title: Ikhtisar koneksi (pratinjau)
description: Koneksi ke layanan lain dari Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245515"
---
# <a name="connections-preview-overview"></a>Ikhtisar koneksi (pratinjau)

Koneksi adalah kunci untuk memungkinkan berbagi data ke dan dari Customer Insights. Setiap koneksi menetapkan berbagi data dengan layanan tertentu. Gunakan koneksi untuk [mengonfigurasi pengayaan](enrichment-hub.md) pihak ketiga dan [mengonfigurasi ekspor](export-destinations.md). Sambungan yang sama dapat digunakan beberapa kali. Misalnya, satu koneksi ke Dynamics 365 Marketing berfungsi untuk beberapa ekspor dan satu koneksi Leadspace dapat digunakan untuk beberapa pengayaan.

## <a name="export-connections"></a>Mengekspor koneksi

Hanya administrator yang dapat mengonfigurasi koneksi baru, tetapi mereka dapat [memberikan akses ke kontributor](#allow-contributors-to-use-a-connection-for-exports) untuk menggunakan koneksi yang ada. Administrator mengontrol ke mana data dapat pergi, kontributor menentukan muatan dan frekuensi yang sesuai dengan kebutuhan mereka.

## <a name="enrichment-connections"></a>Koneksi pengayaan

Hanya administrator yang dapat mengonfigurasi koneksi baru, tetapi koneksi yang dibuat selalu tersedia untuk administrator dan kontributor. Administrator mengelola kredensial dan memberikan persetujuan untuk transfer data. Koneksi kemudian dapat digunakan untuk pengayaan oleh administrator dan kontributor.

## <a name="add-a-new-connection"></a>Tambah koneksi baru

### <a name="prerequisites"></a>Prasyarat

- [Izin administrator](permissions.md)
- Layanan Microsoft lainnya, jika ada, berada di organisasi yang sama

1. Buka **Admin** > **Koneksi**.

1. Pilih **Tambahkan koneksi** dan pilih jenis koneksi yang ingin Anda buat. Atau, buka tab **Temukan** dan pilih **Siapkan** pada ubin koneksi.

1. Beri koneksi Anda nama yang dikenali di bidang **nama tampilan**. Nama dan tipe koneksi menjelaskan koneksi ini. Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi.

1. Masukkan detail yang diperlukan. Bidang yang tepat bergantung pada layanan apa yang Anda sambungkan. Untuk detail jenis koneksi tertentu, lihat artikel tentang layanan target.

1. Jika Anda [menggunakan Key Vault](use-azure-key-vault.md) untuk menyimpan rahasia, aktifkan **Gunakan Key Vault** dan pilih rahasia dari daftar.

1. Tinjau privasi dan kepatuhan data dan pilih **Saya setuju**.

1. Pilih **Simpan** untuk membuat koneksi.

### <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Saat Anda memungkinkan Dynamics 365 Customer Insights untuk mengirimkan data ke pihak ketiga atau produk Microsoft lainnya, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Pribadi. Microsoft akan mentransfer data tersebut atas instruksi Anda, tetapi Anda bertanggung jawab untuk memastikan bahwa pihak ketiga tersebut memenuhi kewajiban privasi atau keamanan apa pun yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Administrator Anda Dynamics 365 Customer Insights dapat menghapus koneksi kapan saja untuk menghentikan penggunaan fungsionalitas.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Izinkan kontributor menggunakan koneksi untuk ekspor

Saat menyiapkan atau mengedit koneksi ekspor, pilih pengguna mana yang diizinkan untuk menggunakan koneksi khusus ini untuk menentukan [ekspor](export-destinations.md). Secara default, koneksi tersedia untuk pengguna dengan peran administrator. **Ubah pengaturan Pilih siapa yang dapat menggunakan koneksi** ini untuk mengizinkan pengguna dengan peran kontributor menggunakan koneksi ini.

- Kontributor tidak akan dapat melihat atau mengedit koneksi. Mereka hanya akan melihat nama tampilan dan jenisnya saat membuat ekspor.
- Dengan berbagi koneksi, Anda memperbolehkan kontributor menggunakan koneksi. Kontributor akan melihat koneksi bersama saat mereka menyiapkan ekspor. Mereka dapat mengelola setiap ekspor yang menggunakan koneksi khusus ini.
- Anda dapat mengubah pengaturan ini sambil mempertahankan ekspor yang telah ditentukan oleh kontributor.

## <a name="manage-existing-connections"></a>Mengelola koneksi yang ada

1. Buka **Admin** > **Koneksi**.

1. Pilih tab **Pengayaan** atau **Ekspor** untuk melihat daftar koneksi pengayaan atau ekspor, jenis koneksi, kapan dibuat, dan siapa yang memiliki akses. Anda dapat mengurutkan daftar koneksi berdasarkan kolom apa pun.

1. Pilih koneksi untuk melihat tindakan yang tersedia.

   - **Edit** koneksi.
   - [**Hapus**](#remove-a-connection) koneksi.

### <a name="remove-a-connection"></a>Hapus koneksi

Jika koneksi yang Anda hapus digunakan oleh pengayaan atau ekspor, pertama-tama lepaskan atau hapus. Dialog hapus memandu Anda ke pengayaan atau ekspor yang relevan.

> [!TIP]
> Pengayaan yang dinonaktifkan dan ekspor yang terpisah menjadi tidak aktif. Anda mengaktifkannya kembali dengan menambahkan koneksi lain ke koneksi tersebut di halaman [Pengayaan](enrichment-hub.md) atau [Ekspor](export-destinations.md).

1. Buka **Admin** > **Koneksi**.

1. Pilih tab **Pengayaan** atau **Ekspor**.

1. Pilih koneksi yang ingin Anda hapus.

1. Dari menu dropdown, pilih **hilangkan**. Dialog konfirmasi akan ditampilkan.

   1. Jika ada pengayaan atau ekspor menggunakan koneksi ini, pilih tombol untuk melihat apa yang menggunakan koneksi.
      - **Ekspor:** Pilih untuk **Menghapus** ekspor atau **Melepaskan koneksi**. Melepaskan koneksi membuat konfigurasi ekspor tetap, tetapi tidak akan dijalankan sampai koneksi lain ditambahkan ke dalamnya.
      - **Pengayaan:** Pilih untuk **Menghapus** atau **Menonaktifkan** pengayaan.
   1. Setelah koneksi tidak memiliki dependensi lagi, kembali ke **Admin** > **Koneksi** dan coba hapus koneksi lagi.

1. Pilih **Hapus**, untuk mengonfirmasi penghapusan tersebut.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Mengkonfigurasikan sambungan dengan rahasia yang dikelola oleh Key Vault Anda sendiri

Beberapa sambungan memerlukan rahasia seperti kunci API atau sandi. Beberapa sambungan mendukung rahasia yang tersimpan di Key Vault Anda sendiri. Pelajari lebih lanjut tentang koneksi yang didukung dan cara menyiapkannya di [Key Vault for Customer Insights](use-azure-key-vault.md) Anda sendiri.

[!INCLUDE [footer-include](includes/footer-banner.md)]
