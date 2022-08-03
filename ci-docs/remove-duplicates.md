---
title: Menghapus duplikat sebelum menyatukan data
description: Langkah kedua dalam proses penyatuan adalah memilih catatan mana yang akan disimpan ketika duplikat ditemukan.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a838fbdabdb3bfffc6d3835a3f0e97306a43964a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139433"
---
# <a name="remove-duplicates-before-unifying-data"></a>Menghapus duplikat sebelum menyatukan data

Langkah penyatuan ini secara opsional memungkinkan Anda menyiapkan aturan untuk menangani rekaman duplikat dalam entitas. *Deduplikasi* mengidentifikasi rekaman duplikat dan menggabungkannya menjadi satu rekaman. Rekaman sumber ditautkan ke rekaman gabungan dengan ID alternatif. Jika aturan tidak dikonfigurasi, aturan yang ditentukan sistem akan diterapkan.

## <a name="include-enriched-entities-preview"></a>Sertakan entitas yang diperkaya (pratinjau)

Jika Anda memperkaya entitas di tingkat sumber data untuk membantu meningkatkan hasil penyatuan Anda, pilih entitas tersebut. Untuk informasi selengkapnya, lihat [Pengayaan untuk sumber data](data-sources-enrichment.md).

1. Pada halaman **Rekaman** duplikat, pilih **Gunakan entitas** yang diperkaya di bagian atas halaman.

1. **Dari panel Gunakan entitas** yang diperkaya, pilih satu atau beberapa entitas yang diperkaya.

1. Pilih **Selesai**.

## <a name="define-deduplication-rules"></a>Menentukan aturan deduplikasi

1. **Pada halaman Rekaman duplikat**, pilih entitas dan pilih **Tambahkan aturan** untuk menentukan aturan deduplikasi.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Cuplikan layar halaman Catatan duplikat dengan Perlihatkan lebih disorot":::

   1. Di **panel Tambahkan aturan**, masukkan informasi berikut ini:
      - **Pilih bidang**: Pilih dari daftar bidang yang tersedia dari entitas yang ingin Anda periksa duplikatnya. Pilih bidang yang mungkin unik untuk setiap pelanggan. Contohnya, alamat email, atau kombinasi nama, kota, dan nomor telepon.
      - **Normalkan**: Pilih dari pilihan normalisasi berikut untuk atribut yang dipilih.
        - **Angka**: Mengonversi sistem angka lain, seperti angka Romawi, ke angka Arab. *VIII* menjadi *8*.
        - **Simbol**: Menghapus semua simbol dan karakter khusus. *Head&Shoulder* menjadi *HeadShoulder*.
        - **Teks ke huruf kecil: Mengonversi semua karakter menjadi huruf kecil**. *SEMUA KAPITAL dan Huruf Judul* menjadi *semua kapital dan huruf judul*.
        - **Jenis (Telepon, Nama, Alamat, Organisasi)**: Menstandarkan nama, judul, nomor telepon, alamat, dll.
        - **Unicode ke ASCII**: Mengonversi notasi unicode ke karakter ASCII. */u00B2* menjadi *2*.
        - **Spasi** putih: Menghapus semua spasi. *Hello   World* menjadi *Hello World*.
      - **Presisi**: Atur tingkat presisi untuk diterapkan untuk kondisi ini.
        - **Dasar**: Pilih dari *Rendah (30%)*, *Sedang (60%)*, *Tinggi (80%)*, dan *Tepat (100%)*. Pilih **Tepat** untuk hanya mencocokkan rekaman yang cocok dengan 100 persen.
        - **Kustom**: Atur persentase yang harus cocok dengan rekaman. Sistem hanya akan mencocokkan rekaman yang melewati ambang batas ini.
      - **Nama**: Nama untuk aturan.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Cuplikan layar panel Tambahkan aturan untuk menghapus duplikat.":::

   1. Secara opsional, pilih **Tambahkan** > **kondisi** untuk menambahkan lebih banyak kondisi ke aturan. Kondisi terhubung dengan operator AND logis dan dengan demikian hanya dijalankan jika semua kondisi terpenuhi.

   1. Secara opsional, **Tambahkan** > **tambahkan pengecualian** untuk [menambahkan pengecualian ke aturan](match-entities.md#add-exceptions-to-a-rule). Pengecualian digunakan untuk mengatasi kasus positif palsu dan negatif palsu yang jarang terjadi.

   1. Pilih **Selesai** untuk membuat aturan.

1. Atau, [tambahkan aturan lainnya](#define-deduplication-rules).

1. Pilih entitas lalu **Edit preferensi** gabungan.

1. Di **panel Preferensi** gabungan:
   1. Pilih salah satu dari tiga opsi untuk menentukan catatan mana yang akan disimpan jika duplikat ditemukan:
      - **Paling terisi**: mengidentifikasi rekaman dengan bidang atribut yang paling banyak diisi sebagai rekaman pemenang. Ini adalah pilihan penggabungan default.
      - **Terbaru** : mengidentifikasi rekaman pemenang berdasarkan keterkinian. Memerlukan tanggal atau bidang numerik untuk menentukan keterkinian.
      - **Paling lama** : mengidentifikasi rekaman pemenang berdasarkan keterkinian terlama. Memerlukan tanggal atau bidang numerik untuk menentukan keterkinian.
      
      Jika seri, rekor pemenang adalah yang memiliki MAX(PK) atau nilai kunci utama yang lebih besar.
      
   1. Secara opsional, untuk menentukan preferensi gabungan pada atribut individual entitas, pilih **Tingkat Lanjut** di bagian bawah panel. Misalnya, Anda dapat memilih untuk menyimpan email terbaru DAN alamat terlengkap dari catatan yang berbeda. Perluas entitas untuk melihat semua atributnya dan tentukan opsi mana yang akan digunakan untuk atribut individual. Jika Anda memilih opsi berbasis kebaruan, Anda juga perlu menentukan bidang tanggal/waktu yang menentukan kebaruan.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Panel preferensi gabungan tingkat lanjut memperlihatkan email terbaru dan alamat lengkap":::

   1. Pilih **Selesai** untuk menerapkan preferensi gabungan Anda.

1. Setelah menentukan aturan deduplikasi dan menggabungkan preferensi, pilih **Berikutnya**.
  
> [!div class="nextstepaction"]
> [Langkah berikutnya untuk satu entitas: Menyatukan bidang](merge-entities.md)

> [!div class="nextstepaction"]
> [Langkah berikutnya untuk beberapa entitas: Kondisi yang cocok](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Output deduplikasi sebagai entitas

Proses deduplikasi menciptakan entitas deduplikasi baru untuk masing-masing entitas sumber. Entitas ini dapat ditemukan bersama dengan **ConflationMatchPairs:CustomerInsights** di bagian **Sistem** di halaman **Entitas**, dengan nama **Deduplication_DataSource_Entity**.

Entitas output deduplikasi berisi informasi berikut:

- ID/Kunci
  - Bidang Kunci utama dan ID Alternatif. Bidang ID alternatif terdiri dari semua ID alternatif yang diidentifikasi untuk rekaman.
  - Bidang Deduplication_GroupId menunjukkan grup atau kluster yang diidentifikasi dalam entitas yang mengelompokkan semua rekaman serupa berdasarkan bidang deduplikasi yang ditentukan. Ini digunakan untuk tujuan pemrosesan sistem. Jika tidak ada aturan deduplikasi manual yang ditentukan dan aturan deduplikasi yang didefinisikan sistem berlaku, Anda tidak dapat menemukan bidang ini dalam entitas output deduplikasi.
  - Deduplication_WinnerId: Bidang ini berisi ID pemenang dari grup atau kluster yang teridentifikasi. Jika Deduplication_WinnerId sama dengan nilai kunci Utama untuk rekaman, berarti rekaman adalah rekaman pemenang.
- Bidang yang digunakan untuk mendefinisikan aturan deduplikasi.
- Bidang Aturan dan Skor untuk menunjukkan aturan deduplikasi mana yang diterapkan dan skor yang dihasilkan oleh algoritme yang cocok.

[!INCLUDE[footer-include](includes/footer-banner.md)]
