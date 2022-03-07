---
title: Mengelola aturan persetujuan default pada segmen
description: Dengan kemampuan manajemen persetujuan, Anda dapat menonaktifkan atau mengubah aturan persetujuan default jika penggantian diaktifkan.
ms.date: 12/01/2021
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4eae4da67fd4c6e70800f495ba30366d4fc9a0dd
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228943"
---
# <a name="disable-or-change-default-consent-rules"></a>Menonaktifkan atau mengubah aturan persetujuan default

Jika organisasi Anda menggunakan [kemampuan](../consent-management/overview.md) manajemen persetujuan yang dikombinasikan dengan audiens insight, [admin dapat menerapkan aturan](activate-consent.md) persetujuan untuk segmen. 

Dengan aturan persetujuan yang diberlakukan di area segmen, setiap segmen menginformasikan tentang keadaan pemeriksaan persetujuan dan aturan. Jika penggantian diizinkan, aturan persetujuan default akan dinonaktifkan untuk segmen tertentu. Setiap pembuat segmen dapat menambahkan lebih banyak aturan persetujuan di atas aturan default ke segmen. 

## <a name="for-administrators"></a>Untuk administrator

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Pembuat segmen dengan opsi aturan persetujuan.":::

**Untuk menonaktifkan aturan persetujuan default:**

1. **Dalam pemberitahuan Aturan persetujuan**, pilih **Lihat detailnya**. 

1. Atur aturan **persetujuan** default beralih ke **Mati**.

**Untuk menambahkan lebih banyak aturan persetujuan:**

1. **Dalam pemberitahuan Aturan persetujuan**, pilih **Lihat detailnya**. 

1. Pilih **Tambahkan aturan** persetujuan dan pilih aturan persetujuan dari **menu pilihan jenis** data persetujuan.

1. Pilih **Simpan** untuk menerapkan aturan baru ke segmen.

## <a name="for-contributors"></a>Untuk kontributor

Untuk membuat segmen tanpa aturan persetujuan yang diberlakukan, Anda harus bekerja sama dengan administrator untuk menonaktifkannya di segmen Anda. Namun, Anda dapat menambahkan aturan persetujuan Anda sendiri ke segmen yang Anda miliki dan kelola.

Ini adalah proses tiga langkah: 
1. [Buat segmen](segments.md) dalam audiens wawasan dan simpan. 

1. Bagikan nama segmen dengan admin Anda dan minta mereka untuk [mengaktifkan penggantian untuk segmen](activate-consent.md) Anda. 

1. Buka segmen Anda lagi. **Dalam pemberitahuan aturan Persetujuan**, pilih **Lihat detail** dan tambahkan aturan persetujuan yang ingin Anda terapkan. Kemudian, **Simpan** dan **Jalankan** segmen Anda.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
