---
title: Batas layanan di Dynamics 365 Customer Insights
description: Pahami batasan dan larangan.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350411"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Batas layanan di kemampuan Customer Insights

Artikel ini menjelaskan batas internal untuk Layanan Customer Insights, yang dirancang untuk memastikan keandalan dan stabilitas layanan. Setiap permintaan untuk perubahan dapat dilakukan melalui [forum ide](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Wawasan audiens

| Luas  | Batas  | Catatan |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmen, ukuran, dan prediksi | 300  | Jumlah [total segmen](audience-insights/segments.md), [ukuran](audience-insights/measures.md), dan [prediksi](audience-insights/predictions.md) gabungan tidak dapat melebihi 300.  |
| Hubungan | 20 tingkat kedalaman pada Relasi dalam jalur entitas. | Saat membuat [segmen](audience-insights/segments.md) atau [ukuran](audience-insights/measures.md) menggunakan antarmuka pembuat, jalur entitas dapat memiliki hingga 20 lompatan relasi antara entitas awal dan entitas target.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
