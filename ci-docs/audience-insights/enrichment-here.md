---
title: Pengayaan dengan pengayaan pihak ketiga HERE Technologies
description: Informasi umum tentang pengayaan pihak ketiga HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668682"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Pengayaan profil pelanggan dengan HERE Technologies (pratinjau)

HERE Technologies adalah perusahaan platform lokasi yang menyediakan data dan layanan yang berpusat lokasi. Dengan layanan pengayaan data HERE Technologies, Anda dapat membangun pemahaman lokasi yang lebih tepat tentang pelanggan Anda dengan normalisasi alamat, ekstraksi garis lintang dan bujur, dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasikan pengayaan HERE Technologies, persyaratan berikut harus dipenuhi:

- Anda memiliki langganan aktif HERE Technologies. Untuk mendapatkan langganan, Anda dapat [mendaftar di sini](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) atau [hubungi langsung HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Selengkapnya tentang pengayaan lokasi HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Anda memiliki kunci API HERE Technologies.

- Anda memiliki izin [administratif](permissions.md#administrator).

## <a name="configuration"></a>Konfigurasi

1. Buka **Data** > **Pengayaan**.

1. Pilih **Perkaya data saya** di petak HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![petak HERE Technologies](media/HERE-tile.png "petak HERE Technologies")

1. Masukkan **kunci API aktif HERE Technologies**. Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**. 

1. Konfirmasikan kedua input dengan memilih **Sambungkan ke HERE**.

1. Pilih **Tambah data** dan pilih jika Anda ingin memetakan bidang ke alamat utama dan/atau sekunder. Anda dapat menentukan pemetaan bidang untuk kedua alamat (misalnya, alamat rumah dan bisnis) dan memperkaya profil untuk kedua alamat secara terpisah. Pilih **Selanjutnya**.

1. Tentukan bidang dari profil terpadu mana yang harus digunakan untuk mencari data lokasi yang cocok dari HERE Technologies. Bidang **jalan 1** dan **Kode Zip/Pos** diperlukan untuk alamat utama dan/atau sekunder yang dipilih. Untuk akurasi kecocokan yang lebih tinggi, lebih banyak bidang dapat ditambahkan.

   > [!div class="mx-imgBorder"]
   > ![Halaman konfigurasi pengayaan HERE Technologies](media/enrichment-HERE-configuration.png "Halaman konfigurasi pengayaan HERE Technologies")

1. Pilih **Terapkan** untuk menyelesaikan pemetaan bidang.

## <a name="enrichment-results"></a>Hasil pengayaan

Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah. Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab). Waktu pemrosesan akan tergantung pada ukuran data pelanggan dan waktu respons API dari HERE Technologies.

Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan baru yang diperkaya di dalam **pengayaan saya**. Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.

Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.

## <a name="next-steps"></a>Langkah berikutnya

Bangun di atas data pelanggan yang diperkaya. Buat [segmen](segments.md), [tindakan](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan bagi pelanggan Anda.

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke HERE Technologies, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa HERE Technologies memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.
