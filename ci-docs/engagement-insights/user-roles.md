---
title: Peran dan izin
description: Ikhtisar peran dan izin yang tersedia untuk anggota ruang kerja.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e28caf1c14c23acd506da5f7b441f1e3b72e8b
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645541"
---
# <a name="roles-and-permissions"></a>Peran dan izin

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ruang kerja adalah tempat Anda menyimpan dan mengelola aktivitas dan laporan. Untuk informasi lebih lanjut, lihat [Membuat ruang kerja dan menambahkan anggota](create-workspace.md). 

Ruang kerja dapat mencakup peran dan izin berikut:

- Peran *anggota* adalah pengguna yang dapat mengakses ruang kerja. Anda dapat menetapkan anggota ke ruang kerja dan menentukan peran dan izin mereka. 
- Peran *administrator* mengelola ruang kerja dan lingkungan, serta mengkonfigurasikan wawasan keterlibatan untuk pengguna lain. 
- peran *kontributor* ditujukan untuk para analisis yang tidak perlu mengkonfigurasi wawasan keterlibatan tetapi ingin membuat laporan, corong, atau segmen mereka sendiri.

## <a name="permissions"></a>Izin
  
Tabel berikut mengidentifikasi izin untuk setiap peran. 

| Izin | Admin lingkungan | Admin ruang kerja | Kontributor lingkungan | Kontributor ruang kerja | 
|--|--|--|--|--|
| Membuat lingkungan (pembuat secara otomatis menjadi admin lingkungan) | X* | X* | X* | X* |  
| Mengkonfigurasi lingkungan (anggota lingkungan, menghapus lingkungan) | X |  |  |  |  
| buat ruang kerja | X |  |  |  |  
| Mengkonfigurasi ruang kerja (anggota ruang kerja, menghapus ruang kerja) | X | X |  |  |  
| Mengkonfigurasi aktivitas dan aktivitas disempurnakan | X | X | |  |  
| Melihat aktivitas ruang kerja dan aktivitas disempurnakan | X | X | |  |  
| Melihat sumber daya ruang kerja (laporan, segmen, dan metrik)| X | X | X | X |  
| Buat laporan kustom dan corong | X | X | X | X |  
| Membuat metrik dasar dan dimensi| X | X |  |  |  
| Buat segmen| X | X | X | X |  

*Hanya dapat membuat lingkungan uji coba dalam pratinjau. 

## <a name="add-members"></a>Tambah anggota

Anda dapat menambah dan menghapus anggota dari ruang kerja dan lingkungan. Untuk informasi lebih lanjut, lihat [lingkungan dan ruang kerja](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
