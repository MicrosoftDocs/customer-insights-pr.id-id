---
title: Pengaturan keamanan di Customer Insights
description: Pelajari tentang pengaturan keamanan di Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947419"
---
# <a name="security-settings-in-customer-insights"></a>Pengaturan keamanan di Customer Insights

Halaman **Keamanan** mencantumkan opsi untuk mengonfigurasi izin dan fitur pengguna yang membantu membuat Dynamics 365 Customer Insights lebih aman. Hanya administrator yang dapat mengakses halaman ini.

Buka **Keamanan** > **Admin** untuk mengonfigurasi pengaturan.

Halaman **Keamanan** mencakup tab berikut:

- [Pengguna](#users-tab)
- [API](#apis-tab)
- [Tautan Privat](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Akses data pelanggan dengan aman dengan Customer Lockbox (Pratinjau)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Tab Pengguna

Akses ke Customer Insights dibatasi untuk pengguna di organisasi Anda yang ditambahkan ke aplikasi oleh admin. Tab **Pengguna** memungkinkan Anda mengelola akses pengguna dan izin mereka. Untuk informasi selengkapnya, lihat [Izin pengguna](permissions.md).

## <a name="apis-tab"></a>Tab API

Lihat dan kelola kunci untuk menggunakan [API](apis.md) Customer Insights dengan data lingkungan Anda.

Anda dapat membuat kunci primer dan sekunder baru dengan **memilih Regenerasi primer** atau **Regenerasi sekunder**. 

Untuk memblokir akses API ke lingkungan, pilih **Nonaktifkan**. Jika API dinonaktifkan, Anda dapat memilih **Aktifkan** untuk memberikan akses lagi.

## <a name="private-links-tab"></a>Tab Tautan Pribadi

[Azure Private Link](/azure/private-link/private-link-overview) memungkinkan Customer Insights terhubung ke akun Anda Azure Data Lake Storage melalui titik akhir privat di jaringan virtual Anda. Untuk data di akun penyimpanan, yang tidak diekspos ke internet publik, Private Link memungkinkan koneksi ke jaringan yang dibatasi tersebut.

> [!IMPORTANT]
> Persyaratan peran minimum untuk menyiapkan koneksi Private Link:
>
> - Wawasan Pelanggan: Administrator
> - Peran bawaan Azure: [Akun Penyimpanan kontributor](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Izin untuk peran Azure kustom: [Microsoft.Storage/storageAccounts/read dan Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Menyiapkan Private Link di Customer Insights adalah proses dua langkah. Pertama, Anda memulai pembuatan Tautan Pribadi dari **Tautan** > **Pribadi Keamanan** > **Admin** di Customer Insights. Panel **Tambahkan Azure Private Link** mencantumkan akun penyimpanan dari penyewa Anda yang anda miliki izinnya untuk melihatnya. Pilih akun penyimpanan dan berikan persetujuan untuk membuat Private Link.

Selanjutnya, Anda perlu menyetujui Tautan Privat di sisi akun Data Lake Storage. Buka tautan yang disajikan di layar untuk menyetujui Tautan Privat baru.

## <a name="key-vault-tab"></a>Tab Key Vault

Tab **Key Vault** memungkinkan Anda menautkan dan mengelola brankas [kunci Azure Anda sendiri](/azure/key-vault/general/basic-concepts) ke lingkungan.
Key Vault khusus dapat digunakan untuk melakukan tahapan dan menggunakan rahasia di batas kepatuhan organisasi. Customer Insights dapat menggunakan rahasia di Azure Key Vault untuk [menyiapkan koneksi](connections.md) ke sistem pihak ketiga.

Untuk informasi lebih lanjut, lihat [bawa Azure key vault Anda sendiri](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Akses data pelanggan dengan aman dengan Customer Lockbox (Pratinjau)

Customer Insights menggunakan Power Platform kemampuan Customer Lockbox. Customer Lockbox menyediakan antarmuka untuk meninjau dan menyetujui (atau menolak) permintaan akses data. Permintaan ini terjadi ketika akses data ke data pelanggan diperlukan untuk menyelesaikan kasus dukungan. Untuk menggunakan fitur ini, Customer Insights harus memiliki koneksi yang sudah ada ke Microsoft Dataverse lingkungan di penyewa Anda.

Untuk informasi selengkapnya tentang Customer Lockbox, lihat [ringkasan](/power-platform/admin/about-lockbox#summary)Power Platform Customer Lockbox. Artikel ini juga menjelaskan [alur kerja](/power-platform/admin/about-lockbox#workflow) dan pengaturan [yang diperlukan](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) untuk mengaktifkan Customer Lockbox.

> [!IMPORTANT]
> Administrator global untuk Power Platform atau Power Platform administrator dapat menyetujui permintaan Customer Lockbox yang dikeluarkan untuk Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
