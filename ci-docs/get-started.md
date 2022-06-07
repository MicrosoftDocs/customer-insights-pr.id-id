---
title: Persiapan Dynamics 365 Customer Insights
description: Gambaran umum Customer Insights membantu sumber daya untuk memulai dengan cepat.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 68c26eb0ad0da787a9f594b4aebe679588b0d6bf
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833579"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Persiapan Dynamics 365 Customer Insights

Customer Insights dapat membantu Anda membangun pemahaman yang lebih dalam tentang pelanggan Anda. Sambungkan data dari berbagai sumber transaksional, perilaku, dan observasional untuk membuat tampilan pelanggan 360 derajat. Gunakan wawasan ini untuk mendorong pengalaman dan proses yang berpusat pada pelanggan. Satukan data pelanggan dan manfaatkan untuk wawasan dan tindakan cerdas.

## <a name="step-1-create-an-environment"></a>Langkah 1: Membuat lingkungan

Pertama, ciptakan lingkungan untuk bekerja. Jika organisasi Anda telah membeli lisensi, lihat [Membuat lingkungan](create-environment.md). Untuk memulai uji coba untuk Customer Insights, lihat [Menyiapkan lingkungan uji coba](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Langkah 2: Jelajahi Wawasan Pelanggan

Pertama kali Anda masuk ke Customer Insights, mengonfigurasi pengaturan, dan menjelajahi produk.

1. [masuk ke Customer Insights](https://home.ci.ai.dynamics.com) menggunakan akun pengguna Microsoft Azure Active Directory (AAD) Anda.

1. Ubah lingkungan untuk melihat data demo dan [jelajahi Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Langkah 3: Menyimpan, menyatukan, dan mengatur relasi untuk data Anda

Profil terpadu adalah landasan untuk mendapatkan wawasan dan melakukan tindakan pada data. Bawa data dari berbagai sumber dan jalankan proses penyatuan data untuk menggabungkan profil terpadu. Tentukan Relasi antara entitas yang diserap dan gunakan fitur pengayaan untuk menambahkan informasi ke profil.

1. Serap data dengan membuat sumber data dari beberapa pilihan. Pilih antara [Power Query konektor](connect-power-query.md), [folder](connect-common-data-model.md) Common Data Model, atau [Microsoft Dataverse](connect-dataverse-managed-lake.md).

1. Jalankan proses penyatuan [data dengan](data-unification.md) mengidentifikasi bidang [sumber, menghapus](map-entities.md) duplikat [,](remove-duplicates.md) kondisi [yang cocok, dan](match-entities.md) bidang [pemersatu.](merge-entities.md)

1. Kenali [entitas yang dibuat sistem](entities.md) dan buat [Relasi antara entitas yang diserap](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Langkah 4: Tingkatkan profil terpadu dengan prediksi, aktivitas, dan ukuran

Dengan menyiapkan profil terpadu, tingkatkan data Anda dan tingkatkan lebih lanjut informasi yang mereka berikan.

1. Pilih dari pustaka penyedia penyimpanan yang terus bertambah untuk [memperkaya data pelanggan Anda](enrichment-hub.md).

1. Gunakan [model bawaan](predictions-overview.md) untuk memperkirakan kemungkinan hilangnya pelanggan atau pendapatan yang diharapkan.

1. [Konfigurasikan aktivitas](activities.md) berdasarkan data yang diserap dan visualisasikan interaksi dengan pelanggan dalam timeline kronologis.

1. [Buat langkah-langkah](measures.md) untuk mengukur sasaran bisnis dan KPI Anda.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Langkah 5: Buat segmen dan aktifkan data melalui berbagai pilihan ekspor

Sekarang setelah data Anda lengkap dan berisi berbagai informasi tentang pelanggan Anda, cari cara untuk mengambil tindakan pada data tersebut.

1. [Buat segmen](segments.md), subset basis pelanggan Anda, untuk memastikan tindakan Anda relevan untuk pelanggan yang ditargetkan.

1. Telusuri katalog [pilihan ekspor](export-destinations.md) yang makin bertambah, yang dapat Anda gunakan data pelanggannya. Misalnya, Anda dapat menggunakan data untuk mengelola promosi dan kontak dengan pemasaran digital.

1. Tinjau opsi integrasi, misalnya ke aplikasi Dynamics 365 lainnya dengan [add-in](customer-card-add-in.md) Customer Card.  


[!INCLUDE [footer-include](includes/footer-banner.md)]
