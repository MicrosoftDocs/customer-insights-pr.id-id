---
title: Gunakan sumber data untuk menyerap data
description: Pelajari cara mengimpor data dari berbagai sumber.
ms.date: 03/18/2022
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
ms.openlocfilehash: bcc50c6fa8f8e2a66ef6164bfa9022e068c0e374
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642499"
---
# <a name="data-sources-overview"></a>Ikhtisar sumber data



Dynamics 365 Customer Insights terhubung ke data dari serangkaian sumber yang luas. Menghubungkan ke sumber data sering disebut sebagai proses *penyerapan data*. Setelah menyerap data, Anda dapat [menyatukan](data-unification.md), dan melakukan tindakan padanya.

## <a name="add-a-data-source"></a>Tambahkan sumber data

Lihat artikel terperinci untuk cara menambahkan sumber data, tergantung pada opsi yang Anda pilih.

Anda dapat menambahkan sumber data berikut:

- [Melalui puluhan Power Query konektor](connect-power-query.md)
- [Dari folder Common Data Model](connect-common-data-model.md)
- [Dari Danau Microsoft Dataverse Anda sendiri](connect-dataverse-managed-lake.md)
- [Azure Synapse Analytics Dari database](connect-synapse.md)

> [!NOTE]
> Jika Anda menggunakan versi uji coba, bagian metode impor menyertakan **opsi pustaka** data Wawasan Pelanggan. Pilih opsi ini untuk memilih kumpulan data sampel yang tersedia untuk berbagai industri. Untuk informasi selengkapnya, lihat [Dynamics 365 Customer Insights uji coba](trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Menambahkan data dari sumber data lokal

Menelan data dari sumber data lokal didukung berdasarkan Microsoft Power Platform aliran data. Anda dapat mengaktifkan Aliran Data di Wawasan [Pelanggan dengan Microsoft Dataverse menyediakan URL](create-environment.md) lingkungan saat menyiapkan lingkungan.

Sumber data yang dibuat setelah mengaitkan Dataverse lingkungan dengan Customer Insights menggunakan [Power Platform aliran data secara](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) default. Aliran data mendukung konektivitas lokal menggunakan gateway data. Anda dapat menghapus dan membuat ulang sumber data yang Dataverse ada sebelum lingkungan dikaitkan [menggunakan gateway](/data-integration/gateway/service-gateway-app) data lokal.

Gateway data dari lingkungan Power BI atau Power Apps yang ada akan terlihat dan Anda dapat menggunakan kembali di Customer Insights. Halaman sumber data menampilkan tautan untuk membuka lingkungan Microsoft Power Platform tempat Anda dapat melihat dan mengkonfigurasi gateway data lokal.

> [!IMPORTANT]
> Pastikan gateway Anda diperbarui ke versi terbaru. Anda dapat menginstal pembaruan dan mengkonfigurasi ulang gateway dari prompt yang ditampilkan di layar gateway secara langsung atau [mengunduh versi](https://powerapps.microsoft.com/downloads/) terbaru. Jika Anda tidak menggunakan versi gateway terbaru, refresh aliran data gagal dengan pesan kesalahan seperti **Kata kunci tidak didukung: properti konfigurasi. Nama parameter: kata kunci**.

## <a name="review-ingested-data"></a>Meninjau data yang diserap
Jika lingkungan Anda berisi Power Platform aliran data, **halaman Sumber** Data mencantumkan tiga bagian: 
- **Dibagikan**: Sumber data yang dapat dikelola oleh semua admin Customer Insights. Power BI aliran data, akun penyimpanan Anda sendiri, dan melampirkan ke danau data yang Dataverse dikelola adalah contoh sumber data bersama.
- **Dikelola oleh saya**: Power Platform aliran data dibuat dan hanya dapat dikelola oleh Anda. Admin Customer Insights lainnya hanya dapat melihat aliran data ini tetapi tidak mengedit, menyegarkan, atau menghapusnya.
- **Dikelola oleh orang lain**: Power Platform aliran data yang dibuat oleh admin lain. Anda hanya bisa melihatnya. Ini mencantumkan pemilik aliran data untuk menghubungi bantuan apa pun.
> [!NOTE]
> Semua entitas dapat dilihat dan digunakan oleh pengguna lain. Kontekstualitas pengguna hanya berlaku untuk sumber data dan bukan untuk entitas yang dihasilkan dari aliran data ini.

Jika tidak ada Power Platform aliran data yang digunakan, Anda tidak akan melihat grup atau bagian apa pun. Halaman **Sumber** Data hanya berisi daftar semua sumber data.

Anda akan melihat nama dari setiap sumber data yang diserap, statusnya, serta waktu terakhir data disegarkan untuk sumber itu. Anda dapat mengurutkan daftar sumber data menurut setiap kolom.

> [!div class="mx-imgBorder"]
> ![Sumber Data ditambahkan.](media/configure-data-datasource-added.png "Sumber Data ditambahkan")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuat data dapat memakan waktu. Setelah penyegaran berhasil, data yang terserap dapat ditinjau dari halaman **entitas**. Untuk informasi lebih lanjut, [Entitas](entities.md).

## <a name="refresh-a-data-source"></a>Segarkan sumber data

Sumber data dapat disegarkan dengan jadwal otomatis atau diperbarui secara manual sesuai permintaan. 

Buka **admin** > **sistem** > [**jadwal**](system.md#schedule-tab) untuk mengkonfigurasi penyegaran terjadwal dari semua sumber data Anda yang diserap.

Untuk me-refresh sumber data sesuai permintaan, ikuti langkah berikut:

1. Buka **Data** > **Sumber data**.

2. Pilih elipsis vertikal di sebelah sumber data yang ingin Anda segarkan, lalu pilih **Segarkan** dari daftar dropdown.

3. Sumber data sekarang dipicu untuk penyegaran manual. Merefresh sumber data akan memperbarui skema entitas dan data untuk semua entitas yang ditentukan dalam sumber data.

4. Pilih **Hentikan penyegaran** jika Anda ingin membatalkan refresh yang ada dan sumber data akan kembali ke status refresh terakhirnya.

## <a name="delete-a-data-source"></a>Hapus sumber data

1. Buka **Data** > **Sumber data**.

2. Pilih elipsis vertikal di sebelah sumber data yang ingin Anda hapus, lalu pilih **Hapus** dari menu dropdown.

3. Konfirmasikan penghapusan.


[!INCLUDE [footer-include](includes/footer-banner.md)]
