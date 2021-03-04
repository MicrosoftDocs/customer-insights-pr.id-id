---
title: Konektor LiveRamp
description: Pelajari cara mengekspor data ke LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270162"
---
# <a name="liverampreg-connector-preview"></a>Konektor LiveRamp&reg; (pratinjau)

Aktifkan data Anda di LiveRamp untuk terhubung dengan lebih dari 500 platform lintas ekosistem digital, sosial, dan TV. Bekerja dengan data Anda di LiveRamp untuk menargetkan, menekan, dan mempersonalisasi kampanye iklan.

## <a name="prerequisites"></a>Prasyarat

- Anda memerlukan langganan LiveRamp untuk menggunakan konektor ini.
- Untuk mendapatkan langganan, [hubungi langsung LiveRamp](https://liveramp.com/contact/). [Pelajari lebih lanjut tentang LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Hubungkan ke LiveRamp

1. Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.

1. Di petak **LiveRamp** pilih **Konfigurasi**.

1. Beri nama yang dikenali di bidang **nama tampilan** tujuan anda.

1. Berikan **nama pengguna** dan **sandi** untuk akun LiveRamp Secure FTP (SFTP) Anda.
Kredensial ini mungkin berbeda dengan kredensial LiveRamp Onboarding Anda.

1. Pilih **Verifikasikan** untuk menguji sambungan ke LiveRamp.

1. Setelah verifikasi berhasil, berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**.

1. Pilih **berikutnya** untuk mengkonfigurasi konektor liveramp.

## <a name="configure-the-connector"></a>Konfigurasikan konektor

1. Di bidang **Pilih pengidentifikasi kunci Anda**, pilih **email**,  **nama dan alamat**, atau **telepon** untuk dikirim ke LiveRamp untuk resolusi identitas.

1. Petakan atribut yang terkait dari entitas pelanggan terpadu Anda untuk pengidentifikasi kunci yang dipilih.

1. Pilih **Tambah atribut** untuk memetakan atribut tambahan untuk dikirim ke LiveRamp.

   > [!TIP]
   > Mengirimkan lebih banyak atribut pengidentifikasi kunci ke LiveRamp kemungkinan akan memberi Anda tingkat kecocokan yang lebih tinggi.

1. Pilih segmen yang ingin Anda ekspor ke LiveRamp.

1. Pilih **Simpan**.

> [!div class="mx-imgBorder"]
> ![Konektor LiveRamp dengan pemetaan atribut](media/export-liveramp-segments.png "Konektor LiveRamp dengan pemetaan atribut")

## <a name="export-the-data"></a>Mengekspor data

Ekspor akan segera dimulai jika semua prasyarat untuk ekspor telah diselesaikan. Ekspor juga akan berjalan dengan setiap [refresh terjadwal](system.md#schedule-tab).
Setelah ekspor berhasil diselesaikan, Anda dapat masuk ke LiveRamp Onboarding untuk mengaktifkan dan mendistribusikan data.

## <a name="data-privacy-and-compliance"></a>Privasi dan kepatuhan data

Bila Anda mengaktifkan Dynamics 365 Customer Insights untuk mengirimkan data ke Liveramp, Anda mengizinkan transfer data di luar batas kepatuhan untuk Dynamics 365 Customer Insights, termasuk data yang mungkin sensitif seperti data pribadi. Microsoft akan mentransfer data tersebut sesuai petunjuk Anda, namun Anda bertanggung jawab untuk memastikan bahwa Liveramp memenuhi setiap privasi atau kewajiban keamanan yang mungkin Anda miliki. Untuk informasi lebih lanjut, lihat [Pernyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Administrator Dynamics 365 Customer Insights Anda dapat menghapus destinasi ekspor ini kapan saja untuk menghentikan penggunaan fungsi ini.

[!INCLUDE[footer-include](../includes/footer-banner.md)]