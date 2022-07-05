---
title: Menggunakan profil terpadu di Dynamics 365 Marketing
description: Pelajari cara mengintegrasikan profil dan segmen terpadu dengan Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99ec463299a24ea81cfe26bb785e36bdefdcd080
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054436"
---
# <a name="use-unified-customer-profiles-in-dynamics-365-marketing"></a>Menggunakan profil pelanggan terpadu di Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) meningkatkan pengalaman pelanggan, memungkinkan Anda mengatur perjalanan yang dipersonalisasi di semua titik kontak untuk memperkuat Relasi dan mendapatkan loyalitas. Aplikasi Dynamics 365 Marketing bekerja tanpa hambatan dengan Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams, dan produk lainnya serta memungkinkan Anda membuat keputusan yang lebih cepat dan lebih baik menggunakan kekuatan data dan AI.

Dengan menghubungkan data Customer Insights dengan Marketing, Anda dapat:

- Targetkan profil dan segmen pelanggan terpadu. Ini memungkinkan Anda untuk melibatkan setiap pelanggan, terlepas dari lokasi data pelanggan.
- Mendasarkan konten dinamis (seperti token yang dipersonalisasi) dalam email, SMS, dan pemberitahuan push pada langkah-langkah seperti status loyalitas, tanggal perpanjangan langganan, akun induk, atau tindakan lain yang telah Anda ambil di profil Customer Insights terpadu.
- Muat data dari Pemasaran ke dalam Customer Insights dan gabungkan dengan data pelanggan dari sumber lain.
- Terapkan alat pembersih, pengayaan, dan pencocokan data Customer Insights.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Gunakan profil pelanggan yang kaya dalam pemasaran real-time

Pemasaran waktu nyata memungkinkan Anda membuat [pemicu](/dynamics365/marketing/real-time-marketing-custom-triggers) khusus yang meluncurkan perjalanan pelanggan berdasarkan tindakan pelanggan apa pun. Semakin personal data Anda, semakin relevan dan personal perjalanan Anda. Inilah yang membuat penggabungan Marketing dan Customer Insights begitu kuat. Anda dapat [menyatukan data](data-unification.md) dari sumber mana pun, lalu menggunakannya untuk mendorong perjalanan pelanggan yang sangat personal.

Pelajari lebih lanjut: [Menggunakan profil dan segmen Customer Insights dalam pemasaran real-time](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Menggunakan segmen terpadu dengan perjalanan pelanggan keluar

Customer Insights memungkinkan Anda untuk memperbaiki data dari banyak sumber dan menggabungkannya menjadi segmen pelanggan agregat. Dengan [menghubungkan Customer Insights dengan pemasaran](export-dynamics365-marketing.md) keluar, segmen ini akan secara otomatis muncul *dan* disegarkan secara otomatis di perjalanan pelanggan desainer.

Pelajari lebih lanjut: [Menggunakan segmen dari Dynamics 365 Customer Insights dengan Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Tarik data dari data Anda sendiri Azure Data Lake Storage

Anda tidak terbatas pada penyimpanan cloud jika ingin menggunakan data Customer Insights dengan Marketing. Jika Anda sudah menyiapkannya sendiri Azure Data Lake Storage, Anda dapat terhubung dengan Customer Insights, lalu berbagi data dengan aplikasi Pemasaran seperti yang Anda lakukan dengan penyiapan berbasis cloud.

Pelajari lebih lanjut: [Mengaktifkan berbagi data dengan Dataverse dari anda sendiri Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
