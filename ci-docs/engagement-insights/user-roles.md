---
title: Peran dan izin
description: Ikhtisar peran dan izin yang tersedia untuk anggota ruang kerja.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036697"
---
# <a name="roles-and-permissions"></a>Peran dan izin

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ruang kerja adalah cara Anda menyimpan dan mengelola aktivitas dan laporan. Anggota adalah pengguna yang dapat mengakses ruang kerja. Anda dapat menetapkan anggota ke ruang kerja dan menentukan peran dan izin mereka. Peran administrator mengelola ruang kerja dan lingkungan, serta mengkonfigurasikan wawasan keterlibatan untuk pengguna lain. Peran kontributor ditujukan untuk para analis yang tidak perlu mengkonfigurasi wawasan keterlibatan tetapi ingin membuat laporan, corong, atau segmen mereka sendiri.

## <a name="permissions"></a>Izin
  
Diagram berikut mengidentifikasi izin untuk setiap peran. 

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
