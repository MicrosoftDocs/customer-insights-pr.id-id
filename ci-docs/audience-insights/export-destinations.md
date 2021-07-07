---
title: Mengekspor data dari Customer Insights
description: Kelola ekspor untuk berbagi data.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305482"
---
# <a name="exports-preview-overview"></a>Gambaran umum Ekspor (pratinjau)

Halaman **Ekspor** memperlihatkan kepada Anda semua ekspor yang dikonfigurasi. Ekspor berbagi data tertentu dengan berbagai aplikasi. Mereka dapat menyertakan profil pelanggan atau entitas, skema, dan detail pemetaan. Setiap ekspor memerlukan [koneksi, yang disiapkan oleh administrator, untuk mengelola autentikasi dan akses](connections.md).

Buka **Data** > **Ekspor** untuk menampilkan halaman ekspor. Semua peran pengguna dapat melihat ekspor yang dikonfigurasi. Gunakan bidang pencarian di bilah perintah untuk menemukan ekspor berdasarkan nama, nama koneksi, atau jenis koneksi.

## <a name="set-up-a-new-export"></a>Konfigurasikan ekspor baru

Untuk menyiapkan atau mengedit ekspor, Anda harus memiliki koneksi yang tersedia untuk Anda. Koneksi bergantung pada [peran pengguna](permissions.md) Anda:
- Administrator memiliki akses ke semua koneksi. Mereka juga dapat membuat koneksi baru saat menyiapkan ekspor.
- Kontributor dapat memiliki akses ke koneksi tertentu. Mereka bergantung pada administrator untuk mengonfigurasi dan berbagi koneksi. Daftar ekspor akan menampilkan kontributor apakah mereka dapat mengedit atau hanya melihat ekspor di kolom **izin Anda**. Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Pemirsa hanya dapat melihat ekspor yang ada tetapi tidak membuatnya.

### <a name="define-a-new-export"></a>Menentukan ekspor baru

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Di panel **Konfigurasikan ekspor**, pilih koneksi mana yang akan digunakan. [Koneksi](connections.md) dikelola oleh administrator. 

1. Berikan detail yang diperlukan dan pilih **Simpan** untuk membuat ekspor.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Menentukan ekspor baru berdasarkan ekspor yang ada

1. Buka **Data** > **Ekspor**.

1. Dalam daftar ekspor, pilih ekspor yang ingin Anda duplikasi.

1. Pilih **Buat duplikat** di bilah perintah untuk membuka panel **Atur ekspor** dengan rincian ekspor yang dipilih.

1. Baca dan sesuaikan ekspor, lalu pilih **Simpan** untuk membuat ekspor baru.

### <a name="edit-an-export"></a>Edit ekspor

1. Buka **Data** > **Ekspor**.

1. Dalam daftar ekspor, pilih ekspor yang ingin Anda edit.

1. Di bilah perintah, pilih **Edit**.

1. Ubah nilai yang ingin Anda perbarui dan pilih **Simpan**.

## <a name="view-exports-and-export-details"></a>Melihat ekspor dan mengekspor detail

Setelah membuat tujuan ekspor, mereka tercantum pada **Data** > **Ekspor**. Semua pengguna dapat melihat data mana yang dibagikan dan status terbarunya.

1. Buka **Data** > **Ekspor**.

1. Pengguna tanpa izin mengedit, pilih **Tampilan**, bukan **Edit** untuk melihat rincian ekspor.

1. Panel sisi menampilkan konfigurasi ekspor. Tanpa izin edit, Anda tidak bisa mengubah nilai. Pilih **Tutup** untuk kembali ke halaman ekspor.

## <a name="schedule-and-run-exports"></a>Jadwalkan dan jalankan ekspor

Setiap ekspor yang Anda konfigurasikan memiliki jadwal refresh. Selama pembaruan, sistem mencari data baru atau yang diperbarui untuk disertakan dalam ekspor. Secara default, ekspor dijalankan sebagai bagian dari setiap [pembaruan sistem terjadwal](system.md#schedule-tab). Anda dapat menyesuaikan jadwal refresh atau menonaktifkannya untuk menjalankan ekspor secara manual.

Jadwal ekspor tergantung pada status lingkungan Anda. Jika ada pembaruan yang sedang berlangsung pada [dependensi](system.md#refresh-policies) ketika ekspor terjadwal harus dimulai, sistem akan terlebih dulu menyelesaikan pembaruan dan kemudian menjalankan ekspor. Anda dapat melihat kapan ekspor terakhir kali di-refresh di kolom **Disegarkan**.

### <a name="schedule-exports"></a>Jadwalkan ekspor

Anda dapat menentukan jadwal refresh kustom untuk ekspor individual atau beberapa ekspor sekaligus. Jadwal yang ditentukan saat ini tercantum di kolom **Jadwal** dari daftar ekspor. Izin untuk mengubah jadwal sama seperti [pengeditan dan penentuan ekspor](export-destinations.md#set-up-a-new-export). 

1. Buka **Data** > **Ekspor**.

1. Pilih ekspor yang ingin dijadwalkan.

1. Pilih **Jadwal** di bilah perintah.

1. Di panel **Jadwalkan ekspor**, atur **Jadwal berjalan** ke **Aktif** untuk menjalankan ekspor secara otomatis. Atur ke **Nonaktif** untuk me-refresh secara manual.

1. Untuk ekspor yang di-refresh secara otomatis, pilih nilai **Pengulangan** dan tentukan rincian untuknya. Waktu yang ditentukan berlaku untuk semua instans pengulangan. Ini adalah waktu ketika ekspor harus mulai me-refresh.

1. Terapkan dan aktifkan perubahan Anda dengan memilih **Simpan**.

Saat mengedit jadwal untuk beberapa ekspor, Anda harus membuat pilihan di dalam **Pertahankan atau timpa jadwal**:
- **Pertahankan jadwal individual**: Pertahankan jadwal yang ditentukan sebelumnya untuk ekspor yang dipilih dan cukup nonaktifkan atau aktifkan.
- **Menentukan jadwal baru untuk semua ekspor yang dipilih**: Menimpa jadwal yang ada dari ekspor yang dipilih.

### <a name="run-exports-on-demand"></a>Menjalankan ekspor Atas Permintaan

Untuk mengekspor data tanpa menunggu refresh terjadwal, buka **Data** > **Ekspor**.

- Untuk menjalankan semua ekspor, pilih **Jalankan semua** di bilah perintah. Tindakan ini hanya akan menjalankan ekspor yang memiliki jadwal aktif.
- Untuk menjalankan satu ekspor, pilih ekspor dalam daftar, lalu pilih **Jalankan** di bilah perintah. Itulah cara Anda menjalankan ekspor tanpa jadwal aktif. 

## <a name="remove-an-export"></a>Menghapus ekspor

1. Buka **Data** > **Ekspor**.

1. Pilih ekspor yang ingin Anda hilangkan.

1. Di bilah perintah, pilih **Hapus**.

1. Konfirmasikan penghapusan dengan memilih **Hapus** di layar konfirmasi.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
