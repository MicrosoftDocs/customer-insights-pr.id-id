---
title: Menyambung ke data di Data Lake yang dikelola oleh Microsoft Dataverse
description: Impor data dari Data Lake terkelola Microsoft Dataverse.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 9ae0b964d8d39835715b7ddadc712e2338b855af
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082156"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Menyambung ke data di Data Lake yang dikelola oleh Microsoft Dataverse

Microsoft Dataverse pengguna dapat dengan cepat terhubung ke entitas analitis di danau terkelola Microsoft Dataverse.

> [!NOTE]
> Anda harus menjadi admin di Dataverse organisasi untuk melanjutkan dan melihat daftar entitas yang tersedia di danau terkelola.

## <a name="important-considerations"></a>Pertimbangan penting

1. Data yang tersimpan di layanan online, misalnya Azure Data Lake Storage, dapat disimpan di lokasi yang berbeda dengan data yang diproses atau disimpan di Dynamics 365 Customer Insights.Dengan mengimpor atau menghubungkan ke data yang disimpan dalam layanan online, Anda setuju bahwa data dapat ditransfer ke dan disimpan dengan Dynamics 365 Customer Insights. [Pelajari selengkapnya di Pusat](https://www.microsoft.com/trust-center) Kepercayaan Microsoft.
2. Hanya Dataverse entitas dengan [pelacakan](/power-platform/admin/enable-change-tracking-control-data-synchronization) perubahan yang diaktifkan yang terlihat. Entitas ini dapat diekspor ke data lake yang Dataverse dikelola dan digunakan dalam Customer Insights. Tabel out-of-box Dataverse memiliki pelacakan perubahan yang diaktifkan secara default. Anda perlu mengaktifkan pelacakan perubahan untuk tabel kustom. Untuk memeriksa apakah Dataverse tabel diaktifkan untuk pelacakan perubahan, buka [Power Apps](https://make.powerapps.com) > **Tabel** > **Data**. Temukan tabel minat Anda dan pilih. Buka **pengaturan** > **opsi** Lanjutan dan tinjau **pengaturan Lacak perubahan**.

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

Hanya satu sumber data dari lingkungan yang dapat secara simultan menggunakan danau terkelola Dataverse yang sama.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Edit sumber data danau terkelola Dataverse

Anda hanya mengedit pilihan entitas setelah membuat sumber data. Misalnya, jika entitas tambahan ditambahkan ke Dataverse dan Anda ingin mengimpornya juga.
Untuk menyambungkan ke Dataverse data lake yang berbeda, [buat sumber data baru](#connect-to-a-dataverse-managed-lake).

1. Buka **Data** > **Sumber data**.

1. Di samping sumber data yang ingin Anda perbarui, pilih **Edit**.

1. Pilih entitas tambahan dari daftar entitas yang tersedia dan pilih **Simpan**.
