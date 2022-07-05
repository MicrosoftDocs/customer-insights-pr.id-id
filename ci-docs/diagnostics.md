---
title: Penerusan log dengan Dynamics 365 Customer Insights Azure Monitor (pratinjau)
description: Pelajari cara mengirim log ke Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8c72df7054a682244215bbee54968d6aef4bbf59
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052657"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Penerusan log dengan Dynamics 365 Customer Insights Azure Monitor (pratinjau)

Dynamics 365 Customer Insights menyediakan integrasi langsung dengan Azure Monitor. Log sumber daya Azure Monitor memungkinkan Anda memantau dan mengirim log ke [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview), atau mengalirkannya ke [Azure Pusat Aktivitas](https://azure.microsoft.com/services/event-hubs/).

Customer Insights mengirimkan log peristiwa berikut:

- **Peristiwa Audit**
  - **APIEvent** - memungkinkan pelacakan perubahan yang dilakukan melalui Dynamics 365 Customer Insights UI.
- **Acara Operasional**
  - **WorkflowEvent** - Alur kerja memungkinkan Anda menyiapkan [Sumber](data-sources.md) Data, [menyatukan](data-unification.md), [memperkaya](enrichment-hub.md), dan akhirnya [mengekspor](export-destinations.md) data ke sistem lain. Semua langkah tersebut dapat dilakukan secara individual (misalnya, memicu satu ekspor). Dapat juga berjalan diatur (misalnya, penyegaran data dari sumber data yang memicu proses penyatuan, yang akan menarik pengayaan dan setelah selesai mengekspor data ke sistem lain). Untuk informasi selengkapnya, lihat [Skema](#workflow-event-schema) WorkflowEvent.
  - **APIEvent** - semua panggilan API ke instans pelanggan ke Dynamics 365 Customer Insights. Untuk informasi selengkapnya, lihat [Skema](#api-event-schema) APIEvent.

## <a name="set-up-the-diagnostic-settings"></a>Menyiapkan pengaturan diagnostik

### <a name="prerequisites"></a>Prasyarat

Untuk mengonfigurasi diagnostik di Customer Insights, prasyarat berikut harus dipenuhi:

- Anda memiliki Langganan [Azure aktif](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Anda memiliki [izin Administrator](permissions.md#admin) di Customer Insights.
- Anda memiliki **peran administrator** kontributor **dan** Akses Pengguna pada sumber daya tujuan di Azure. Sumber daya dapat berupa Azure Data Lake Storage akun, Azure Event Hub, atau ruang kerja Azure Log Analytics. Untuk informasi selengkapnya, lihat [Menambahkan atau menghapus penetapan peran Azure menggunakan portal](/azure/role-based-access-control/role-assignments-portal) Microsoft Azure. Izin ini diperlukan saat mengonfigurasi pengaturan diagnostik di Customer Insights, izin ini dapat diubah setelah penyiapan berhasil.
- [Persyaratan tujuan](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) untuk Azure Storage, Azure Event Hub, atau Azure Log Analytics terpenuhi.
- Anda memiliki setidaknya **peran Pembaca** pada grup sumber daya tempat sumber daya berada.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Menyiapkan diagnostik dengan Azure Monitor

1. Di Customer Insights, pilih **Diagnostik** > **Sistem** untuk melihat tujuan diagnostik yang dikonfigurasi instans ini.

1. Pilih **Tambahkan tujuan**.

   > [!div class="mx-imgBorder"]
   > ![Koneksi diagnostik](media/diagnostics-pane.png "Koneksi diagnostik")

1. Berikan nama di **bidang Nama untuk tujuan** diagnostik.

1. Pilih **Penyewa** langganan Azure dengan sumber daya tujuan dan pilih **masuk**.

1. **Pilih Jenis** sumber daya (Akun penyimpanan, pusat aktivitas, atau analitik log).

1. Pilih **Langganan** untuk sumber daya tujuan.

1. **Pilih Grup** sumber daya untuk sumber daya tujuan.

1. Pilih **Sumber Daya**.

1. Konfirmasikan **pernyataan privasi dan kepatuhan** Data.

1. Pilih **Sambungkan ke sistem** untuk terhubung ke sumber daya tujuan. Log mulai muncul di tujuan setelah 15 menit, jika API sedang digunakan dan menghasilkan peristiwa.

### <a name="remove-a-destination"></a>Menghapus tujuan

1. Buka **Diagnostik** > **Sistem**.

1. Pilih tujuan diagnostik dalam daftar.

1. Di kolom **Tindakan**, pilih ikon **Hapus**.

1. Konfirmasikan penghapusan untuk menghentikan penerusan log. Sumber daya pada langganan Azure tidak akan dihapus. Anda dapat memilih tautan di **kolom Tindakan** untuk membuka portal Microsoft Azure untuk sumber daya yang dipilih dan menghapusnya di sana.

## <a name="log-categories-and-event-schemas"></a>Kategori log dan skema peristiwa

Saat ini [peristiwa](apis.md) API dan peristiwa alur kerja didukung dan kategori serta skema berikut berlaku.
Skema log mengikuti [skema umum Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategori

Customer Insights menyediakan dua kategori:

- **Peristiwa audit**: [Peristiwa](#api-event-schema) API untuk melacak perubahan konfigurasi pada layanan. `POST|PUT|DELETE|PATCH` operasi masuk ke dalam kategori ini.
- **Peristiwa** operasional: [Peristiwa](#api-event-schema) API atau [peristiwa](#workflow-event-schema) alur kerja yang dihasilkan saat menggunakan layanan.  Misalnya, `GET` permintaan atau peristiwa eksekusi alur kerja.

## <a name="configuration-on-the-destination-resource"></a>Konfigurasi pada sumber daya tujuan

Berdasarkan pilihan Anda pada jenis sumber daya, langkah-langkah berikut akan secara otomatis berlaku:

### <a name="storage-account"></a>Akun Penyimpanan

Perwakilan layanan Customer Insights mendapatkan **izin kontributor** Akun Penyimpanan pada sumber daya yang dipilih dan membuat dua kontainer di bawah namespace layanan yang dipilih:

- `insight-logs-audit` berisi **peristiwa audit**
- `insight-logs-operational` berisi **acara operasional**

### <a name="event-hub"></a>Pusat Aktivitas

Perwakilan layanan Customer Insights mendapatkan **izin Pemilik** Data Azure Pusat Aktivitas pada sumber daya dan akan membuat dua Pusat Aktivitas di bawah namespace layanan yang dipilih:

- `insight-logs-audit` berisi **peristiwa audit**
- `insight-logs-operational` berisi **acara operasional**

### <a name="log-analytics"></a>Analisis Log

Perwakilan layanan Customer Insights mendapatkan **izin kontributor** Log Analytics pada sumber daya. Log akan tersedia di **bawah** > **Manajemen** > **Log Tabel** Log di ruang kerja Log Analytics yang dipilih. **Perluas solusi Manajemen** Log dan temukan `CIEventsAudit` tabel dan `CIEventsOperational`.

- `CIEventsAudit` berisi **peristiwa audit**
- `CIEventsOperational` berisi **acara operasional**

Di bawah jendela **Kueri, perluas** solusi Audit **dan temukan contoh kueri yang disediakan dengan mencari**`CIEvents`.

## <a name="event-schemas"></a>Skema peristiwa

Peristiwa API dan peristiwa alur kerja memiliki struktur dan detail umum di mana mereka berbeda, lihat [Skema peristiwa API atau](#api-event-schema) skema [peristiwa](#workflow-event-schema) alur kerja.

### <a name="api-event-schema"></a>Skema peristiwa API

| Bidang             | Datatype  | Wajib/Opsional | Deskripsi       | Contoh        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Tanda Waktu | Wajib          | Stempel waktu acara (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Wajib          | ResourceId dari instans yang memancarkan peristiwa         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Wajib          | Nama operasi yang diwakili oleh acara ini.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Wajib          | Kategori log acara. `Operational` Salah satu atau `Audit`. Semua Permintaan HTTP POST / PUT / PATCH / DELETE ditandai dengan `Audit`, segala sesuatu yang lain dengan`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Wajib          | Status acara. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Opsional          | Status hasil acara. Jika operasi sesuai dengan panggilan REST API, itu adalah kode status HTTP.        | `200`             |
| `durationMs`      | Panjang      | Opsional          | Durasi operasi dalam milidetik.     | `133`     |
| `callerIpAddress` | String    | Opsional          | Alamat IP penelepon, jika operasi sesuai dengan panggilan API yang berasal dari alamat IP yang tersedia untuk umum.                                                 | `144.318.99.233`         |
| `identity`        | String    | Opsional          | Objek JSON yang menggambarkan identitas pengguna atau aplikasi yang melakukan operasi.       | Lihat [bagian Identitas](#identity-schema).     |  
| `properties`      | String    | Opsional          | Objek JSON dengan lebih banyak properti ke kategori peristiwa tertentu.      | Lihat [bagian Properti](#api-properties-schema).    |
| `level`           | String    | Wajib          | Tingkat keparahan acara.    | `Informational`, `Warning`, `Error`, atau `Critical`.           |
| `uri`             | String    | Opsional          | URI permintaan mutlak.    |               |

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
| `Authorization.UserRole`      | Peran yang ditetapkan untuk pengguna atau aplikasi. Untuk informasi selengkapnya, lihat [izin](permissions.md) pengguna.                                     |
| `Authorization.RequiredRoles` | Peran yang diperlukan untuk melakukan operasi. `Admin` peran diizinkan untuk melakukan semua operasi.                                                    |
| `Claims`                      | Klaim token web JSON pengguna atau aplikasi (JWT). Properti klaim bervariasi per organisasi dan Azure Active Directory konfigurasi. |

#### <a name="api-properties-schema"></a>Skema properti API

[Peristiwa](apis.md) API memiliki properti berikut.

| Bidang                        | Deskripsi                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Selalu `ApiEvent`, menandai peristiwa log sebagai peristiwa API.                                                                 |
| `properties.userAgent`       | Agen browser yang mengirim permintaan atau `unknown`.                                                                        |
| `properties.method`          | Metode HTTP:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Jalur relatif permintaan.                                                                                          |
| `properties.origin`          | URI yang menunjukkan dari mana fetch berasal atau `unknown`.                                                                  |
| `properties.operationStatus` | `Success` untuk kode Status HTTP < 400 <br> `ClientError` untuk kode Status HTTP < 500 <br> `Error` untuk Status HTTP >= 500 |
| `properties.tenantId`        | ID Organisasi                                                                                                        |
| `properties.tenantName`      | Nama organisasi.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId dari penelepon.                                                                         |
| `properties.instanceId`      | Wawasan Pelanggan`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Skema peristiwa alur kerja

Alur kerja berisi beberapa langkah. [Menyerap sumber](data-sources.md) data, menyatukan [,](data-unification.md)[memperkaya](enrichment-hub.md), dan [mengekspor](export-destinations.md) data. Semua langkah tersebut dapat berjalan secara individual atau diatur dengan proses berikut.

#### <a name="operation-types"></a>Jenis operasi

| OperationType     | Grupkan                                     |
| ----------------- | ----------------------------------------- |
| Konsumsi         | [Sumber data](data-sources.md)           |
| DataPreparasi   | [Sumber data](data-sources.md)           |
| Peta               | [Penyatuan data](data-unification.md)   |
| Cocokkan             | [Penyatuan data](data-unification.md)   |
| Penggabungan             | [Penyatuan data](data-unification.md)   |
| Toko Profil      | [Profil pelanggan](customer-profiles.md) |
| Pencarian            | [Profil pelanggan](customer-profiles.md) |
| Aktivitas          | [Aktivitas](activities.md)                  |
| AtributMeasures | [Segmen dan Ukuran](segments.md)      |
| EntitasMeasures    | [Segmen dan Ukuran](segments.md)      |
| Tindakan          | [Segmen dan Ukuran](segments.md)      |
| Segmentasi      | [Segmen dan Ukuran](segments.md)      |
| Pengayaan        | [Pengayaan](enrichment-hub.md)                                          |
| Intelijen      | [Prediksi](predictions-overview.md)                                          |
| AiBuilder         | [Prediksi](predictions-overview.md)                                          |
| Wawasan          | [Prediksi](predictions-overview.md)                                          |
| Export            | [Ekspor](export-destinations.md)                                          |
| Manajemen Model   | [Prediksi](custom-models.md)                                           |
| Hubungan      | [Penyatuan data](relationships.md)                                           |

#### <a name="field-description"></a>Deskripsi bidang

| Bidang           | Datatype  | Wajib/Opsional | Deskripsi                                                                                                                                                   | Contoh                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Tanda Waktu | Wajib          | Stempel waktu acara (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Wajib          | ResourceId dari instans yang memancarkan peristiwa.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Wajib          | Nama operasi yang diwakili oleh acara ini. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Lihat [Jenis](#operation-types) Operasi untuk referensi. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Wajib          | Kategori log acara. Selalu `Operational` untuk peristiwa Alur Kerja                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Wajib          | Status acara. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Panjang      | Opsional          | Durasi operasi dalam milidetik.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Opsional          | Objek JSON dengan lebih banyak properti ke kategori peristiwa tertentu.                                                                                        | Lihat sub bagian [Properti Alur Kerja](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Wajib          | Tingkat keparahan acara.                                                                                                                                  | `Informational`, `Warning`, atau `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Skema properti alur kerja

Peristiwa alur kerja memiliki properti berikut.

| Bidang              | Alur kerja | Tugas | Deskripsi            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ya      | Ya  | Selalu `WorkflowEvent`, menandai acara sebagai peristiwa alur kerja.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ya      | Ya  | Pengidentifikasi alur kerja yang dijalankan. Semua alur kerja dan peristiwa tugas dalam eksekusi alur kerja memiliki .`workflowJobId`                                                                                                                                   |
| `properties.operationType`                   | Ya      | Ya  | Pengidentifikasi operasi, lihat [Jenis operasi](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Ya      | No   | Alur kerja saja. Jumlah tugas yang dipicu alur kerja.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ya      | No   | Opsional. Peristiwa alur kerja saja. ObjectId Azure Active Directory [pengguna](/azure/marketplace/find-tenant-object-id#find-user-object-id) yang memicu alur kerja, lihat juga `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ya      | No   | `full` atau `incremental` menyegarkan.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ya      | No   | `OnDemand` atau `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ya      | No   | `Running` atau `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ya      | Ya  | Stempel Waktu UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ya      | Ya  | Stempel Waktu UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ya      | Ya  | Stempel Waktu UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ya      | Ya  | Wawasan Pelanggan`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Ya  | - Untuk OperationType = `Export`, pengidentifikasi adalah guid dari konfigurasi ekspor. <br> - Untuk OperationType = `Enrichment`, ini adalah panduan pengayaan <br> - Untuk OperationType `Measures` dan `Segmentation`, pengidentifikasi adalah nama entitas. |
| `properties.friendlyName`                    | No       | Ya  | Nama ekspor yang mudah digunakan atau entitas yang diproses.                                                                                                                                                                                           |
| `properties.error`                           | No       | Ya  | Opsional. Pesan kesalahan dengan detail selengkapnya.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Ya  | Opsional. Hanya untuk OperationType `Export`. Mengidentifikasi jenis ekspor. Untuk informasi selengkapnya, lihat [gambaran umum tujuan](export-destinations.md) ekspor.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Ya  | Opsional. Hanya untuk OperationType `Export`. Berisi daftar entitas yang dikonfigurasi dalam ekspor.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Ya  | Opsional. Hanya untuk OperationType `Export`. Pesan terperinci untuk ekspor.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Ya  | Opsional. Hanya untuk OperationType `Segmentation`. Menunjukkan jumlah total anggota yang dimiliki segmen tersebut.                                                                                                                                                    |