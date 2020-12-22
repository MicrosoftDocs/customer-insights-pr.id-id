---
title: Pengayaan dengan Experian pengayaan pihak ketiga
description: Informasi umum tentang pengayaan pihak ketiga Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668816"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Memperkaya profil pelanggan dengan demografi dari Experian (pratinjau)

Experian adalah pemimpin global dalam pelaporan kredit konsumen dan bisnis serta layanan pemasaran. Dengan layanan pengayaan data Experian, Anda dapat membangun pemahaman yang lebih mendalam tentang pelanggan Anda dengan memperkaya profil pelanggan Anda dengan data demografis seperti ukuran rumah tangga, pendapatan, dan lainnya.

## <a name="prerequisites"></a>Prasyarat

Untuk mengonfigurasikan Experian, prasyarat berikut harus dipenuhi:

- Anda memiliki langganan Experian aktif. Untuk mendapatkan langganan, [Hubungi Experian](https://www.experian.com/marketing-services/contact) secara langsung. [Pelajari selengkapnya tentang pengayaan data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Anda memiliki ID pengguna, ID pihak, dan nomor model untuk akun transpor aman (ST) yang diaktifkan SSH yang dibuat Experian untuk Anda.
- Anda memiliki izin [Administrator](permissions.md#administrator) di wawasan audiens.

## <a name="configuration"></a>Konfigurasi

1. Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.

1. Pilih **Perkaya data saya** di petak Experian.

   > [!div class="mx-imgBorder"]
   > ![petak Experian](media/experian-tile.png "petak Experian")

1. Pilih **persiapan** dan masukkan ID pengguna, id pihak, dan nomor model untuk akun transportasi aman Experian Anda. Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**. Konfirmasikan semua input dengan memilih **Terapkan**.

## <a name="map-your-fields"></a>Petakan bidang Anda

1. Pilih **Tambah data** dan pilih pengidentifikasi kunci Anda dari **nama dan alamat**, **email**, atau **telepon** untuk dikirim ke Experian untuk resolusi identitas.

   > [!TIP]
   > Atribut pengidentifikasi kunci lainnya yang dikirim ke Experian kemungkinan menghasilkan tingkat kecocokan yang lebih tinggi.

1. Pilih **berikutnya** dan Petakan atribut terkait dari entitas pelanggan terpadu Anda untuk bidang pengidentifikasi kunci yang dipilih.

1. Pilih **Tambah atribut** untuk memetakan atribut tambahan yang ingin Anda kirim ke Experian.

1.  Pilih **Simpan** untuk menyelesaikan pemetaan bidang.

   > [!div class="mx-imgBorder"]
   > ![Pemetaan bidang Experian](media/experian-field-mapping.png "Pemetaan bidang Experian")

## <a name="enrichment-results"></a>Hasil pengayaan

Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah. Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab). Waktu pemrosesan akan tergantung pada ukuran data pelanggan Anda dan proses pengayaan diatur untuk akun Anda oleh Experian.

Setelah proses pengayaan selesai, Anda dapat meninjau data profil pelanggan baru yang diperkaya di dalam **pengayaan saya**. Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.

Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.

## <a name="next-steps"></a>Langkah berikutnya

Bangun di atas data pelanggan yang diperkaya. Buat [segmen](segments.md), [tindakan](measures.md), dan bahkan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan bagi pelanggan Anda.

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Experian, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Experian memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus pengayaan ini kapan saja untuk menghentikan penggunaan fungsi ini.
