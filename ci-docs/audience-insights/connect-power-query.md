---
title: Menelan data melalui konektor Power Query (Video)
description: Konektor untuk sumber data berdasarkan Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 38c447d80a25feca087ca9f110278b8401423018
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903844"
---
# <a name="connect-to-a-power-query-data-source"></a>Sambungkan ke sumber data Power Query

Power Query menawarkan seperangkat konektor yang luas untuk menyerap data. Sebagian besar konektor ini didukung oleh Dynamics 365 Customer Insights. 

Menambahkan sumber data berdasarkan konektor Power Query umumnya mengikuti langkah-langkah yang diuraikan di bagian ini. Namun, tergantung pada konektor yang Anda gunakan, informasi yang berbeda diperlukan. Untuk mempelajari selengkapnya, lihat dokumentasi tentang konektor individual dalam [referensi konektor Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Buat sumber data baru

1. Di wawasan audiens, buka **Data** > **Sumber data**.

1. Pilih **Tambahkan sumber data**.

1. Pilih **Microsoft Power Query, lalu pilih** **Berikutnya**.

1. Berikan **nama** untuk sumber data, lalu pilih **berikutnya** untuk membuat sumber data.

1. Pilih salah satu dari [konektor yang tersedia](#available-power-query-data-sources). Dalam contoh ini, kami memilih **konektor Teks** /CSV.

1. Masukkan rincian yang diperlukan dalam **pengaturan sambungan** untuk konektor yang dipilih dan pilih **berikutnya** untuk melihat pratinjau data.

1. Pilih **Transformasi data**. Pada langkah ini, Anda akan menambahkan entitas ke sumber data. Entitas adalah dataset. Jika Anda memiliki database yang mencakup beberapa dataset, maka setiap himpunan data adalah entitas sendiri.

1. Dialog **Power Query Edit kueri** memungkinkan anda meninjau dan menyempurnakan data. Entitas yang diidentifikasi dalam sumber data yang dipilih muncul di panel kiri.

   > [!div class="mx-imgBorder"]
   > ![Dialog Edit kueri.](media/data-manager-configure-edit-queries.png "Dialog Edit kueri")

1. Anda juga dapat mengubah data Anda. Pilih entitas untuk mengedit atau mengubah. Gunakan pilihan di jendela Power Query untuk menerapkan transformasi. Setiap transformasi akan terdaftar di dalam **langkah yang diterapkan**. Power Query menyediakan banyak pilihan transformasi yang telah dibuat sebelumnya. Lihat [Transformasi Power Query](/power-query/power-query-what-is-power-query#transformations) Untuk informasi lebih lanjut.

1. Anda dapat menambahkan entitas tambahan ke sumber data dengan memilih **dapatkan data**, dalam dialog **Edit kueri**.

   Kami menyarankan Anda untuk menggunakan transformasi berikut:

   - Jika Anda menyerap data dari file CSV, baris pertama sering berisi header. Buka **Transformasi tabel** dan pilih **Gunakan header sebagai baris pertama**.
   - Pastikan jenis data diatur dengan benar.

1. Pilih **Simpan** di bawah jendela Power Query untuk menyimpan transformasi. Setelah menyimpan, anda akan menemukan sumber data anda di **Data** > **sumber data**.

1. Di halaman **sumber data**, anda akan melihat sumber data baru berada dalam status yang **Menyegarkan**.

## <a name="available-power-query-data-sources"></a>Sumber data Power Query yang tersedia

Lihat [referensi konektor Power Query](/power-query/connectors/) untuk daftar konektor yang dapat Anda gunakan untuk mengimpor data ke Wawasan Pelanggan. 

Konektor dengan tanda centang di kolom **Customer Insights (aliran data)** tersedia untuk membuat sumber data baru berdasarkan Power query. Tinjau dokumentasi konektor tertentu untuk mempelajari lebih lanjut tentang prasyarat, batasan, dan rincian lainnya.

## <a name="edit-power-query-data-sources"></a>Edit sumber data Power Query

> [!NOTE]
> Anda mungkin tidak dapat melakukan perubahan pada sumber data yang saat ini sedang digunakan di salah satu proses aplikasi *(segmentasi*, *kecocokan*, atau *penggabungan*, misalnya). 
>
> Di **halaman** Pengaturan, Anda dapat melacak kemajuan masing-masing proses aktif. Setelah proses selesai, Anda dapat kembali ke halaman **sumber data** dan melakukan perubahan.

1. Di wawasan audiens, buka **Data** > **Sumber data**.

2. Pilih elipsis vertikal di sebelah sumber data yang ingin Anda ubah, lalu pilih **Edit** dari menu dropdown.

   > [!div class="mx-imgBorder"]
   > ![Opsi edit.](media/edit-option-data-sources.png "Opsi edit")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Terapkan perubahan dan transformasi anda di **dialog Power Query-Edit kueri** seperti yang dijelaskan di bagian [buat sumber data baru](#create-a-new-data-source).

4. Pilih **simpan** di Power Query setelah menyelesaikan pengeditan untuk menyimpan perubahan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
