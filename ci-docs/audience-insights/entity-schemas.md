---
title: Skema entitas Customer Insights dalam Common Data Model
description: Bekerja dengan entitas dalam Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6667e411a1b56e13105a6b59b7b5d249bc8141ea
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596365"
---
# <a name="entity-schemas-in-common-data-model"></a>Skema entitas dalam Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](/common-data-model/) adalah spesifikasi deklaratif, dan definisi entitas stAndar yang menunjukkan konsep, dan aktivitas yang sering digunakan di seluruh aplikasi bisnis dan produktivitas. Model ini diperluas ke data pengamatan dan analitik juga. Common Data Model menyediakan entitas bisnis yang terdefinisi, modular, dan Terluaskan seperti akun, unit bisnis, kasus, kontak, prospek, peluang, dan produk, serta interaksi dengan vendor, pekerja, dan pelanggan, seperti aktivitas dan perjanjian tingkat layanan. Siapa pun dapat membangun dan memperluas definisi Common Data Model untuk mendapatkan ide khusus bisnis tambahan.

Model data bersama ini memungkinkan aplikasi dan integrator data berkolaborasi lebih mudah dengan menyediakan definisi data terpadu. Common Data Model mencakup sistem metadata kaya dengan entitas standar, Relasi, hierarki, properti, dan lainnya. Ini berasal dari aplikasi Dynamics 365 dan bersumber terbuka di GitHub dengan lebih dari 260 entitas standar. Sistem besar mitra internal dan eksternal berkontribusi pada konsep industri khusus untuk Common Data Model.

Beberapa sistem dan platform menerapkan Common Data Model hari ini, termasuk aliran data Power BI dan Azure Data Services. Ini sudah didukung dalam Common Data Service, Dynamics 365, Power Apps, Power BI, dan layanan data Azure mendatang, yang langsung menimbulkan nilai terhadap [prakarsa data terbuka](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Skema entitas Customer Insights

Untuk membuat tampilan 360 derajat pelanggan dan membuat model Customer Insights tersedia dalam Common Data Model untuk bisa diperluas, kami menerbitkan skema entitas berikut:

| Entitas | Keterangan |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Aktivitas yang dilakukan oleh pengguna yang memiliki nilai observasional ke bisnis. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Seseorang atau organisasi yang melakukan maupun memiliki potensi untuk terlibat dalam aktivitas bisnis. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definisi KPI yang dipartisi dengan nol atau lebih dimensi (mis. pengguna aktif bulanan, pembelanjaan Total oleh pelanggan, biaya perolehan pelanggan rata-rata) |
|[Segmen](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Mendefinisikan sekelompok anggota dengan ciri-ciri umum. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Anggota yang berpartisipasi dalam segmen tertentu. |

Untuk informasi lebih lanjut, lihat dokumentasi tentang [skema entitas Customer Insights dalam Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Lihat entitas menggunakan Navigator entitas Common Data Model

Anda dapat melihat entitas [Navigator entitas Common Data Model](https://microsoft.github.io/CDM/). Pilih tombol **Muat dari GitHub!** dan navigasi ke **foundationcommon** > **crmcommon** > **solusi** > **customerinsights** di mana Anda akan menemukan daftar entitas Customer Insights dan definisinya.
> [!div class="mx-imgBorder"]
> ![Navigator Entitas CDM menampilkan entitas CustomerActivity](media/CDM-entity-navigator.png "Navigator Entitas CDM menampilkan entitas CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]