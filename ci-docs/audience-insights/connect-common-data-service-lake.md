---
title: Sambungkan ke entitas di Danau terkelola Common Data Service
description: Impor data dari Data Lake terkelola Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643402"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Menyambung ke data di Data Lake yang dikelola oleh Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Artikel ini memberikan informasi tentang bagaimana pelanggan Dynamics 365 yang ada dapat dengan cepat terhubung ke entitas analitik mereka di Danau terkelola Common Data Service. Anda harus menjadi admin pada organisasi Common Data Service untuk melanjutkan dan melihat daftar entitas yang tersedia di Danau terkelola.

## <a name="important-considerations"></a>Pertimbangan penting

Data yang tersimpan di layanan online, misalnya Azure Data Lake Storage, dapat disimpan di lokasi yang berbeda dengan data yang diproses atau disimpan di Dynamics 365 Customer Insights.Dengan mengimpor atau menyambung ke data yang tersimpan di layanan online, Anda setuju bahwa data dapat ditransfer ke dan disimpan dengan Dynamics 365 Customer Insights. [Pelajari lebih lanjut di pusat kepercayaan Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Terhubung ke danau yang dikelola Common Data Service

1. Di wawasan audiens, buka **Data** > **Sumber data**.

2. Pilih **Tambahkan sumber data**.

3. Pilih **Sambungkan ke Common Data Service** dan pilih **berikutnya**.

4. Masukkan **nama** untuk sumber data, lalu pilih **Berikutnya**.

5. Berikan **Alamat server** untuk organisasi Anda Common Data Service, lalu pilih **masuk**.

   > [!div class="mx-imgBorder"]
   > ![Kotak dialog untuk memasukkan Alamat server Common Data Service](media/enter-CDS-org-details.png)

6. Pilih entitas yang ingin Anda serap dari daftar yang tersedia.    

   > [!NOTE]
   > Jika beberapa entitas telah dipilih, mereka dapat digunakan oleh aplikasi dynamics 365 lainnya (seperti Dynamics 365 Sales Insights atau Customer Service Insights). Anda tidak dapat mengubah pilihan. Entitas ini akan tersedia setelah sumber data dibuat.

   > [!div class="mx-imgBorder"]
   > ![Kotak dialog menampilkan daftar entitas di organisasi Common Data Service](media/select-analytical-entities.png)

7. Simpan pilihan Anda untuk mulai mensinkronisasi entitas yang dipilih ke Danau terkelola Common Data Service. Anda akan menemukan sambungan yang baru ditambahkan pada halaman **sumber data**. Ini akan diantre untuk refresh dan menampilkan jumlah entitas sebagai 0 hingga semua entitas disinkronisasikan.

Hanya satu sumber data dari lingkungan yang dapat secara simultan menggunakan danau terkelola Common Data Service yang sama.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Edit sumber data danau terkelola Common Data Service

Anda hanya mengedit pilihan entitas setelah membuat sumber data. Misalnya, jika entitas tambahan ditambahkan ke Common Data Service dan Anda ingin mengimpornya juga.    
Untuk menghubungkan ke Common Data Service berbeda, [buat sumber data baru](#connect-to-a-common-data-service-managed-lake).

1. Di wawasan audiens, buka **Data** > **Sumber data**.

2. Di samping sumber data yang ingin anda perbarui, pilih elipsis.

3. Pilih opsi **Edit** dari daftar.

4. Pilih entitas tambahan dari daftar entitas yang tersedia dan pilih **Simpan**.
