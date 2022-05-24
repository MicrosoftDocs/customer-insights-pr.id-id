---
title: Persiapan Dynamics 365 Customer Insights
description: Gambaran umum Wawasan Pelanggan membantu sumber daya untuk memulai dengan cepat.
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
ms.openlocfilehash: 1a19d83930d667bdca5301dcc5a3ffa5db6a7bdc
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741137"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Persiapan Dynamics 365 Customer Insights

Wawasan Pelanggan dapat membantu Anda membangun pemahaman yang lebih dalam tentang pelanggan Anda. Sambungkan data dari berbagai sumber transaksional, perilaku, dan observasional untuk membuat tampilan pelanggan 360 derajat. Gunakan wawasan ini untuk mendorong pengalaman dan proses yang berpusat pada pelanggan. Satukan data pelanggan dan manfaatkan untuk wawasan dan tindakan cerdas.

## <a name="step-1-create-an-environment"></a>Langkah 1: Membuat lingkungan

Untuk memulai, Anda harus terlebih dulu membuat lingkungan untuk bekerja. Jika organisasi Anda telah membeli lisensi, lihat [Membuat lingkungan](create-environment.md). Untuk memulai uji coba untuk Wawasan Pelanggan, lihat [Menyiapkan lingkungan uji coba](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Langkah 2: Jelajahi Wawasan Pelanggan

Saat pertama kali masuk ke Customer Insights, Anda dapat mengonfigurasi pengaturan dan menjelajahi produk.

1. [masuk ke Customer Insights](https://home.ci.ai.dynamics.com) menggunakan akun pengguna Microsoft Azure Active Directory (AAD) Anda.

1. [Ubah lingkungan](manage-environments.md#switch-environments) untuk melihat data demo dan [jelajahi Wawasan Pelanggan](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Langkah 3: Menyimpan, menyatukan, dan mengatur relasi untuk data Anda

Profil terpadu adalah landasan untuk mendapatkan wawasan dan melakukan tindakan pada data. Bawa data dari berbagai sumber dan jalankan proses penyatuan data untuk menggabungkan profil terpadu. Tentukan Relasi antara entitas yang diserap menggunakan fitur pengayaan untuk menambahkan informasi ke profil.

1. Serap data dengan membuat sumber data dari beberapa pilihan. Pilih antara [Power Query konektor](connect-power-query.md), [folder](connect-common-data-model.md) Model Data Umum, atau [Microsoft Dataverse](connect-dataverse-managed-lake.md). 

1. Jalankan proses [penyatuan](data-unification.md) data dengan [mengidentifikasi bidang](map-entities.md) sumber, menghapus [duplikat](remove-duplicates.md), [mencocokkan kondisi](match-entities.md), dan [menyatukan bidang](merge-entities.md).

1. Kenali [entitas yang dibuat sistem](entities.md) dan buat [Relasi antara entitas yang diserap](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Langkah 4: Tingkatkan profil terpadu dengan prediksi, aktivitas, dan ukuran

Dengan konfigurasi profil terpadu, Anda dapat meningkatkan data dan meningkatkan lebih lanjut informasi yang mereka berikan.

1. Pilih dari pustaka penyedia penyimpanan yang terus bertambah untuk [memperkaya data pelanggan Anda](enrichment-hub.md).

1. Gunakan [model bawaan](predictions-overview.md) untuk memperkirakan kemungkinan hilangnya pelanggan atau pendapatan yang diharapkan.

1. [Konfigurasikan aktivitas](activities.md) berdasarkan data yang diserap dan visualisasikan interaksi dengan pelanggan dalam timeline kronologis.

1. [Buat langkah-langkah](measures.md) untuk mengukur sasaran bisnis dan KPI Anda.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Langkah 5: Buat segmen dan aktifkan data melalui berbagai pilihan ekspor

Setelah data Anda selesai dan berisi berbagai informasi tentang pelanggan, sudah waktunya untuk mencari cara melakukan tindakan pada data tersebut.

1. [Buat segmen](segments.md), subset basis pelanggan Anda, untuk memastikan tindakan Anda relevan untuk pelanggan yang ditargetkan.

1. Telusuri katalog [pilihan ekspor](export-destinations.md) yang makin bertambah, yang dapat Anda gunakan data pelanggannya. Misalnya, Anda dapat menggunakan data untuk mengelola promosi dan kontak dengan pemasaran digital.

1. Tinjau opsi integrasi, misalnya ke aplikasi Dynamics 365 lainnya dengan [add-in](customer-card-add-in.md) Kartu Pelanggan.  


[!INCLUDE [footer-include](includes/footer-banner.md)]
