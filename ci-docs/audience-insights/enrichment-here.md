---
title: Pengayaan dengan pengayaan pihak ketiga HERE Technologies
description: Informasi umum tentang pengayaan pihak ketiga HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896055"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Pengayaan profil pelanggan dengan HERE Technologies (pratinjau)

HERE Technologies adalah perusahaan platform lokasi yang menyediakan data dan layanan yang berpusat lokasi. Dengan layanan pengayaan data HERE Technologies, Anda dapat membangun pemahaman lokasi yang lebih tepat tentang pelanggan Anda dengan normalisasi alamat, ekstraksi garis lintang dan bujur, dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasikan pengayaan HERE Technologies, persyaratan berikut harus dipenuhi:

- Anda memiliki langganan aktif HERE Technologies. Untuk mendapatkan langganan, Anda dapat [mendaftar di sini](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) atau [hubungi langsung HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Selengkapnya tentang pengayaan lokasi HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Ada [koneksi](connections.md) HERE yang tersedia *atau* Anda memiliki izin [administrator](permissions.md#administrator) dan kunci API HERE Technologies.

## <a name="configure-the-enrichment"></a>Konfigurasi pengayaan

1. Buka **Data** > **Pengayaan**. 

1. Pilih **Perkaya data** saya di petak HERE Technologies dan pilih **Mulai**.

   > [!div class="mx-imgBorder"]
   > ![petak HERE Technologies](media/HERE-tile.png "petak HERE Technologies")

1. Pilih [koneksi](connections.md) dari menu tarik-turun. Hubungi administrator jika tidak ada koneksi yang tersedia. Jika Anda adalah administrator, Anda bisa membuat koneksi dengan memilih **Tambahkan koneksi**. Pilih **HERE Technologies** dari menu tarik-turun. 

1. Pilih **Sambungkan ke HERE Technologies** untuk mengonfirmasi pilihan.

1.  Pilih **Berikutnya** dan pilih **himpunan data Pelanggan** yang ingin Anda perkaya dengan data lokasi dari HERE Technologies. Anda dapat memilih entitas **Pelanggan** untuk memperkaya semua profil pelanggan atau memilih entitas segmen untuk memperkaya hanya profil pelanggan yang terdapat dalam segmen tersebut.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Tangkapan layar saat memilih himpunan data pelanggan.":::

1. Pilih jika Anda ingin memetakan bidang ke alamat utama dan/atau sekunder. Anda dapat menentukan pemetaan bidang untuk kedua alamat dan memperkaya profil untuk kedua alamat secara terpisah. Misalnya, jika ada alamat rumah dan bisnis. Pilih **Selanjutnya**.

1. Tentukan bidang dari profil terpadu mana yang harus digunakan untuk mencari data lokasi yang cocok dari HERE Technologies. Bidang **jalan 1** dan **Kode Zip/Pos** diperlukan untuk alamat utama dan/atau sekunder yang dipilih. Untuk akurasi kecocokan yang lebih tinggi, lebih banyak bidang dapat ditambahkan.

   > [!div class="mx-imgBorder"]
   > ![Halaman konfigurasi pengayaan HERE Technologies](media/enrichment-HERE-configuration.png "Halaman konfigurasi pengayaan HERE Technologies")

1. Untuk menyelesaikan pemetaan bidang, pilih **berikutnya**.

1. Berikan nama untuk pengayaan. 

1. Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.

## <a name="configure-the-connection-for-here-technologies"></a>Mengonfigurasi koneksi untuk HERE technologies 

Anda perlu menjadi administrator untuk mengonfigurasi koneksi. Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan *atau* masuk ke **Admin** > **Koneksi** dan pilih **Konfigurasi** pada petak HERE technologies.

1. Masukkan nama untuk koneksi dalam kotak **nama tampilan**.

1. Berikan kunci API HERE Technologies yang valid.

1. Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**

1. Pilih **Verifikasi** untuk memvalidasi konfigurasi.

1. Setelah menyelesaikan verifikasi, pilih **Simpan**.

> [!div class="mx-imgBorder"]
   > ![Halaman konfigurasi koneksi HERE technologies](media/enrichment-HERE-connection.png "Halaman konfigurasi koneksi HERE technologies")

## <a name="enrichment-results"></a>Hasil pengayaan

Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah. Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab). Waktu pemrosesan akan tergantung pada ukuran data pelanggan dan waktu respons API dari HERE Technologies.

Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan baru yang diperkaya di dalam **pengayaan saya**. Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.

Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.

## <a name="next-steps"></a>Langkah berikutnya

Bangun di atas data pelanggan yang diperkaya. Buat [segmen](segments.md), [tindakan](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan bagi pelanggan Anda.

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke HERE Technologies, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa HERE Technologies memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]