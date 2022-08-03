---
title: Menggunakan persetujuan pelanggan
description: Hormati preferensi persetujuan pelanggan Anda di Customer Insights dengan mengimpor data persetujuan.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188051"
---
# <a name="use-customer-consent"></a>Menggunakan persetujuan pelanggan

Peraturan perlindungan data dan privasi memberi individu hak untuk mengatur bagaimana organisasi menggunakan data pribadi mereka. Contoh peraturan tersebut adalah Peraturan Perlindungan Data Umum di Uni Eropa atau Undang-Undang Privasi Konsumen California di Amerika Serikat. Peraturan ini memungkinkan orang untuk memilih agar data pribadi mereka tidak dikumpulkan, diproses oleh, atau dibagikan dengan pihak ketiga.  

Pelanggan dapat memilih untuk menarik atau menahan persetujuan mereka untuk bentuk kontak tertentu. Mereka juga dapat meminta Anda memilih mereka untuk tidak mengambil, menyimpan, menggunakan, atau menjual data pribadi mereka. Penting bagi organisasi Anda untuk menghormati semua persetujuan pelanggan dan preferensi privasi.  

Dynamics 365 Customer Insights membantu Anda memenuhi permintaan pelanggan Anda dengan mengimpor dan menyimpan preferensi mereka sebagai bagian dari profil pelanggan terpadu.

Jika data persetujuan disimpan secara terpisah dari profil pelanggan Anda, [tambahkan data persetujuan Anda sebagai sumber data baru](#import-and-unify-consent-data). Sumber data yang berisi data persetujuan ditambahkan ke proses penyatuan data. Keberhasilan penyatuan data persetujuan dan profil pelanggan kemudian mengarah ke profil pelanggan terpadu yang berisi informasi persetujuan. Untuk profil pelanggan yang sudah berisi informasi persetujuan, langsung buka [bagian menggunakan data](#use-consent-data) persetujuan.

## <a name="prerequisites"></a>Prasyarat

Informasi berikut harus tersedia dalam data sumber Anda untuk menyatukan data persetujuan dengan profil pelanggan lainnya:

- Kunci alternatif untuk memetakan informasi persetujuan ke profil pengguna di Customer Insights. Misalnya, alamat email atau nomor telepon.
- Nilai persetujuan untuk menentukan status persetujuan pelanggan.

Pertimbangkan untuk menambahkan informasi opsional *berikut*:

- Kunci utama untuk memperbarui status persetujuan jika pelanggan meminta perubahan.
- Jenis persetujuan, jika ada lebih dari satu cara untuk memproses informasi pelanggan.
- Tanggal persetujuan atau jenis data lain yang relevan dengan skenario persetujuan Anda.

Contoh tabel database persetujuan sederhana dengan beberapa opsi persetujuan:

|ID Persetujuan (kunci utama)   |Surel (kunci alternatif)  |Opsi persetujuan  |Nilai persetujuan  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Newsletter       |  False       |
|2    |  holly@contoso.com       |  Pembaruan Produk       |  True       |
|3    |  frank@contoso.com       |  Newsletter       | True        |
|4    |  frank@contoso.com       |  Pembaruan Produk       |  False       |

## <a name="import-and-unify-consent-data"></a>Mengimpor dan menyatukan data persetujuan

Impor data persetujuan dengan cara yang sama seperti Anda menyerap sumber data lain ke Customer Insights. Untuk informasi selengkapnya tentang sumber data yang didukung dan cara mengimpornya, lihat [Gambaran umum sumber data](data-sources.md).

Untuk informasi selengkapnya tentang menyatukan sumber data Anda, lihat [Gambaran umum penyatuan data](data-unification.md).

## <a name="use-consent-data"></a>Menggunakan data persetujuan

Setelah data persetujuan Anda menjadi bagian dari profil pelanggan terpadu, Anda dapat menggunakannya di Customer Insights. Misalnya, buat segmen dengan aturan untuk memastikan bahwa Anda mematuhi preferensi privasi dan perlindungan data pelanggan Anda. Aturan yang mendukung preferensi persetujuan digunakan untuk mengecualikan pengguna dari segmen berdasarkan atribut profil. Tambahkan aturan ke segmen yang mengecualikan profil pelanggan yang tidak memberikan persetujuan untuk menghubungi.

Mengacu pada tabel sampel di atas, segmen dapat berisi aturan ini:`Consent option=Newsletter & Consent value=True`. Konfigurasi ini menghasilkan segmen yang menghormati preferensi kontak untuk mengirim buletin.

Untuk informasi selengkapnya tentang membangun segmen, lihat [Membuat segmen](segment-builder.md).

Setelah segmen dibuat, Anda dapat menggunakan salah satu dari banyak [opsi](export-destinations.md) ekspor untuk menggunakan segmen di aplikasi lain.

## <a name="ensure-updated-consent-status"></a>Memastikan status persetujuan yang diperbarui

Penting untuk terus memperbarui status persetujuan untuk pelanggan Anda. Refresh terjadwal di Customer Insights selalu mengimpor status terbaru sumber data Anda. Informasi ini kemudian diproses melalui penyatuan data dan menghasilkan profil pelanggan yang diperbarui. Profil yang diperbarui ini kemudian digunakan untuk menyegarkan segmen untuk memastikan bahwa Anda bekerja dengan informasi terbaru.

Dengan kata lain, pastikan data sumber yang diimpor ke Customer Insights selalu memiliki informasi terbaru.

Untuk informasi selengkapnya, lihat [Merefresh segmen secara manual](segments.md#refresh-segments) atau [mengonfigurasi refresh](system.md#schedule-tab) terjadwal.

[!INCLUDE [footer-include](includes/footer-banner.md)]
