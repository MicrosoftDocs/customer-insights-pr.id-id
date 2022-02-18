---
title: Menelan data melalui Power Query konektor (berisi video)
description: Konektor untuk sumber data berdasarkan Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 727cb9a4d754b6dbd74d6ecab1b183d41f713d8f
ms.sourcegitcommit: aadee829eff111c95eb30c0a97a68dcc87994acf
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/04/2022
ms.locfileid: "8092076"
---
# <a name="connect-to-a-power-query-data-source"></a>Menyambungkan ke Power Query sumber data

Power Query menawarkan serangkaian konektor yang luas untuk menelan data. Sebagian besar konektor ini didukung oleh Dynamics 365 Customer Insights. 

Menambahkan sumber data berdasarkan Power Query konektor umumnya mengikuti langkah-langkah yang diuraikan di bagian ini. Namun, tergantung pada konektor yang Anda gunakan, informasi yang berbeda diperlukan. Untuk mempelajari selengkapnya, lihat dokumentasi tentang konektor individual dalam [Power Query referensi konektor](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Buat sumber data baru

1. Di wawasan audiens, buka **Data** > **Sumber data**.

1. Pilih **Tambahkan sumber data**.

1. Pilih **Microsoft Power Query**.

1. Berikan **nama** untuk sumber data, lalu pilih **berikutnya** untuk membuat sumber data.

1. Pilih salah satu dari [konektor yang tersedia](#available-power-query-data-sources). Dalam contoh ini, kita memilih **konektor Text/CSV**.

1. Masukkan rincian yang diperlukan dalam **pengaturan sambungan** untuk konektor yang dipilih dan pilih **berikutnya** untuk melihat pratinjau data.

1. Pilih **Transformasi data**. Pada langkah ini, Anda akan menambahkan entitas ke sumber data. Entitas adalah dataset. Jika Anda memiliki database yang mencakup beberapa dataset, maka setiap himpunan data adalah entitas sendiri.

1. Dialog **Power Query - Edit kueri** memungkinkan Anda meninjau dan memperbaiki data. Entitas yang diidentifikasi dalam sumber data yang dipilih muncul di panel kiri.

   > [!div class="mx-imgBorder"]
   > ![Dialog Edit kueri.](media/data-manager-configure-edit-queries.png "Dialog Edit kueri")

1. Anda juga dapat mengubah data Anda. Pilih entitas untuk mengedit atau mengubah. Gunakan opsi di Power Query jendela untuk menerapkan transformasi. Setiap transformasi akan terdaftar di dalam **langkah yang diterapkan**. Power Query menyediakan banyak opsi transformasi pra-bangun. Untuk informasi selengkapnya, lihat [Power Query Transformasi](/power-query/power-query-what-is-power-query#transformations).

   Kami menyarankan Anda menggunakan transformasi berikut:

   - Jika Anda menyerap data dari file CSV, baris pertama sering berisi header. **Buka Mengubah** dan memilih **Gunakan baris pertama sebagai header**.
   - Pastikan jenis data diatur dengan benar. Misalnya, untuk bidang tanggal, pilih jenis tanggal.

1. Untuk menambahkan entitas tambahan ke sumber data Anda dalam **dialog Edit kueri**, buka **Beranda** dan pilih **Dapatkan data**.

1. Pilih **Simpan** di bagian Power Query bawah jendela untuk menyimpan transformasi. Setelah menyimpan, anda akan menemukan sumber data anda di **Data** > **sumber data**.

1. Di halaman **sumber data**, anda akan melihat sumber data baru berada dalam status yang **Menyegarkan**.

## <a name="available-power-query-data-sources"></a>Sumber data yang tersedia Power Query

[Power Query Lihat referensi](/power-query/connectors/) konektor untuk daftar konektor yang dapat Anda gunakan untuk mengimpor data ke Wawasan Pelanggan. 

Konektor dengan tanda centang di **kolom Wawasan Pelanggan (Aliran Data)** tersedia untuk membuat sumber data baru berdasarkan Power Query. Tinjau dokumentasi konektor tertentu untuk mempelajari lebih lanjut tentang prasyarat, batasan, dan rincian lainnya.

## <a name="edit-power-query-data-sources"></a>Mengedit Power Query sumber data

> [!NOTE]
> Anda mungkin tidak dapat melakukan perubahan pada sumber data yang saat ini sedang digunakan di salah satu proses aplikasi *(segmentasi*, *kecocokan*, atau *penggabungan*, misalnya). 
>
> **Di halaman Pengaturan**, Anda dapat melacak kemajuan masing-masing proses aktif. Setelah proses selesai, Anda dapat kembali ke halaman **sumber data** dan melakukan perubahan.

1. Di wawasan audiens, buka **Data** > **Sumber data**.

2. Pilih elipsis vertikal di sebelah sumber data yang ingin Anda ubah, lalu pilih **Edit** dari menu dropdown.

   > [!div class="mx-imgBorder"]
   > ![Opsi edit.](media/edit-option-data-sources.png "Opsi edit")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Terapkan perubahan dan transformasi Anda dalam **Power Query dialog - Edit kueri** seperti yang dijelaskan di [bagian Buat sumber data](#create-a-new-data-source) baru.

4. Pilih **Simpan** Power Query setelah menyelesaikan pengeditan untuk menyimpan perubahan Anda.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
