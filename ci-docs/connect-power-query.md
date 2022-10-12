---
title: Menyambungkan ke Power Query sumber data (berisi video)
description: Menyerap data melalui Power Query konektor (berisi video).
ms.date: 09/29/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4cc7e57dfb0f8d050e91adc441c24e849882f5d8
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609894"
---
# <a name="connect-to-a-power-query-data-source"></a>Menyambungkan ke Power Query sumber data

Power Query menawarkan satu set konektor yang luas untuk menyerap data. Sebagian besar konektor ini didukung oleh Dynamics 365 Customer Insights.

Menambahkan sumber data berdasarkan Power Query konektor umumnya mengikuti langkah-langkah yang diuraikan di bagian ini. Namun, tergantung pada konektor yang Anda gunakan, informasi yang berbeda diperlukan. Untuk mempelajari selengkapnya, lihat dokumentasi tentang konektor individual dalam [Power Query referensi konektor](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Buat sumber data baru

1. Buka **Data** > **Sumber data**.

1. Pilih **Tambahkan sumber data**.

1. Pilih **Microsoft Power Query**.

1. **Berikan Nama** dan Deskripsi **opsional** untuk sumber data, dan pilih **Berikutnya**.

1. Pilih salah satu dari [konektor yang tersedia](#available-power-query-data-sources). Dalam contoh ini, kita memilih **konektor Text/CSV**.

1. Masukkan rincian yang diperlukan dalam **pengaturan sambungan** untuk konektor yang dipilih dan pilih **berikutnya** untuk melihat pratinjau data.

1. Pilih **Transformasi data**.

1. Tinjau dan perbaiki data Anda di **Power Query halaman - Edit kueri**. Entitas yang diidentifikasi dalam sumber data yang dipilih muncul di panel kiri.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Dialog Edit kueri":::

1. Ubah data Anda. Pilih entitas untuk mengedit atau mengubah. Gunakan opsi di Power Query jendela untuk menerapkan transformasi. Setiap transformasi tercantum di bawah Langkah-langkah **yang** diterapkan. Power Query menyediakan banyak [opsi transformasi](/power-query/power-query-what-is-power-query#transformations) yang dibuat sebelumnya.

   > [!IMPORTANT]
   > Kami menyarankan Anda menggunakan transformasi berikut:
   >
   > - Jika Anda menyerap data dari file CSV, baris pertama sering berisi header. Buka **Transformasi dan pilih** Gunakan baris pertama sebagai **header**.
   > - Pastikan tipe data diatur dengan tepat dan cocok dengan data. Misalnya, untuk bidang tanggal, pilih tipe tanggal.

1. Untuk menambahkan entitas tambahan ke sumber data Anda dalam **dialog Edit kueri**, buka **Beranda** dan pilih **Dapatkan data**. Ulangi langkah 5-10 hingga Anda menambahkan semua entitas untuk sumber data ini. Jika Anda memiliki database yang mencakup beberapa dataset, maka setiap himpunan data adalah entitas sendiri.

1. Pilih **Simpan**. Halaman **Sumber data** terbuka memperlihatkan sumber data baru dalam **status Refresh**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuat data dapat memakan waktu. Setelah refresh berhasil, data yang diserap dapat ditinjau dari [**halaman Entitas**](entities.md).

> [!CAUTION]
>
> - Sebuah sumber data berdasarkan Power Query membuat [aliran data di Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Jangan mengubah nama aliran data di Power Platform pusat admin yang digunakan di Customer Insights. Mengganti nama aliran data menyebabkan masalah dengan referensi antara sumber data Customer Insights dan Dataverse aliran data.
> - Evaluasi bersamaan untuk Power Query sumber data di Customer Insights memiliki batas refresh yang sama [seperti Aliran data di PowerBI.com](/power-query/power-query-online-limits#refresh-limits). Jika refresh data gagal karena mencapai batas evaluasi, sebaiknya sesuaikan jadwal refresh untuk setiap aliran data untuk memastikan sumber data tidak diproses secara bersamaan.

### <a name="available-power-query-data-sources"></a>Sumber data yang Power Query tersedia

[Power Query Lihat referensi](/power-query/connectors/) konektor untuk daftar konektor yang dapat Anda gunakan untuk mengimpor data ke Customer Insights.

Konektor dengan tanda centang di **kolom Customer Insights (Aliran Data)** tersedia untuk membuat sumber data baru berdasarkan Power Query. Tinjau dokumentasi konektor tertentu untuk mempelajari selengkapnya tentang prasyarat, [batasan](/power-query/power-query-online-limits) kueri, dan detail lainnya.

## <a name="add-data-from-on-premises-data-sources"></a>Menambahkan data dari sumber data lokal

Menyerap data dari sumber data lokal didukung berdasarkan Microsoft Power Platform aliran data (PPDF). Anda dapat mengaktifkan aliran data di Customer Insights [dengan Microsoft Dataverse memberikan URL](create-environment.md) lingkungan saat menyiapkan lingkungan.

Sumber data yang dibuat setelah mengaitkan Dataverse lingkungan dengan Customer Insights menggunakan [Power Platform aliran](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) data secara default. Aliran data mendukung konektivitas lokal menggunakan gateway data. Anda dapat menghapus dan membuat ulang sumber data yang ada sebelum Dataverse lingkungan dikaitkan [menggunakan gateway data lokal](/data-integration/gateway/service-gateway-app).

Gateway data dari lingkungan yang ada atau Power BI yang sudah ada Power Apps akan terlihat dan Anda dapat menggunakannya kembali di Customer Insights jika gateway data dan lingkungan Customer Insights berada di Wilayah Azure yang sama. Halaman sumber data menampilkan tautan untuk membuka lingkungan Microsoft Power Platform tempat Anda dapat melihat dan mengkonfigurasi gateway data lokal.

> [!IMPORTANT]
> Pastikan gateway Anda diperbarui ke versi terbaru. Anda dapat menginstal pembaruan dan mengonfigurasi ulang gateway dari prompt yang ditampilkan di layar gateway secara langsung atau [mengunduh versi](https://powerapps.microsoft.com/downloads/) terbaru. Jika Anda tidak menggunakan versi gateway terbaru, refresh aliran data gagal dengan pesan kesalahan seperti **Kata kunci tidak didukung: properti konfigurasi. Nama parameter: kata kunci**.
>
> Kesalahan dengan gateway data lokal di Customer Insights sering disebabkan oleh masalah konfigurasi. Untuk informasi selengkapnya tentang pemecahan masalah gateway data, lihat [Memecahkan masalah gateway](/data-integration/gateway/service-gateway-tshoot) data lokal.

## <a name="edit-power-query-data-sources"></a>Mengedit Power Query sumber data

> [!NOTE]
> Mungkin tidak mungkin membuat perubahan pada sumber data yang saat ini sedang digunakan dalam salah satu proses aplikasi (segmentasi atau penyatuan data misalnya).
>
> **Di halaman Pengaturan**, Anda dapat melacak kemajuan masing-masing proses aktif. Setelah proses selesai, Anda dapat kembali ke halaman **sumber data** dan melakukan perubahan.

1. Buka **Data** > **Sumber data**.

1. Di samping sumber data yang ingin Anda perbarui, pilih **Edit**.

1. Terapkan perubahan dan transformasi Anda dalam **Power Query dialog - Edit kueri** seperti yang dijelaskan di [bagian Buat sumber data](#create-a-new-data-source) baru.

1. Pilih **Simpan** untuk menerapkan perubahan Anda dan kembali ke **halaman Sumber** data.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupt-data"></a>Alasan umum untuk kesalahan penyerapan atau data yang rusak

### <a name="data-type-does-not-match-data"></a>Tipe data tidak cocok dengan data

Ketidakcocokan tipe data yang paling umum terjadi ketika bidang tanggal tidak diatur ke format tanggal yang benar.

Data dapat diperbaiki di sumbernya dan diserap kembali. Atau perbaiki transformasi dalam Customer Insights. Untuk memperbaiki transformasi:

1. Buka **Data** > **Sumber data**.

1. Di samping sumber data dengan data yang rusak, pilih **Edit**.

1. Pilih **Selanjutnya**.

1. Pilih setiap kueri dan cari transformasi yang diterapkan di dalam "Langkah Yang Diterapkan" yang salah, atau kolom tanggal yang belum diubah dengan format tanggal.

   :::image type="content" source="media/PQ_corruped_date.png" alt-text="Power Query- Edit menunjukkan format tanggal yang salah":::

1. Ubah tipe data agar cocok dengan data dengan benar.

1. Pilih **Simpan**. Itu sumber data disegarkan.

## <a name="troubleshoot-ppdf-power-query-based-data-source-refresh-issues"></a>Memecahkan masalah refresh sumber data berbasis PPDF Power Query

Jika data kedaluwarsa atau Anda menerima kesalahan setelah refresh sumber data, lakukan langkah-langkah berikut:

1. Navigasikan ke [Power Platform](https://make.powerapps.com).

1. **Pilih instans Environment** for your Customer Insights.

1. Navigasikan ke **Aliran** Data.

1. Untuk aliran data yang sesuai dengan sumber data di Customer Insights, pilih elipsis vertikal (&vellip;) lalu pilih **Tampilkan riwayat** refresh.

1. **Jika Status** aliran data adalah **Sukses**, kepemilikan Power Query sumber data berbasis -mungkin telah berubah:

   1. Tinjau jadwal refresh dari riwayat refresh.
   1. Atur jadwal pemilik baru dan simpan pengaturan.

1. **Jika Status** aliran **data Gagal**:

   1. Unduh file riwayat refresh.
   1. Tinjau file yang diunduh untuk alasan kegagalan.
   1. Jika kesalahan tidak dapat diatasi, pilih **?** Untuk membuka tiket dukungan. Sertakan file riwayat refresh yang diunduh.


[!INCLUDE [footer-include](includes/footer-banner.md)]
