---
title: Audit Dynamics 365 Customer Insights dengan Azure Monitor
description: Pelajari cara mengirim log ke Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: d962c359d70a068fcf939b61e340f86de088b419
ms.sourcegitcommit: 0c3c473e0220de9ee3c1f1ee1825de0b3b3663c3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920869"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Log forwarding Dynamics 365 Customer Insights in dengan Azure Monitor (Pratinjau)

Dynamics 365 Customer Insights menyediakan integrasi langsung dengan Azure Monitor. Azure Monitor resource logs memungkinkan Anda memantau dan mengirim log ke [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview), atau streaming mereka ke [Azure Event Hubs](https://azure.microsoft.com/services/event-hubs/).

Wawasan Pelanggan mengirimkan log peristiwa berikut:

- **Peristiwa Audit**
  - **APIEvent** - memungkinkan pelacakan perubahan yang dilakukan melalui Dynamics 365 Customer Insights UI.
- **Peristiwa Operasional**
  - **WorkflowEvent** - Alur Kerja memungkinkan seseorang untuk mengatur Sumber [Data](data-sources.md), menyatukan dan memperkaya [dan akhirnya mengekspor data ke sistem](data-unification.md)[...](enrichment-hub.md)[lain](export-destinations.md). Semua langkah tersebut dapat dilakukan secara individual (misalnya memicu ekspor tunggal) atau diatur (misalnya refresh data dari sumber data yang memicu proses penyatuan yang akan menarik pengayaan tambahan dan sekali selesai mengekspor data ke sistem lain). Untuk detail selengkapnya lihat [Skema Alur Kerja](#workflow-event-schema).
  - **APIEvent** - semua panggilan API ke instans pelanggan ke Dynamics 365 Customer Insights. Untuk detail selengkapnya lihat [Skema APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Menyiapkan pengaturan diagnostik

### <a name="prerequisites"></a>Prasyarat

Untuk mengonfigurasi diagnostik dalam Wawasan Pelanggan, prasyarat berikut harus dipenuhi:

- Anda memiliki [Langganan Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) aktif.
- Anda memiliki [izin Administrator dalam Wawasan](permissions.md#administrator) Pelanggan.
- Anda memiliki **peran kontributor dan User Access Administrator pada sumber daya tujuan di** **Azure**. Sumber daya dapat menjadi akun Azure Storage, Azure Event Hub, atau ruang kerja Azure Log Analytics. Untuk informasi selengkapnya, lihat [Menambahkan atau menghapus tugas peran Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal).
- [Destination requirements](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) for Azure Storage, Azure Event Hub, or Azure Log Analytics met.
- Anda memiliki setidaknya **peran Pembaca pada kelompok sumber daya milik sumber** daya.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Menyiapkan diagnostik dengan Azure Monitor

1. Di Wawasan Pelanggan, pilih **Diagnostik Sistem untuk melihat tujuan diagnostik mengonfigurasi** > **instans** ini.

1. Pilih **Tambahkan tujuan**.

   > [!div class="mx-imgBorder"]
   > ![Koneksi diagnostik](media/diagnostics-pane.png "Koneksi diagnostik")

1. Berikan nama di **bidang Nama untuk tujuan** diagnostik.

1. Pilih **Penyewa** langganan Azure dengan sumber daya tujuan dan pilih **masuk**.

1. Pilih **tipe Sumber Daya** (Akun penyimpanan, Hub Acara, atau analitik log).

1. Pilih **Langganan** untuk sumber daya tujuan.

1. Pilih **grup Sumber Daya** untuk sumber daya tujuan.

1. Pilih **Sumber** Daya.

1. Konfirmasikan **pernyataan privasi dan kepatuhan** Data.

1. Pilih **Sambungkan ke sistem** untuk terhubung ke sumber daya tujuan. Log mulai muncul di tujuan setelah 15 menit, jika API digunakan dan menghasilkan peristiwa.

### <a name="remove-a-destination"></a>Menghapus tujuan

1. Pergi **ke** > **Diagnostik** Sistem.

1. Pilih tujuan diagnostik dalam daftar.

1. Di **kolom** Tindakan, pilih **ikon** Hapus.

1. Konfirmasi penghapusan untuk menghentikan penerusan log. Sumber daya pada langganan Azure tidak akan dihapus. Anda dapat memilih tautan di **kolom Tindakan untuk membuka portal Azure untuk sumber daya yang dipilih dan** menghapusnya di sana.

## <a name="log-categories-and-event-schemas"></a>Log kategori dan skema acara

Saat ini [acara API dan acara alur kerja didukung dan kategori dan skema berikut](apis.md) berlaku.
Skema log mengikuti [skema umum Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategori

Customer Insights menyediakan dua kategori:

- **Peristiwa** audit: [Peristiwa API untuk melacak perubahan konfigurasi pada](#api-event-schema) layanan. `POST|PUT|DELETE|PATCH` operasi masuk ke dalam kategori ini.
- **Peristiwa** operasional: [Peristiwa API atau peristiwa alur kerja yang dihasilkan saat menggunakan](#api-event-schema)[layanan](#workflow-event-schema).  Misalnya, `GET` permintaan atau peristiwa eksekusi alur kerja.

## <a name="configuration-on-the-destination-resource"></a>Konfigurasi pada sumber daya tujuan

Berdasarkan pilihan Anda pada tipe sumber daya, langkah-langkah berikut akan berlaku secara otomatis:

### <a name="storage-account"></a>Akun Penyimpanan

Prinsipal layanan Customer Insights mendapatkan **izin kontributor Akun Penyimpanan pada sumber daya yang dipilih dan membuat dua kontainer di bawah ruang nama yang** dipilih:

- `insight-logs-audit` berisi **peristiwa audit**
- `insight-logs-operational` Berisi **peristiwa operasional**

### <a name="event-hub"></a>Pusat Aktivitas

Prinsipal layanan Customer Insights mendapatkan **izin Azure Pusat Aktivitas Data Owner pada sumber daya dan akan membuat dua Pusat Aktivitas di bawah ruang nama yang** dipilih:

- `insight-logs-audit` berisi **peristiwa audit**
- `insight-logs-operational` Berisi **peristiwa operasional**

### <a name="log-analytics"></a>Analisis Log

Prinsipal layanan Customer Insights mendapatkan **izin log analytics kontributor pada sumber** daya. Log akan tersedia di bawah **Manajemen Log Tabel Log pada ruang kerja Log Analytics yang** > **·** > **dipilih**. Perluas **solusi Manajemen Log dan temukan dan**`CIEventsAudit``CIEventsOperational` tabel.

- `CIEventsAudit` berisi **peristiwa audit**
- `CIEventsOperational` Berisi **peristiwa operasional**

Di bawah **jendela** Kueri, perluas **solusi Audit dan temukan kueri contoh yang disediakan dengan mencari**`CIEvents`.

## <a name="event-schemas"></a>Skema acara

Peristiwa API dan peristiwa alur kerja memiliki struktur dan detail umum di mana mereka berbeda, lihat [skema peristiwa API atau skema acara alur kerja](#api-event-schema)[...](#workflow-event-schema).

### <a name="api-event-schema"></a>Skema acara API

| Bidang             | Datatype  | Diperlukan/Opsional | Deskripsi       | Contoh        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Tanda Waktu | Wajib          | Timestamp dari acara (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Wajib          | ResourceId dari contoh yang memancarkan peristiwa         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Wajib          | Nama operasi yang diwakili oleh acara ini.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Wajib          | Kategori log dari acara tersebut. Salah `Operational` atau `Audit`. Semua Permintaan HTTP POST /PUT/PATCH/DELETE ditandai dengan `Audit`, segala sesuatu yang lain dengan`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Wajib          | Status acara. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Opsional          | Status hasil dari peristiwa tersebut. Jika operasi sesuai dengan panggilan REST API, itu adalah kode status HTTP.        | `200`             |
| `durationMs`      | Panjang      | Opsional          | Durasi operasi dalam milidetik.     | `133`     |
| `callerIpAddress` | String    | Opsional          | Alamat IP penelepon, jika operasi sesuai dengan panggilan API yang berasal dari alamat IP yang tersedia untuk umum.                                                 | `144.318.99.233`         |
| `identity`        | String    | Opsional          | Objek JSON yang menggambarkan identitas pengguna atau aplikasi yang melakukan operasi.       | Lihat [bagian](#identity-schema) Identitas.     |  |
| `properties`      | String    | Opsional          | Objek JSON dengan lebih banyak properti untuk kategori peristiwa tertentu.      | Lihat [bagian](#api-properties-schema) Properti.    |
| `level`           | String    | Wajib          | Tingkat keparahan dari peristiwa tersebut.    | `Informational``Warning`, `Error`, atau `Critical`.           |
| `uri`             | String    | Opsional          | Permintaan mutlak URI.    |               |

#### <a name="identity-schema"></a>Skema identitas

Objek `identity` JSON memiliki struktur berikut

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Bidang                         | Deskripsi                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Peran yang ditetapkan untuk pengguna atau aplikasi. Untuk informasi selengkapnya, lihat [izin pengguna](permissions.md).                                     |
| `Authorization.RequiredRoles` | Diperlukan peran untuk melakukan operasi. `Admin` Peran diperbolehkan untuk melakukan semua operasi.                                                    |
| `Claims`                      | Klaim pengguna atau aplikasi JSON web token (JWT). Properti klaim bervariasi per organisasi dan Azure Active Directory konfigurasi. |

#### <a name="api-properties-schema"></a>Skema properti API

[Acara API](apis.md) memiliki properti berikut.

| Bidang                        | Deskripsi                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Selalu `ApiEvent`, menandai peristiwa log sebagai acara API.                                                                 |
| `properties.userAgent`       | Agen browser mengirim permintaan atau `unknown`.                                                                        |
| `properties.method`          | Metode HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Jalur relatif dari permintaan tersebut.                                                                                          |
| `properties.origin`          | URI menunjukkan dari mana pengambilan berasal atau `unknown`.                                                                  |
| `properties.operationStatus` | `Success` untuk kode Status HTTP < 400 <br> `ClientError` untuk kode Status HTTP < 500 <br> `Error` untuk status HTTP >= 500 |
| `properties.tenantId`        | ID Organisasi                                                                                                        |
| `properties.tenantName`      | Nama organisasi.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId dari penelepon.                                                                         |
| `properties.instanceId`      | Wawasan Pelanggan`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Skema acara alur kerja

Alur kerja berisi beberapa langkah. [Menelan sumber](data-sources.md) data, [menyatukan](data-unification.md), [memperkaya](enrichment-hub.md), dan [mengekspor](export-destinations.md) data. Semua langkah tersebut dapat berjalan secara individual atau diatur dengan proses berikut. 

#### <a name="operation-types"></a>Tipe operasi

| OperationType     | Grupkan                                     |
| ----------------- | ----------------------------------------- |
| Konsumsi         | [Sumber data](data-sources.md)           |
| Penpreparasi Data   | [Sumber data](data-sources.md)           |
| Peta               | [Penyatuan data](data-unification.md)   |
| Cocokkan             | [Penyatuan data](data-unification.md)   |
| Penggabungan             | [Penyatuan data](data-unification.md)   |
| ProfileStore      | [Profil pelanggan](customer-profiles.md) |
| Pencarian            | [Profil pelanggan](customer-profiles.md) |
| Aktivitas          | [Aktivitas](activities.md)                  |
| AttributeMeasures | [Segmen dan Ukuran](segments.md)      |
| EntityMeasures    | [Segmen dan Ukuran](segments.md)      |
| Tindakan          | [Segmen dan Ukuran](segments.md)      |
| Segmentasi      | [Segmen dan Ukuran](segments.md)      |
| Pengayaan        | [Pengayaan](enrichment-hub.md)                                          |
| Intelijen      | [Prediksi](predictions-overview.md)                                          |
| AiBuilder         | [Prediksi](predictions-overview.md)                                          |
| Wawasan          | [Prediksi](predictions-overview.md)                                          |
| Export            | [Ekspor](export-destinations.md)                                          |
| ModelManagement   | [Prediksi](custom-models.md)                                           |
| Hubungan      | [Penyatuan data](relationships.md)                                           |

#### <a name="field-description"></a>Deskripsi bidang

| Bidang           | Datatype  | Diperlukan/Opsional | Deskripsi                                                                                                                                                   | Contoh                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Tanda Waktu | Wajib          | Timestamp dari acara (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Wajib          | ResourceId dari contoh yang dipancarkan peristiwa tersebut.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Wajib          | Nama operasi yang diwakili oleh acara ini. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Lihat [Tipe Operasi untuk](#operation-types) referensi. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Wajib          | Kategori log dari acara tersebut. Selalu `Operational` untuk acara Alur Kerja                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Wajib          | Status acara. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Panjang      | Opsional          | Durasi operasi dalam milidetik.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Opsional          | Objek JSON dengan lebih banyak properti untuk kategori peristiwa tertentu.                                                                                        | Lihat sub bagian [Properti Alur kerja](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Wajib          | Tingkat keparahan dari peristiwa tersebut.                                                                                                                                  | `Informational`, `Warning`, atau `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Skema properti alur kerja

Peristiwa alur kerja memiliki properti berikut.

| Bidang              | Alur kerja | Tugas | Deskripsi            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ya      | Ya  | Selalu `WorkflowEvent`, menandai peristiwa sebagai peristiwa alur kerja.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ya      | Ya  | Pengidentifikasi alur kerja berjalan. Semua alur kerja dan peristiwa tugas dalam eksekusi alur kerja memiliki hal yang `workflowJobId` sama.                                                                                                                                   |
| `properties.operationType`                   | Ya      | Ya  | Pengidentifikasi operasi, lihat [Tipe operasi]. (tipe #operation)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Ya      | No   | Alur kerja saja. Jumlah tugas yang dipicu alur kerja.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ya      | No   | Opsional. Hanya peristiwa alur kerja. Azure Active Directory [ObjectId pengguna](/azure/marketplace/find-tenant-object-id#find-user-object-id) yang memicu alur kerja, lihat juga `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ya      | No   | `full` atau `incremental` refresh.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ya      | No   | `OnDemand` atau `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ya      | No   | `Running` atau `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ya      | Ya  | Waktu UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ya      | Ya  | Waktu UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ya      | Ya  | Waktu UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ya      | Ya  | Wawasan Pelanggan`instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Ya  | - Untuk OperationType = `Export`, pengenal adalah panduan dari konfigurasi ekspor. <br> - Untuk OperationType = `Enrichment`, ini adalah panduan pengayaan <br> - Untuk OperationType `Measures` dan, pengenal adalah nama `Segmentation` entitas. |
| `properties.friendlyName`                    | No       | Ya  | Nama ekspor yang mudah digunakan atau entitas yang diproses.                                                                                                                                                                                           |
| `properties.error`                           | No       | Ya  | Opsional. Pesan kesalahan dengan detail lebih lanjut.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Ya  | Opsional. Hanya untuk `Export` OperationType. Mengidentifikasi jenis ekspor. Untuk informasi [selengkapnya, lihat gambaran umum tujuan](export-destinations.md) ekspor.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Ya  | Opsional. Hanya untuk `Export` OperationType. Berisi daftar entitas yang dikonfigurasi dalam ekspor.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Ya  | Opsional. Hanya untuk `Export` OperationType. Pesan terperinci untuk ekspor.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Ya  | Opsional. Hanya untuk `Segmentation` OperationType. Menunjukkan jumlah total anggota yang dimiliki segmen tersebut.                                                                                                                                                    |
