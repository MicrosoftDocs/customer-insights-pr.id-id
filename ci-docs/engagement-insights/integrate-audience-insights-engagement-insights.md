---
title: Membuat tautan antara wawasan audiens dan wawasan keterlibatan
description: Buat tautan aktif antara wawasan audiens dan wawasan keterlibatan untuk mengaktifkan pembagian data dua arah.
ms.date: 07/22/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 870209a7e19fec464ec41462a02365771bd653bd
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461017"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Membuat tautan antara wawasan audiens dan wawasan keterlibatan

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Integrasi antara wawasan keterlibatan dan wawasan audiens ini menghubungkan lingkungan dari kedua kemampuan tersebut, dan memungkinkan data dibagikan secara dua arah di antaranya.

Gunakan profil terpadu dan segmen dari audiens wawasan untuk pilihan analisis lainnya dalam wawasan keterlibatan. Ekspor aktivitas yang memiliki nilai bisnis tinggi dari wawasan keterlibatan. Gunakan aktivitas ini untuk menambahkan data ke profil terpadu di wawasan audiens.

## <a name="prerequisites"></a>Prasyarat

- Profil wawasan Audiens harus disimpan di akun Azure Data Lake Storage yang Anda miliki atau di data lake terkelola&ndash;[Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). 

- Anda memerlukan izin administrator untuk lingkungan wawasan keterlibatan dan wawasan audiens.

- Lingkungan yang ditautkan harus berada di kawasan geografis yang sama.

> [!NOTE]
> - Jika langganan Wawasan audiens Anda adalah uji coba, yang menggunakan data lake terkelola internal wawasan audiens, hubungi [pirequest@microsoft.com](mailto:pirequest@microsoft.com) untuk bantuan. 
> - Jika lingkungan wwawasan audiens Anda menggunakan Azure Data Lake Storage Anda sendiri untuk menyimpan data, Anda harus menambahkan prinsipal layanan Azure wawasan keterlibatan ke akun penyimpanan Anda. Untuk rincian, buka [Sambungkan ke akun Azure Data Lake Storage dengan prinsipal layanan Azure untuk wawasan audiens](../audience-insights/connect-service-principal.md). Selain itu, wawasan audiens Anda harus memiliki [lingkungan Dataverse](../audience-insights/get-started-paid.md) terkait. 

## <a name="create-an-environment-link"></a>Membuat tautan lingkungan

Anda dapat membuat tautan lingkungan dengan memperbarui pengaturan **Admin** > **Lingkungan** dalam wawasan keterlibatan.

**Untuk membuat tautan aktif antara wawasan audiens dan wawasan keterlibatan**

1. Pada halaman **admin Lingkungan**, pilih tab **tautkan Lingkungan**.

    :::image type="content" source="media/integrate1.png" alt-text="Konfigurasi lingkungan.":::

1. Pilih **Atur lingkungan** di sudut kiri atas atau di bagian bawah layar.

     :::image type="content" source="media/integrate2.png" alt-text="Pilih lingkungan wawasan audiens.":::

1. Pilih lingkungan wawasan audiens, lalu pilih **Berikutnya** untuk menyelesaikan. Sekarang Anda dapat memilih fitur opsional untuk lingkungan yang terhubung.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Aktifkan atribut dan segmen profil terpadu wawasan audiens

Setelah menautkan lingkungan, Anda dapat memilih fitur opsional untuk lingkungan yang terhubung. Fitur ini memungkinkan atribut profil terpadu dan segmen dari audiens wawasan untuk analisis interaktif pada data pelanggan.

**Untuk menganalisis data web dalam wawasan keterlibatan**

1. Di halaman **admin Lingkungan**, aktifkan tombol **Bagikan data dari audiens dengan wawasan keterlibatan**, lalu pilih **Berikutnya**.

    :::image type="content" source="media/integrate4.png" alt-text="Pilih fitur.":::

1. Pilih atribut profil terpadu yang akan menjadi dimensi dalam wawasan keterlibatan. (Tidak semua atribut merupakan dimensi yang berguna. Misalnya, Anda tidak memerlukan informasi **nama depan** atau **nama belakang** sebagai atribut untuk analisis aktivitas situs web Anda.)

    :::image type="content" source="media/integrate5.png" alt-text="Kurasi dimensi.":::

   >[!NOTE]
   > Semua atribut profil wawasan audiens yang menunjukkan pengidentifikasi (seperti **ID** dan **ID alternatif**) difilter dari atribut yang tersedia dan menjadi dimensi dalam wawasan keterlibatan.

1. Setelah selesai memilih atribut, pilih **Berikutnya**.
1. Tambahkan pengguna yang dapat melihat dimensi profil wawasan audiens dan segmen dalam wawasan keterlibatan.

    :::image type="content" source="media/integrate6.png" alt-text="Kelola akses ke data pelanggan.":::

   > [!IMPORTANT]
   > Jika Anda tidak menambahkan pengguna secara eksplisit pada langkah ini, data akan disembunyikan dari pengguna dalam wawasan keterlibatan.

1. Tinjau pilihan Anda lalu pilih **Selesai**.

    :::image type="content" source="media/integrate7.png" alt-text="Memeriksa pengaturan data pelanggan.":::

## <a name="export-refined-events-to-audience-insights"></a>Ekspor aktivitas yang disempurnakan ke wawasan audiens

Setelah membuat tautan antara lingkungan, Anda dapat mengekspor aktivitas yang disempurnakan dari wawasan keterlibatan ke wawasan audiens dan menggunakannya sebagai sumber data baru. 

Untuk informasi lebih lanjut, buka [Mengintegrasikan data web dari wawasan keterlibatan dengan wawasan audiens](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
