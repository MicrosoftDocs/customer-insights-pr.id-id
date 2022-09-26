---
title: Mengelola profil yang tidak dikenal dengan Customer Insights
description: Bekerja dengan profil pelanggan yang tidak dikenal yang dibuat dan dikelola di Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: d7e5050ee5832df5ecf40a352f7ea8d42830fa45
ms.sourcegitcommit: f6b6a4c4ce9cf12e449488b24aab80a2cbfe0c47
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/21/2022
ms.locfileid: "9556400"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Mengelola profil yang tidak dikenal dengan Customer Insights

Pengguna internet seringkali tidak dikenal dan anonim secara online. Jika mereka tidak masuk karena mereka menggunakan perangkat atau saluran yang berbeda, itu bahkan berlaku untuk pelanggan yang paling setia. Dengan cookie pihak ketiga yang kemungkinan akan segera hilang, mengelola preferensi pengguna berdasarkan data pihak pertama sangat penting untuk mencapai pengalaman pribadi yang berbeda. Bagi banyak merek, pengguna yang dikenal atau diautentikasi adalah minoritas meskipun harapan pelanggan meningkat seputar personalisasi. Sangat bagus bagi bisnis untuk mengetahui siapa pelanggan mereka, berdasarkan data yang andal, terperinci, dan terpadu.

Personalisasi yang mudah diingat bergantung pada kekayaan dan kelengkapan data pelanggan Anda dan Customer Insights membantu Anda mencapai tujuan ini. Anda tidak perlu membatasi atau menghentikan penggunaan data yang dikumpulkan di awal perjalanan pelanggan. Customer Insights memungkinkan Anda membawa data Anda sendiri untuk membuat profil pelanggan bagi pengguna yang tidak dikenal. Anda kemudian dapat menggunakan profil tersebut untuk tindakan lebih lanjut, meskipun informasi kontaknya hilang. Impor data pihak pertama dari sumber seperti web, seluler, atau sistem CRM ke customer insights untuk memperkaya profil pelanggan secara terus menerus. Saat Anda menyatukan lebih banyak interaksi, [ubah pelanggan yang *tidak dikenal* menjadi pelanggan yang *dikenal*](unknown-to-known.md).

## <a name="sample-scenario"></a>Contoh Skenario

E-commerce adalah saluran dengan pertumbuhan tercepat selama dekade terakhir. Asumsikan pengguna menggunakan perangkat seluler mereka untuk menelusuri situs e-niaga Anda. Situs web menetapkan pengunjung "mobile_guest123" sebagai pengidentifikasi unik dan Anda mulai mengumpulkan aktivitas perilaku berdasarkan aktivitas online mereka. Misalnya, halaman mana yang mereka kunjungi, berapa banyak waktu yang mereka habiskan untuk halaman tersebut, atau tautan mana yang mereka klik. Anda tidak tahu nama atau alamat email mereka, tetapi data ini dapat membantu memberikan wawasan yang bermakna kepada merek tentang pengguna tertentu ini. Pada gilirannya, Anda dapat menempatkan wawasan tersebut untuk bekerja saat berikutnya pengguna mengunjungi situs. Kueri Customer Insights untuk "mobile_guest123" untuk mengambil daftar segmen pengguna, seperti "organik", "pelanggan pre-order seluler", "pelanggan bernilai tinggi", dll., atau mengambil profil untuk menciptakan pengalaman web yang dipersonalisasi. Anda juga dapat mengekspor data ke sistem aktivasi apa pun untuk melakukan hal yang sama.

## <a name="prerequisites"></a>Prasyarat

- Menyerap data pihak pertama ke dalam Customer Insights
- Setiap entitas memiliki ID unik yang ditetapkan sebagai kunci utama
- Setiap entitas dengan kunci utama untuk personalisasi disatukan
- Sistem manajemen konten situs web Anda mampu menggunakan API (untuk personalisasi web berdasarkan komunikasi langsung dengan Customer Insights)

Tabel berikut menunjukkan contoh yang disederhanakan bagaimana peristiwa web bernilai tinggi dapat ditangkap.

|EventID|EventTimeStamp|UserID|Kunci Utama|Nama Acara|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Tampilan produk|
|2|09-18-2022 10:05:00|abc123|CookieID1|Tampilan produk|
|3|09-18-2022 10:10:00|abc123|CookieID1|Tambahkan ke keranjang|
|4|09-21-2022 09:05:00|abc123|CookieID1|Tampilan produk|

## <a name="data-ingestion"></a>Penyerapan data

Untuk informasi selengkapnya tentang opsi yang tersedia untuk penyerapan data, lihat [Gambaran umum sumber data](data-sources.md).

## <a name="data-unification"></a>Penyatuan data

Untuk informasi selengkapnya tentang menyatukan profil pelanggan, lihat [Gambaran umum penyatuan data](data-unification.md).

## <a name="get-insights"></a>Dapatkan wawasan

[Perkaya](enrichment-hub.md) data Anda, buat [langkah-langkah](measures.md), dan buat [segmen](segments.md) untuk aktivasi lebih lanjut.

Misalnya, Anda dapat membuat segmen pengguna yang tidak dikenal yang menelusuri halaman produk yang sama tetapi tidak pernah menyelesaikan checkout.

## <a name="activation"></a>Pengaktifan

Dengan data Anda di Customer Insights dan wawasan Anda yang siap untuk mulai bekerja, Anda dapat menggunakan Customer Insights untuk personalisasi:

1. [Menggunakan API](apis.md) OData untuk mengambil keanggotaan segmen atau profil pelanggan Untuk contoh selengkapnya, lihat [Contoh kueri OData untuk API](odata-examples.md) Customer Insights.

1. [Ekspor](export-destinations.md) data Anda ke sistem aktivasi Anda.

Contoh: Pengguna yang tidak dikenal mengunjungi situs web beberapa kali dan mengunjungi halaman produk untuk berbagai model sepatu kulit. Dengan data yang tersedia di Customer Insights, Anda dapat menyertakan pengguna yang tidak dikenal di segmen orang yang tertarik dengan sepatu kulit. Gunakan segmen ini untuk menginformasikan situs web Anda membangun personalisasi untuk pengunjung yang kembali. Pada kunjungan berikutnya, situs ini mengenali pengguna yang tidak dikenal dan dapat menawarkan kupon 10% untuk sepatu kulit.

[!INCLUDE [footer-include](includes/footer-banner.md)]
