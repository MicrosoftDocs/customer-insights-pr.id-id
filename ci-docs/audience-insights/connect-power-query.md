---
title: Serap data melalui Power Query connector
description: Konektor untuk sumber data berdasarkan Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d51a7efa5fd9f7336d1662500eb804a674738493
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267773"
---
# <a name="connect-to-a-power-query-data-source"></a>Sambungkan ke sumber data Power Query

Power Query menawarkan seperangkat konektor yang luas untuk menyerap data. Sebagian besar konektor ini didukung oleh Dynamics 365 Customer Insights. Menambahkan sumber data berdasarkan Power Query connectors biasanya mengikuti langkah yang diuraikan di bagian berikutnya. Namun, tergantung pada konektor yang Anda gunakan, informasi yang berbeda diperlukan. Untuk informasi lebih lanjut, lihat dokumentasi tentang konektor individual di [Power Query connector](https://docs.microsoft.com/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Buat sumber data baru

1. Di wawasan audiens, buka **Data** > **Sumber data**.

1. Pilih **Tambahkan sumber data**.

1. Pilih metode **impor data** dan pilih **berikutnya**.

1. Berikan **nama** untuk sumber data, lalu pilih **berikutnya** untuk membuat sumber data. Panduan nama: 
   - Diawali dengan huruf.
   - Gunakan huruf dan angka saja. Spasi atau karakter khusus tidak dibolehkan.
   - Gunakan antara 3 hingga 64 karakter.

1. Pilih salah satu dari [konektor yang tersedia](#available-power-query-data-sources). Untuk contoh ini, kita pilih konektor **teks/CSV**.

1. Masukkan rincian yang diperlukan dalam **pengaturan sambungan** untuk konektor yang dipilih dan pilih **berikutnya** untuk melihat pratinjau data.

1. Pilih **Transformasi data**. Pada langkah ini, Anda akan menambahkan entitas ke sumber data. Entitas adalah dataset. Jika Anda memiliki database yang mencakup beberapa dataset, maka setiap himpunan data adalah entitas sendiri.

1. Dialog **Power Query Edit kueri** memungkinkan anda meninjau dan menyempurnakan data. Entitas yang diidentifikasi dalam sumber data yang dipilih muncul di panel kiri.

   > [!div class="mx-imgBorder"]
   > ![Dialog Edit kueri](media/data-manager-configure-edit-queries.png "Dialog Edit kueri")

1. Anda juga dapat mengubah data Anda. Pilih entitas untuk mengedit atau mengubah. Gunakan pilihan di jendela Power Query untuk menerapkan transformasi. Setiap transformasi akan terdaftar di dalam **langkah yang diterapkan**. Power Query menyediakan banyak pilihan transformasi yang telah dibuat sebelumnya. Lihat [Transformasi Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations) Untuk informasi lebih lanjut.

1. Anda dapat menambahkan entitas tambahan ke sumber data dengan memilih **dapatkan data**, dalam dialog **Edit kueri**.

   Transformasi ini sangat dianjurkan:

   - Jika Anda menyerap data dari file CSV, baris pertama sering berisi header. Buka **Transformasi tabel** dan pilih **Gunakan header sebagai baris pertama**.
   - Pastikan jenis data diatur dengan benar.

1. Pilih **Simpan** di bawah jendela Power Query untuk menyimpan transformasi. Setelah menyimpan, anda akan menemukan sumber data anda di **Data** > **sumber data**.

1. Di halaman **sumber data**, anda akan melihat sumber data baru berada dalam status yang **Menyegarkan**.

## <a name="available-power-query-data-sources"></a>Sumber data Power Query yang tersedia

Lihat referensi [Power Query connector](https://docs.microsoft.com/power-query/connectors/) untuk daftar konektor terkini yang dapat Anda pilih untuk mengimpor data ke Customer Insights. 

Konektor dengan tanda centang di kolom **Customer Insights (aliran data)** tersedia untuk membuat sumber data baru berdasarkan Power query. Tinjau dokumentasi konektor tertentu untuk mempelajari lebih lanjut tentang prasyarat, batasan, dan rincian lainnya.

## <a name="edit-power-query-data-sources"></a>Edit sumber data Power Query

> [!NOTE]
> Anda mungkin tidak dapat melakukan perubahan pada sumber data yang saat ini sedang digunakan di salah satu proses aplikasi *(segmentasi*, *kecocokan*, atau *penggabungan*, misalnya). 
>
> Dengan menggunakan halaman **pengaturan**, Anda dapat melacak progres setiap proses aktif. Setelah proses selesai, Anda dapat kembali ke halaman **sumber data** dan melakukan perubahan.

1. Di wawasan audiens, buka **Data** > **Sumber data**.

2. Pilih elipsis vertikal di sebelah sumber data yang akan diubah dan pilih **Edit** dari menu drop-down.

   > [!div class="mx-imgBorder"]
   > ![Opsi edit](media/edit-option-data-sources.png "Opsi edit")

3. Terapkan perubahan dan transformasi anda di **dialog Power Query-Edit kueri** seperti yang dijelaskan di bagian [buat sumber data baru](#create-a-new-data-source).

4. Pilih **simpan** di Power Query setelah menyelesaikan pengeditan untuk menyimpan perubahan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]