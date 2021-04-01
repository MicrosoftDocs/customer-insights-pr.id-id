---
title: Konektor Power BI
description: Pelajari cara menggunakan konektor Dynamics 365 Customer Insights di Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596043"
---
# <a name="connector-for-power-bi-preview"></a>Konektor untuk Power BI (pratinjau)

Buat visualisasi untuk data Anda dengan Power BI Desktop. Buat wawasan tambahan dan Buat laporan dengan data pelanggan terpadu Anda.

## <a name="prerequisites"></a>Prasyarat

- Anda memiliki profil pelanggan terpadu.
- versi terbaru [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) telah diinstal di komputer Anda. [Pelajari lebih lanjut tentang Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurasikan konektor untuk Power BI

1. Di Power BI Desktop, pilih **file** > **Dapatkan data**.

1. Pilih **Lihat lainnya** dan Cari **Dynamics 365 Customer Insights**

1. Pilih **Sambungkan**.

1. **masuk** dengan akun organisasi yang sama yang Anda gunakan untuk Customer Insights dan pilih **Sambungkan**.
   > [!NOTE]
   > Akun yang Anda tunjukkan dalam langkah ini digunakan untuk mengambil data dari Customer Insights dan tidak perlu sama dengan yang Anda gunakan untuk masuk ke Power BI. Untuk mengatur ulang akun yang digunakan untuk pengambilan data, buka Power BI dan buka **File** > **pilihan** > **pengaturan** > **pengaturan sumber data**. Di daftar sumber data, pilih **Login Dynamics 365 Customer Insights** dan pilih **izin yang jelas**.  

1. Di kotak dialog **Navigator**. Anda akan melihat daftar semua lingkungan yang dapat Anda akses. Perluas lingkungan dan buka folder apa pun (entitas, langkah-langkah, segmen, pengayaan). Misalnya, buka folder **entitas**, untuk melihat semua entitas yang dapat diimpor.

   ![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")

1. Pilih kotak centang di samping entitas untuk mencakup dan **memuat**. Anda dapat memilih beberapa entitas dari beberapa lingkungan.

1. Anda akan melihat kotak dialog pemuatan saat entitas Anda dimuat. Setelah semua entitas yang dipilih telah dimuat, Anda dapat menggunakan kemampuan Power BI untuk memvisualisasikan data.

## <a name="large-data-sets"></a>himpunan data besar

Customer Insights connector untuk Power BI dirancang untuk berfungsi untuk himpunan data yang berisi 1 juta profil pelanggan. Mengimpor kumpulan data yang lebih besar mungkin berfungsi, namun memerlukan waktu lama. Selain itu, proses dapat berjalan ke batas waktu karena keterbatasan Power BI. Untuk informasi lebih lanjut, lihat [Power BI : rekomendasi untuk himpunan data besar](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Bekerja dengan subset data

Pertimbangkan untuk bekerja dengan subset data Anda. Misalnya, Anda dapat membuat [segmen](segments.md) dan bukan mengekspor semua rekaman pelanggan ke Power BI.

## <a name="troubleshooting"></a>Mengatasi Masalah

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Lingkungan Customer Insights tidak ditampilkan di Power BI

Lingkungan yang memiliki lebih dari satu [relasi](relationships.md) yang didefinisikan antara dua entitas yang sama di wawasan audiens tidak akan tersedia di Power BI connector.

Anda dapat mengidentifikasi dan menghilangkan duplikat Relasi.

1. Secara audiens, buka **Data** > **Relasi** tentang lingkungan yang Anda lewatkan di Power BI.
2. Identifikasikan duplikat Relasi:
   - Periksa apakah ada lebih dari satu relasi yang didefinisikan antara dua entitas yang sama.
   - Periksa apakah ada relasi yang dibuat antara dua entitas yang tercakup dalam proses penyatuan. Terdapat relasi implisit yang didefinisikan antara semua entitas yang tercakup dalam proses penyatuan.
3. Hilangkan duplikat Relasi yang diidentifikasi.

Setelah penghapusan duplikat Relasi, coba untuk mengkonfigurasi Power BI connector lagi. Lingkungan seharusnya tersedia sekarang.

[!INCLUDE[footer-include](../includes/footer-banner.md)]