---
title: Penyegaran inkremental untuk Power Query sumber data berbasis
description: Refresh data baru dan terbaru untuk sumber data besar berdasarkan Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 62632efda3c0c7e53fcdd8864b053ba93e2918bc
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353686"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Penyegaran inkremental untuk sumber data berdasarkan Power Query

Artikel ini membahas cara mengonfigurasi refresh inkremental untuk sumber data berdasarkan Power Query.

Peningkatan refresh secara bertahap untuk sumber data memberikan keuntungan berikut:

- **Refresh lebih cepat** -hanya data yang telah diubah akan disegarkan. Misalnya, Anda mungkin hanya me-refresh lima hari terakhir dari kumpulan data historis.
- **Peningkatan keandalan** -dengan penyegaran lebih kecil, Anda tidak perlu memelihara koneksi ke sistem sumber volatil begitu lama, sehingga mengurangi risiko masalah koneksi.
- **Pengurangan konsumsi sumber daya** -menyegarkan hanya subset dari total data Anda yang menyebabkan penggunaan sumber daya komputasi lebih efisien dan mengurangi emisi lingkungan.

## <a name="configure-incremental-refresh"></a>Konfigurasikan refresh bertahap

Audiens wawasan memungkinkan penyegaran tambahan untuk sumber data yang diimpor melalui Power Query dukungan penyerapan inkremental tersebut. Misalnya, database Azure SQL dengan bidang tanggal dan waktu, yang menunjukkan Kapan rekaman data terakhir diperbarui.

1. [Buat sumber data baru berdasarkan Power Query](connect-power-query.md).

1. **Berikan nama** untuk sumber data.

1. Pilih sumber data yang mendukung refresh inkremental, seperti [database](/power-query/connectors/azuresqldatabase) Azure SQL.

1. Pilih entitas atau tabel untuk diserap.

1. Selesaikan langkah transformasi dan pilih **berikutnya**.

1. Di kotak dialog **Atur penyegaran tambahan**, pilih **konfigurasi** untuk membuka **pengaturan penyegaran tambahan**. Jika anda memilih **lewati**, sumber data akan me-refresh seluruh himpunan data.
   > [!TIP]
   > Anda juga dapat menerapkan penyegaran tambahan nanti dengan mengedit sumber data yang ada.

1. Pada **pengaturanpenyegaran tambahan**, anda akan mengkonfigurasikan refresh tambahan untuk semua entitas yang anda pilih saat membuat sumber data.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="konfigurasikan entitas di sumber data untuk penyegaran tambahan.":::

1. Pilih entitas, dan berikan rincian berikut:

   - **Tentukan primary key**: Pilih primary key untuk entitas atau tabel.
   - **Tentukan bidang"terakhir diperbarui"**: bidang ini hanya akan menampilkan atribut jenis tanggal atau waktu. Pilih atribut yang menunjukkan Kapan rekaman terakhir diperbarui. Ini akan digunakan untuk mengidentifikasi rekaman yang berada dalam jangka waktu refresh tambahan.
   - **periksa pembaruan setiap**: tentukan berapa lama anda ingin jangka waktu refresh inkremental.

1. Pilih **simpan** untuk menyelesaikan pembuatan sumber data. Penyegaran data awal akan menjadi penyegaran penuh. Setelah itu, penyegaran data tambahan terjadi sebagaimana dikonfigurasi di langkah sebelumnya.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
