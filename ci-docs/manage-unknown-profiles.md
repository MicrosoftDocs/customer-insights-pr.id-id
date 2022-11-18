---
title: Mengelola profil yang tidak dikenal dengan Customer Insights
description: Bekerja dengan profil pelanggan yang tidak dikenal yang dibuat dan dikelola dalam format Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776825"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Mengelola profil yang tidak dikenal dengan Customer Insights

Pengguna internet seringkali tidak dikenal atau anonim saat online. Bahkan pelanggan yang paling setia pun mungkin tampak "tidak dikenal" jika mereka tidak masuk di perangkat yang berbeda. Bagi banyak merek, pengguna yang dikenal atau diautentikasi adalah minoritas meskipun ekspektasi pelanggan meningkat seputar personalisasi. Dengan masa depan cookie pihak ketiga yang dipertanyakan, mengelola preferensi pengguna berdasarkan data pihak pertama sebagai gantinya, sangat penting untuk mencapai pengalaman yang dipersonalisasi.

Personalisasi yang mudah diingat tergantung pada seberapa baik Anda mengenal pelanggan Anda dan Customer Insights membantu Anda melakukannya dengan melacak semua pelanggan Anda.  Anda tidak perlu membatasi atau menghentikan penggunaan data yang dikumpulkan di awal perjalanan pelanggan. Customer Insights memungkinkan Anda membawa data Anda sendiri untuk membuat profil pelanggan bagi pengguna yang tidak dikenal. Anda kemudian dapat menggunakan profil tersebut untuk tindakan lebih lanjut, meskipun informasi kontak hilang. Impor data pihak pertama dari sumber seperti sistem web, seluler, atau CRM ke Customer Insights untuk memperkaya profil pelanggan secara terus menerus. Saat Anda menyatukan lebih banyak interaksi, [ubah pelanggan yang *tidak dikenal menjadi* pelanggan yang *dikenal*](unknown-to-known.md).

## <a name="sample-scenario"></a>Contoh skenario

Asumsikan pengguna menggunakan perangkat seluler mereka untuk menelusuri situs e-commerce Anda. Situs web menetapkan pengunjung "mobile_guest123" sebagai pengidentifikasi unik dan Anda mulai mengumpulkan aktivitas perilaku berdasarkan aktivitas online mereka. Misalnya, halaman mana yang mereka kunjungi, berapa banyak waktu yang mereka habiskan di halaman tersebut, atau tautan mana yang mereka klik. Anda tidak tahu nama atau alamat email mereka, tetapi data ini dapat membantu memberikan wawasan yang bermakna kepada merek tentang pengguna tertentu ini. Pada gilirannya, Anda dapat menempatkan wawasan tersebut untuk bekerja pada saat pengguna mengunjungi situs berikutnya. Kueri Customer Insights untuk "mobile_guest123" untuk mengambil daftar segmen pengguna, seperti "organik", "pelanggan pre-order seluler", "pelanggan bernilai tinggi", dll., atau mengambil profil untuk menciptakan pengalaman web yang dipersonalisasi. Anda juga dapat mengekspor data ke sistem aktivasi apa pun untuk melakukan hal yang sama.

## <a name="prerequisites"></a>Prasyarat

- Menyerap data pihak pertama ke dalam Customer Insights
- Setiap entitas memiliki ID unik yang ditetapkan sebagai kunci utama
- Setiap entitas dengan kunci utama untuk personalisasi disatukan
- Sistem manajemen konten situs web Anda dapat menggunakan API (untuk personalisasi web berdasarkan komunikasi langsung dengan Customer Insights)

Tabel berikut menunjukkan contoh sederhana bagaimana peristiwa web bernilai tinggi dapat ditangkap.

|ID Peristiwa|EventTimeStamp|ID Pengguna|Kunci Utama|Nama Acara|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|ABC123|CookieID1|Tampilan produk|
|2|09-18-2022 10:05:00|ABC123|CookieID1|Tampilan produk|
|3|09-18-2022 10:10:00|ABC123|CookieID1|Tambahkan ke keranjang|
|4|09-21-2022 09:05:00|ABC123|CookieID1|Tampilan produk|

## <a name="data-ingestion"></a>Penyerapan data

Untuk informasi selengkapnya tentang opsi yang tersedia untuk penyerapan data, lihat [Gambaran umum sumber data](data-sources.md).

## <a name="data-unification"></a>Penyatuan data

Untuk informasi selengkapnya tentang menyatukan profil pelanggan, lihat [Gambaran umum](data-unification.md) penyatuan data.

## <a name="get-insights"></a>Dapatkan wawasan

[Perkaya](enrichment-hub.md) data Anda, buat ukuran [, dan buat](measures.md)[segmen](segments.md) untuk aktivasi lebih lanjut.

Misalnya, Anda dapat membuat segmen pengguna tidak dikenal yang menjelajahi halaman produk yang sama tetapi tidak pernah menyelesaikan pembayaran.

## <a name="activation"></a>Pengaktifan

Dengan data Anda di Customer Insights dan wawasan Anda siap untuk mulai bekerja, Anda dapat menggunakan Customer Insights untuk personalisasi:

1. [Gunakan API OData untuk mengambil keanggotaan segmen atau profil pelanggan Untuk contoh selengkapnya, lihat](apis.md) Contoh kueri OData untuk API [Customer](odata-examples.md) Insights.

1. [Ekspor](export-destinations.md) data Anda ke sistem aktivasi Anda.

Contoh: Pengguna yang tidak dikenal mengunjungi situs web beberapa kali dan mengunjungi halaman produk untuk berbagai model sepatu kulit. Dengan data yang tersedia di Customer Insights, Anda dapat memasukkan pengguna yang tidak dikenal ke dalam segmen orang yang tertarik dengan sepatu kulit. Gunakan segmen ini untuk menginformasikan personalisasi pembuatan situs web Anda untuk pengunjung yang kembali. Pada kunjungan berikutnya, situs mengenali pengguna yang tidak dikenal dan dapat menawarkan mereka kupon 10% untuk sepatu kulit.

[!INCLUDE [footer-include](includes/footer-banner.md)]
