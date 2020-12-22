---
title: Gunakan sumber data untuk menyerap data
description: Pelajari cara mengimpor data dari berbagai sumber.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643957"
---
# <a name="overview-about-data-sources"></a>Ikhtisar tentang sumber data

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Kemampuan wawasan audiens di Dynamics 365 Customer Insights terhubung ke data dari sekumpulan sumber yang luas. Menghubungkan ke sumber data sering disebut sebagai proses *penyerapan data*. Setelah menyerap data, Anda dapat [menyatukan](data-unification.md), dan melakukan tindakan padanya.

## <a name="add-a-data-source"></a>Tambahkan sumber data

Lihat artikel rinci tentang cara menambahkan sumber data, tergantung pada pilihan yang anda pilih.

Anda dapat menambahkan sumber data dengan tiga cara utama:

- [melalui lusinan Power Query connectors](connect-power-query.md)
- [Dari folder Common Data Model](connect-common-data-model.md)
- [Dari Danau Common Data Service Anda sendiri](connect-common-data-service-lake.md)

> [!NOTE]
> Anda tidak dapat menambahkan data dari sumber data lokal.

## <a name="review-ingested-data"></a>Meninjau data yang diserap

Anda akan melihat nama dari setiap sumber data yang diserap, statusnya, serta waktu terakhir data disegarkan untuk sumber itu. Anda dapat mengurutkan daftar sumber data menurut setiap kolom.

> [!div class="mx-imgBorder"]
> ![Sumber Data ditambahkan](media/configure-data-datasource-added.png "Sumber Data ditambahkan")

|Status  |KETERANGAN  |
|---------|---------|
|Berhasil   |Sumber data berhasil diserap jika waktu disebutkan di bidang **Disegarkan**.
|Belum dimulai   |Sumber data belum diserap datanya atau masih dalam mode draf.         |
|Me-refresh    |Penyerapan data sedang berlangsung. Anda dapat membatalkan operasi ini dengan memilih **berhenti menyegarkan** di kolom **tindakan**. Menghentikan refresh sumber data akan mengembalikannya ke status refresh terakhir.       |
|Gagal     |Penyerapan data mengalami kesalahan.         |

Pilih status **Penyegaran** untuk meninjau rincian lebih lanjut tentang status penyegaran, termasuk rincian kesalahan dan pembaruan proses hilir.

Pemuatan data dapat memerlukan waktu. Setelah penyegaran berhasil, data yang terserap dapat ditinjau dari halaman **entitas**. Untuk informasi lebih lanjut, [Entitas](entities.md).

## <a name="refresh-a-data-source"></a>Segarkan sumber data

Sumber data dapat disegarkan dengan jadwal otomatis atau diperbarui secara manual sesuai permintaan. 

Buka **admin** > **sistem** > [**jadwal**](system.md#schedule-tab) untuk mengkonfigurasi penyegaran terjadwal dari semua sumber data Anda yang diserap.

Untuk me-refresh sumber data sesuai permintaan, ikuti langkah berikut:

1. Di wawasan audiens, buka **Data** > **Sumber data**

2. Pilih elipsis vertikal di sebelah sumber data ingin anda refresh dan pilih **Segarkan** dari daftar drop-down.

3. Sumber data sekarang dipicu untuk penyegaran manual. Menyegarkan sumber data akan memperbarui skema entitas serta data untuk semua entitas yang ditentukan dalam sumber data.

4. Pilih **Hentikan penyegaran** jika Anda ingin membatalkan refresh yang ada dan sumber data akan kembali ke status refresh terakhirnya.

## <a name="delete-a-data-source"></a>Hapus sumber data

1. Di wawasan audiens, buka **Data** > **Sumber data**.

2. Pilih elipsis vertikal di sebelah sumber data yang akan dihapus dan pilih **Hapus** dari menu drop-down.

3. Konfirmasikan penghapusan.
