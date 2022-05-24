---
title: Contoh OData untuk Dynamics 365 Customer Insights API
description: Contoh yang umum digunakan untuk Open Data Protocol (OData) untuk meminta API Wawasan Pelanggan untuk meninjau data.
ms.date: 05/10/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 007278e1330e1a8e64d524ded8496acaf83b874c
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740068"
---
# <a name="odata-query-examples"></a>Contoh kueri OData

Open Data Protocol (OData) adalah protokol akses data yang dibangun di atas protokol inti seperti HTTP. Ini menggunakan metodologi yang diterima secara umum seperti REST untuk web. Ada berbagai macam perpustakaan dan alat yang dapat digunakan untuk mengkonsumsi layanan OData.

Artikel ini mencantumkan beberapa contoh kueri yang sering diminta untuk membantu Anda membangun implementasi Anda sendiri berdasarkan [API Wawasan Pelanggan](apis.md).

Anda harus memodifikasi sampel kueri untuk membuatnya berfungsi di lingkungan target: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` di mana {instanceId} GUID lingkungan Customer Insights yang ingin Anda kueri. Operasi [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) memungkinkan Anda menemukan akses yang {InstanceId} Anda miliki.
- {CID}: PANDUAN dari catatan pelanggan terpadu. Contoh:`ce759201f786d590bf2134bff576c369`.
- {AlternateKey} Pengidentifikasi kunci utama catatan pelanggan dalam sumber data. Contoh: `CNTID_1002`
- {DSname} String dengan nama entitas sumber data yang akan dicerna ke Customer Insights. Contoh:`Website_contacts`.
- {SegmentName}: String dengan nama entitas output segmen di Customer Insights. Contoh:`Male_under_40`.

## <a name="customer"></a>yang terhormat

Tabel berikut berisi serangkaian kueri sampel untuk *entitas Pelanggan*.


|Jenis kueri |Contoh  | Catatan  |
|---------|---------|---------|
|ID pelanggan tunggal     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Kunci alternatif    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}' `         |  Kunci alternatif tetap ada di entitas pelanggan terpadu       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Pada    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Kunci alternatif + Dalam   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Pencarian  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Mengembalikan 10 hasil teratas untuk string pencarian      |
|Keanggotaan segmen  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10  `     | Mengembalikan jumlah baris yang telah ditetapkan sebelumnya dari entitas segmentasi.      |

## <a name="unified-activity"></a>Aktivitas terpadu

Tabel berikut berisi sekumpulan kueri sampel untuk *entitas UnifiedActivity*.

|Jenis kueri |Contoh  | Catatan  |
|---------|---------|---------|
|Aktivitas CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Mencantumkan aktivitas profil pelanggan tertentu |
|Aktivitas jangka waktu    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktivitas profil pelanggan dalam jangka waktu       |
|Jenis aktivitas    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktivitas oleh nama tampilan     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’ `        | |
|Penyortiran aktivitas    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Mengurutkan aktivitas naik atau turun       |
|Aktivitas diperluas dari keanggotaan segmen  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Contoh lainnya

Tabel berikut berisi sekumpulan kueri sampel untuk entitas lain.

|Jenis kueri |Contoh  | Catatan  |
|---------|---------|---------|
|Ukuran CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Merek CID yang diperkaya    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Kepentingan CID yang diperkaya    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Dalam Klausul + Perluas     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |
