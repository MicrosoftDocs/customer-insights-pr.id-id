---
title: Pengaturan keamanan di Dynamics 365 Customer Insights
description: Pelajari tentang pengaturan keamanan di Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653785"
---
# <a name="security-overview-page"></a>Halaman gambaran umum keamanan

Halaman **Keamanan** mencantumkan opsi untuk mengonfigurasi izin dan fitur pengguna yang membantu membuat Dynamics 365 Customer Insights lebih aman. Hanya administrator yang dapat mengakses halaman ini. 

**Buka AdminSecurity** > **untuk** mengonfigurasi pengaturan.

Halaman **Keamanan** menyertakan tab berikut:
- [Pengguna](#users-tab)
- [API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Tab Pengguna

Akses ke Customer Insights dibatasi untuk pengguna di organisasi Anda yang ditambahkan ke aplikasi oleh admin. Tab **Pengguna** memungkinkan Anda mengelola akses pengguna dan izinnya. Untuk informasi selengkapnya, lihat [Izin pengguna](permissions.md).

## <a name="apis-tab"></a>Tab API

Melihat dan mengelola kunci untuk menggunakan [API Wawasan Pelanggan](apis.md) dengan data lingkungan Anda.

Anda dapat membuat kunci primer dan sekunder baru dengan **memilih Regenerasi primer** atau **Regenerasi sekunder**. 

Untuk memblokir akses API ke lingkungan, pilih **Nonaktifkan**. Jika API dinonaktifkan, Anda dapat memilih **Aktifkan** untuk memberikan akses lagi.

## <a name="key-vault-tab"></a>Tab Brankas Kunci

Tab **Key Vault** memungkinkan Anda menautkan dan mengelola brankas [kunci Azure Anda sendiri](/azure/key-vault/general/basic-concepts) ke lingkungan.
Key Vault khusus dapat digunakan untuk melakukan tahapan dan menggunakan rahasia di batas kepatuhan organisasi. Customer Insights dapat menggunakan rahasia di Azure Key Vault untuk [menyiapkan koneksi](connections.md) ke sistem pihak ketiga.

Untuk informasi lebih lanjut, lihat [bawa Azure key vault Anda sendiri](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
