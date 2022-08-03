---
title: Refresh inkremental untuk Power Query dan sumber data Azure Data Lake
description: Refresh data baru dan yang diperbarui untuk sumber data besar berdasarkan Power Query atau sumber data danau data Azure.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: de39743eb8728fac34e417724c5f73bf44309c89
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207141"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Refresh inkremental untuk Power Query dan sumber data Azure Data Lake

Refresh inkremental untuk sumber data berdasarkan Power Query atau Azure Data Lake memberikan keuntungan berikut:

- **Refresh lebih cepat** -hanya data yang telah diubah akan disegarkan. Misalnya, Anda mungkin hanya me-refresh lima hari terakhir dari kumpulan data historis.
- **Peningkatan keandalan** -dengan penyegaran lebih kecil, Anda tidak perlu memelihara koneksi ke sistem sumber volatil begitu lama, sehingga mengurangi risiko masalah koneksi.
- **Pengurangan konsumsi sumber daya** -menyegarkan hanya subset dari total data Anda yang menyebabkan penggunaan sumber daya komputasi lebih efisien dan mengurangi emisi lingkungan.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Mengonfigurasi refresh inkremental untuk sumber data berdasarkan Power Query

Customer Insights memungkinkan refresh inkremental untuk sumber data yang diimpor melalui Power Query yang mendukung penyerapan inkremental. Misalnya, database Azure SQL dengan bidang tanggal dan waktu, yang menunjukkan Kapan rekaman data terakhir diperbarui.

1. [Buat sumber data baru berdasarkan file Power Query](connect-power-query.md).

1. Pilih sumber data yang mendukung refresh inkremental, seperti [database Azure SQL](/power-query/connectors/azuresqldatabase).

1. Pilih entitas atau tabel untuk diserap.

1. Selesaikan langkah transformasi dan pilih **berikutnya**.

1. Di kotak dialog **Atur penyegaran tambahan**, pilih **konfigurasi** untuk membuka **pengaturan penyegaran tambahan**. Jika anda memilih **lewati**, sumber data akan me-refresh seluruh himpunan data.
   > [!TIP]
   > Anda juga dapat menerapkan penyegaran tambahan nanti dengan mengedit sumber data yang ada.

1. Pada **pengaturanpenyegaran tambahan**, anda akan mengkonfigurasikan refresh tambahan untuk semua entitas yang anda pilih saat membuat sumber data.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurasikan pengaturan refresh inkremental.":::

1. Pilih entitas, dan berikan rincian berikut:

   - **Tentukan primary key**: Pilih primary key untuk entitas atau tabel.
   - **Tentukan bidang"terakhir diperbarui"**: bidang ini hanya akan menampilkan atribut jenis tanggal atau waktu. Pilih atribut yang menunjukkan Kapan rekaman terakhir diperbarui. Ini akan digunakan untuk mengidentifikasi rekaman yang berada dalam jangka waktu refresh tambahan.
   - **periksa pembaruan setiap**: tentukan berapa lama anda ingin jangka waktu refresh inkremental.

1. Pilih **simpan** untuk menyelesaikan pembuatan sumber data. Penyegaran data awal akan menjadi penyegaran penuh. Setelah itu, penyegaran data tambahan terjadi sebagaimana dikonfigurasi di langkah sebelumnya.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Mengonfigurasi refresh inkremental untuk sumber data Azure Data Lake

Customer Insights memungkinkan refresh inkremental untuk sumber data yang terhubung ke Azure Data Lake Storage. Untuk menggunakan penyerapan dan refresh inkremental untuk entitas, konfigurasikan entitas tersebut saat menambahkan azure Data Lake sumber data atau yang lebih baru saat mengedit sumber data. Folder data entitas harus berisi folder berikut:

- **FullData**: Folder dengan file data yang berisi rekaman awal
- **IncrementalData**: Folder dengan folder hierarki tanggal/waktu dalam **format yyyy/mm/dd/hh** yang berisi pembaruan inkremental. **hh** mewakili jam UTC pembaruan dan berisi **folder Upserts** dan **Deletes**. **Upsert** berisi file data dengan pembaruan pada rekaman yang sudah ada atau catatan baru. **Penghapusan** berisi file data dengan catatan yang akan dihapus.

1. Saat menambahkan atau mengedit sumber data, navigasikan ke **panel Atribut** untuk entitas tersebut.

1. Tinjau atribut. Pastikan atribut tanggal yang dibuat atau terakhir diperbarui diatur dengan *format Data dateTime* **dan** tipe *Semantik* Calendar.Date **·**. Edit atribut jika perlu dan pilih **Selesai**.

1. **Dari panel Pilih Entitas**, edit entitas. Kotak **centang Penyerapan** inkremental dipilih.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="konfigurasikan entitas di sumber data untuk penyegaran tambahan.":::

   1. Telusuri ke folder akar yang berisi file .csv atau .parquet untuk data lengkap, peningkatan data inkremental, dan penghapusan data inkremental.
   1. Masukkan ekstensi untuk data lengkap dan kedua file inkremental (\. csv atau \. parket).
   1. Untuk file .csv, pilih pembatas kolom dan jika Anda menginginkan baris pertama file sebagai header kolom.
   1. Pilih **Simpan**.

1. Untuk **Terakhir diperbarui**, pilih atribut stempel waktu tanggal.

1. Jika kunci **Utama** tidak dipilih, pilih kunci utama. Kunci utama adalah atribut yang unik untuk entitas. Agar atribut menjadi kunci primer yang valid, ia seharusnya tidak menyertakan nilai duplikat, nilai yang tidak ada, atau nilai null. Atribut tipe data string, integer, dan GUID didukung sebagai kunci utama.

1. Pilih **Tutup** untuk menyimpan dan menutup panel.

1. Lanjutkan dengan menambahkan atau mengedit sumber data.

[!INCLUDE [footer-include](includes/footer-banner.md)]
