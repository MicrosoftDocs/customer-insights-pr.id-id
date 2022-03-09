---
title: Bot untuk Microsoft Teams
description: Cari profil pelanggan terpadu di Microsoft Teams dengan bantuan bot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d6b016c1ec35e26ce6449333234edfd218bc9354
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232106"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Teams untuk Dynamics 365 Customer Insights (pratinjau)

Hubungkan dengan Microsoft Teams untuk memungkinkan bot mencari profil pelanggan terpadu dalam saluran Teams.

> [!div class="mx-imgBorder"]
> ![Bot Teams menampilkan rekaman pelanggan.](media/teams-bot.png "Bot Teams menampilkan rekaman pelanggan")

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi dan mengkonfigurasi bot, prasyarat berikut harus dipenuhi:

- Setidaknya ada satu [sumber data ditambahkan](data-sources.md).
- [Proses penyatuan](data-unification.md) selesai.
- Bidang ditambahkan ke [indeks pencarian dan filter](search-filter-index.md).
- Customer Insights dan Teams berada dalam organisasi yang sama.
- Lingkungan Anda memiliki audiens target utama yang diatur untuk setiap pelanggan. Akun bisnis tidak didukung.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]
## <a name="configure-the-bot"></a>Mengkonfigurasi bot

1. Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.
1. Di ubin Microsoft Teams, pilih **konfigurasi**.
1. Anda akan diarahkan ke **area aplikasi** dalam Teams. Anda juga dapat membuka Teamsdan memilih **aplikasi** di sudut kiri bawah atau [mendapatkannya dari AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) langsung.
1. Cari **Customer Insights** dan pilih aplikasi.
1. Pilih **Tambahkan**.
1. Setelah masuk ke Customer Insights dalam Teams, Anda akan melihat pesan pembuka, dan dapat memulai.

## <a name="things-you-can-do-with-the-bot"></a>Berbagai hal yang dapat dilakukan dengan bot

Bot memberikan kemampuan pencarian untuk profil pelanggan terpadu.

- Masukkan **pencarian** diikuti nama, alamat email, atau bidang lain pada profil pelanggan terpadu yang ditambahkan ke indeks pencarian dan filter.

  Anda akan mendapatkan kartu yang berisi hingga 15 bidang dari profil pelanggan yang dihasilkan. Beberapa kecocokan menghasilkan daftar hasil di mana Anda dapat memilih profil. Anda dapat menambahkan istilah pencarian dalam tanda kutip ganda untuk mencari pencocokan yang sama persis.

- Jika organisasi Anda mengelola beberapa lingkungan Customer Insights di organisasi yang sama, Anda dapat memasukkan **switchinstance** untuk memilih lingkungan yang akan dihubungkan dengan bot.

- Masukkan **bantuan** untuk melihat daftar perintah yang tersedia untuk bot.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]