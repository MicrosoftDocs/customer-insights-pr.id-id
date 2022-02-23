---
title: Temukan pelanggan serupa dengan AI (berisi video)
description: Temukan segmen pelanggan serupa dengan kecerdasan buatan.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: de337ae989558c81fff25a6ff7cca01890ed306b
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934844"
---
# <a name="similar-customers-preview"></a>Pelanggan serupa (pratinjau)

Fitur ini memungkinkan Anda menemukan pelanggan serupa di basis pelanggan menggunakan kecerdasan buatan. Anda harus memiliki minimal satu segmen yang dibuat untuk menggunakan fitur ini. Memperluas kriteria segmen yang ada membantu menemukan Pelanggan yang serupa dengan segmen tersebut.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Menemukan Pelanggan yang serupa* menggunakan sarana otomatis untuk mengevaluasi data dan membuat prediksi berdasarkan data tersebut, sehingga memiliki kemampuan untuk digunakan sebagai metode pembuatan profil, karena istilah tersebut ditentukan oleh peraturan perlindungan data umum ("GDPR"). Penggunaan fitur ini oleh pelanggan untuk memproses data dapat tergantung pada GDPR atau hukum atau peraturan lain. Anda bertanggung jawab untuk memastikan bahwa penggunaan Dynamics 365 Customer Insights, termasuk prediksi, mematuhi semua hukum dan peraturan yang berlaku, termasuk hukum yang terkait dengan privasi, data pribadi, data biometrik, perlindungan data, dan kerahasiaan komunikasi.

## <a name="finding-similar-customers"></a>Menemukan Pelanggan serupa

1. Di wawasan audiens, buka **segmen** lalu pilih segmen yang akan mendasari segmen baru anda. Itulah *segmen sumber* Anda.

1. Di panel tindakan, pilih **temukan pelanggan serupa**.

1. Tinjau nama yang disarankan untuk segmen baru Anda dan ubah jika perlu.

1. Tinjau bidang yang menentukan segmen baru Anda. Bidang ini menentukan dasar untuk sistem mencoba menemukan pelanggan serupa dengan segmen sumber Anda. Sistem akan memilih bidang yang disarankan secara default.
  Bidang yang secara signifikan dapat mengurangi performa model secara otomatis dikecualikan:
  
   - Bidang dengan jenis data berikut: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Bidang dengan kardinalitas (jumlah elemen dalam bidang) kurang dari 2 atau lebih dari 30

1. Pilih jika Anda ingin menyertakan **semua pelanggan** atau hanya pelanggan di **segmen tertentu yang ada** di segmen baru.

1. Kecualikan pelanggan di segmen sumber Anda dengan memilih kotak centang **Kecualikan semua orang di segmen sumber**.

1. Secara default, sistem menyarankan memasukkan hanya 20% dari ukuran audiens target dalam output anda. Edit ambang ini bila diperlukan. Meningkatkan ambang batas akan mengurangi presisi.

1. Pilih **jalankan** di bagian bawah halaman untuk memulai tugas klasifikasi biner (metode Pembelajaran Mesin) yang menganalisis himpunan data.

## <a name="view-the-similar-segment"></a>Melihat segmen serupa

Setelah memproses segmen serupa, Anda akan menemukan segmen baru yang tercantum pada halaman **segmen**.

> [!div class="mx-imgBorder"]
> ![Segmen pelanggan serupa.](media/expanded-segment.png "Segmen pelanggan serupa")

Pilih **tampilan** di bilah tindakan untuk membuka detail segmen. Tampilan ini berisi informasi tentang distribusi hasil di seluruh [skor kemiripan](#about-similarity-scores). Anda juga akan menemukan nilai skor kemiripan dalam **pratinjau anggota segmen**.

## <a name="use-the-output-of-a-similar-segment"></a>Gunakan output dari segmen yang serupa

Anda dapat [bekerja dengan output segmen yang serupa](segments.md) seperti yang Anda lakukan dengan segmen lain. Misalnya, ekspor segmen atau buat ukuran.

## <a name="refresh-and-edit-a-similar-segment"></a>Segarkan dan edit segmen serupa

Untuk menyegarkan segmen yang serupa, pilih segmen pada halaman **segmen** dan pilih **Segarkan** di bilah tindakan.

Mengedit segmen serupa akan memproses ulang data Anda. Segmen yang dibuat sebelumnya akan diperbarui dengan data yang diperbarui.    
Untuk mengedit segmen yang serupa, pilih segmen pada halaman **segmen** dan pilih **Edit** di bilah tindakan. Terapkan perubahan dan pilih **Jalankan** untuk memulai pemrosesan.

## <a name="delete-a-similar-segment"></a>Menghapus segmen yang sama

Pilih segmen pada halaman **segmen** dan pilih **Hapus** di bilah tindakan. Kemudian, konfirmasikan penghapusan.

## <a name="about-similarity-scores"></a>Tentang skor kemiripan

Model Pembelajaran Mesin klasifikasi biner menetapkan skor untuk pelanggan di segmen serupa. Skor didasarkan pada kemiripan dengan pelanggan di segmen sumber.

- skor kemiripan di bawah 0,55 adalah pelanggan yang diklasifikasikan sistem sebagai *tidak mirip dengan* pelanggan di segmen sumber
- Nilai kemiripan antara 0,55 – 0,7 diklasifikasikan sebagai *agak mirip*
- Nilai kemiripan antara 0,7 – 0,85 diklasifikasikan sebagai *mirip*
- Nilai kemiripan antara 0,85 – 1 adalah pelanggan yang diklasifikasikan sistem sebagai *sangat mirip*

Pelanggan dengan Skor kemiripan di bawah 0,4 tidak disertakan dalam output model. Sistem tidak menganggapnya cukup mirip dengan segmen sumber.


[!INCLUDE[footer-include](../includes/footer-banner.md)]