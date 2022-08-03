---
title: Segmen yang disarankan berdasarkan pengukuran (pratinjau)
description: Biarkan Pembelajaran Mesin anda menemukan segmen baru dan menarik berdasarkan atribut pelanggan.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170961"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Segmen yang disarankan berdasarkan pengukuran (pratinjau)

Temukan segmen menarik pelanggan Anda dengan bantuan model AI. Fitur Pembelajaran Mesin ini menyarankan segmen berdasarkan tindakan atau atribut pelanggan. Ini dapat membantu meningkatkan Indikator Kinerja Utama (KPI) Anda atau lebih memahami pengaruh atribut dalam konteks atribut lain.

> [!NOTE]
> Fitur segmen yang disarankan menggunakan cara otomatis untuk mengevaluasi data dan membuat prediksi berdasarkan data tersebut. Oleh karena itu, ia memiliki kemampuan untuk digunakan sebagai metode pembuatan profil, karena istilah tersebut didefinisikan oleh Peraturan Perlindungan Data Umum ("GDPR"). Penggunaan fitur ini oleh Anda untuk memproses data mungkin diatur dalam GDPR atau hukum atau peraturan lainnya. Anda bertanggung jawab untuk memastikan bahwa penggunaan Dynamics 365 Customer Insights, termasuk fitur ini, mematuhi semua hukum dan peraturan yang berlaku, termasuk hukum yang terkait dengan privasi, data pribadi, data biometrik, perlindungan data, dan kerahasiaan komunikasi.

:::image type="content" source="media/suggested-segments.png" alt-text="Halaman segmen yang disarankan yang menampilkan rincian saran di panel sisi.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmen yang disarankan untuk meningkatkan KPI

Jika Anda menggunakan [langkah-langkah yang dibuat](measures.md) untuk membantu melacak KPI Anda, buat segmen untuk melihat pengaruh pada KPI. Anda dapat menggunakan informasi ini untuk menjalankan kampanye yang sangat bertarget.

Misalnya, Anda melacak pengukuran yang disebut *TotalSpendPerCustomer*. Sebagai bisnis, Anda ingin melihat jumlah tersebut berkembang. Memilih ukuran sebagai atribut utama, pilih atribut yang ingin Anda nilai untuk pengaruh. Misalnya *tingkat keanggotaan*, *periode keanggotaan*, dan *pekerjaan*. Selanjutnya, Customer insights dapat menyarankan segmen yang memberi tahu Anda tentang pengaruh terbesar dari pengukuran tersebut. Misalnya, *Akuntan* yang merupakan anggota *Emas* dan telah bersama bisnis Anda selama *minimal lima tahun* adalah pemberi pengaruh terbesar dari *TotalSpendPerCustomer*. Anda akan mendapatkan perkiraan ukuran segmen untuk setiap saran. Anda dapat menggunakan informasi ini untuk membuat kampanye untuk audiens yang ditargetkan.

## <a name="understand-what-influences-a-customer-attribute"></a>Memahami yang memengaruhi atribut pelanggan

Anda dapat memilih atribut pelanggan, bukan ukuran sebagai atribut utama. Berdasarkan pilihan atribut yang mempengaruhi, model AI membuat rangkaian saran yang menunjukkan pengaruh atribut yang dipilih terhadap atribut utama.

Misalnya, Anda memilih *Anggota Penghargaan (Ya/Tidak)* sebagai atribut utama. *Masa*, *Pekerjaan*, dan *Jumlah Tiket Dukungan* ditetapkan sebagai atribut lainnya yang mempengaruhi. Model AI dapat menyarankan segmen yang menunjukkan kebanyakan profesional TI dengan masa jabatan lebih dari dua tahun adalah anggota penghargaan. Saran lain dapat menyorot bahwa akuntan dengan masa jabatan lebih dari satu tahun dan kurang dari tiga tiket dukungan adalah anggota penghargaan.

## <a name="artificial-intelligence-usage"></a>Penggunaan inteligensi buatan

Menggunakan atribut utama dan atribut yang mempengaruhi, algoritme pohon keputusan menyarankan segmen yang menarik. Saran didasarkan pada aturan atau pola yang dipilih oleh algoritme AI. Hanya segmen yang berbeda secara signifikan dari rata-rata penduduk yang akan ditampilkan sebagai saran. Perbandingan dengan rata-rata populasi didasarkan pada pengukuran yang dipilih atau atribut utama.

### <a name="responsible-ai"></a>AI yang bertanggung jawab

Dengan segmen yang disarankan, Anda memilih atribut untuk membuat segmen baru dan memproses data yang Anda pilih. Saat memilih atribut, termasuk atribut sensitif seperti ras, orientasi seksual, atau jenis kelamin, Anda harus memastikan bahwa Anda dapat dan harus memproses data tersebut. Anda bertanggung jawab untuk mematuhi hukum yang berlaku untuk organisasi Anda dan mematuhi prinsip dan kebijakan privasi organisasi Anda.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Hasil yang berbeda untuk atribut utama dengan nilai kategori dan angka

Saran segmen berbeda jika Anda memilih atribut numerik atau atribut kategoris sebagai atribut utama. Nilai dalam atribut kategori berisi dua atau beberapa kategori atau jenis. Atribut numerik berisi data kuantitatif dan memiliki arti pengukuran yang terkait.

Dengan atribut angka seperti *penghasilan tahunan* atau *periode keanggotaan* sebagai atribut utama, sistem menyarankan segmen yang memiliki nilai rata-rata atribut numerik yang lebih tinggi atau lebih rendah bila dibandingkan dengan semua pelanggan.

Atribut kategoris seperti *kepuasan pelanggan* sebagai atribut utama menghasilkan segmen yang disarankan dengan persentase pelanggan yang lebih tinggi atau lebih rendah milik kategori tertentu bila dibandingkan dengan persentase semua pelanggan yang termasuk dalam kategori yang sama. Misalnya, *kepuasan pelanggan* dipilih sebagai atribut utama dan terdiri dari tiga kategori (*Rendah*, *Sedang* dan *Tinggi*). Untuk setiap kategori, segmen akan disarankan yang memiliki persentase pelanggan yang lebih tinggi atau lebih rendah yang termasuk dalam kategori tersebut dibandingkan dengan proporsi semua pelanggan dalam kategori yang sama. Jika 22% dari semua pelanggan memiliki kepuasan *Tinggi*, maka hanya segmen yang memiliki proporsi pelanggan yang lebih tinggi atau lebih rendah dengan kepuasan *Tinggi* dibandingkan dengan 22% yang akan disarankan untuk kategori tersebut. Dengan cara yang sama, segmen akan disarankan untuk masing-masing kategori lain (*Rendah* dan *Sedang*) jika secara statistik signifikan.

> [!NOTE]
> Saat ini, kami hanya mendukung atribut kategoris utama yang memiliki hingga 10 kategori. Jika Anda ingin melihat saran segmen berdasarkan atribut utama dengan lebih dari 10 kategori, sebaiknya kelompokkan beberapa kategori untuk mengurangi jumlah kategori menjadi 10 kategori atau kurang. Pembatasan ini hanya berlaku untuk atribut utama. Untuk atribut kategoris yang mempengaruhi, saat ini kami mendukung maksimum 100 kategori.

## <a name="generate-suggested-segments"></a>Membuat segmen yang disarankan

1. Buka **Segmen** dan pilih tab **Saran (pratinjau**).

1. Pilih **Temukan saran** baru dan pilih **Tingkatkan pengukuran/metrik**. Pilih **Mulai**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Memilih meningkatkan ukuran pada segmen yang disarankan.":::

1. Pilih atribut pelanggan atau ukur sebagai atribut utama dan pilih **Berikutnya**.

1. Pilih atribut yang mempengaruhi dan pilih **Jalankan**.

   > [!TIP]
   > Memilih beberapa atribut yang mempengaruhi akan meningkatkan peluang untuk mengevaluasi pengaruh atribut utama. Jangan sertakan atribut yang tidak memiliki pengaruh pada atribut utama. Contohnya, jika semua pelanggan berasal dari negara tertentu, jangan sertakan atribut *negara* karena tidak akan mempengaruhi output.

Tergantung pada jumlah profil pelanggan dan atribut yang dipilih, diperlukan waktu beberapa menit untuk memproses atribut yang dipilih.

## <a name="manage-suggested-segments"></a>Mengelola segmen yang disarankan

Buka **Segmen** dan pilih tab **Saran (pratinjau**). Di bagian **Saran segmen berbasis atribut**, pilih segmen yang disarankan untuk melihat tindakan yang tersedia.

- **Lihat** detail segmen yang disarankan dan nilai atau aturan atribut yang dipelajari model AI.
- **Simpan sebagai segmen** saran sebagai segmen. Ini ditampilkan pada tab **Semua segmen dan dapat** disegarkan [, diedit, atau dihapus](segments.md).
- **Edit atribut** dan ubah atribut yang dikonfigurasi yang akan menggantikan saran saat ini.
- **Refresh saran** untuk me-refresh saran sambil menyimpan atribut yang dikonfigurasi.

## <a name="limitations"></a>Pembatasan

1. Perkiraan ketidakcocokan ukuran segmen: Jika Anda memilih atribut utama yang berisi nilai kosong, perkiraan ukuran segmen dapat mempengaruhi perkiraan ukuran segmen dalam saran segmen. Bila menyimpan segmen tersebut, ukuran segmen aktual dapat berbeda dengan perkiraan asli.

2. Atribut utama jenis Boolean tidak berfungsi: Saat ini, kami hanya mendukung string dan jenis data numerik sebagai atribut utama.

3. Segmen yang disarankan tidak cukup berbeda: Ingat bahwa atribut yang dipilih dan distribusi nilai atribut tersebut akan mempengaruhi hasil. Anda dapat mengubah atribut yang mempengaruhi atau bahkan atribut utama Anda untuk mendapatkan hasil yang berbeda.

[!INCLUDE [footer-include](includes/footer-banner.md)]