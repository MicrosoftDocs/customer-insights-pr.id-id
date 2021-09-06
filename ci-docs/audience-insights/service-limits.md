---
title: Batas Layanan
description: Pahami batasan dan larangan.
ms.date: 07/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2966f2ede1ddbe0245471771365cbf5b593be608764aa10ed28d962c52bb8067
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034868"
---
# <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Batas layanan di kemampuan wawasan audiens Dynamics 365 Customer Insights

Artikel ini menjelaskan batas internal untuk Layanan Customer Insights, yang dirancang untuk memastikan keandalan dan stabilitas layanan. Setiap permintaan untuk perubahan dapat dilakukan melalui [forum ide](https://go.microsoft.com/fwlink/?linkid=2074172). 
 
| Luas  | Batas  | Catatan |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmen dan ukuran | 100 segmen atau ukuran. | Jumlah total [segmen](segments.md) aktif [dan](measures.md) ukuran gabungan tidak boleh melebihi 100.  |
| Hubungan | 20 tingkat kedalaman pada Relasi dalam jalur entitas. | Saat membuat [segmen](segments.md) atau [ukuran](measures.md) menggunakan antarmuka pembuat, jalur entitas dapat memiliki hingga 20 lompatan relasi antara entitas awal dan entitas target.  |


[!INCLUDE[footer-include](../includes/footer-banner.md)]