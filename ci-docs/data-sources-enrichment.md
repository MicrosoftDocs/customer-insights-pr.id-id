---
title: Pengayaan untuk sumber data (pratinjau)
description: Perkaya sumber data sebelum melalui proses penyatuan data.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207187"
---
# <a name="enrichment-for-data-sources-preview"></a>Pengayaan untuk sumber data (pratinjau)

Gunakan data dari sumber seperti Microsoft dan mitra lain untuk memperkaya data pelanggan Anda sebelum penyatuan data. Sumber data pengayaan membantu menghasilkan kelengkapan dan kualitas data yang lebih tinggi yang dapat membantu mencapai hasil yang lebih baik setelah Anda menyatukan data Anda. Misalnya, menggunakan format yang dinormalisasi dan distandarisasi untuk alamat meningkatkan kualitas hasil pertandingan. Untuk daftar pengayaan yang didukung, lihat [opsi pengayaan sumber data yang didukung](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Perkaya sumber data

Anda harus memiliki izin [kontributor atau Administrator](permissions.md) untuk membuat atau mengedit pengayaan.  

1. **Buka Data** > **Unify**. Pilih entitas yang ingin Anda perkaya dan pilih satu atribut sebagai [kunci](map-entities.md#select-primary-key-and-semantic-type-for-attributes) utama untuk entitas tersebut.

1. Buka **Data** > **Sumber data**.

1. Pilih elipsis vertikal (&vellip;) di samping sumber data yang ingin Anda perkaya dan pilih **Perkaya**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Halaman sumber data dengan Enrich disorot":::

   Tab **Temukan** menampilkan [opsi](#supported-data-source-enrichments) pengayaan sumber data yang didukung.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Halaman pengayaan sumber data.":::

1. Pilih **Perkaya data** saya untuk mengonfigurasi pengayaan sumber data. Nama entitas output diisi secara otomatis.

## <a name="supported-data-source-enrichments"></a>Pengayaan sumber data yang didukung

Pengayaan berikut saat ini tersedia untuk sumber data. Tinjau langkah-langkah terperinci untuk pengayaan untuk mempelajari cara mengonfigurasinya.

- [Alamat yang disempurnakan](enrichment-enhanced-addresses.md)
- [Data perusahaan yang disempurnakan](enrichment-enhanced-company-data.md)
- [Data identitas dari LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Mengelola pengayaan sumber data yang ada

Buka **Data** > **Pengayaan**. Pada tab **Pengayaan** saya, lihat pengayaan yang dikonfigurasi, status mereka, jumlah pelanggan yang diperkaya, dan terakhir kali data disegarkan. Anda dapat mengurutkan daftar pengayaan berdasarkan kolom mana pun atau menggunakan kotak pencarian untuk menemukan pengayaan yang ingin Anda kelola.

Pilih pengayaan untuk melihat opsi yang tersedia. Anda juga dapat memilih elipsis vertikal (&vellip;) pada item daftar untuk melihat opsi.

Anda dapat melihat, mengedit, menjalankan, atau menghapus pengayaan sumber data. Untuk informasi selengkapnya, lihat [Mengelola pengayaan](enrichment-hub.md#manage-existing-enrichments) yang ada.
