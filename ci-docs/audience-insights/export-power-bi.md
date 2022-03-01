---
title: Konektor Power BI
description: Pelajari cara menggunakan konektor Dynamics 365 Customer Insights di Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406040"
---
# <a name="connector-for-power-bi-preview"></a>Konektor untuk Power BI (pratinjau)

Buat visualisasi untuk data Anda dengan Power BI Desktop. Buat wawasan tambahan dan Buat laporan dengan data pelanggan terpadu Anda.

## <a name="prerequisites"></a>Prasyarat

- Anda memiliki profil pelanggan terpadu.
- Versi terbaru [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) terinstal di komputer Anda. [Pelajari lebih lanjut tentang Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konfigurasikan konektor untuk Power BI

1. Di Power BI Desktop, pilih **file** > **Dapatkan data**.

1. Pilih **Lihat lainnya** dan Cari **Dynamics 365 Customer Insights**

1. Pilih hasil, lalu pilih **Sambungkan**.

1. **masuk** dengan akun organisasi yang sama yang Anda gunakan untuk Customer Insights dan pilih **Sambungkan**.
   > [!NOTE]
   > Akun yang Anda tunjukkan dalam langkah ini digunakan untuk mengambil data dari Customer Insights dan tidak perlu sama dengan yang Anda gunakan untuk masuk ke Power BI. Untuk mengatur ulang akun yang digunakan untuk pengambilan data, buka Power BI dan buka **File** > **pilihan** > **pengaturan** > **pengaturan sumber data**. Di daftar sumber data, pilih **Login Dynamics 365 Customer Insights** dan pilih **izin yang jelas**.  

1. Di kotak dialog **Navigator**. Anda akan melihat daftar semua lingkungan yang dapat Anda akses. Perluas lingkungan dan buka folder apa pun (entitas, langkah-langkah, segmen, pengayaan). Misalnya, buka folder **entitas**, untuk melihat semua entitas yang dapat diimpor.

   ![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")

1. Pilih kotak centang di samping entitas untuk mencakup dan **memuat**. Anda dapat memilih beberapa entitas dari beberapa lingkungan.

1. Anda akan melihat kotak dialog pemuatan saat entitas Anda dimuat. Setelah semua entitas yang dipilih telah dimuat, Anda dapat menggunakan kemampuan Power BI untuk memvisualisasikan data.

## <a name="large-data-sets"></a>himpunan data besar

Customer Insights connector untuk Power BI dirancang untuk berfungsi untuk himpunan data yang berisi 1 juta profil pelanggan. Mengimpor kumpulan data yang lebih besar mungkin berfungsi, namun memerlukan waktu lama. Selain itu, proses dapat berjalan ke batas waktu karena keterbatasan Power BI. Untuk informasi lebih lanjut, lihat [Power BI : rekomendasi untuk himpunan data besar](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Bekerja dengan subset data

Pertimbangkan untuk bekerja dengan subset data Anda. Misalnya, Anda dapat membuat [segmen](segments.md) dan bukan mengekspor semua rekaman pelanggan ke Power BI.
