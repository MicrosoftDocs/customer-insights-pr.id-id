---
title: Segmen yang disarankan berdasarkan aktivitas (pratinjau)
description: Biarkan Pembelajaran Mesin anda menemukan segmen baru dan menarik berdasarkan aktivitas pelanggan.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170593"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Segmen yang disarankan berdasarkan aktivitas (pratinjau)

Temukan segmen menarik dari pelanggan Anda berdasarkan data aktivitas pelanggan yang diserap ke Customer Insights. Contoh data aktivitas adalah transaksi, durasi panggilan dukungan, pembelian, atau retur. Untuk menyarankan segmen, data aktivitas akan analisis untuk potensi, frekuensi, dan nilai moneter (atau durasi). Atau, Anda dapat membuat [segmen yang disarankan untuk meningkatkan ukuran atau lebih memahami pengaruh atribut](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Tab segmen yang disarankan yang menampilkan saran segmen untuk segmen berbasis aktivitas dan berbasis atribut.":::

## <a name="categorize-customers-by-activity"></a>Mengkategorikan pelanggan berdasarkan aktivitas

Dengan [data aktivitas](activities.md) yang tersedia dalam Customer Insights, kami dapat menghasilkan saran yang mewakili grup pelanggan:

- sebagian besar pelanggan aktif 
- Pelanggan yang melakukan pembelian terbanyak 
- Pelanggan yang menghasilkan pendapatan terbanyak 
- Pelanggan yang belum aktif akhir-akhir ini 
- Pelanggan yang sering berinteraksi dengan bisnis Anda  

Jika Anda memiliki bisnis ritel, Anda dapat mengetahui pelanggan yang menghasilkan pendapatan terbanyak dan memberi mereka hadiah dengan kupon. Atau Anda dapat mengidentifikasi pelanggan sesekali dan menawarkan kepada mereka untuk bergabung dalam program penghargaan sehingga mereka lebih sering mengunjungi bisnis Anda.
Jika Anda menyediakan perawatan kesehatan publik dan tujuan Anda adalah meminimalkan biaya untuk masing-masing pasien, Anda dapat mencoba mengurangi kunjungan berulang dengan memberikan perawatan terbaik dalam kunjungan sesedikit mungkin. Dalam kasus ini, sasaran Anda adalah menjaga frekuensi kunjungan tetap rendah dan meminimalkan biaya berulang untuk pasien. Atau Anda dapat mengidentifikasi segmen pasien yang sering melakukan janji temu dan biaya berulang tinggi serta menganalisis kasus ini untuk meningkatkan perawatan individu.

## <a name="required-data"></a>Data yang diperlukan

Saran dibuat berdasarkan data input yang dipilih.

- Profil pelanggan: Semua pelanggan atau anggota dari segmen tertentu.

- Periode waktu: Bulan lalu, tahun lalu, atau jangka waktu kustom.

- Jenis aktivitas: pembelian, transaksi ritel, transaksi online, kasus dukungan pelanggan, langganan, dan sebagainya.  

- Entitas dalam Customer Insights yang berisi data aktivitas: Entitas UnifiedActivity atau entitas untuk aktivitas tertentu.

- Dimensi untuk dimasukkan: Kekinian, frekuensi, atau dimensi moneter, tergantung pada kebutuhan bisnis Anda.

## <a name="generate-suggested-segments"></a>Membuat segmen yang disarankan

1. Buka **Segmen** dan pilih tab **Saran (pratinjau**).

1. Pilih **Cari saran baru**, lalu pilih **Lihat atau antisipasi perilaku pelanggan**. Pilih **Mulai**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Langkah pertama wizard konfigurasi untuk segmen yang disarankan berdasarkan aktivitas.":::

1. Berikan data input yang diperlukan dan pilih **Berikutnya**.

   - Pilih pelanggan: Sertakan semua pelanggan atau segmen tertentu.
   - Pilih aktivitas: Pilih jenis aktivitas dan entitas yang mendeskripsikan aktivitas.
   - Preferensi: Atur periode waktu untuk dipertimbangkan, faktor untuk saran, dan petakan atribut.

1. Tinjau input Anda, lalu pilih **Jalankan** untuk menjalankan model dan buat saran.

Tergantung pada jumlah profil pelanggan dan aktivitas yang dipilih, proses ini dapat berlangsung selama beberapa menit.

Setelah membuat saran, Anda dapat memfilternya berdasarkan dimensi atau nilai yang paling Anda minati.

## <a name="manage-suggested-segments"></a>Mengelola segmen yang disarankan

Buka **Segmen** dan pilih tab **Saran (pratinjau**). Di bagian **Saran berbasis aktivitas**, pilih segmen yang disarankan untuk melihat tindakan yang tersedia.

- **Lihat saran** untuk melihat detail segmen tersebut seperti luasnya setiap dimensi dibandingkan dengan grup target. Video ini juga menyorot jumlah calon anggota dalam segmen dan persentase terkait dari total pelanggan.
- **Buat segmen** untuk menyimpan yang disarankan sebagai segmen. Ini ditampilkan pada tab **Semua segmen dan dapat disegarkan**[atau dihapus](segments.md). Anda tidak dapat mengedit rincian segmen. Namun, Anda dapat mengubah kriteria input untuk saran dan membuat saran yang berbeda.
- **Edit saran** untuk mengubah atribut yang dikonfigurasi yang akan menggantikan saran saat ini.
- **Refresh saran** untuk me-refresh saran sambil menyimpan atribut yang dikonfigurasi.

[!INCLUDE [footer-include](includes/footer-banner.md)]
