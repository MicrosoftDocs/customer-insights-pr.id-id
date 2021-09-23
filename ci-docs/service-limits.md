---
title: Batas layanan di Dynamics 365 Customer Insights
description: Pahami batasan dan larangan.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483677"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Batas layanan di kemampuan Customer Insights

Artikel ini menjelaskan batas internal untuk Layanan Customer Insights, yang dirancang untuk memastikan keandalan dan stabilitas layanan. Setiap permintaan untuk perubahan dapat dilakukan melalui [forum ide](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Wawasan audiens

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Batas layanan di kemampuan wawasan audiens Dynamics 365 Customer Insights

| Luas  | Batas  | Catatan |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmen dan ukuran | 100 segmen atau ukuran. | Jumlah total [segmen](audience-insights/segments.md) aktif [dan](audience-insights/measures.md) ukuran gabungan tidak boleh melebihi 100.  |
| Hubungan | 20 tingkat kedalaman pada Relasi dalam jalur entitas. | Saat membuat [segmen](audience-insights/segments.md) atau [ukuran](audience-insights/measures.md) menggunakan antarmuka pembuat, jalur entitas dapat memiliki hingga 20 lompatan relasi antara entitas awal dan entitas target.  |


## <a name="engagement-insights"></a>Wawasan keterlibatan

### <a name="workspace-and-event-quotas"></a>Kuota ruang kerja dan aktivitas

Wawasan keterlibatan adalah aplikasi yang sangat dapat diskalakan yang dapat mendukung jutaan aktivitas per detik. Selama pratinjau umum, aktivitas memiliki ambang batas volume. Juga ada batas untuk jumlah ruang kerja di organisasi.

### <a name="engagement-insights-limits"></a>Batas Wawasan keterlibatan

- Volume aktivitas maksimum per ruang kerja = 100 aktivitas per detik

- Jumlah ruang kerja maksimum per organisasi = 100

Bila aktivitas melebihi ambang batas, maka aktivitas dapat mengakibatkan hilangnya data dalam laporan berdasarkan aktivitas tersebut. Anda dapat [menghubungi dukungan](https://go.microsoft.com/fwlink/?linkid=2145734) untuk meminta peningkatan volume sebelum melampaui batas. Kami akan bekerja sama dengan Anda untuk menentukan kebutuhan Anda untuk peningkatan volume dan mendukung permintaan Anda.


[!INCLUDE[footer-include](includes/footer-banner.md)]