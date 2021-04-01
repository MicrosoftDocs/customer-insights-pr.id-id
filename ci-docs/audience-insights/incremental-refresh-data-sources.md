---
title: Penyegaran tambahan untuk sumber data berbasis kueri daya
description: Refresh data baru dan yang diperbarui untuk sumber data besar berdasarkan Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 03f76bcfc7336d8430146e8a26ffa649c6a17db0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596825"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Penyegaran inkremental untuk sumber daya berbasis Power Query

Peningkatan refresh secara bertahap untuk sumber data memberikan keuntungan berikut:

- **Refresh lebih cepat** -hanya data yang telah diubah akan disegarkan. Misalnya, Anda mungkin hanya me-refresh lima hari terakhir dari kumpulan data historis.
- **Peningkatan keandalan** -dengan penyegaran lebih kecil, Anda tidak perlu memelihara koneksi ke sistem sumber volatil begitu lama, sehingga mengurangi risiko masalah koneksi.
- **Pengurangan konsumsi sumber daya** -menyegarkan hanya subset dari total data Anda yang menyebabkan penggunaan sumber daya komputasi lebih efisien dan mengurangi emisi lingkungan.

## <a name="configure-incremental-refresh"></a>Konfigurasikan refresh bertahap

Wawasan audiens memungkinkan refresh tambahan untuk sumber data yang diimpor melalui Power Query yang mendukung konsumsi inkremental. Misalnya, database Azure SQL dengan bidang tanggal dan waktu, yang menunjukkan Kapan rekaman data terakhir diperbarui.

1. [buat sumber data baru berdasarkan Power Query](connect-power-query.md).

1. Berikan nama untuk sumber data.

1. Pilih sumber data yang mendukung penyegaran tambahan, seperti database Azure SQL.

1. Pilih entitas atau tabel untuk diserap.

1. Selesaikan langkah transformasi dan pilih **berikutnya**.

1. Di kotak dialog **Atur penyegaran tambahan**, pilih **konfigurasi** untuk membuka **pengaturan penyegaran tambahan**. Jika anda memilih **lewati**, sumber data akan me-refresh seluruh himpunan data.
   > [!TIP]
   > Anda juga dapat menerapkan penyegaran tambahan nanti dengan mengedit sumber data yang ada.

1. Pada **pengaturanpenyegaran tambahan**, anda akan mengkonfigurasikan refresh tambahan untuk semua entitas yang anda pilih saat membuat sumber data.

   > [!div class="mx-imgBorder"]
   > ![konfigurasikan entitas di sumber data untuk penyegaran tambahan](media/incremental-refresh-settings.png "konfigurasikan entitas di sumber data untuk penyegaran tambahan")

1. Pilih entitas, dan berikan rincian berikut:

   - **Tentukan primary key**: Pilih primary key untuk entitas atau tabel.
   - **Tentukan bidang"terakhir diperbarui"**: bidang ini hanya akan menampilkan atribut jenis tanggal atau waktu. Pilih atribut yang menunjukkan Kapan rekaman terakhir diperbarui. Ini akan digunakan untuk mengidentifikasi rekaman yang berada dalam jangka waktu refresh tambahan.
   - **periksa pembaruan setiap**: tentukan berapa lama anda ingin jangka waktu refresh inkremental.

1. Pilih **simpan** untuk menyelesaikan pembuatan sumber data. Penyegaran data awal akan menjadi penyegaran penuh. Setelah itu, penyegaran data tambahan terjadi sebagaimana dikonfigurasi di langkah sebelumnya.


[!INCLUDE[footer-include](../includes/footer-banner.md)]