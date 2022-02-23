---
title: Batas layanan dalam Dynamics 365 Customer Insights
description: Pahami batasan dan larangan.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791985"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Batas layanan di kemampuan Customer Insights

Artikel ini menjelaskan batas internal untuk Layanan Customer Insights, yang dirancang untuk memastikan keandalan dan stabilitas layanan. Setiap permintaan untuk perubahan dapat dilakukan melalui [forum ide](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Wawasan audiens

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Batas layanan dalam kemampuan wawasan Dynamics 365 Customer Insights audiens

| Luas  | Batas  | Catatan |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmen, ukuran, dan prediksi | 300  | Jumlah total [...](audience-insights/segments.md) segmen, [...](audience-insights/measures.md) ukuran, dan [prediksi gabungan tidak dapat](audience-insights/predictions.md) melebihi 300.  |
| Hubungan | 20 tingkat kedalaman pada Relasi dalam jalur entitas. | Saat membuat [segmen](audience-insights/segments.md) atau [ukuran](audience-insights/measures.md) menggunakan antarmuka pembuat, jalur entitas dapat memiliki hingga 20 lompatan relasi antara entitas awal dan entitas target.  |


## <a name="engagement-insights"></a>Wawasan keterlibatan

### <a name="workspace-and-event-quotas"></a>Kuota ruang kerja dan aktivitas

Wawasan keterlibatan adalah aplikasi yang sangat dapat diskalakan yang dapat mendukung jutaan aktivitas per detik. Selama pratinjau umum, aktivitas memiliki ambang batas volume. Juga ada batas untuk jumlah ruang kerja di organisasi.

### <a name="engagement-insights-limits"></a>Batas Wawasan keterlibatan

- Volume aktivitas maksimum per ruang kerja = 100 aktivitas per detik

- Jumlah ruang kerja maksimum per organisasi = 100

Bila aktivitas melebihi ambang batas, maka aktivitas dapat mengakibatkan hilangnya data dalam laporan berdasarkan aktivitas tersebut. Anda dapat [menghubungi dukungan](https://go.microsoft.com/fwlink/?linkid=2145734) untuk meminta peningkatan volume sebelum melampaui batas. Kami akan bekerja sama dengan Anda untuk menentukan kebutuhan Anda untuk peningkatan volume dan mendukung permintaan Anda.


[!INCLUDE[footer-include](includes/footer-banner.md)]
