---
title: Gambaran umum Ekspor (pratinjau)
description: Kelola ekspor untuk berbagi data.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: a70aadda4fc0eff3ddb4c89665506762613c291a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194972"
---
# <a name="exports-preview-overview"></a>Gambaran umum Ekspor (pratinjau)

 Ekspor memungkinkan Anda untuk berbagi data tertentu dengan berbagai aplikasi. Mereka dapat mencakup profil pelanggan, entitas, skema, dan rincian pemetaan. Setiap ekspor memerlukan [koneksi, yang disiapkan oleh administrator, untuk mengelola autentikasi dan akses](connections.md). Halaman **Ekspor** memperlihatkan kepada Anda semua ekspor yang dikonfigurasi.

## <a name="export-types"></a>Jenis ekspor

Ada dua jenis utama ekspor:  

- **Ekspor data keluar**: ekspor semua jenis entitas yang tersedia di Customer Insights. Entitas yang Anda pilih untuk ekspor akan diekspor dengan semua bidang data, metadata, skema, dan rincian pemetaan.
- **Ekspor segmen**: mengekspor entitas segmen dari Customer Insights. Segmen mewakili daftar profil pelanggan. Saat mengonfigurasi ekspor, Anda memilih bidang data yang disertakan, bergantung pada sistem target tempat Anda mengekspor data.

### <a name="export-segments"></a>Ekspor segmen

**Mengekspor segmen di lingkungan untuk akun bisnis (B to B) atau pelanggan individual (B to C)**  
Sebagian besar opsi ekspor mendukung kedua jenis lingkungan tersebut. Mengekspor segmen ke berbagai sistem target memiliki persyaratan khusus. 

**Segmentasi ekspor di lingkungan untuk konsumen perorangan (B to C)**  
- Segmen dalam konteks lingkungan untuk pelanggan individual dibangun pada entitas *profil pelanggan terpadu*. Setiap segmen yang memenuhi persyaratan sistem target (contoh: alamat email) dapat diekspor.

**lingkungan ekspor Segmentasi untuk akun bisnis (B to B)**  
- Segmen dalam konteks lingkungan untuk akun bisnis dibangun pada entitas *akun*. Untuk mengekspor segmen akun sebagaimana adanya, sistem target harus mendukung segmen akun murni. Hal ini terjadi untuk [LinkedIn](export-linkedin-ads.md) bila Anda memilih pilihan **perusahaan** saat menentukan ekspor.
- Semua sistem target lainnya memerlukan bidang dari entitas kontak. Untuk memastikan segmen akun dapat mengambil data dari kontak terkait, definisi segmen Anda harus memproyeksikan atribut entitas kontak. Pelajari lebih lanjut tentang cara [mengkonfigurasi segmen dan atribut proyek](segment-builder.md).

**Batas pada ekspor segmen**  
- Sistem target pihak ketiga dapat membatasi jumlah profil pelanggan yang dapat Anda ekspor. 
- Untuk pelanggan individual, Anda akan melihat jumlah aktual anggota segmen saat memilih segmen untuk ekspor. Anda akan mendapatkan peringatan jika segmen terlalu besar. 
- Untuk akun bisnis, Anda akan melihat jumlah akun dalam satu segmen; namun, jumlah kontak yang mungkin di diproyeksikan tidak ditampilkan. Dalam kasus tertentu, hal ini dapat mengakibatkan segmen yang diekspor benar-benar berisi profil pelanggan yang lebih banyak daripada yang dapat diterima sistem target. Jika batas sistem target terlampaui, ekspor dilewati.

## <a name="set-up-a-new-export"></a>Konfigurasikan ekspor baru

Untuk menyiapkan atau mengedit ekspor, Anda memerlukan koneksi yang tepat yang tersedia untuk Anda. Koneksi bergantung pada [peran pengguna](permissions.md) Anda:
- **Administrator** memiliki akses ke semua koneksi. Mereka juga dapat membuat koneksi baru saat menyiapkan ekspor.
- **Kontributor** dapat memiliki akses ke koneksi tertentu. Mereka bergantung pada administrator untuk mengonfigurasi dan berbagi koneksi. Daftar ekspor akan menampilkan kontributor apakah mereka dapat mengedit atau hanya melihat ekspor di kolom **izin Anda**. Untuk informasi lebih lanjut, buka [Izinkan kontributor agar dapat menggunakan sambungan untuk ekspor](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Pemirsa** hanya dapat melihat ekspor yang ada— tidak membuatnya.

1. Buka **Data** > **Ekspor**.

1. Pilih **Tambahkan ekspor** untuk membuat ekspor baru.

1. Di **panel Siapkan ekspor**, pilih koneksi [mana yang](connections.md) akan digunakan.

1. Berikan detail yang diperlukan dan pilih **Simpan** untuk membuat ekspor. Untuk detail yang diperlukan, tinjau dokumentasi Customer Insights untuk ekspor tertentu.

## <a name="manage-existing-exports"></a>Mengelola ekspor yang ada

Buka **Ekspor** > **Data** untuk melihat ekspor, nama koneksi, jenis koneksi, dan statusnya. Semua peran pengguna dapat melihat ekspor yang dikonfigurasi. Anda bisa mengurutkan daftar ekspor menurut kolom mana pun atau menggunakan kotak pencarian untuk menemukan ekspor yang ingin Anda kelola.

Pilih ekspor untuk melihat tindakan yang tersedia.

:::image type="content" source="media/exports_showmore.png" alt-text="Halaman ekspor.":::

- **Menampilkan** atau **Mengedit** ekspor. Pengguna tanpa izin mengedit, pilih **Tampilan**, bukan **Edit** untuk melihat rincian ekspor.
- **Jalankan** ekspor untuk mengekspor data terbaru.
- **Buat duplikat** ekspor.
- **[Jadwalkan](#schedule-and-run-exports)** ekspor.
- **Lepaskan koneksi** untuk menghapus koneksi untuk ekspor ini. Lepaskan tidak menghapus koneksi, tetapi menonaktifkan ekspor. Kolom **Koneksi yang digunakan** menampilkan Tidak Ada Koneksi.
- **Hapus** ekspor.

## <a name="schedule-and-run-exports"></a>Jadwalkan dan jalankan ekspor

Setiap ekspor yang Anda konfigurasikan memiliki jadwal refresh. Selama pembaruan, sistem mencari data baru atau yang diperbarui untuk disertakan dalam ekspor. Secara default, ekspor dijalankan sebagai bagian dari setiap [pembaruan sistem terjadwal](system.md#schedule-tab). Anda dapat menyesuaikan jadwal refresh atau menonaktifkannya untuk menjalankan ekspor secara manual.

Jadwal ekspor tergantung pada status lingkungan Anda. Jika ada pembaruan yang sedang berlangsung pada [dependensi](system.md#refresh-processes) ketika ekspor terjadwal harus dimulai, sistem akan terlebih dulu menyelesaikan pembaruan dan kemudian menjalankan ekspor. Kolom **Refresh menunjukkan** kapan ekspor terakhir disegarkan.

### <a name="schedule-exports"></a>Jadwalkan ekspor

Tentukan jadwal refresh kustom untuk ekspor individual atau beberapa ekspor sekaligus. Jadwal yang ditentukan saat ini tercantum di kolom **Jadwal** dari daftar ekspor. Izin untuk mengubah jadwal sama [dengan mengedit dan mendefinisikan ekspor](export-destinations.md#set-up-a-new-export).

1. Buka **Data** > **Ekspor**.

1. Pilih ekspor yang ingin dijadwalkan.

1. Pilih **jadwal**.

1. Di panel **Jadwalkan ekspor**, atur **Jadwal berjalan** ke **Aktif** untuk menjalankan ekspor secara otomatis. Atur ke **Nonaktif** untuk me-refresh secara manual.

1. Untuk ekspor yang di-refresh secara otomatis, pilih nilai **Pengulangan** dan tentukan rincian untuknya. Waktu yang ditentukan berlaku untuk semua instans pengulangan. Ini adalah waktu ketika ekspor harus mulai me-refresh.

1. Pilih **Simpan**.

Saat mengedit jadwal untuk beberapa ekspor, buat pilihan di bawah **Simpan atau ganti jadwal**:

- **Pertahankan jadwal** individual: Simpan jadwal yang ditentukan sebelumnya untuk ekspor yang dipilih dan hanya nonaktifkan atau aktifkan.
- **Menentukan jadwal baru untuk semua ekspor yang dipilih**: Menimpa jadwal yang ada dari ekspor yang dipilih.

### <a name="run-exports-on-demand"></a>Menjalankan ekspor Atas Permintaan

Untuk mengekspor data tanpa menunggu refresh terjadwal, buka **Data** > **Ekspor**.

- Untuk menjalankan semua ekspor, pilih **Jalankan semua** di bilah perintah. Hanya ekspor yang memiliki jadwal aktif yang dijalankan. Untuk menjalankan ekspor yang tidak aktif, jalankan satu ekspor.
- Untuk menjalankan satu ekspor, pilih ekspor dalam daftar, lalu pilih **Jalankan** di bilah perintah.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
