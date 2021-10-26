---
title: Gunakan sumber data untuk menyerap data
description: Pelajari cara mengimpor data dari berbagai sumber.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: de31e1f25c08d0bcb5341c5f465b1999de48acf3
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645359"
---
# <a name="data-sources-overview"></a>Ikhtisar sumber data

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Kemampuan wawasan audiens di Dynamics 365 Customer Insights terhubung ke data dari sekumpulan sumber yang luas. Menghubungkan ke sumber data sering disebut sebagai proses *penyerapan data*. Setelah menyerap data, Anda dapat [menyatukan](data-unification.md), dan melakukan tindakan padanya.

## <a name="add-a-data-source"></a>Tambahkan sumber data

Lihat artikel rinci tentang cara menambahkan sumber data, tergantung pada pilihan yang anda pilih.

Anda dapat menambahkan sumber data dengan tiga cara utama:

- [melalui lusinan Power Query connectors](connect-power-query.md)
- [Dari folder Common Data Model](connect-common-data-model.md)
- [Dari Danau Microsoft Dataverse Anda sendiri](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Menambahkan data dari sumber data lokal

Menyerap data dari sumber data lokal di Wawasan Audiens didukung berdasarkan aliran data Microsoft Power Platform. Aliran data dapat diaktifkan di Customer Insights dengan [menyediakan URL lingkungan Microsoft Dataverse](create-environment.md) saat menyiapkan lingkungan.

Sumber data yang dibuat setelah mengaitkan lingkungan Dataverse dengan Customer Insights akan menggunakan [aliran data Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) secara default. Aliran data mendukung konektivitas lokal menggunakan gateway data. Hapus dan buat ulang sumber data yang ada sebelum lingkungan Dataverse dikaitkan untuk [menggunakan gateway data lokal](/data-integration/gateway/service-gateway-app).

Gateway data dari lingkungan Power BI atau Power Apps yang ada akan terlihat dan Anda dapat menggunakan kembali di Customer Insights. Halaman sumber data menampilkan tautan untuk membuka lingkungan Microsoft Power Platform tempat Anda dapat melihat dan mengkonfigurasi gateway data lokal.

## <a name="review-ingested-data"></a>Meninjau data yang diserap

Anda akan melihat nama dari setiap sumber data yang diserap, statusnya, serta waktu terakhir data disegarkan untuk sumber itu. Anda dapat mengurutkan daftar sumber data menurut setiap kolom.

> [!div class="mx-imgBorder"]
> ![Sumber Data ditambahkan.](media/configure-data-datasource-added.png "Sumber Data ditambahkan")

|Status  |KETERANGAN  |
|---------|---------|
|Berhasil   |Sumber data berhasil diserap jika waktu disebutkan di bidang **Disegarkan**.
|Belum dimulai   |Sumber data belum diserap datanya atau masih dalam mode draf.         |
|Me-refresh    |Penyerapan data sedang berlangsung. Anda dapat membatalkan operasi ini dengan memilih **berhenti menyegarkan** di kolom **tindakan**. Menghentikan refresh sumber data akan mengembalikannya ke status refresh terakhir.       |
|Gagal     |Penyerapan data mengalami kesalahan.         |

Pilih nilai di kolom **Status** dari daftar sumber data untuk meninjau rincian lainnya. Di panel **Rincian progres**, perluas **sumber Data**. Pilih **Lihat rincian** untuk informasi lebih lanjut tentang status penyegaran, termasuk rincian kesalahan dan pembaruan proses hilir.

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
