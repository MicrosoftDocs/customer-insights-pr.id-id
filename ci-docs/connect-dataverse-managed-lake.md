---
title: Menyambung ke data di Data Lake yang dikelola oleh Microsoft Dataverse
description: Impor data dari Data Lake terkelola Microsoft Dataverse.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206957"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Menyambung ke data di Data Lake yang dikelola oleh Microsoft Dataverse

Microsoft Dataverse pengguna dapat dengan cepat terhubung ke entitas analitis di danau terkelola Microsoft Dataverse. Hanya satu sumber data dari lingkungan yang dapat secara simultan menggunakan danau terkelola Dataverse yang sama.

> [!NOTE]
> Anda harus menjadi admin di Dataverse organisasi untuk melanjutkan dan melihat daftar entitas yang tersedia di danau terkelola.

## <a name="prerequisites"></a>Prasyarat

- Data yang tersimpan di layanan online, misalnya Azure Data Lake Storage, dapat disimpan di lokasi yang berbeda dengan data yang diproses atau disimpan di Dynamics 365 Customer Insights.Dengan mengimpor atau menghubungkan ke data yang disimpan dalam layanan online, Anda setuju bahwa data dapat ditransfer ke dan disimpan dengan Dynamics 365 Customer Insights. [Pelajari selengkapnya di Pusat](https://www.microsoft.com/trust-center) Kepercayaan Microsoft.

- Hanya Dataverse entitas dengan [pelacakan](/power-platform/admin/enable-change-tracking-control-data-synchronization) perubahan yang diaktifkan yang terlihat. Entitas ini dapat diekspor ke data lake yang Dataverse dikelola dan digunakan dalam Customer Insights. Tabel out-of-box Dataverse memiliki pelacakan perubahan yang diaktifkan secara default. Anda perlu mengaktifkan pelacakan perubahan untuk tabel kustom. Untuk memeriksa apakah Dataverse tabel diaktifkan untuk pelacakan perubahan, buka [Power Apps](https://make.powerapps.com) > **Tabel** > **Data**. Temukan tabel minat Anda dan pilih. Buka **pengaturan** > **opsi** Lanjutan dan tinjau **pengaturan Lacak perubahan**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Terhubung ke danau yang dikelola Dataverse

1. Buka **Data** > **Sumber data**.

1. Pilih **Tambahkan sumber data**.

1. Pilih **Microsoft Dataverse**.

1. **Masukkan Nama** untuk sumber data dan Deskripsi **opsional**.

1. Sediakan **alamat Server** untuk organisasi Dataverse, dan pilih **masuk**.

1. Pilih tabel yang ingin Anda serap sebagai entitas ke Customer Insights dari daftar yang tersedia.

   > [!NOTE]
   > Jika beberapa tabel sudah dipilih, tabel mungkin digunakan oleh aplikasi Dynamics 365 lainnya (seperti Dynamics 365 Sales Insights atau Customer Service Insights). Anda tidak dapat mengubah pilihan. Tabel ini akan tersedia sebagai entitas setelah sumber data dibuat.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Kotak dialog memperlihatkan daftar entitas di lingkungan Dataverse.":::

1. Simpan pilihan Anda untuk mulai menyinkronkan tabel yang dipilih dari Dataverse. Anda akan menemukan sambungan yang baru ditambahkan pada halaman **sumber data**. Ini akan diantrikan untuk refresh dan menunjukkan jumlah entitas sebagai 0 sampai semua tabel yang dipilih disinkronkan.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuat data dapat memakan waktu. Setelah refresh berhasil, data yang diserap dapat ditinjau dari [**halaman Entitas**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Edit sumber data danau terkelola Dataverse

Anda hanya mengedit pilihan entitas setelah membuat sumber data. Misalnya, jika entitas tambahan ditambahkan ke Dataverse dan Anda ingin mengimpornya juga.
Untuk menyambungkan ke Dataverse data lake yang berbeda, [buat sumber data baru](#connect-to-a-dataverse-managed-lake).

1. Buka **Data** > **Sumber data**.

1. Di samping sumber data yang ingin Anda perbarui, pilih **Edit**.

1. Pilih entitas tambahan dari daftar entitas yang tersedia.

1. Klik **Simpan** untuk menerapkan perubahan Anda dan kembali ke **halaman Sumber** data.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
