---
title: Temukan pelanggan serupa dengan AI (pratinjau) (berisi video)
description: Temukan segmen pelanggan serupa dengan kecerdasan buatan.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170731"
---
# <a name="find-similar-customers-with-ai-preview"></a>Temukan pelanggan serupa dengan AI (pratinjau)

Temukan pelanggan serupa di basis pelanggan Anda menggunakan kecerdasan buatan. Anda memerlukan setidaknya satu segmen yang dibuat untuk menggunakan fitur ini. Memperluas kriteria segmen yang ada membantu menemukan pelanggan yang mirip dengan segmen tersebut.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Temukan pelanggan* serupa menggunakan cara otomatis untuk mengevaluasi data dan membuat prediksi berdasarkan data tersebut. Oleh karena itu ia memiliki kemampuan untuk digunakan sebagai metode pembuatan profil, karena istilah tersebut didefinisikan oleh Peraturan Perlindungan Data Umum ("GDPR"). Penggunaan fitur ini oleh pelanggan untuk memproses data dapat tergantung pada GDPR atau hukum atau peraturan lain. Anda bertanggung jawab untuk memastikan bahwa penggunaan Dynamics 365 Customer Insights, termasuk prediksi, mematuhi semua hukum dan peraturan yang berlaku, termasuk hukum yang terkait dengan privasi, data pribadi, data biometrik, perlindungan data, dan kerahasiaan komunikasi.

## <a name="find-similar-customers"></a>Temukan pelanggan serupa

1. Buka **Segmen** dan pilih segmen yang ingin Anda jadikan dasar segmen baru Anda. Itulah *segmen sumber* Anda.

1. Pilih **Temukan pelanggan serupa**.

1. Tinjau nama yang disarankan untuk segmen baru Anda dan ubah jika perlu.

1. Secara opsional, tambahkan [tag](work-with-tags-columns.md#manage-tags) ke segmen baru.

1. Tinjau bidang yang menentukan segmen baru Anda. Bidang ini menentukan dasar untuk sistem mencoba menemukan pelanggan serupa dengan segmen sumber Anda. Sistem memilih bidang yang direkomendasikan secara default. Jika diperlukan, tambahkan lebih banyak bidang.
  Bidang yang secara signifikan dapat mengurangi performa model secara otomatis dikecualikan:
  
   - Bidang dengan jenis data berikut: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Bidang dengan kardinalitas (jumlah elemen dalam bidang) kurang dari 2 atau lebih dari 30

1. Pilih apakah Anda ingin menyertakan **Semua pelanggan** kecuali segmen sumber atau hanya pelanggan di segmen **yang** berbeda di segmen baru Anda.

1. Secara default, sistem menyarankan memasukkan hanya 20% dari ukuran audiens target dalam output anda. Edit ambang ini bila diperlukan. Meningkatkan ambang batas akan mengurangi presisi.

1. Sertakan pelanggan di segmen sumber Anda dengan **memilih kotak centang Sertakan anggota dari segmen sumber selain pelanggan dengan atribut** serupa.

1. Pilih **Jalankan** di bagian bawah halaman untuk memulai [tugas](#about-similarity-scores) klasifikasi biner (metode Pembelajaran Mesin) yang menganalisis himpunan data.

## <a name="view-the-similar-segment"></a>Melihat segmen serupa

Setelah memproses segmen serupa, Anda akan menemukan segmen baru yang tercantum di **halaman Segmen** dengan jenis **Ekspansi**.

Pilih **Tampilan** untuk melihat distribusi hasil di seluruh [skor](#about-similarity-scores) kesamaan dan nilai skor kesamaan di bawah **Pratinjau anggota segmen**.

:::image type="content" source="media/expanded-segment.png" alt-text="Segmen pelanggan serupa.":::

## <a name="manage-a-similar-segment"></a>Mengelola segmen serupa

[Bekerja dengan dan mengelola segmen](segments.md#manage-existing-segments) yang sama seperti yang Anda lakukan dengan segmen lain. Misalnya, ekspor segmen atau buat ukuran.

Edit, refresh, ganti nama, unduh, dan hapus segmen serupa. Mengedit segmen serupa memproses ulang data Anda. Segmen yang dibuat sebelumnya akan diperbarui dengan data yang diperbarui.

## <a name="about-similarity-scores"></a>Tentang skor kemiripan

Model Pembelajaran Mesin klasifikasi biner menetapkan skor untuk pelanggan di segmen serupa. Skor didasarkan pada kemiripan dengan pelanggan di segmen sumber.

- skor kemiripan di bawah 0,55 adalah pelanggan yang diklasifikasikan sistem sebagai *tidak mirip dengan* pelanggan di segmen sumber
- Nilai kemiripan antara 0,55 – 0,7 diklasifikasikan sebagai *agak mirip*
- Nilai kemiripan antara 0,7 – 0,85 diklasifikasikan sebagai *mirip*
- Nilai kemiripan antara 0,85 – 1 adalah pelanggan yang diklasifikasikan sistem sebagai *sangat mirip*

Pelanggan dengan Skor kemiripan di bawah 0,4 tidak disertakan dalam output model. Sistem tidak menganggapnya cukup mirip dengan segmen sumber.

[!INCLUDE [footer-include](includes/footer-banner.md)]
