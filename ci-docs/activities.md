---
title: Aktivitas pelanggan
description: Tentukan aktivitas pelanggan dan lihat di timeline pada profil pelanggan.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: 29b5d3f5848d36abd8e941136a6330dbb7730016
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642619"
---
# <a name="customer-activities"></a>Aktivitas pelanggan

Gabungkan aktivitas pelanggan dari [berbagai sumber data](data-sources.md) di Dynamics 365 Customer Insights untuk membuat timeline yang mencantumkan aktivitas secara kronologis. Sertakan timeline di aplikasi Dynamics 365 dengan solusi [add-in Kartu Pelanggan](customer-card-add-in.md), atau di dasbor Power BI.

## <a name="define-an-activity"></a>Menentukan Aktivitas

Sumber data Anda dapat mencakup entitas dengan data transaksional dan aktivitas dari beberapa sumber data. Identifikasi entitas tersebut dan pilih aktivitas yang ingin Anda lihat pada kronologi pelanggan. Pilih entitas yang mencakup aktivitas atau aktivitas target Anda.

Entitas harus memiliki minimal satu atribut jenis **tanggal** untuk disertakan dalam kronologi pelanggan dan Anda tidak dapat menambahkan entitas tanpa bidang **tanggal**. Kontrol **Tambah aktivitas** dinonaktifkan jika tidak ada entitas yang ditemukan.

1. **Buka DataActivities** > **·**.

1. Pilih **Tambahkan aktivitas** untuk memulai pengalaman terpandu untuk proses penyetelan aktivitas.

1. Dalam langkah **Data aktivitas**, atur nilai untuk bidang berikut ini:

   - **Nama aktivitas**: Pilih nama untuk aktivitas Anda.
   - **Entitas**: Pilih entitas yang mencakup data transaksi atau aktivitas.
   - **Kunci utama**: Pilih bidang yang secara unik mengidentifikasi rekaman. Ini tidak boleh berisi nilai duplikat, nilai kosong, atau nilai yang tidak ada.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Siapkan data aktivitas dengan nama, entitas, dan kunci utama.":::

1. Pilih **Berikutnya** untuk masuk ke langkah berikutnya.

1. Pada langkah **Relasi**, konfigurasikan rincian untuk menghubungkan data aktivitas Anda dengan rekaman pelanggan terkait. Langkah ini memvisualisasikan hubungan antar entitas.  

   - **Pertama:** Bidang asing dalam entitas aktivitas Anda yang akan digunakan untuk menjalin hubungan dengan entitas lain.
   - **Kedua**: Entitas pelanggan sumber yang sesuai dengan entitas aktivitas Anda akan menjalin hubungan. Anda hanya dapat berhubungan dengan entitas pelanggan sumber yang digunakan dalam proses penyatuan data.
   - **Ketiga**: Jika hubungan antara entitas aktivitas ini dan entitas pelanggan sumber yang dipilih sudah ada, nama hubungan akan berada dalam mode baca-saja. Jika tidak ada relasi tersebut, relasi baru akan dibuat dengan nama yang Anda berikan di kotak ini.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Tentukan relasi entitas.":::

   > [!TIP]
   > Di lingkungan B to B, Anda dapat memilih antara entitas akun dan entitas lain. Jika Anda memilih entitas akun, jalur relasi akan secara otomatis diatur. Untuk entitas lain, Anda harus menentukan jalur relasi pada satu atau beberapa entitas menengah hingga mencapai entitas akun.

1. Pilih **Berikutnya** untuk masuk ke langkah berikutnya. 

1. Dalam langkah **Penyatuan aktivitas**, pilih peristiwa aktivitas dan waktu mulai aktivitas Anda. 
   - **Bidang yang diperlukan**
      - **Aktivitas peristiwa**: Bidang yang menjadi ajang aktivitas ini.
      - **Cap waktu**: Bidang yang mewakili waktu mulai aktivitas Anda.

   - **Bidang Opsional**
      - **Detail tambahan**: Bidang dengan informasi yang relevan untuk kegiatan ini.
      - **Ikon**: Ikon yang paling mewakili jenis aktivitas ini.
      - **Alamat web**: Bidang yang berisi URL dengan informasi tentang aktivitas ini. Misalnya, sistem transaksional yang menjadi sumber aktivitas ini. URL ini dapat berupa bidang apa pun dari sumber data, atau dapat dibangun sebagai bidang baru menggunakan Power Query transformasi. Data URL akan disimpan di entitas *Aktivitas Terpadu*, yang dapat dikonsumsi di hilir menggunakan [API](apis.md).

   - **Tampilkan di kronologi**
      - Pilih apakah Anda ingin menampilkan aktivitas ini di tampilan timeline pada profil pelanggan Anda. Pilih **Ya** untuk menampilkan aktivitas di timeline atau **Tidak** untuk menyembunyikannya.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Tentukan data aktivitas pelanggan dalam entitas Aktivitas Terpadu.":::

1. Pilih **berikutnya** untuk beralih ke langkah berikutnya. Anda dapat memilih **Selesai dan tinjau** untuk menyimpan aktivitas sekarang dengan tipe aktivitas yang diatur ke **Lainnya**. 

1. Dalam langkah **Jenis Aktivitas**, pilih jenis aktivitas dan pilih secara opsional jika Anda ingin memetakan beberapa jenis aktivitas untuk digunakan di area lain dari Customer Insights. Saat ini, jenis aktivitas *tanggapan*, *loyalitas*, *SalesOrder*, *SalesOrderLine*, dan *langganan* dapat dipetakan secara semantis setelah setuju untuk memetakan bidang. Jika jenis aktivitas tidak relevan untuk aktivitas baru, Anda dapat memilih *Lainnya* atau *buat yang baru* untuk jenis aktivitas kustom.

1. Pilih **berikutnya** untuk beralih ke langkah berikutnya. 

1. Di langkah **Tinjau**, verifikasi pilihan Anda. Kembali ke langkah-langkah sebelumnya dan perbarui informasi jika perlu.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Meninjau bidang yang ditentukan untuk aktivitas.":::
   
1. Pilih **Simpan aktivitas** untuk menerapkan perubahan Anda dan pilih **Selesai** untuk kembali ke **Data** > **Aktivitas**. Di sini Anda melihat aktivitas mana yang diatur untuk ditampilkan di timeline. 

1. Pada halaman **Aktivitas**, pilih **Jalankan** untuk memproses aktivitas. 

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Mengelola aktivitas yang ada

Pada **Data** > **Aktivitas**, Anda dapat melihat semua aktivitas yang disimpan, dan mengelolanya. Setiap aktivitas diwakili oleh baris yang juga menyertakan detail tentang sumber, entitas, dan jenis aktivitas.

Tindakan berikut ini tersedia saat Anda memilih aktivitas. 

- **Edit**: Membuka penyiapan aktivitas pada langkah peninjauan. Anda dapat mengubah salah satu atau semua konfigurasi saat ini dari langkah ini. Setelah mengubah konfigurasi, pilih **Simpan aktivitas** lalu pilih **Jalankan** untuk memproses perubahan.

- **Ganti nama**: Buka dialog yang memungkinkan Anda memasukkan nama lain untuk aktivitas yang dipilih. Pilih **Simpan** untuk menerapkan perubahan.

- **Hapus**: Membuka dialog untuk mengonfirmasi penghapusan aktivitas yang dipilih. Anda juga dapat menghapus lebih dari satu aktivitas sekaligus dengan memilih aktivitas lalu memilih ikon hapus. Klik **Hapus**, untuk mengonfirmasi penghapusan tersebut.

## <a name="view-activity-timelines-on-customer-profiles"></a>Melihat timeline aktivitas di profil pelanggan

Setelah anda mengkonfigurasi aktivitas pelanggan, pilih **Tampilkan dalam timeline aktivitas** dalam konfigurasi aktivitas untuk menemukan semua aktivitas pelanggan pada profil pelanggan mereka.

Untuk membuka timeline pelanggan, buka **Pelanggan** dan pilih profil pelanggan yang akan dilihat.

Jika pelanggan telah berpartisipasi dalam aktivitas yang telah dikonfigurasi, Anda akan menemukannya di bagian **timeline Aktivitas**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Melihat aktivitas terkonfigurasi di Profil Pelanggan.":::

Ada beberapa cara untuk memfilter aktivitas dalam timeline aktivitas:

- Anda dapat memilih satu atau beberapa ikon aktivitas untuk menyempurnakan hasil agar hanya menyertakan jenis yang dipilih.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Memfilter aktivitas berdasarkan jenis menggunakan ikon.":::

- Anda dapat memilih **Filter** untuk membuka panel filter untuk mengkonfigurasi filter timeline.

   1. Anda dapat memfilter berdasarkan *ActivityType* dan *Tanggal*
   1. Pilih **Terapkan** untuk menggunakan filter di timeline aktivitas.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Gunakan panel filter untuk mengkonfigurasi kondisi filter.":::

Untuk menghilangkan filter, pilih **x** di sebelah setiap filter yang diterapkan ke timeline atau pilih **Kosongkan filter**.


> [!NOTE]
> Filter aktivitas akan dihapus bila Anda meninggalkan profil pelanggan. Anda harus menerapkannya setiap kali membukanya di profil pelanggan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
