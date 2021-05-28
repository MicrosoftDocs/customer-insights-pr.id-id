---
title: Konektor Power Apps
description: Hubungkan Power Apps dengan Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598159"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps connector (pratinjau)

Bawa profil pelanggan terpadu ke aplikasi Anda yang disesuaikan dengan Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Hubungkan Power Apps dan Dynamics 365 Customer Insights

Customer Insights adalah salah satu dari banyak [sumber yang tersedia untuk data di Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Lihat dokumentasi Power Apps untuk mempelajari cara [menambahkan sambungan data ke aplikasi](/powerapps/maker/canvas-apps/add-data-connection). Sebaiknya Anda juga meninjau [cara Power Apps menggunakan delegasi untuk menangani kumpulan data besar di aplikasi Canvas](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entitas yang tersedia

Setelah menambahkan Customer Insights sebagai sambungan data, Anda dapat memilih entitas berikut di Power Apps:

- Pelanggan: untuk menggunakan data dari [profil pelanggan terpadu](customer-profiles.md).
- UnifiedActivity: untuk menampilkan [Timeline aktivitas](activities.md) pada aplikasi.

## <a name="limitations"></a>Pembatasan

### <a name="retrievable-entities"></a>Entitas yang dapat diambil

Anda hanya dapat mengambil entitas **pelanggan**, **unifiedactivity**, dan **segmen** melalui Power Apps connector. Entitas lain ditampilkan karena konektor yang mendasari mendukung mereka melalui pemicu di Power Automate.  

### <a name="delegation"></a>Delegasi

Delegasi bekerja untuk entitas pelanggan dan entitas UnifiedActivity. 

- Delegasi untuk entitas **pelanggan**: untuk menggunakan delegasi untuk entitas ini, bidang harus diindeks dalam [index pencarian & Filter](search-filter-index.md).  

- Delegasi untuk **unifiedactivity** : delegasi untuk entitas ini hanya berfungsi untuk bidang **activityid** dan **customerid**.  

- Untuk informasi lebih lanjut tentang delegasi, lihat [fungsi dan operasi Power Apps yang dapat didelegasikan](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Kontrol galeri contoh

Misalnya, Anda menambahkan profil pelanggan ke [kontrol Galeri](/powerapps/maker/canvas-apps/add-gallery).

1. Tambahkan **kontrol galeri** ke aplikasi yang sedang Anda bangun.

> [!div class="mx-imgBorder"]
> ![Menambahkan elemen galeri](media/connector-powerapps9.png "Menambahkan elemen galeri")

1. Pilih **pelanggan** sebagai sumber data item.

    > [!div class="mx-imgBorder"]
    > ![Pilih sumber data](media/choose-datasource-powerapps.png "Pilih sumber data")

1. Anda dapat mengubah panel data di sebelah kanan untuk memilih bidang untuk entitas Pelanggan yang akan ditampilkan di galeri.

1. Jika Anda ingin menampilkan bidang apa pun dari pelanggan yang dipilih di Galeri, isi properti teks label:  **{Name_of_the_gallery}.Selected.{property_name}**

    Contoh: Gallery1. Selected. address1_city

1. Untuk menampilkan Timeline terpadu untuk pelanggan, tambahkan elemen Galeri, dan tambahkan properti item: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Contoh: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]