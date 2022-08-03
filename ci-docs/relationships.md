---
title: Hubungan antara entitas dan jalur entitas
description: Buat dan kelola Relasi antara entitas dari beberapa sumber data.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: e622e5fa0b5738e31db1c668d95312adbc4f7d36
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183566"
---
# <a name="relationships-between-entities-and-entity-paths"></a>Hubungan antara entitas dan jalur entitas

Relasi menghubungkan entitas dan menentukan grafik data Anda saat entitas berbagi pengidentifikasi umum, kunci asing. Kunci asing ini dapat dirujuk dari satu entitas ke entitas lain. Entitas tersambung memungkinkan definisi segmen dan ukuran berdasarkan beberapa sumber data.

Ada tiga jenis dasbor di relasi: 
- Sistem yang tidak dapat diedit Relasi dibuat oleh sistem sebagai bagian dari proses penyatuan data
- Relasi warisan yang tidak dapat diedit dibuat secara otomatis dari penyerapan sumber data
- Relasi kustom yang dapat diedit dibuat dan dikonfigurasi oleh pengguna

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

1. Buka **data** > **Relasi**.

2. Pilih **relasi baru**.

3. Di panel **Relasi rakyat**, berikan informasi berikut:

   :::image type="content" source="media/relationship-add.png" alt-text="Panel sisi relasi baru dengan bidang input kosong.":::

   - **Nama relasi**: Nama yang mencerminkan tujuan relasi. Contoh: CustomerToSupportCase.
   - **Deskripsi** deskripsi relasi.
   - **Entitas sumber**: Entitas yang digunakan sebagai sumber dalam relasi tersebut. Contoh: SupportCase.
   - **Entitas target**: Entitas yang digunakan sebagai target dalam relasi tersebut. Contoh: Pelanggan.
   - **Sumber kardinalitas**: Kardinalitas entitas sumber. Kardinalitas menjelaskan jumlah elemen yang mungkin dalam satu set. Ini selalu berkaitan dengan kardinalitas target. Anda dapat memilih antara **Satu** dan **Banyak**. Hanya Relasi banyak ke satu dan satu-ke-satu yang didukung.  
     - Banyak ke satu: Beberapa rekaman sumber dapat berhubungan dengan satu rekaman target. Contoh: Beberapa kasus dukungan dari satu pelanggan.
     - Satu-ke-satu: Rekaman sumber tunggal berkaitan dengan satu rekaman target. Contoh: Satu ID loyalitas untuk satu pelanggan.

     > [!NOTE]
     > Relasi banyak ke banyak dapat dibuat menggunakan dua Relasi banyak ke satu dan penautan entitas, yang menghubungkan entitas sumber dan entitas target.

   - **Kardinalitas target**: Kardinalitas catatan entitas target.
   - **Bidang kunci sumber**: Bidang kunci asing di entitas sumber. Contoh: SupportCase menggunakan **CaseID** sebagai bidang kunci asing.
   - **Bidang kunci target**: Bidang kunci entitas target. Contoh: Pelanggan menggunakan **CustomerID** sebagai bidang kunci.

4. Pilih **Simpan** untuk membuat relasi kustom.

## <a name="set-up-account-hierarchies"></a>Konfigurasi hierarki akun

Lingkungan yang dikonfigurasi untuk menggunakan akun bisnis sebagai target utama audiens dapat mengonfigurasi hierarki akun untuk akun bisnis terkait. Misalnya, perusahaan yang memiliki unit bisnis terpisah.

Organisasi membuat hierarki akun untuk lebih baik mengelola akun dan Relasi satu sama lain. Customer Insights mendukung hierarki akun orang tua-turunan yang sudah ada dalam data pelanggan yang diserap. Contohnya, akun dari Dynamics 365 Sales. Hierarki ini dapat dikonfigurasi pada **halaman Relasi**.

1. Buka **data** > **Relasi**.
1. Pilih tab **hierarki akun**.
1. Pilih **hierarki akun baru**.
1. Pada panel **hierarki Akun**, berikan nama untuk hierarki. Sistem membuat nama untuk entitas output, tetapi Anda dapat mengubahnya.
1. Pilih entitas yang berisi hierarki akun Anda. Akun biasanya ada dalam entitas yang sama yang berisi akun.
1. **Pilih UID** Akun dan **UID** Induk dari entitas yang dipilih.
1. Pilih **Simpan** untuk menyelesaikan hierarki akun.

## <a name="manage-existing-relationships"></a>Kelola relasi yang ada

**Buka halaman Relasi** untuk melihat semua Relasi yang telah dibuat, entitas sumbernya, entitas target, dan kardinalitas.

:::image type="content" source="media/relationships-list.png" alt-text="Daftar Relasi dan opsi di bilah tindakan halaman Relasi.":::

**Gunakan opsi Filter menurut** atau **Cari Relasi** untuk menemukan hubungan tertentu. Untuk melihat diagram jaringan dari Relasi yang ada dan kardinalitasnya, pilih [**Visualizer**](#explore-the-relationship-visualizer).

Pilih hubungan untuk melihat tindakan yang tersedia:
- **Edit**: Perbarui properti Relasi kustom di panel edit dan simpan perubahan.
- **Hapus**: Hapus Relasi kustom.
- **Lihat**: Melihat relasi warisan dan yang dibuat sistem.

### <a name="explore-the-relationship-visualizer"></a>Jelajahi visualisator relasi

Visualisator relasi menampilkan diagram jaringan dari Relasi yang ada antara entitas yang dihubungkan dan kardinalitas mereka. Ia juga memvisualisasikan jalur relasi.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Tangkapan layar diagram jaringan visualisator relasi dengan sambungan di antara entitas terkait.":::

Untuk mengkustomisasi tampilan, Anda bisa mengubah posisi kotak dengan menyeretnya ke kanvas. Opsi lain termasuk: 
- **Ekspor sebagai gambar**: Simpan tampilan saat ini sebagai file gambar.
- **Mengubah ke tata letak horizontal/vertikal**: Mengubah perataan entitas dan Relasi.
- **Edit**: Perbarui properti Relasi kustom di panel edit dan simpan perubahan.

## <a name="relationship-paths"></a>Jalur relasi

Jalur relasi menjelaskan entitas yang tersambung dengan Relasi antara entitas sumber dan entitas target. Ini digunakan saat membuat segmen atau ukuran yang mencakup entitas selain entitas profil terpadu dan ada beberapa opsi untuk mencapai entitas profil terpadu. Jalur relasi yang berbeda dapat menghasilkan hasil yang berbeda.

Contohnya, entitas *eCommerce_eCommercePurchases* memiliki daftar Relasi ke entitas *Pelanggan* profil terpadu:

- eCommerce_eCommercePurchases > Pelanggan
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Pelanggan
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Pelanggan

Jalur relasi menentukan entitas yang dapat Anda gunakan saat membuat aturan untuk langkah-langkah atau segmen. Memilih pilihan dengan jalur relasi terpanjang kemungkinan akan menghasilkan hasil yang lebih sedikit karena rekaman yang cocok harus menjadi bagian dari semua entitas. Dalam contoh ini, pelanggan harus membeli barang melalui e-commerce (eCommerce_eCommercePurchases), pada titik penjualan (POS_posPurchases), dan berpartisipasi dalam program loyalitas kita (loyaltyScheme_loyCustomers). Saat memilih pilihan pertama, Kemungkinan Anda mendapatkan hasil lebih banyak karena pelanggan hanya perlu ada dalam satu entitas tambahan.

### <a name="direct-relationship"></a>Relasi langsung

Relasi diklasifikasi sebagai **relasi langsung** bila entitas sumber terhubung ke entitas target dengan hanya satu relasi.

Contohnya, jika entitas aktivitas yang disebut *eCommerce_eCommercePurchases* terhubung ke entitas target *eCommerce_eCommerceContacts* melalui *ContactId* hanya, maka ini adalah relasi langsung.

:::image type="content" source="media/direct_Relationship.png" alt-text="Entitas sumber terhubung secara langsung ke entitas target.":::

#### <a name="multi-path-relationship"></a>Relasi multi-jalur

**Relasi multi-jalur** adalah jenis khusus relasi langsung yang menghubungkan entitas sumber ke lebih dari satu entitas target.

Contohnya, jika entitas aktivitas yang disebut *eCommerce_eCommercePurchases* terkait dengan dua entitas target, baik *eCommerce_eCommerceContacts* maupun *loyaltyScheme_loyCustomers*, maka ini merupakan relasi multi-jalur.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Entitas sumber terhubung langsung ke lebih dari satu entitas target melalui relasi multi-lompatan.":::

### <a name="indirect-relationship"></a>Relasi tidak langsung

Relasi diklasifikasi sebagai **relasi tidak langsung** bila entitas sumber terkait ke satu atau lebih entitas tambahan sebelum terkait dengan entitas target.

#### <a name="multi-hop-relationship"></a>Relasi multi-lompatan

Relasi **multi-lompatan** adalah *relasi tidak langsung* yang memungkinkan Anda menghubungkan entitas sumber ke entitas target melalui satu atau beberapa entitas perantara lainnya.

Contohnya, jika entitas aktivitas yang disebut *eCommerce_eCommercePurchasesWest* terhubung ke entitas tingkat lanjut yang disebut *eCommerce_eCommercePurchasesEast*, kemudian terhubung ke entitas target yang disebut *eCommerce_eCommerceContacts*, maka ini adalah relasi multi-lompatan.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Entitas sumber terhubung secara langsung ke entitas target dengan entitas menengah.":::

### <a name="multi-hop-multi-path-relationship"></a>Relasi multi-lompatan, multi-jalur

Relasi multi-jalur dan multi-lompatan dapat digunakan bersama-sama untuk membuat **relasi multi-lompatan, multi-jalur**. Jenis khusus ini menggabungkan fungsi **relasi multi-lompatan** dan **multi-jalur**. Anda dapat menyambung ke lebih dari satu entitas target saat menggunakan entitas tingkat lanjut.

Contohnya, jika entitas aktivitas yang disebut *eCommerce_eCommercePurchasesWest* terhubung ke entitas tingkat lanjut yang disebut *eCommerce_eCommercePurchasesEast*, kemudian terhubung ke dua entitas target, baik *eCommerce_eCommerceContacts* maupun *loyaltyScheme_loyCustomers*, maka ini adalah relasi multi-jalur.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Entitas sumber terhubung secara langsung ke satu entitas target dan terhubung ke entitas target lain melalui entitas menengah.":::

## <a name="next-step"></a>Langkah selanjutnya

Relasi sistem dan kustom digunakan di halaman [buat segmen](segments.md) dan [ukuran](measures.md) berdasarkan beberapa sumber data yang tidak lagi diisolasi.

[!INCLUDE [footer-include](includes/footer-banner.md)]
