---
title: Contoh kueri OData untuk API Customer Insights
description: Contoh yang umum digunakan untuk Open Data Protocol (OData) untuk mengkueri API Customer Insights untuk meninjau data.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387206"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Contoh kueri OData untuk API Customer Insights

Open Data Protocol (OData) adalah protokol akses data yang dibangun di atas protokol inti seperti HTTP. Ini menggunakan metodologi yang diterima secara umum seperti REST untuk web. Ada berbagai macam library dan tools yang bisa digunakan untuk mengkonsumsi jasa OData.

Untuk membantu Anda membangun implementasi Anda sendiri berdasarkan [API](apis.md) Customer Insights, tinjau beberapa contoh kueri yang sering diminta.

Ubah sampel kueri untuk membuatnya berfungsi di lingkungan target:

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` di mana {instanceId} GUID lingkungan Customer Insights yang ingin Anda tanyakan. Operasi [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) memungkinkan Anda menemukan akses yang {InstanceId} Anda miliki.
- {CID}: GUID dari catatan pelanggan terpadu. Contoh:`ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: Pengidentifikasi kunci utama catatan pelanggan dalam sumber data. Contoh: `CNTID_1002`
- {DSname}: String dengan nama entitas sumber data yang diserap ke Customer Insights. Contoh:`Website_contacts`.
- {SegmentName}: String dengan nama entitas output segmen di Customer Insights. Contoh:`Male_under_40`.

## <a name="customer"></a>yang terhormat

Contoh kueri untuk *entitas Pelanggan* .

|Jenis kueri |Contoh  | Catatan  |
|---------|---------|---------|
|ID pelanggan tunggal     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|kunci alternatif    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Kunci alternatif tetap ada di entitas pelanggan terpadu       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Pada    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|kunci alternatif + Dalam   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Pencarian  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Mengembalikan 10 hasil teratas untuk string pencarian      |
|Keanggotaan segmen  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Mengembalikan jumlah baris yang telah ditetapkan sebelumnya dari entitas segmentasi.      |
|Keanggotaan segmen untuk pelanggan | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Mengembalikan profil pelanggan jika mereka adalah anggota segmen tertentu     |

## <a name="unified-activity"></a>Aktivitas terpadu

Contoh kueri untuk *entitas UnifiedActivity* .

|Jenis kueri |Contoh  | Catatan  |
|---------|---------|---------|
|Aktivitas CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Mencantumkan aktivitas profil pelanggan tertentu |
|jangka waktu Aktivitas    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Aktivitas profil pelanggan dalam jangka waktu       |
|Jenis aktivitas    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Aktivitas oleh nama tampilan     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Penyortiran aktivitas    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Mengurutkan aktivitas naik atau turun       |
|Aktivitas diperluas dari keanggotaan segmen  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Contoh lainnya

Contoh kueri untuk entitas lain.

|Jenis kueri |Contoh  | Catatan  |
|---------|---------|---------|
|Ukuran CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Merek CID yang diperkaya    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Kepentingan CID yang diperkaya    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Dalam Klausa + Perluas     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Kueri OData yang tidak didukung

Kueri berikut tidak didukung oleh Customer Insights:

- `$filter` pada entitas sumber yang tertelan. Anda hanya dapat menjalankan kueri $filter pada entitas sistem yang dibuat Customer Insights.
- `$expand``$search` dari kueri. Contoh: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` dari `$select` jika hanya sebagian atribut yang dipilih. Contoh: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` afinitas merek atau minat yang diperkaya untuk pelanggan tertentu. Contoh: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Kueri prediksi entitas output model melalui kunci alternatif. Contoh: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
