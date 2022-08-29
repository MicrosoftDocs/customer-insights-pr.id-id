---
title: Gambaran umum Ekspor (pratinjau)
description: Kelola ekspor untuk berbagi data.
ms.date: 08/12/2022
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
ms.openlocfilehash: c580b6c01e1b4ac6b095733193d86ebd0b4005f2
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304063"
---
# <a name="exports-preview-overview"></a>Gambaran umum Ekspor (pratinjau)

 Ekspor memungkinkan Anda untuk berbagi data tertentu dengan berbagai aplikasi. Mereka dapat mencakup profil pelanggan, entitas, skema, dan rincian pemetaan. Setiap ekspor memerlukan [koneksi, yang disiapkan oleh administrator, untuk mengelola autentikasi dan akses](connections.md). Halaman **Ekspor** memperlihatkan kepada Anda semua ekspor yang dikonfigurasi.

## <a name="export-types"></a>Jenis ekspor

Ada dua jenis utama ekspor:  

- **Ekspor data keluar memungkinkan** Anda mengekspor semua jenis entitas yang tersedia di Customer Insights. Entitas yang Anda pilih untuk ekspor akan diekspor dengan semua bidang data, metadata, skema, dan rincian pemetaan.
- **Ekspor segmen memungkinkan** Anda mengekspor entitas segmen dari Customer Insights. Untuk konsumen individu (B-to-C), segmen mewakili daftar profil pelanggan. Untuk bisnis (B-to-B), [segmen dapat mewakili daftar akun atau kontak](segment-builder.md#create-a-new-segment-with-segment-builder). Saat mengonfigurasi ekspor, Anda memilih bidang data yang disertakan, bergantung pada sistem target tempat Anda mengekspor data.

### <a name="export-segments"></a>Ekspor segmen

**Mengekspor segmen di lingkungan untuk akun bisnis (B to B) atau pelanggan individual (B to C)**  
Sebagian besar opsi ekspor mendukung kedua jenis lingkungan tersebut. Mengekspor segmen ke berbagai sistem target memiliki persyaratan khusus. 

**Segmentasi ekspor di lingkungan untuk konsumen perorangan (B to C)**  
- Segmen dalam konteks lingkungan untuk pelanggan individual dibangun pada entitas *profil pelanggan terpadu*. Setiap segmen yang memenuhi persyaratan sistem target (contoh: alamat email) dapat diekspor.

**Ekspor segmen di lingkungan untuk akun bisnis (B-ke-B)**  
- Segmen dalam konteks lingkungan untuk akun bisnis dibangun di atas *entitas akun* atau *entitas kontak*. Untuk mengekspor segmen akun sebagaimana adanya, sistem target harus mendukung segmen akun murni. Hal ini terjadi untuk [LinkedIn](export-linkedin-ads.md) bila Anda memilih pilihan **perusahaan** saat menentukan ekspor.
- Semua sistem target lainnya memerlukan bidang dari entitas kontak.
- Dengan dua jenis segmen (kontak dan akun), Customer Insights secara otomatis mengidentifikasi jenis segmen mana yang memenuhi syarat untuk diekspor berdasarkan sistem target. Misalnya, untuk sistem target yang berfokus pada kontak seperti Mailchimp, Customer Insights hanya memungkinkan Anda memilih segmen kontak untuk diekspor.

**Batas pada ekspor segmen**  
- Sistem target pihak ketiga dapat membatasi jumlah profil pelanggan yang dapat Anda ekspor. 
- Untuk pelanggan individual, Anda akan melihat jumlah aktual anggota segmen saat memilih segmen untuk ekspor. Anda akan mendapatkan peringatan jika suatu segmen terlalu besar. 
- Untuk akun bisnis, Anda akan melihat jumlah akun atau kontak tergantung pada segmennya. Anda akan mendapatkan peringatan jika segmennya terlalu besar. Melebihi batas hasil sistem target akan melewatkan ekspor.

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

Setiap ekspor yang Anda konfigurasikan memiliki jadwal refresh. Selama pembaruan, sistem mencari data baru atau yang diperbarui untuk disertakan dalam ekspor. Secara default, ekspor dijalankan sebagai bagian dari setiap [pembaruan sistem terjadwal](schedule-refresh.md). Anda dapat menyesuaikan jadwal refresh atau menonaktifkannya untuk menjalankan ekspor secara manual.

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

## <a name="troubleshooting"></a>Mengatasi Masalah

### <a name="segment-not-eligible-for-export"></a>Segmen yang tidak memenuhi syarat untuk diekspor

**Masalah** Dalam lingkungan akun bisnis, ekspor Anda gagal dengan pesan kesalahan: "Segmen berikut tidak memenuhi syarat untuk tujuan ekspor ini: '{nama segmen}'. Silakan pilih hanya segmen jenis ContactProfile dan coba lagi."

**Lingkungan Resolution** Customer Insights untuk akun bisnis diperbarui untuk mendukung segmen kontak selain segmen akun. Karena perubahan itu, ekspor yang membutuhkan detail kontak hanya berfungsi dengan segmen berdasarkan kontak.

1. [Buat segmen berdasarkan kontak](segment-builder.md) yang cocok dengan segmen yang Anda gunakan sebelumnya.

1. Setelah segmen kontak itu dijalankan, edit ekspor masing-masing dan pilih segmen baru.

1. Pilih **Simpan** untuk menyimpan konfigurasi atau **Simpan dan jalankan** untuk menguji ekspor ini segera.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
