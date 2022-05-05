---
title: Menggunakan profil terpadu di Dynamics 365 Marketing
description: Pelajari cara mengintegrasikan profil dan segmen terpadu dengan Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 45c59465771e4ad25ed36d5da1568e67b94cf994
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653794"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Bekerja dengan profil pelanggan terpadu di Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) meningkatkan pengalaman pelanggan, memungkinkan Anda untuk mengatur perjalanan yang dipersonalisasi di semua titik kontak untuk memperkuat Relasi dan mendapatkan loyalitas. Aplikasi Dynamics 365 Marketing bekerja dengan mulus dengan Dynamics 365 Sales, Dynamics 365 Customer Insights,, Microsoft Teams dan produk lainnya dan memungkinkan Anda untuk membuat keputusan yang lebih cepat dan lebih baik menggunakan kekuatan data dan AI.

Dengan menghubungkan data Customer Insights dengan Marketing, Anda dapat:

- Targetkan profil dan segmen pelanggan terpadu. Ini memungkinkan Anda untuk melibatkan setiap pelanggan, terlepas dari lokasi data pelanggan.
- Konten dinamis dasar (seperti token yang dipersonalisasi) dalam email, SMS, dan pemberitahuan push tentang langkah-langkah seperti status loyalitas, tanggal perpanjangan langganan, akun induk, atau tindakan lain apa pun yang telah Anda ambil di profil Customer Insights terpadu.
- Muat data dari Pemasaran ke dalam Wawasan Pelanggan dan gabungkan dengan data pelanggan dari sumber lain.
- Terapkan pembersihan data, pengayaan, dan alat pencocokan fuzzy Customer Insights.


## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Gunakan profil pelanggan yang kaya dalam pemasaran real-time

Pemasaran real-time memungkinkan Anda membuat [pemicu](/dynamics365/marketing/real-time-marketing-custom-triggers) khusus yang meluncurkan perjalanan pelanggan berdasarkan tindakan pelanggan apa pun. Semakin personal data Anda, semakin relevan dan dipersonalisasi perjalanan Anda. Inilah yang membuat menggabungkan Pemasaran dan Wawasan Pelanggan begitu kuat. Anda dapat [menyatukan data](data-unification.md) dari sumber mana pun, lalu menggunakannya untuk memicu perjalanan pelanggan yang sangat dipersonalisasi.

Pelajari lebih lanjut: [Gunakan profil dan segmen Customer Insights dalam pemasaran real-time](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Menggunakan segmen terpadu dengan perjalanan pelanggan keluar

Customer Insights memungkinkan Anda untuk memperbaiki data dari berbagai sumber dan menggabungkannya menjadi segmen pelanggan agregat. Dengan [menghubungkan Customer Insights dengan outbound marketing](export-dynamics365-marketing.md), segmen ini akan secara otomatis muncul *dan* refresh secara otomatis di perjalanan pelanggan desainer.

Pelajari lebih lanjut: [Gunakan segmen dari Dynamics 365 Customer Insights Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Tarik data dari data Anda sendiri Azure Data Lake Storage

Anda tidak terbatas pada penyimpanan cloud jika ingin menggunakan data Customer Insights dengan Marketing. Jika Anda sudah menyiapkan sendiri Azure Data Lake Storage, Anda dapat terhubung dengan Customer Insights, lalu berbagi data dengan aplikasi Marketing seperti yang Anda lakukan dengan pengaturan berbasis cloud.

Pelajari lebih lanjut: [Aktifkan berbagi data dengan Dataverse dari Anda sendiri Azure Data Lake Storage](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)