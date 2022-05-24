---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755548"
---
Setelah menelan data, mulailah proses penyatuan data untuk membuat profil pelanggan terpadu. Untuk informasi selengkapnya, lihat [Penyatuan data](../data-unification.md).

### <a name="select-source-fields"></a>Pilih bidang sumber

1. Setelah menyerap data, Petakan kontak dari eCommerce dan data kesetiaan ke jenis data umum. **Buka Data** > **Unify**.

1. Pilih entitas yang menunjukkan profil pelanggan- **ecommercecontacts** dan **loycustomer**.

   ![menyatukan sumber data eCommerce dan kesetiaan.](../media/unify-ecommerce-loyalty.png)

1. Pilih **contactid** sebagai kunci primer untuk **ecommercecontacts** dan **loyaltyid** sebagai kunci primer untuk **loycustomer**.

1. Pilih **Selanjutnya**. Lewati catatan duplikat dan pilih **Berikutnya**.

### <a name="match-conditions"></a>Kondisi pertandingan

1. Pilih **eCommerceContacts: eCommerce** sebagai entitas utama dan sertakan semua catatan.

1. Pilih **loyCustomers: LoyaltyScheme** dan sertakan semua catatan.

1. Menambahkan aturan:
   - Pilih **FullName** untuk eCommerceContacts dan loyCustomers.
   - Pilih **Ketik (Telepon, Nama, Alamat, ...)** untuk **Normalisasi**.
   - Atur **tingkat presisi**: **dasar** dan **nilai**: **tinggi**.
   - Masukkan **FullName, Email** untuk namanya.

1. Tambahkan kondisi kedua untuk alamat email:
   - Pilih **Email** untuk eCommerceContacts dan loyCustomers.
   - Biarkan Normalkan kosong.
   - Atur **tingkat presisi**: **dasar** dan **nilai**: **tinggi**.

   ![Satukan aturan kecocokan untuk nama dan email.](../media/unify-match-rule.png)

1. Pilih **Selesai**.

1. Pilih **Selanjutnya**.

### <a name="unify-fields"></a>Menyatukan bidang

1. **Ganti nama ContactId** untuk **entitas loyCustomers** menjadi **ContactIdLOYALTY** untuk membedakannya dari ID lain yang tertelan.

1. Pilih **Berikutnya** untuk meninjau lalu pilih **Buat profil** pelanggan.
