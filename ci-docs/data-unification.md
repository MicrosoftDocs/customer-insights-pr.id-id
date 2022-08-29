---
title: Membuat tampilan terpadu pelanggan Anda
description: Lakukan proses penyatuan data dengan data Anda untuk membuat satu himpunan data master akun atau profil pelanggan.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304431"
---
# <a name="data-unification-overview"></a>Ikhtisar penyatuan data

Setelah [mengkonfigurasi sumber data](data-sources.md), Anda dapat menyatukan data. Penyatuan data memungkinkan Anda menyatukan sumber data yang dulunya berbeda ke dalam satu himpunan data master yang menyediakan tampilan terpadu dari data tersebut.

Untuk konsumen individu (B-to-C) di mana data berpusat di sekitar individu, penyatuan memberikan pandangan terpadu tentang pelanggan Anda. Untuk akun bisnis (B-to-B) di mana data berpusat di sekitar akun, penyatuan memberikan tampilan terpadu dari akun Anda. [Penyatuan kontak (pratinjau)](data-unification-contacts.md) memungkinkan kontak untuk akun tersebut disatukan secara terpisah dan dikaitkan dengan akun.

Data dapat disatukan pada satu entitas atau beberapa entitas.

# <a name="individual-consumers-b-to-c"></a>[Konsumen perorangan (B-ke-C)](#tab/b2c)

Proses penyatuan memetakan data pelanggan dari sumber data Anda, menghapus duplikat, mencocokkan data di seluruh entitas, dan membuat profil terpadu. Penyatuan dilakukan dengan urutan sebagai berikut:

1. [Bidang sumber](map-entities.md) (sebelumnya disebut Peta): Di langkah bidang sumber, pilih entitas dan bidang untuk disertakan dalam proses penyatuan. Petakan bidang ke tipe semantik umum yang menjelaskan tujuan bidang.

1. [Rekaman duplikat](remove-duplicates.md) (sebelumnya bagian dari Kecocokan): Dalam langkah data duplikat, tentukan aturan secara opsional untuk menghapus rekaman pelanggan duplikat dari dalam setiap entitas.

1. [Kondisi](match-entities.md) pencocokan (sebelumnya disebut Kecocokan): Dalam langkah kondisi pencocokan, tentukan aturan yang cocok dengan rekaman pelanggan antar entitas. Ketika pelanggan ditemukan di dua entitas atau lebih, satu rekaman terkonsolidasi dibuat dengan semua kolom dan data dari setiap entitas.

1. [Bidang](merge-entities.md) pelanggan terpadu (sebelumnya disebut Gabungkan): Dalam langkah bidang pelanggan terpadu, tentukan bidang sumber mana yang harus disertakan, dikecualikan, atau digabungkan ke dalam profil pelanggan terpadu.  

1. [Tinjau](review-unification.md) dan buat profil terpadu.

# <a name="business-accounts-b-to-b"></a>[Akun bisnis (B-ke-B)](#tab/b2b)

Proses penyatuan memetakan data akun dari sumber data Anda, menghapus duplikat, mencocokkan data di seluruh entitas, dan membuat profil terpadu. Penyatuan dilakukan dengan urutan sebagai berikut:

1. [Bidang sumber](map-entities.md) (sebelumnya disebut Peta): Di langkah bidang sumber, pilih entitas dan bidang untuk disertakan dalam proses akun pemersatu. Petakan bidang ke tipe semantik umum yang menjelaskan tujuan bidang.

1. [Rekaman duplikat](remove-duplicates.md) (sebelumnya bagian dari Kecocokan): Dalam langkah data duplikat, tentukan aturan secara opsional untuk menghapus rekaman akun duplikat dari dalam setiap entitas.

1. [Kondisi](match-entities.md) pencocokan (sebelumnya disebut Kecocokan): Dalam langkah kondisi pencocokan, tentukan aturan yang cocok dengan rekaman akun antar entitas. Ketika akun ditemukan di dua entitas atau lebih, satu rekaman terkonsolidasi dibuat dengan semua kolom dan data dari setiap entitas.

1. [Bidang](merge-entities.md) pelanggan terpadu (sebelumnya disebut Gabungkan): Dalam langkah bidang pelanggan terpadu, tentukan bidang sumber mana yang harus disertakan, dikecualikan, atau digabungkan ke dalam profil pelanggan terpadu.  

1. [Tinjau](review-unification.md) dan buat profil terpadu.

Setelah menyatukan akun, Anda dapat secara [opsional menyatukan kontak (pratinjau)](data-unification-contacts.md) untuk akun tersebut dan menautkan kontak terpadu ke akun terpadu.

---

Setelah menyelesaikan penyatuan data, Anda dapat secara opsional:

- [Siapkan Relasi antar entitas](relationships.md) untuk membuat segmen yang canggih.
- [Perkaya data](enrichment-hub.md) Anda untuk mendapatkan wawasan yang lebih luas tentang pelanggan Anda.
- [Tentukan aktivitas](activities.md) dari beberapa atribut yang tertelan.
- [Buat langkah-langkah](measures.md) untuk lebih memahami perilaku pelanggan dan kinerja bisnis.

[!INCLUDE [footer-include](includes/footer-banner.md)]
