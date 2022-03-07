---
title: Segmen yang disarankan berdasarkan aktivitas.
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
ms.openlocfilehash: 9c10a32b770ea110a1166f20f72116a3a12cb92e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354467"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Segmen yang disarankan berdasarkan data aktivitas (pratinjau)

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
Jika Anda berada dalam bisnis perawatan kesehatan yang menyediakan layanan kesehatan publik dan tujuan Anda adalah mengurangi biaya untuk masing-masing pasien. Cara untuk melakukannya dapat berupa mengurangi kunjungan berulang dengan memberikan perawatan terbaik dalam kunjungan sesedikit mungkin. Dalam kasus ini, sasaran Anda adalah menjaga frekuensi kunjungan tetap rendah dan meminimalkan biaya berulang untuk pasien. Atau Anda dapat mengidentifikasi segmen pasien yang sering melakukan janji temu dan biaya berulang tinggi serta menganalisis kasus ini untuk meningkatkan perawatan individu. 

## <a name="required-data"></a>Data yang diperlukan

Saran dibuat berdasarkan data input yang dipilih. 

- Profil pelanggan: Semua pelanggan atau anggota dari segmen tertentu. 

- Periode waktu: Bulan lalu, tahun lalu, atau jangka waktu kustom.

- Jenis aktivitas: pembelian, transaksi ritel, transaksi online, kasus dukungan pelanggan, langganan, dan sebagainya.  

- Entitas dalam Customer Insights yang berisi data aktivitas: Entitas UnifiedActivity atau entitas untuk aktivitas tertentu. 

- Dimensi untuk dimasukkan: Kekinian, frekuensi, atau dimensi moneter, tergantung pada kebutuhan bisnis Anda.

## <a name="generate-suggested-segments"></a>Membuat segmen yang disarankan

1. Buka **Segmen**.

1. Pilih tab **Saran (pratinjau)**.

1. Pilih **Cari saran baru**, lalu pilih **Lihat atau antisipasi perilaku pelanggan**. Pilih **Mulai** untuk menjalankan pengalaman terpandu.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Langkah pertama wizard konfigurasi untuk segmen yang disarankan berdasarkan aktivitas.":::

1. Berikan data input yang diperlukan, lalu pilih **selanjutnya**.

   - Pilih pelanggan: Sertakan semua pelanggan atau segmen tertentu.
   - Pilih aktivitas: Pilih jenis aktivitas dan entitas yang mendeskripsikan aktivitas.
   - Preferensi: Atur periode waktu untuk dipertimbangkan, faktor untuk saran, dan petakan atribut.

1. Tinjau input Anda, lalu pilih **Jalankan** untuk menjalankan model dan buat saran.

1. Tergantung pada jumlah profil pelanggan dan aktivitas yang dipilih, proses ini dapat berlangsung selama beberapa menit. 

Setelah membuat saran, Anda dapat memfilternya berdasarkan dimensi atau nilai yang paling Anda minati. 

## <a name="view-details-of-a-suggested-segment"></a>Lihat detail segmen yang disarankan

Setelah saran dibuat, Anda akan menemukannya terdaftar di **Saran** > **Segmen (pratinjau)** di bagian **saran berbasis Aktivitas**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Panel sisi yang diperluas yang menampilkan data terperinci dari segmen yang disarankan.":::

Pilih **Lihat saran** pada segmen yang disarankan untuk melihat rincian segmen tersebut. Panel sisi memberikan rincian seperti derajat setiap dimensi dibandingkan dengan grup target. Video ini juga menyorot jumlah calon anggota dalam segmen dan persentase terkait dari total pelanggan. Jika Anda ingin menyimpan saran sebagai segmen, pilih **Buat segmen**.    

## <a name="save-a-suggestion-as-a-segment"></a>Simpan saran sebagai segmen

1. Buka **Segmen** > **Saran (pratinjau)**.

1. Pilih segmen yang ingin disimpan. 

1. Di panel sisi, pilih **Buat segmen**. 

1. Setelah menyimpan segmen, segmen tersebut akan ditampilkan dalam daftar segmen pada tab **Semua segmen**. Segmen tersebut sekarang dapat [di-refresh atau dihapus seperti segmen lain](segments.md). Anda tidak dapat mengedit rincian segmen. Namun, Anda dapat mengubah kriteria input untuk saran dan membuat saran yang berbeda.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Refresh atau edit rangkaian saran

1. Buka **Segmen** > **Saran (pratinjau)** lalu cari segmen di bagian **saran berbasis Aktivitas**.

1. Pilih **Refresh saran** untuk me-refresh saran sekaligus menyimpan atribut yang dikonfigurasi. Atau pilih **Edit saran** untuk memodifikasi atribut yang dikonfigurasi. Sistem akan menjalankan ulang proses, membuat saran segmen berdasarkan data terbaru, dan mengganti saran saat ini.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
