---
title: Mengelola aturan persetujuan default pada segmen
description: Dengan kemampuan manajemen persetujuan, Anda dapat menonaktifkan atau mengubah aturan persetujuan default jika penggantian diaktifkan.
ms.date: 12/01/2021
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 43f03ea97765e112a8ea2a7da97cc548c8c84dfc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642579"
---
# <a name="disable-or-change-default-consent-rules"></a>Menonaktifkan atau mengubah aturan persetujuan default

Jika organisasi Anda menggunakan [kemampuan](consent-management/overview.md) manajemen persetujuan dengan Dynamics 365 Customer Insights, [admin dapat menerapkan aturan](activate-consent.md) persetujuan untuk segmen. 

Dengan aturan persetujuan yang diberlakukan di area segmen, setiap segmen menginformasikan tentang status pemeriksaan dan aturan persetujuan. Jika penimpaan diizinkan, aturan persetujuan default dinonaktifkan untuk segmen tertentu. Setiap pembuat segmen dapat menambahkan lebih banyak aturan persetujuan di atas aturan default ke segmen. 

## <a name="for-administrators"></a>Untuk administrator

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Pembuat segmen dengan opsi aturan persetujuan.":::

**Untuk menonaktifkan aturan persetujuan default:**

1. **Di notifikasi Aturan** persetujuan, pilih **Lihat detailnya**. 

1. **Atur aturan Persetujuan default** untuk beralih ke **Nonaktif**.

**Untuk menambahkan lebih banyak aturan persetujuan:**

1. **Di notifikasi Aturan** persetujuan, pilih **Lihat detailnya**. 

1. Pilih **Tambahkan aturan** persetujuan dan pilih aturan persetujuan dari **dropdown Pilih tipe** data persetujuan.

1. Pilih **Simpan** untuk menerapkan aturan baru ke segmen.

## <a name="for-contributors"></a>Untuk kontributor

Untuk membuat segmen tanpa aturan persetujuan yang diberlakukan, Anda harus bekerja sama dengan administrator untuk menonaktifkannya di segmen Anda. Namun, Anda dapat menambahkan aturan persetujuan Anda sendiri ke segmen yang Anda miliki dan kelola.

Ini adalah proses tiga langkah: 
1. [Buat segmen](segments.md) di Customer Insights dan simpan. 

1. Bagikan nama segmen dengan admin Anda dan minta mereka untuk [mengaktifkan penggantian untuk segmen](activate-consent.md) Anda. 

1. Buka segmen Anda lagi. **Dalam pemberitahuan Aturan** persetujuan, pilih **Lihat detail** dan tambahkan aturan persetujuan yang ingin Anda terapkan. Kemudian, **Simpan** dan **Jalankan** segmen Anda.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
