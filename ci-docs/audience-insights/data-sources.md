---
title: Gunakan sumber data untuk menyerap data
description: Pelajari cara mengimpor data dari berbagai sumber.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: e7bcf82c4fe3625ef791ec2b0a7651be0356a006
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354053"
---
# <a name="data-sources-overview"></a>Ikhtisar sumber data



Kemampuan wawasan audiens di Dynamics 365 Customer Insights terhubung ke data dari sekumpulan sumber yang luas. Menghubungkan ke sumber data sering disebut sebagai proses *penyerapan data*. Setelah menyerap data, Anda dapat [menyatukan](data-unification.md), dan melakukan tindakan padanya.

## <a name="add-a-data-source"></a>Tambahkan sumber data

Lihat artikel terperinci untuk cara menambahkan sumber data, tergantung pada opsi yang Anda pilih.

Anda dapat menambahkan sumber data berikut:

- [Melalui puluhan Power Query konektor](connect-power-query.md)
- [Dari folder Common Data Model](connect-common-data-model.md)
- [Dari Danau Microsoft Dataverse Anda sendiri](connect-dataverse-managed-lake.md)
- [Azure Synapse Analytics Dari database](connect-synapse.md)

> [!NOTE]
> Jika Anda menggunakan versi uji coba, bagian metode impor menyertakan **opsi pustaka** data Wawasan Pelanggan. Pilih opsi ini untuk memilih dataset sampel yang tersedia untuk berbagai industri. Untuk informasi selengkapnya, lihat [Dynamics 365 Customer Insights uji coba](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Menambahkan data dari sumber data lokal

Menyerap data dari sumber data lokal di Wawasan Audiens didukung berdasarkan aliran data Microsoft Power Platform. Anda dapat mengaktifkan Aliran Data di Wawasan [Pelanggan dengan menyediakan URL Microsoft Dataverse lingkungan saat](create-environment.md) menyiapkan lingkungan.

Sumber data yang dibuat setelah mengaitkan Dataverse lingkungan dengan Wawasan Pelanggan menggunakan [Power Platform aliran data secara](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) default. Aliran data mendukung konektivitas lokal menggunakan gateway data. Anda dapat menghapus dan membuat ulang sumber data yang ada sebelum Dataverse lingkungan dikaitkan [menggunakan gateway](/data-integration/gateway/service-gateway-app) data lokal.

Gateway data dari lingkungan Power BI atau Power Apps yang ada akan terlihat dan Anda dapat menggunakan kembali di Customer Insights. Halaman sumber data menampilkan tautan untuk membuka lingkungan Microsoft Power Platform tempat Anda dapat melihat dan mengkonfigurasi gateway data lokal.

## <a name="review-ingested-data"></a>Meninjau data yang diserap

Anda akan melihat nama dari setiap sumber data yang diserap, statusnya, serta waktu terakhir data disegarkan untuk sumber itu. Anda dapat mengurutkan daftar sumber data menurut setiap kolom.

> [!div class="mx-imgBorder"]
> ![Sumber Data ditambahkan.](media/configure-data-datasource-added.png "Sumber Data ditambahkan")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Memuat data dapat memakan waktu. Setelah penyegaran berhasil, data yang terserap dapat ditinjau dari halaman **entitas**. Untuk informasi lebih lanjut, [Entitas](entities.md).

## <a name="refresh-a-data-source"></a>Segarkan sumber data

Sumber data dapat disegarkan dengan jadwal otomatis atau diperbarui secara manual sesuai permintaan. 

Buka **admin** > **sistem** > [**jadwal**](system.md#schedule-tab) untuk mengkonfigurasi penyegaran terjadwal dari semua sumber data Anda yang diserap.

Untuk me-refresh sumber data sesuai permintaan, ikuti langkah berikut:

1. Di wawasan audiens, buka **Data** > **Sumber data**.

2. Pilih elipsis vertikal di sebelah sumber data yang ingin Anda segarkan, lalu pilih **Segarkan** dari daftar dropdown.

3. Sumber data sekarang dipicu untuk penyegaran manual. Merefresh sumber data akan memperbarui skema entitas dan data untuk semua entitas yang ditentukan dalam sumber data.

4. Pilih **Hentikan penyegaran** jika Anda ingin membatalkan refresh yang ada dan sumber data akan kembali ke status refresh terakhirnya.

## <a name="delete-a-data-source"></a>Hapus sumber data

1. Di wawasan audiens, buka **Data** > **Sumber data**.

2. Pilih elipsis vertikal di sebelah sumber data yang ingin Anda hapus, lalu pilih **Hapus** dari menu dropdown.

3. Konfirmasikan penghapusan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
