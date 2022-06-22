---
title: Batas layanan di Customer Insights
description: Pahami batasan dan batasan dalam layanan SaaS Customer Insights.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940672"
---
# <a name="service-limits-in-customer-insights"></a>Batas layanan di Customer Insights

Artikel ini menjelaskan batas internal untuk Layanan Customer Insights, yang dirancang untuk memastikan keandalan dan stabilitas layanan. Setiap permintaan untuk perubahan dapat dilakukan melalui [forum ide](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Luas  | Batas  | Catatan |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmen, ukuran, dan prediksi | 300  | Jumlah [total segmen](segments.md), ukuran [,](measures.md) dan [prediksi yang](predictions.md) digabungkan tidak boleh melebihi 300.  |
| Hubungan | 20 tingkat kedalaman pada Relasi dalam jalur entitas. | Saat membuat [segmen](segments.md) atau [ukuran](measures.md) menggunakan antarmuka pembuat, jalur entitas dapat memiliki hingga 20 lompatan relasi antara entitas awal dan entitas target.  |

## <a name="fair-scheduling-of-jobs"></a>Penjadwalan pekerjaan yang adil

Customer Insights adalah layanan SaaS yang menggunakan sumber daya Azure bersama. Pelanggan cenderung memiliki beban kerja dengan intensitas variabel dan pada jadwal yang berbeda. Untuk memastikan akses yang adil ke sumber daya yang mendasarinya, kami memastikan proses sistem dijalankan dalam urutan yang adil. Contoh proses sistem adalah pekerjaan yang terkait dengan penyatuan data, pembaruan segmen, atau perhitungan ukuran. Penjadwalan yang adil melindungi Anda dari antrian sumber daya jika ada lonjakan pekerjaan yang diminta. Pada saat yang sama, Customer Insights tidak menjamin semua pekerjaan yang Anda antri diproses secara paralel.

[!INCLUDE [footer-include](includes/footer-banner.md)]
