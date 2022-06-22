---
title: Gunakan akun Gen2 Anda sendiri Azure Data Lake Storage
author: mukeshpo
description: Pelajari tentang persyaratan untuk menggunakan akun Anda sendiri Azure Data Lake Storage untuk menyimpan data Customer Insights.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5acb58906c1a9db54337f3b4dc2ab7891db7954e
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011937"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Gunakan akun Gen2 Anda sendiri Azure Data Lake Storage

Dynamics 365 Customer Insights memberi Anda opsi untuk menyimpan semua data Anda di [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Dengan menyimpan data ke Data Lake Storage, Anda setuju bahwa data akan ditransfer ke dan disimpan di lokasi geografis yang sesuai untuk akun penyimpanan Azure tersebut. Untuk informasi selengkapnya, lihat [Pusat Kepercayaan Microsoft](https://www.microsoft.com/trust-center).

Administrator di Customer Insights dapat [membuat lingkungan](create-environment.md) dan [menentukan opsi](create-environment.md#step-2-configure-data-storage) penyimpanan data dalam prosesnya.

## <a name="prerequisites-to-use-your-storage-account"></a>Prasyarat untuk menggunakan akun penyimpanan Anda

- Azure Data Lake Storage akun harus berada di wilayah Azure yang sama dengan yang Anda pilih saat membuat lingkungan Customer Insights. Anda dapat memeriksa wilayah lingkungan Customer Insights di bawah **Admin** > **System** > **About**.
- Data Lake Storage harus Gen2 dan mengaktifkan [namespace hierarki](/azure/storage/blobs/create-data-lake-storage-account). Akun penyimpanan Gen1 tidak didukung.
- Kontainer bernama `customerinsights` harus ada di akun penyimpanan. Anda harus membuatnya sebelum menggunakan Data Lake Storage Anda sendiri di Customer Insights. Administrator yang menyiapkan lingkungan Customer Insights memerlukan peran Storage Blob Data kontributor atau Storage Blob Data Owner pada akun penyimpanan atau `customerinsights` kontainer. Untuk informasi selengkapnya tentang menetapkan izin di akun penyimpanan, lihat [Membuat akun](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) penyimpanan.

## <a name="connect-customer-insights-with-your-storage-account"></a>Menghubungkan Customer Insights dengan akun penyimpanan Anda

Saat Anda membuat lingkungan baru, pastikan akun Data Lake Storage ada dan semua prasyarat terpenuhi.

1. **Dalam langkah Penyimpanan data** selama pembuatan lingkungan, atur **Simpan data** output ke **Azure Data Lake Storage Gen2**.
1. Pilih cara **Menyambungkan penyimpanan** Anda. Anda dapat memilih antara opsi berbasis sumber daya dan opsi berbasis langganan untuk autentikasi. Untuk informasi selengkapnya, lihat [Menyambungkan ke akun dengan Azure Data Lake Storage menggunakan Azure Service Principal](connect-service-principal.md).
   - Untuk **langganan** Azure, pilih **langganan**, **Grup** sumber daya, dan **akun** Penyimpanan yang berisi `customerinsights` kontainer.
   - Untuk **Kunci akun**, berikan **nama** Akun dan **kunci** Akun untuk akun Data Lake Storage. Menggunakan metode autentikasi ini menyiratkan bahwa Anda diberi tahu jika organisasi Anda memutar kunci. Anda harus [memperbarui konfigurasi](manage-environments.md#edit-an-existing-environment) lingkungan dengan kunci baru saat diputar.
1. Pilih apakah Anda ingin menggunakan Azure Private Link untuk menyambungkan ke akun penyimpanan dan [membuat koneksi ke Private Link](security-overview.md#private-links-tab) dengan proses dua langkah.

Ketika proses sistem seperti penyerapan data selesai, sistem membuat folder yang sesuai di akun penyimpanan. File data dan file *model.json* dibuat dan ditambahkan ke folder berdasarkan nama proses.

Jika Anda membuat beberapa lingkungan Customer Insights dan memilih untuk menyimpan entitas output dari lingkungan tersebut ke akun penyimpanan Anda, Customer Insights akan membuat folder terpisah untuk setiap lingkungan dengan `ci_environmentID` dalam wadah.
