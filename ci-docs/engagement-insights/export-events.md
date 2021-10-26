---
title: Mengekspor aktivitas disempurnakan
description: Cara mengekspor aktivitas dan aktivitas dasar yang disempurnakan.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7881f8f63134170a7f76e3c75dcfc5fa8930754b
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606224"
---
# <a name="export-events"></a>Ekspor aktivitas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Aktivitas menunjukkan perilaku pengguna. Ia merekam ketika pengguna melihat halaman (aktivitas melihat) atau berinteraksi dengan konten (aktivitas tindakan). Bila Anda dapat memutuskan properti data yang akan ditampilkan dalam laporan, tampilan virtual data ini disebut *aktivitas yang disempurnakan*. Untuk informasi lebih lanjut, lihat [Buat dan modifikasi aktivitas](refined-events.md).

- Anda dapat mengekspor aktivitas dan aktivitas disempurnakan ke penyimpanan eksternal. 
- Ekspor merupakan aliran data penerusan. Anda tidak dapat mengisi ulang aliran. 
- Ekspor memiliki skema tetap. Jika Anda menambahkan properti kustom ke aktivitas, properti tersebut tidak akan disertakan. Anda harus membuat ekspor baru.

## <a name="prerequisites"></a>Prasyarat

Sebelum menyiapkan ekspor, Anda harus memiliki akses dan langganan aktif ke portal Azure. Anda memerlukan informasi akun penyimpanan selama proses ekspor. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Buat akun Azure Data Lake Storage Gen 2

1. Masuk ke portal Azure dan [buat akun penyimpanan baru](/azure/storage/common/storage-account-create). 

1. Pastikan Anda mengaktifkan **namespace hierarkis** pada tab **Tingkat Lanjut**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Aktifkan namespace hierarkis pada tab Tingkat Lanjut.":::

1. Setelah diterapkan, buka akun penyimpanan yang baru dibuat. Di panel navigasi, pilih **pengaturan** > **Kunci Akses**. 

1. Salin **nama Akun** dan **Kunci** untuk menggunakannya saat membuat ekspor baru.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Kunci akses di akun penyimpanan.":::

## <a name="export-events"></a>Ekspor aktivitas

Ada dua cara untuk menghadirkan dialog **Aktivitas Ekspor**: 
- Buka **Data** > **ekspor**, lalu pilih **ekspor baru**.
- Buka **Data** > **Aktivitas**, pilih **Lainnya [...]** di samping aktivitas yang akan diekspor, lalu pilih **Ekspor** dari menu dropdown. 

:::image type="content" source="media/new-export.png" alt-text="Membuat ekspor baru.":::

Anda dipandu melalui langkah-langkah untuk membuat ekspor:

1. Berikan **nama Ekspor**, lalu pilih **Berikutnya**.

1. Dalam daftar menurun **pilihan Aktivitas**, pilih aktivitas dasar dan aktivitas disempurnakan untuk disertakan dalam ekspor. 

1. Di bagian **Struktur file**, pilih irama (per jam atau harian) untuk membuat file baru dalam penyimpanan tujuan, lalu pilih **Berikutnya**. Aktivitas akan diekspor terus-menerus saat mereka tiba.

1. Dalam dialog **Pilih format**, pilih format untuk ekspor Anda. Pilih antara format **Common Data Model**, **CSV**, dan **JSON**. Untuk menggunakan ekspor dengan aplikasi Dynamics 365 lainnya, sebaiknya gunakan format **Common Data Model**.

1. Dalam dialog **Pilih tujuan**, tentukan lokasi Azure Data Lake Storage Gen 2.
    1. **Nama akun ADLS Gen 2** adalah nama akun penyimpanan tempat menyimpan ekspor. 
    1. **Jalur folder** menentukan lokasi ekspor harus disimpan dalam sistem file dan struktur direktori akun penyimpanan.
    1. **Kunci bersama** tersedia dari portal Azure untuk akun penyimpanan.

1. Tinjau dan konfirmasikan pilihan Anda untuk menyelesaikan.

## <a name="view-and-manage-exports"></a>Melihat dan mengelola ekspor

Setelah Anda mengkonfigurasi ekspor, buka **Data** > **Ekspor** untuk melihatnya. Pilih **Lainnya [...]** untuk ekspor yang ada agar dapat mengedit atau menghapusnya.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
