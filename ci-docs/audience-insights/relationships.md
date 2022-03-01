---
title: Hubungan antara entitas dan jalur entitas
description: Buat dan kelola Relasi antara entitas dari beberapa sumber data.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171168"
---
# <a name="relationships-between-entities"></a>Relasi di antara dua entitas

Relasi menghubungkan entitas dan menentukan grafik data Anda saat entitas berbagi pengidentifikasi umum, kunci asing. Kunci asing ini dapat dirujuk dari satu entitas ke entitas lain. Entitas tersambung memungkinkan definisi segmen dan ukuran berdasarkan beberapa sumber data.

Ada tiga jenis dasbor di relasi: 
- Sistem Relasi yang tidak dapat dapat diedit, yang dibuat oleh sistem sebagai bagian dari proses penyatuan data
- Konten Relasi warisan yang tidak dapat diedit, yang dibuat secara otomatis dari menyerap sumber data 
- Relasi kustom yang dapat diedit, yang dibuat dan dikonfigurasi oleh pengguna

## <a name="non-editable-system-relationships"></a>Relasi sistem yang tidak dapat diedit

Selama penyatuan data, Relasi sistem dibuat secara otomatis berdasarkan pencocokan cerdas. Relasi ini membantu mengaitkan rekaman profil pelanggan dengan rekaman terkait lainnya. Diagram berikut menggambarkan pembuatan Relasi berbasis tiga sistem. Entitas pelanggan dicocokkan dengan entitas lain untuk menghasilkan entitas *Pelanggan* terpadu.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagram dengan jalur relasi untuk entitas pelanggan dengan tiga Relasi 1-n.":::

- **Relasi *CustomerToContact*** dibuat antara entitas *pelanggan* dan entitas *kontak*. Entitas *pelanggan* mendapatkan bidang penting **Contact_contactId** untuk dikaitkan dengan bidang kunci entitas *kontak* **contactId**.
- **Relasi *CustomerToAccount*** dibuat antara entitas *pelanggan* dan entitas *Akun*. Entitas *pelanggan* mendapatkan bidang penting **Account_accountID** untuk dikaitkan dengan bidang kunci entitas *Akun* **accountId**.
- **Relasi *CustomerToWebAccount*** dibuat antara entitas *pelanggan* dan entitas *WebAccount*. Entitas *pelanggan* mendapatkan bidang kunci **WebAccount_webaccountID** untuk dikaitkan dengan bidang kunci entitas *WebAccount* **webaccountID**.

## <a name="non-editable-inherited-relationships"></a>Relasi warisan yang tidak dapat diedit

Selama proses penyerapan data, sistem memeriksa sumber data untuk Relasi yang ada. Jika tidak ada hubungan, sistem secara otomatis membuatnya. Relasi produk ini juga digunakan dalam proses hilir.

## <a name="create-a-custom-relationship"></a>Membuat relasi kustom

Hubungan terdiri dari *entitas sumber* yang berisi kunci asing dan *entitas target* yang diarahkan pada kunci asing entitas sumber. 

1. Di wawasan audiens, buka **Data** > **Relasi**.

2. Pilih **relasi baru**.

3. Di panel **Relasi rakyat**, berikan informasi berikut:

   :::image type="content" source="media/relationship-add.png" alt-text="Panel sisi relasi baru dengan bidang input kosong.":::

   - **Nama relasi**: Nama yang mencerminkan tujuan relasi. Contoh: CustomerToSupportCase.
   - **Deskripsi** deskripsi relasi.
   - **Entitas sumber**: Entitas yang digunakan sebagai sumber dalam relasi tersebut. Contoh: SupportCase.
   - **Entitas target**: Entitas yang digunakan sebagai target dalam relasi tersebut. Contoh: Pelanggan.
   - **Kardinalitas sumber**: Menentukan Kardinalitas entitas sumber. Kardinalitas menjelaskan jumlah elemen yang mungkin dalam satu set. Ini selalu berkaitan dengan kardinalitas target. Anda dapat memilih antara **Satu** dan **Banyak**. Hanya Relasi banyak ke satu dan satu-ke-satu yang didukung.  
     - Banyak ke satu: Beberapa rekaman sumber dapat berhubungan dengan satu rekaman target. Contoh: Beberapa kasus dukungan dari satu pelanggan.
     - Satu-ke-satu: Rekaman sumber tunggal berkaitan dengan satu rekaman target. Contoh: Satu ID loyalitas untuk satu pelanggan.

     > [!NOTE]
     > Relasi banyak ke banyak dapat dibuat menggunakan dua Relasi banyak ke satu dan penautan entitas, yang menghubungkan entitas sumber dan entitas target.

   - **Kardinalitas target**: pilih menunjukkan Kardinalitas rekaman entitas target. 
   - **Bidang kunci sumber**: Bidang kunci asing di entitas sumber. Contoh: SupportCase dapat menggunakan CaseID sebagai bidang kunci asing.
   - **Bidang kunci target**: bidang kunci dari entitas target. Contoh Pelanggan dapat menggunakan bidang kunci **CustomerID**.

4. Pilih **Simpan** untuk membuat relasi kustom.

## <a name="view-relationships"></a>Lihat relasi

Halaman Relasi mencantumkan semua Relasi yang telah dibuat. Setiap baris mewakili relasi, yang juga mencakup detail tentang entitas sumber, entitas target, dan kardinalitas. 

:::image type="content" source="media/relationships-list.png" alt-text="Daftar Relasi dan opsi di bilah tindakan halaman Relasi.":::

Halaman ini menawarkan sekumpulan opsi untuk relasi yang lama dan baru: 
- **Relasi baru**: Pilih [Buat Relasi kustom](#create-a-custom-relationship).
- **Visualisator**: [Jelajahi visualisator relasi](#explore-the-relationship-visualizer) untuk melihat diagram jaringan dari Relasi yang ada dan kardinalitas mereka.
- **Filter menurut**: Pilih tipe Relasi untuk ditampilkan dalam daftar.
- **Cari Relasi**: Gunakan pencarian berbasis teks pada properti Relasi.

### <a name="explore-the-relationship-visualizer"></a>Jelajahi visualisator relasi

Visualisator relasi menampilkan diagram jaringan dari Relasi yang ada antara entitas yang dihubungkan dan kardinalitas mereka.

Untuk mengkustomisasi tampilan, Anda bisa mengubah posisi kotak dengan menyeretnya ke kanvas.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Tangkapan layar diagram jaringan visualisator relasi dengan sambungan di antara entitas terkait.":::

Pilihan yang Tersedia: 
- **Ekspor sebagai gambar**: Simpan tampilan saat ini sebagai file gambar.
- **Mengubah ke tata letak horizontal/vertikal**: Mengubah perataan entitas dan Relasi.
- **Edit**: Perbarui properti Relasi kustom di panel edit dan simpan perubahan.

## <a name="manage-existing-relationships"></a>Kelola relasi yang ada 

Di halaman Relasi, setiap relasi ditunjukkan dengan baris. 

Pilih relasi, lalu tentukan salah satu pilihan berikut: 
 
- **Edit**: Perbarui properti Relasi kustom di panel edit dan simpan perubahan.
- **Hapus**: Hapus Relasi kustom.
- **Lihat**: Melihat relasi warisan dan yang dibuat sistem. 

## <a name="next-step"></a>Langkah selanjutnya

Relasi sistem dan kustom digunakan untuk [membuat segmen](segments.md) berdasarkan beberapa sumber data yang tidak lagi diisolasi.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
