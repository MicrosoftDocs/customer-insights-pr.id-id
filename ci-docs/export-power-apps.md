---
title: Konektor Power Apps
description: Hubungkan Power Apps dengan Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: e99d7d4f231eb2ade67f27c9e52c61af3a21b99d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643942"
---
# <a name="microsoft-power-apps-connector-preview"></a>Microsoft Power Apps connector (pratinjau)

Bawa profil pelanggan terpadu ke aplikasi Anda yang disesuaikan dengan Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Hubungkan Power Apps dan Dynamics 365 Customer Insights

Customer Insights adalah salah satu dari banyak [sumber yang tersedia untuk data di Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Lihat dokumentasi Power Apps untuk mempelajari cara [menambahkan sambungan data ke aplikasi](/powerapps/maker/canvas-apps/add-data-connection). Sebaiknya Anda juga meninjau [cara Power Apps menggunakan delegasi untuk menangani kumpulan data besar di aplikasi Canvas](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entitas yang tersedia

Setelah menambahkan Customer Insights sebagai sambungan data, Anda dapat memilih entitas berikut di Power Apps:

- **Pelanggan**: untuk menggunakan data dari [profil pelanggan terpadu](customer-profiles.md).
- **UnifiedActivity**: untuk menampilkan [timeline aktivitas](activities.md) dalam aplikasi.
- **ContactProfile**: untuk menampilkan kontak pelanggan. Entitas ini hanya tersedia di lingkungan Customer Insights untuk akun bisnis.

## <a name="limitations"></a>Pembatasan

### <a name="retrievable-entities"></a>Entitas yang dapat diambil

Anda hanya dapat mengambil entitas **Pelanggan**, **UnifiedActivity**, **Segmen**, dan **ContactProfile** melalui konektor Power Apps. ContactProfile hanya tersedia dalam instans Customer Insights untuk akun bisnis. Entitas lain ditampilkan karena konektor yang mendasari mendukung mereka melalui pemicu di Power Automate.

Anda dapat melakukan maksimal 100 panggilan per 60 detik. Anda dapat memanggil API titik akhir beberapa kali dengan menggunakan parameter $skip. [Pelajari parameter $skip lebih lanjut](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegasi

Delegasi bekerja untuk entitas **pelanggan** dan entitas **UnifiedActivity**. 

- Delegasi untuk entitas **pelanggan**: untuk menggunakan delegasi untuk entitas ini, bidang harus diindeks dalam [index pencarian & Filter](search-filter-index.md).  
- Delegasi untuk **unifiedactivity** : delegasi untuk entitas ini hanya berfungsi untuk bidang **activityid** dan **customerid**.  
- Delegasi untuk **ContactProfile**: Delegasi untuk entitas ini hanya berfungsi untuk bidang **ContactId** dan **CustomerId**. ContactProfile hanya tersedia di lingkungan Customer Insights untuk akun bisnis.

Untuk informasi lebih lanjut tentang delegasi, buka [fungsi dan operasi yang dapat didelegasikan Power Apps](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Kontrol galeri contoh

Anda dapat menambahkan profil pelanggan ke [kontrol galeri](/powerapps/maker/canvas-apps/add-gallery).

1. Tambahkan kontrol **galeri** ke aplikasi yang sedang Anda bangun.

    > [!div class="mx-imgBorder"]
    > ![Menambahkan elemen galeri.](media/connector-powerapps9.png "Menambahkan elemen galeri.")

2. Pilih **pelanggan** sebagai sumber data item.

    > [!div class="mx-imgBorder"]
    > ![Pilih sumber data.](media/choose-datasource-powerapps.png "Pilih sumber data.")

3. Anda dapat mengubah panel data di sebelah kanan untuk memilih bidang untuk entitas Pelanggan yang akan ditampilkan di galeri.

4. Jika Anda ingin menampilkan bidang apa pun dari pelanggan yang dipilih di Galeri, isi properti **teks** label dengan **{Name_of_the_gallery}.Selected.{property_name}**  
    - Contoh: _Gallery1. Selected. address1_city_

5. Untuk menampilkan Timeline terpadu untuk pelanggan, tambahkan elemen Galeri, dan tambahkan properti **item** dengan **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Contoh: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
