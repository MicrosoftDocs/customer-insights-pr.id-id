---
title: Menyambungkan tabel di Microsoft Dataverse
description: Impor data dari Data Lake terkelola Microsoft Dataverse.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033084"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Menyambung ke data di Data Lake yang dikelola oleh Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Artikel ini menyediakan informasi tentang bagaimana pengguna Dataverse dapat dengan cepat terhubung ke entitas analitik mereka di danau terkelola Dataverse. Anda harus menjadi admin pada organisasi Dataverse untuk melanjutkan dan melihat daftar entitas yang tersedia di Danau terkelola.

## <a name="important-considerations"></a>Pertimbangan penting

Data yang tersimpan di layanan online, misalnya Azure Data Lake Storage, dapat disimpan di lokasi yang berbeda dengan data yang diproses atau disimpan di Dynamics 365 Customer Insights.Dengan mengimpor atau menyambung ke data yang tersimpan di layanan online, Anda setuju bahwa data dapat ditransfer ke dan disimpan dengan Dynamics 365 Customer Insights. [Pelajari lebih lanjut di pusat kepercayaan Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Terhubung ke danau yang dikelola Dataverse

1. Di wawasan audiens, buka **Data** > **Sumber data**.

2. Pilih **Tambahkan sumber data**.

3. Pilih **Sambungkan ke danau terkelola Microsoft Dataverse** dan pilih **Berikutnya**.

4. Masukkan **nama** untuk sumber data, lalu pilih **Berikutnya**. Panduan nama: 
   - Diawali dengan huruf.
   - Gunakan huruf dan angka saja. Spasi atau karakter khusus tidak dibolehkan.
   - Gunakan antara 3 hingga 64 karakter.

5. Sediakan **alamat Server** untuk organisasi Dataverse, dan pilih **masuk**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Layar dalam langkah penyerapan data di mana pengguna dapat memasukkan URL lingkungan Dataverse.":::

6. Pilih tabel yang ingin Anda serap sebagai entitas untuk wawasan audiens dari daftar yang tersedia.    

   > [!NOTE]
   > Jika beberapa tabel sudah dipilih, tabel mungkin digunakan oleh aplikasi Dynamics 365 lainnya (seperti Dynamics 365 Sales Insights atau Customer Service Insights). Anda tidak dapat mengubah pilihan. Tabel ini akan tersedia sebagai entitas setelah sumber data dibuat.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Kotak dialog memperlihatkan daftar entitas di lingkungan Dataverse.":::

7. Simpan pilihan Anda untuk mulai menyinkronkan tabel yang dipilih dari Dataverse. Anda akan menemukan sambungan yang baru ditambahkan pada halaman **sumber data**. Ini akan diantrikan untuk refresh dan menunjukkan jumlah entitas sebagai 0 sampai semua tabel yang dipilih disinkronkan.

Hanya satu sumber data dari lingkungan yang dapat secara simultan menggunakan danau terkelola Dataverse yang sama.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Edit sumber data danau terkelola Dataverse

Anda hanya mengedit pilihan entitas setelah membuat sumber data. Misalnya, jika entitas tambahan ditambahkan ke Dataverse dan Anda ingin mengimpornya juga.    
Untuk menyambungkan ke Dataverse data lake yang berbeda, [buat sumber data baru](#connect-to-a-dataverse-managed-lake).

1. Di wawasan audiens, buka **Data** > **Sumber data**.

2. Di samping sumber data yang ingin anda perbarui, pilih elipsis.

3. Pilih opsi **Edit** dari daftar.

4. Pilih entitas tambahan dari daftar entitas yang tersedia dan pilih **Simpan**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]