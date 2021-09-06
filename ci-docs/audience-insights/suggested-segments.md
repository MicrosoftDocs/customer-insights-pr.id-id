---
title: Saran segmen yang didukung oleh Pembelajaran Mesin
description: Biarkan Pembelajaran Mesin anda menemukan segmen baru dan menarik berdasarkan atribut pelanggan.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: f743853826cee0427618abccfba27f10016a0f05cc674f5f7da2210366d60305
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7028364"
---
# <a name="suggested-segments-preview"></a>Segmen yang disarankan (pratinjau)

Temukan segmen menarik pelanggan Anda dengan bantuan model AI. Fitur Pembelajaran Mesin ini menyarankan segmen berdasarkan tindakan atau atribut pelanggan. Ini dapat membantu meningkatkan KPI atau lebih memahami pengaruh atribut dalam konteks atribut lainnya. 

> [!NOTE]
> Fitur segmen yang disarankan menggunakan cara otomatis untuk mengevaluasi data dan membuat prediksi berdasarkan data tersebut, dan oleh karena itu, memiliki kemampuan untuk digunakan sebagai metode pembuatan profil, sebagaimana istilah tersebut ditentukan oleh Peraturan Perlindungan Data Umum ("GDPR"). Penggunaan fitur ini oleh Anda untuk memproses data mungkin diatur dalam GDPR atau hukum atau peraturan lainnya. Anda bertanggung jawab untuk memastikan bahwa penggunaan Dynamics 365 Customer Insights, termasuk fitur ini, mematuhi semua hukum dan peraturan yang berlaku, termasuk hukum yang terkait dengan privasi, data pribadi, data biometrik, perlindungan data, dan kerahasiaan komunikasi.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Halaman segmen yang disarankan di Customer insights yang menampilkan rincian saran di panel sisi.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmen yang disarankan untuk meningkatkan KPI

Sebagai pengguna wawasan audiens, Anda mungkin memiliki [ukuran yang dibuat](measures.md) yang membantu melacak KPI (Indikator Performa Utama). Penting untuk memahami pengaruh atribut tertentu terhadap KPI ini agar dapat membuat segmen dan menjalankan kampanye yang sangat ditargetkan.   
Misalnya, Anda melacak pengukuran yang disebut *TotalSpendPerCustomer*. Sebagai bisnis, Anda ingin melihat jumlah tersebut berkembang. Memilih ukuran sebagai atribut utama, memungkinkan Anda memilih atribut yang akan dinilai untuk pengaruh. Misalnya *tingkat keanggotaan*, *periode keanggotaan*, dan *pekerjaan*. Selanjutnya, Customer insights dapat menyarankan segmen yang memberi tahu Anda tentang pengaruh terbesar dari pengukuran tersebut. Misalnya, *Akuntan* yang merupakan anggota *Emas* dan telah bersama bisnis Anda selama *minimal lima tahun* adalah pemberi pengaruh terbesar dari *TotalSpendPerCustomer*. Anda akan mendapatkan perkiraan ukuran segmen untuk setiap saran. Anda dapat menggunakan informasi ini untuk membuat kampanye untuk audiens yang ditargetkan.

## <a name="understand-what-influences-a-customer-attribute"></a>Memahami yang memengaruhi atribut pelanggan

Anda dapat memilih atribut pelanggan, bukan ukuran sebagai atribut utama. Berdasarkan pilihan atribut yang mempengaruhi, model AI membuat rangkaian saran yang menunjukkan pengaruh atribut yang dipilih terhadap atribut utama.   
Misalnya, Anda memilih *Anggota Penghargaan (Ya/Tidak)* sebagai atribut utama. *Masa*, *Pekerjaan*, dan *Jumlah Tiket Dukungan* ditetapkan sebagai atribut lainnya yang mempengaruhi. Model AI dapat menyarankan segmen yang menunjukkan kebanyakan profesional TI dengan masa jabatan lebih dari dua tahun adalah anggota penghargaan. Saran lain dapat menyorot bahwa akuntan dengan masa jabatan lebih dari satu tahun dan kurang dari tiga tiket dukungan adalah anggota penghargaan. 

## <a name="artificial-intelligence-usage"></a>Penggunaan inteligensi buatan

Menggunakan atribut utama dan atribut yang mempengaruhi, algoritme pohon keputusan menyarankan segmen yang menarik. Saran didasarkan pada aturan atau pola yang dipilih oleh algoritme AI. Hanya segmen yang berbeda secara signifikan dari rata-rata penduduk yang akan ditampilkan sebagai saran. Perbandingan dengan rata-rata populasi didasarkan pada pengukuran yang dipilih atau atribut utama.

### <a name="responsible-ai"></a>AI yang bertanggung jawab

Segmen yang disarankan memungkinkan Anda memilih atribut untuk membuat segmen baru dan memproses data yang Anda pilih. Saat memilih atribut, termasuk atribut sensitif seperti ras, orientasi seksual, atau jenis kelamin, Anda harus memastikan bahwa Anda dapat dan harus memproses data tersebut. Anda bertanggung jawab untuk mematuhi hukum yang berlaku untuk organisasi Anda dan mematuhi prinsip dan kebijakan privasi organisasi Anda.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Hasil yang berbeda untuk atribut utama dengan nilai kategori dan angka

Saran segmen berbeda jika Anda memilih atribut numerik atau atribut kategoris sebagai atribut utama. Nilai dalam atribut kategori berisi dua atau beberapa kategori atau jenis. Atribut numerik berisi data kuantitatif dan memiliki arti pengukuran yang terkait.

Dengan atribut angka seperti *penghasilan tahunan* atau *periode keanggotaan* sebagai atribut utama, sistem menyarankan segmen yang memiliki nilai rata-rata atribut numerik yang lebih tinggi atau lebih rendah bila dibandingkan dengan semua pelanggan.

Atribut kategoris seperti *kepuasan pelanggan* sebagai atribut utama menghasilkan segmen yang disarankan dengan persentase pelanggan yang lebih tinggi atau lebih rendah milik kategori tertentu bila dibandingkan dengan persentase semua pelanggan yang termasuk dalam kategori yang sama. Misalnya, *kepuasan pelanggan* dipilih sebagai atribut utama dan terdiri dari tiga kategori (*Rendah*, *Sedang* dan *Tinggi*). Untuk tiap kategori, segmen akan disarankan memiliki persentase pelanggan yang jauh lebih tinggi atau lebih rendah milik kategori tersebut dibandingkan dengan perbandingan semua pelanggan dalam kategori yang sama. Jika 22% dari semua pelanggan memiliki kepuasan *Tinggi*, maka hanya segmen yang memiliki perbandingan pelanggan yang jauh lebih tinggi atau lebih rendah dengan kepuasan *Tinggi* dibandingkan dengan 22% yang akan disarankan untuk kategori tersebut. Dengan cara yang sama, segmen akan disarankan untuk masing-masing kategori lain (*Rendah* dan *Sedang*) jika secara statistik signifikan.

> [!NOTE]
> Saat ini, kami hanya mendukung atribut kategoris utama yang memiliki hingga 10 kategori. Jika Anda ingin melihat saran segmen berdasarkan atribut utama dengan lebih dari 10 kategori, sebaiknya kelompokkan beberapa kategori untuk mengurangi jumlah kategori menjadi 10 atau lebih sedikit. Pembatasan ini hanya berlaku untuk atribut utama. Untuk atribut kategoris yang mempengaruhi, saat ini kami mendukung maksimum 100 kategori.

## <a name="generate-suggested-segments"></a>Membuat segmen yang disarankan

1. Buka **Segmen**.

1. Pilih tab **Saran (pratinjau)**.

1. Pilih **Dapatkan saran baru** untuk memulai pengalaman terpandu.

1. Pilih ukuran atau atribut pelanggan sebagai atribut utama dan pilih **Selanjutnya**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Memilih atribut utama untuk saran pada segmen yang disarankan.":::

1. Pilih atribut yang mempengaruhi, lalu pilih **Simpan**.
   
   > [!TIP]
   > Memilih beberapa atribut yang mempengaruhi akan meningkatkan peluang untuk mengevaluasi pengaruh atribut utama. Jangan sertakan atribut yang tidak mempengaruhi atribut utama. Contohnya, jika semua pelanggan berasal dari negara tertentu, jangan sertakan atribut *negara* karena tidak akan mempengaruhi output.

1. Tergantung pada jumlah profil pelanggan dan atribut yang dipilih, diperlukan waktu beberapa menit untuk memproses atribut yang dipilih. 

## <a name="view-details-of-a-suggested-segment"></a>Lihat detail segmen yang disarankan

Setelah model AI menghasilkan saran, Anda akan menemukannya terdaftar di **Segmen** > **Saran (pratinjau)**.
 
Pilih segmen yang disarankan untuk meninjau rincian saran tersebut, termasuk perbandingan nilai rata-rata dan jumlah anggota segmen. Anda juga dapat meninjau nilai atribut atau aturan yang dipelajari model AI untuk menyarankan segmen yang dipilih.

## <a name="save-a-suggestion-as-a-segment"></a>Simpan saran sebagai segmen

1. Buka **Segmen** > **Saran (pratinjau)**.

1. Pilih segmen yang ingin disimpan. 

1. Pada panel sisi, pilih **Simpan sebagai segmen**. 

1. Setelah menyimpan segmen, segmen tersebut akan ditampilkan dalam daftar segmen pada tab **Semua segmen**. Segmen tersebut sekarang dapat [di-refresh, diedit, atau dihapus seperti segmen lainnya](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Refresh atau edit rangkaian saran

1. Buka **Segmen** > **Saran (pratinjau)**.

1. Pilih **Refresh saran** untuk me-refresh saran sekaligus menyimpan atribut yang dikonfigurasi. Atau pilih **Edit atribut** untuk memodifikasi atribut yang dikonfigurasi. Sistem akan menjalankan ulang model AI, menghasilkan saran segmen berdasarkan data terbaru, dan mengganti saran saat ini.

## <a name="limitations"></a>Pembatasan

1. Perkiraan ketidakcocokan ukuran segmen: Jika Anda memilih atribut utama yang berisi nilai kosong, perkiraan ukuran segmen dapat mempengaruhi perkiraan ukuran segmen dalam saran segmen. Bila menyimpan segmen tersebut, ukuran segmen aktual dapat berbeda dengan perkiraan asli.
 
2. Atribut utama jenis Boolean tidak berfungsi: Saat ini, kami hanya mendukung string dan jenis data numerik sebagai atribut utama.

3. Segmen yang disarankan tidak cukup berbeda: Ingat bahwa atribut yang dipilih dan distribusi nilai atribut tersebut akan mempengaruhi hasil. Anda dapat mengubah atribut yang mempengaruhi atau bahkan atribut utama Anda untuk mendapatkan hasil yang berbeda.



[!INCLUDE[footer-include](../includes/footer-banner.md)]