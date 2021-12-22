---
title: Mengelola aturan persetujuan default pada segmen
description: Dengan kemampuan manajemen persetujuan, Anda dapat menonaktifkan atau mengubah aturan persetujuan default jika menimpa diaktifkan.
ms.date: 12/01/2021
ms.service: customer-insights
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28c9ea49b1f3aebd3abd7d4de58fe61e6474158b
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884174"
---
# <a name="disable-or-change-default-consent-rules"></a>Menonaktifkan atau mengubah aturan persetujuan default

Jika organisasi Anda menggunakan [kemampuan manajemen persetujuan yang dikombinasikan dengan wawasan](../consent-management/overview.md) audiens, admin dapat menegakkan aturan persetujuan [untuk](activate-consent.md) segmen. 

Dengan aturan persetujuan yang diberlakukan di area segmen, setiap segmen menginformasikan tentang keadaan pemeriksaan persetujuan dan aturan. Jika penipu diizinkan, aturan persetujuan default dinonaktifkan untuk segmen tertentu. Setiap pembuat segmen dapat menambahkan lebih banyak aturan persetujuan di atas aturan default ke segmen. 

## <a name="for-administrators"></a>Untuk administrator

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Pembangun segmen dengan opsi aturan persetujuan.":::

**Untuk menonaktifkan aturan persetujuan default:**

1. Dalam **pemberitahuan aturan** Persetujuan, pilih **Lihat** detailnya. 

1. Atur **aturan persetujuan Default** beralih ke **Mati**.

**Untuk menambahkan lebih banyak aturan persetujuan:**

1. Dalam **pemberitahuan aturan** Persetujuan, pilih **Lihat** detailnya. 

1. Pilih **Tambahkan aturan persetujuan dan pilih aturan persetujuan dari** **dropdown tipe data persetujuan** Pilih.

1. Pilih **Simpan untuk menerapkan aturan baru ke** segmen.

## <a name="for-contributors"></a>Untuk kontributor

Untuk membuat segmen tanpa aturan persetujuan yang diberlakukan, Anda harus bekerja dengan administrator Anda untuk menonaktifkannya di segmen Anda. Namun, Anda dapat menambahkan aturan persetujuan Anda sendiri ke segmen yang Anda miliki dan kelola.

Ini adalah proses tiga langkah: 
1. [Buat segmen](segments.md) dalam wawasan audiens dan simpan. 

1. Bagikan nama segmen dengan admin Anda dan minta mereka untuk [mengaktifkan penilang untuk segmen](activate-consent.md) Anda. 

1. Buka segmen Anda lagi. Dalam **pemberitahuan aturan** Persetujuan, pilih **Lihat detail dan tambahkan aturan persetujuan yang ingin Anda** terapkan. Kemudian, **Simpan dan Jalankan segmen** **Anda**.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
