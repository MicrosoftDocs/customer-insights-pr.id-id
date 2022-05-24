---
title: Membuat tampilan terpadu pelanggan Anda
description: Melalui proses penyatuan data dengan data Anda untuk membuat satu himpunan data profil pelanggan terpadu.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: bb8da6f4b9f92f2b265ff9807e04638edae4f814
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755738"
---
# <a name="data-unification-overview"></a>Ikhtisar penyatuan data

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Setelah [mengkonfigurasi sumber data](data-sources.md), Anda dapat menyatukan data. Penyatuan data memungkinkan Anda menyatukan sumber data yang pernah berbeda menjadi satu himpunan data master yang menyediakan tampilan terpadu dari data tersebut. Untuk konsumen individu (B-to-C) di mana data berpusat di sekitar individu, penyatuan memberikan pandangan terpadu tentang pelanggan Anda. Untuk akun bisnis (B-to-B) di mana data berpusat di sekitar akun, penyatuan memberikan tampilan terpadu akun Anda.

Data dapat disatukan pada satu entitas atau beberapa entitas. Penyatuan dilakukan dalam urutan berikut:

1. [Bidang sumber](map-entities.md) (sebelumnya disebut Peta): Di langkah bidang sumber, pilih entitas dan bidang untuk disertakan dalam proses pemersatu. Petakan bidang ke tipe semantik umum yang menggambarkan tujuan bidang.

1. [Catatan](remove-duplicates.md) duplikat (sebelumnya bagian dari Pencocokan): Pada langkah catatan duplikat, tentukan aturan opsional untuk menghapus catatan pelanggan duplikat dari dalam setiap entitas.

1. [Kondisi pencocokan](match-entities.md) (sebelumnya disebut Cocokkan): Dalam langkah kondisi yang cocok, tentukan aturan yang cocok dengan catatan pelanggan antar entitas. Ketika pelanggan ditemukan dalam dua entitas atau lebih, satu rekaman konsolidasi dibuat dengan semua kolom dan data dari setiap entitas.

1. [Bidang pelanggan terpadu](merge-entities.md) (sebelumnya disebut Gabungkan): Dalam langkah bidang pelanggan terpadu, tentukan bidang sumber mana yang harus disertakan, dikecualikan, atau digabungkan ke dalam profil pelanggan terpadu.  

1. [Tinjau](review-unification.md) dan buat profil terpadu.

Setelah menyelesaikan penyatuan data, Anda dapat secara opsional:

- [Siapkan Relasi antar entitas](relationships.md) untuk membuat segmen yang canggih.
- [Perkaya data](enrichment-hub.md) Anda untuk mendapatkan wawasan yang lebih luas tentang pelanggan Anda.
- [Tentukan aktivitas](activities.md) dari beberapa atribut yang tertelan.
- [Membangun langkah-langkah](measures.md) untuk lebih memahami perilaku pelanggan dan kinerja bisnis.

[!INCLUDE [footer-include](includes/footer-banner.md)]
