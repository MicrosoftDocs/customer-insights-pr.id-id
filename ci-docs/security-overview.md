---
title: Mengonfigurasi pengaturan keamanan
description: Pelajari tentang pengaturan keamanan di Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387253"
---
# <a name="configure-security-settings"></a>Mengonfigurasi pengaturan keamanan

Kelola kunci API, akses data pelanggan, dan siapkan Azure Private Link.

## <a name="manage-api-keys"></a>Mengelola kunci API

Lihat dan kelola kunci untuk menggunakan [API](apis.md) Customer Insights dengan data di lingkungan Anda.

1. Buka **Keamanan** > **Admin** dan pilih tab **API**.

1. Jika akses API ke lingkungan belum disiapkan, pilih **Aktifkan**. Atau, untuk memblokir akses API ke lingkungan, pilih **Nonaktifkan** dan konfirmasi.

1. Mengelola kunci API primer dan sekunder:

   1. Untuk memperlihatkan kunci API primer atau sekunder, pilih **simbol Perlihatkan**.

   1. Untuk menyalin kunci API utama atau sekunder, pilih **simbol Salin**.

   1. Untuk membuat kunci API primer atau sekunder baru, pilih **Meregenerasi kunci primer** atau **Meregenerasi sekunder**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Akses data pelanggan dengan aman dengan Customer Lockbox (Pratinjau)

Customer Insights menggunakan Power Platform kemampuan Customer Lockbox. Customer Lockbox menyediakan antarmuka untuk meninjau dan menyetujui (atau menolak) permintaan akses data. Permintaan ini terjadi ketika akses data ke data pelanggan diperlukan untuk menyelesaikan kasus dukungan. Untuk menggunakan fitur ini, Customer Insights harus memiliki koneksi yang sudah ada ke Microsoft Dataverse lingkungan di penyewa Anda.

Untuk informasi selengkapnya tentang Customer Lockbox, lihat [ringkasan](/power-platform/admin/about-lockbox#summary)Power Platform Customer Lockbox. Artikel ini juga menjelaskan [alur kerja](/power-platform/admin/about-lockbox#workflow) dan pengaturan [yang diperlukan](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) untuk mengaktifkan Customer Lockbox.

> [!IMPORTANT]
> Administrator global untuk Power Platform atau Power Platform administrator dapat menyetujui permintaan Customer Lockbox yang dikeluarkan untuk Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Menyiapkan Azure Private Link

[Azure Private Link](/azure/private-link/private-link-overview) memungkinkan Customer Insights terhubung ke akun Anda Azure Data Lake Storage melalui titik akhir privat di jaringan virtual Anda. Untuk data di akun penyimpanan, yang tidak diekspos ke internet publik, Private Link memungkinkan koneksi ke jaringan yang dibatasi tersebut.

> [!IMPORTANT]
> Persyaratan peran minimum untuk menyiapkan koneksi Private Link:
>
> - Wawasan Pelanggan: Administrator
> - Peran bawaan Azure: [Akun Penyimpanan kontributor](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Izin untuk peran Azure kustom: [Microsoft.Storage/storageAccounts/read dan Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Di Customer Insights, buka **Keamanan** > **Admin** dan pilih tab **Tautan** Privat.

1. Pilih **Tambahkan Tautan** Privat.

   Panel **Tambahkan Azure Private Link** mencantumkan akun penyimpanan dari penyewa Anda yang anda miliki izinnya untuk melihatnya.

1. Pilih akun langganan, grup sumber daya, dan penyimpanan.

1. [Tinjau privasi dan kepatuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya setuju**.

1. Pilih **Simpan**.

1. Buka akun Data Lake Storage Anda dan buka tautan yang disajikan di layar.

1. Setujui Tautan Pribadi.


[!INCLUDE [footer-include](includes/footer-banner.md)]
