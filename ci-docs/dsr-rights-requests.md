---
title: Permintaan hak subjek data (DSR) di bawah GDPR | Microsoft Docs
description: Merespons permintaan subjek Data untuk kemampuan wawasan audiens Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350273"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Permintaan hak subjek data (DSR) di bawah GDPR

Peraturan Perlindungan Data Umum Uni Eropa (GDPR) telah berlaku sejak 25 Mei 2018. Peraturan ini memberikan hak yang signifikan kepada individu terkait data mereka. GDPR adalah tentang melindungi dan mengaktifkan hak privasi individu. Anda dapat membaca lebih lanjut tentang komitmen Microsoft untuk keamanan dan kesesuaian di [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Kami berkomitmen untuk membantu pelanggan memenuhi persyaratan GDPR. Ini mencakup hak untuk menghapus dan mengekspor data yang mencakup informasi pribadi seperti ID pengguna, nomor telepon, dan alamat email. Administrator dapat menerapkan permintaan pengguna untuk menghapus atau mengekspor data pribadi.

## <a name="audience-insights"></a>Wawasan audiens

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Merespons permintaan penghapusan subjek GDPR untuk kemampuan wawasan audiens Dynamics 365 Customer Insights

"Hak untuk menghapus" data pribadi dari data pelanggan organisasi adalah perlindungan kunci dalam peraturan perlindungan data umum (GDPR). Menghapus data pribadi mencakup penghapusan semua data pribadi dan log yang dihasilkan sistem, kecuali informasi log audit.

#### <a name="manage-data-subject-delete-requests"></a>Mengelola permintaan penghapusan subjek data

Wawasan audiens menawarkan pengalaman dalam produk berikut untuk menghapus data pribadi untuk pelanggan tertentu atau pengguna:

- **Mengelola permintaan untuk data pelanggan**: data pelanggan dalam Customer Insights terserap dari sumber data asli eksternal untuk Customer Insights. Semua permintaan penghapusan GDPR harus dilakukan di sumber data asli.
- **Mengelola permintaan penghapusan untuk data pengguna Customer Insights**: data untuk pengguna dibuat oleh Customer Insights. Semua permintaan penghapusan GDPR harus dilakukan di Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Mengelola permintaan untuk menghapus data pelanggan

Admin Customer Insights dapat mengikuti langkah berikut untuk menghapus data pelanggan yang telah dihapus di sumber data:

1. Masuk ke Dynamics 365 Customer Insights.
2. Di wawasan audiens, buka **Data** > **Sumber data**
3. Untuk setiap sumber data dalam daftar berisi data pelanggan yang telah dihapus:
   1. Pilih (...) dan kemudian pilih **Segarkan**.
   2. Periksa status sumber data dalam **status**. Tanda centang berarti penyegaran berhasil. Segitiga peringatan berarti terjadi kesalahan. Jika segitiga peringatan ditampilkan, hubungi D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Menangani permintaan penghapusan GDPR untuk data pelanggan.](audience-insights/media/gdpr-data-sources.png "Menangani permintaan penghapusan GDPR untuk data pelanggan")

##### <a name="manage-delete-requests-for-user-data"></a>Mengelola permintaan penghapusan untuk data pengguna

Admin Customer Insights dapat mengikuti langkah berikut untuk menghapus data pengguna Customer Insights:

1. Masuk ke Dynamics 365 Customer Insights.
2. Di wawasan audiens, buka **Admin** > **Izin**.
3. Centang kotak untuk pengguna yang akan dihapus.
4. Pilih **Hapus**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Merespons permintaan ekspor subjek data GDPR

Sebagai bagian dari komitmen kami untuk bermitra dengan Anda dalam perjalanan Anda ke peraturan perlindungan data umum (GDPR), kami telah mengembangkan dokumentasi untuk membantu Anda bersiap. Dokumentasi ini menjelaskan langkah yang dapat anda lakukan hari ini untuk mendukung kepatuhan GDPR saat menggunakan wawasan audiens.

#### <a name="manage-export-and-view-requests"></a>Mengelola ekspor dan lihat permintaan

Hak portabilitas data memungkinkan subjek data untuk meminta salinan data pribadi mereka dalam format elektronik (yaitu format "terstruktur, umum digunakan, dapat dibaca mesin, dan dapat dioperasikan") yang dapat ditransmisikan ke pengontrol data lainnya.

##### <a name="export-customer-data-tenant-admin"></a>Ekspor data pelanggan (admin penyewa)

Administrator penyewa dapat mengikuti langkah berikut untuk mengekspor data:

1. Kirim email ke D365CI@microsoft.com yang menentukan alamat email pelanggan yang diminta. Tim Customer Insights akan mengirim email ke alamat email admin penyewa yang terdaftar, meminta konfirmasi untuk mengekspor data.
2. Berikan konfirmasi untuk mengekspor data untuk pelanggan yang diminta.
3. Terima data yang diekspor melalui alamat email admin penyewa.

##### <a name="export-user-data-tenant-admin"></a>Ekspor data pengguna (admin penyewa)

1. Kirim email ke D365CI@microsoft.com yang menentukan alamat email pengguna yang diminta. Tim Customer Insights akan mengirim email ke alamat email admin penyewa yang terdaftar, meminta konfirmasi untuk mengekspor data.
2. Berikan konfirmasi untuk mengekspor data untuk pengguna yang diminta.
3. Terima data yang diekspor melalui alamat email admin penyewa.

## <a name="consent-management-preview"></a>Manajemen persetujuan (pratinjau)

Kemampuan manajemen persetujuan tidak mengumpulkan data pengguna secara langsung. Ini hanya mengimpor dan memproses data persetujuan yang disediakan oleh pengguna di aplikasi lain.

Untuk menghapus data persetujuan tentang pengguna tertentu, hapus di sumber data yang tertelan ke kemampuan manajemen persetujuan. Setelah menyegarkan sumber data, data yang dihapus akan dihapus di Pusat Persetujuan juga. Aplikasi yang menggunakan entitas persetujuan juga akan menghapus data yang telah dihapus pada sumber setelah [penyegaran](audience-insights/system.md#refresh-processes). Sebaiknya per refreshing sumber data dengan cepat setelah menanggapi permintaan subjek data untuk menghapus data pengguna dari semua proses dan aplikasi lainnya.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]