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
ms.openlocfilehash: aae49be4364676ecc7a307e60eeca13859f1662a
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934982"
---
# <a name="connect-to-a-power-query-data-source"></a>Terhubung ke Power Query sumber data

Power Query menawarkan satu set konektor yang luas untuk menelan data. Sebagian besar konektor ini didukung oleh Dynamics 365 Customer Insights. 

Menambahkan sumber data berdasarkan Power Query konektor umumnya mengikuti langkah-langkah yang diuraikan di bagian ini. Namun, tergantung pada konektor yang Anda gunakan, informasi yang berbeda diperlukan. Untuk mempelajari selengkapnya, lihat dokumentasi tentang konektor individual dalam [Power Query referensi konektor](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Buat sumber data baru

1. Di wawasan audiens, buka **Data** > **Sumber data**.

1. Pilih **Tambahkan sumber data**.

1. Pilih **Power Query** Microsoft, lalu pilih **Berikutnya**.

1. Berikan **nama** untuk sumber data, lalu pilih **berikutnya** untuk membuat sumber data.

1. Pilih salah satu dari [konektor yang tersedia](#available-power-query-data-sources). Dalam contoh ini, kami memilih **konektor Teks** /CSV.

1. Masukkan rincian yang diperlukan dalam **pengaturan sambungan** untuk konektor yang dipilih dan pilih **berikutnya** untuk melihat pratinjau data.

1. Pilih **Transformasi data**. Pada langkah ini, Anda akan menambahkan entitas ke sumber data. Entitas adalah dataset. Jika Anda memiliki database yang mencakup beberapa dataset, maka setiap himpunan data adalah entitas sendiri.

1. Dialog **Power Query - Edit kueri memungkinkan Anda meninjau dan memperbaiki** data. Entitas yang diidentifikasi dalam sumber data yang dipilih muncul di panel kiri.

   > [!div class="mx-imgBorder"]
   > ![Dialog Edit kueri.](media/data-manager-configure-edit-queries.png "Dialog Edit kueri")

1. Anda juga dapat mengubah data Anda. Pilih entitas untuk mengedit atau mengubah. Gunakan opsi di Power Query jendela untuk menerapkan transformasi. Setiap transformasi akan terdaftar di dalam **langkah yang diterapkan**. Power Query menyediakan banyak pilihan transformasi pra-dibangun. Untuk informasi lebih lanjut, lihat [Power Query](/power-query/power-query-what-is-power-query#transformations) Transformasi.

1. Anda dapat menambahkan entitas tambahan ke sumber data dengan memilih **dapatkan data**, dalam dialog **Edit kueri**.

   Kami menyarankan Anda untuk menggunakan transformasi berikut:

   - Jika Anda menyerap data dari file CSV, baris pertama sering berisi header. Buka **Transformasi tabel** dan pilih **Gunakan header sebagai baris pertama**.
   - Pastikan jenis data diatur dengan benar.

1. Pilih **Simpan di bagian bawah jendela untuk menyimpan** Power Query transformasi. Setelah menyimpan, anda akan menemukan sumber data anda di **Data** > **sumber data**.

1. Di halaman **sumber data**, anda akan melihat sumber data baru berada dalam status yang **Menyegarkan**.

## <a name="available-power-query-data-sources"></a>Power Query Sumber data yang tersedia

Lihat [Power Query referensi konektor](/power-query/connectors/) untuk daftar konektor yang dapat Anda gunakan untuk mengimpor data ke Wawasan Pelanggan. 

Konektor dengan tanda centang di **kolom Customer Insights (Dataflows)** tersedia untuk membuat sumber data baru berdasarkan Power Query. Tinjau dokumentasi konektor tertentu untuk mempelajari lebih lanjut tentang prasyarat, batasan, dan rincian lainnya.

## <a name="edit-power-query-data-sources"></a>Mengedit Power Query sumber data

> [!NOTE]
> Anda mungkin tidak dapat melakukan perubahan pada sumber data yang saat ini sedang digunakan di salah satu proses aplikasi *(segmentasi*, *kecocokan*, atau *penggabungan*, misalnya). 
>
> Di **halaman** Pengaturan, Anda dapat melacak kemajuan masing-masing proses aktif. Setelah proses selesai, Anda dapat kembali ke halaman **sumber data** dan melakukan perubahan.

1. Di wawasan audiens, buka **Data** > **Sumber data**.

2. Pilih elipsis vertikal di sebelah sumber data yang ingin Anda ubah, lalu pilih **Edit** dari menu dropdown.

   > [!div class="mx-imgBorder"]
   > ![Opsi edit.](media/edit-option-data-sources.png "Opsi edit")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Menerapkan perubahan dan transformasi Anda dalam **Power Query dialog - Edit kueri seperti yang dijelaskan di bagian Buat sumber data**[baru](#create-a-new-data-source).

4. Pilih **Simpan setelah menyelesaikan pengeditan untuk menyimpan perubahan** Power Query Anda.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
