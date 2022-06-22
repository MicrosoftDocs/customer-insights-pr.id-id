---
title: Menyerap data melalui Power Query konektor (berisi video)
description: Konektor untuk sumber data berdasarkan file Power Query.
ms.date: 05/09/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: b99c3b446e580f455f9678d54d9db414aea9b331
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011661"
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

1. Pilih **Transformasi data**. Pada langkah ini, Anda akan menambahkan entitas ke sumber data. Entitas adalah dataset. Jika Anda memiliki database yang mencakup beberapa dataset, maka setiap himpunan data adalah entitas sendiri.

1. Dialog **Power Query - Edit kueri** memungkinkan Anda meninjau dan memperbaiki data. Entitas yang diidentifikasi dalam sumber data yang dipilih muncul di panel kiri.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Dialog Edit kueri":::

1. Anda juga dapat mengubah data Anda. Pilih entitas untuk mengedit atau mengubah. Gunakan opsi di Power Query jendela untuk menerapkan transformasi. Setiap transformasi tercantum di bawah Langkah-langkah **yang** diterapkan. Power Query menyediakan banyak opsi transformasi yang dibuat sebelumnya. Untuk informasi selengkapnya, lihat [Power Query Transformasi](/power-query/power-query-what-is-power-query#transformations).

   Kami menyarankan Anda menggunakan transformasi berikut:

   - Jika Anda menyerap data dari file CSV, baris pertama sering berisi header. Buka **Transformasi dan pilih** Gunakan baris pertama sebagai **header**.
   - Pastikan jenis data diatur dengan benar. Misalnya, untuk bidang tanggal, pilih tipe tanggal.

1. Untuk menambahkan entitas tambahan ke sumber data Anda dalam **dialog Edit kueri**, buka **Beranda** dan pilih **Dapatkan data**. Ulangi langkah 6-10 hingga Anda menambahkan semua entitas untuk sumber data ini.

1. Pilih **Simpan**. Halaman **Sumber data** terbuka memperlihatkan sumber data baru dalam **status Refresh**.

### <a name="available-power-query-data-sources"></a>Sumber data yang Power Query tersedia

[Power Query Lihat referensi](/power-query/connectors/) konektor untuk daftar konektor yang dapat Anda gunakan untuk mengimpor data ke Customer Insights.

Konektor dengan tanda centang di **kolom Customer Insights (Aliran Data)** tersedia untuk membuat sumber data baru berdasarkan Power Query. Tinjau dokumentasi konektor tertentu untuk mempelajari selengkapnya tentang prasyarat, [batasan](/power-query/power-query-online-limits) kueri, dan detail lainnya.

## <a name="add-data-from-on-premises-data-sources"></a>Menambahkan data dari sumber data lokal

Menyerap data dari sumber data lokal didukung berdasarkan Microsoft Power Platform aliran data (PPDF). Anda dapat mengaktifkan aliran data di Customer Insights [dengan Microsoft Dataverse memberikan URL](create-environment.md) lingkungan saat menyiapkan lingkungan.

Sumber data yang dibuat setelah mengaitkan Dataverse lingkungan dengan Customer Insights menggunakan [Power Platform aliran](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) data secara default. Aliran data mendukung konektivitas lokal menggunakan gateway data. Anda dapat menghapus dan membuat ulang sumber data yang ada sebelum Dataverse lingkungan dikaitkan [menggunakan gateway](/data-integration/gateway/service-gateway-app) data lokal.

Gateway data dari lingkungan Power BI atau Power Apps yang ada akan terlihat dan Anda dapat menggunakan kembali di Customer Insights. Halaman sumber data menampilkan tautan untuk membuka lingkungan Microsoft Power Platform tempat Anda dapat melihat dan mengkonfigurasi gateway data lokal.

> [!IMPORTANT]
> Pastikan gateway Anda diperbarui ke versi terbaru. Anda dapat menginstal pembaruan dan mengonfigurasi ulang gateway dari prompt yang ditampilkan di layar gateway secara langsung atau [mengunduh versi](https://powerapps.microsoft.com/downloads/) terbaru. Jika Anda tidak menggunakan versi gateway terbaru, refresh aliran data gagal dengan pesan kesalahan seperti **Kata kunci tidak didukung: properti konfigurasi. Nama parameter: kata kunci**.

## <a name="edit-power-query-data-sources"></a>Mengedit Power Query sumber data

> [!NOTE]
> Anda mungkin tidak dapat melakukan perubahan pada sumber data yang saat ini sedang digunakan di salah satu proses aplikasi *(segmentasi*, *kecocokan*, atau *penggabungan*, misalnya).
>
> **Di halaman Pengaturan**, Anda dapat melacak kemajuan masing-masing proses aktif. Setelah proses selesai, Anda dapat kembali ke halaman **sumber data** dan melakukan perubahan.

1. Buka **Data** > **Sumber data**.

1. Di samping sumber data yang ingin Anda perbarui, pilih **Edit**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Terapkan perubahan dan transformasi Anda dalam **Power Query dialog - Edit kueri** seperti yang dijelaskan di [bagian Buat sumber data](#create-a-new-data-source) baru.

1. Pilih **Simpan** di Power Query setelah menyelesaikan pengeditan Anda untuk menyimpan perubahan Anda.
