---
title: Ikhtisar penyatuan data
description: Lakukan proses penyatuan data dengan data Anda untuk membuat satu himpunan data profil pelanggan terpadu.
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
ms.openlocfilehash: 0dbc3b2c75365e94758a1b6330e8cb557e6bd768
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082219"
---
# <a name="data-unification-overview"></a>Ikhtisar penyatuan data

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Setelah [mengkonfigurasi sumber data](data-sources.md), Anda dapat menyatukan data. Penyatuan data memungkinkan Anda menyatukan sumber data yang dulunya berbeda ke dalam satu himpunan data master yang menyediakan tampilan terpadu dari data tersebut. Untuk konsumen individu (B-to-C) di mana data berpusat di sekitar individu, penyatuan memberikan pandangan terpadu tentang pelanggan Anda. Untuk akun bisnis (B-to-B) di mana data berpusat di sekitar akun, penyatuan memberikan tampilan terpadu dari akun Anda.

Data dapat disatukan pada satu entitas atau beberapa entitas. Penyatuan dilakukan dengan urutan sebagai berikut:

1. [Bidang sumber](map-entities.md) (sebelumnya disebut Peta): Di langkah bidang sumber, pilih entitas dan bidang untuk disertakan dalam proses penyatuan. Petakan bidang ke tipe semantik umum yang menjelaskan tujuan bidang.

1. [Rekaman duplikat](remove-duplicates.md) (sebelumnya bagian dari Kecocokan): Dalam langkah data duplikat, tentukan aturan secara opsional untuk menghapus rekaman pelanggan duplikat dari dalam setiap entitas.

1. [Kondisi](match-entities.md) pencocokan (sebelumnya disebut Kecocokan): Dalam langkah kondisi pencocokan, tentukan aturan yang cocok dengan rekaman pelanggan antar entitas. Ketika pelanggan ditemukan di dua entitas atau lebih, satu rekaman terkonsolidasi dibuat dengan semua kolom dan data dari setiap entitas.

1. [Bidang](merge-entities.md) pelanggan terpadu (sebelumnya disebut Gabungkan): Dalam langkah bidang pelanggan terpadu, tentukan bidang sumber mana yang harus disertakan, dikecualikan, atau digabungkan ke dalam profil pelanggan terpadu.  

1. [Tinjau](review-unification.md) dan buat profil terpadu.

Setelah menyelesaikan penyatuan data, Anda dapat secara opsional:

- [Siapkan Relasi antar entitas](relationships.md) untuk membuat segmen yang canggih.
- [Perkaya data](enrichment-hub.md) Anda untuk mendapatkan wawasan yang lebih luas tentang pelanggan Anda.
- [Tentukan aktivitas](activities.md) dari beberapa atribut yang tertelan.
- [Buat langkah-langkah](measures.md) untuk lebih memahami perilaku pelanggan dan kinerja bisnis.

[!INCLUDE [footer-include](includes/footer-banner.md)]
