---
title: Bot Teams untuk Dynamics 365 Customer Insights (pratinjau)
description: Cari profil pelanggan terpadu di Microsoft Teams dengan bantuan bot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195846"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot Teams untuk Dynamics 365 Customer Insights (pratinjau)

Hubungkan dengan Microsoft Teams untuk memungkinkan bot mencari profil pelanggan terpadu dalam saluran Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Bot Teams menampilkan rekaman pelanggan":::

## <a name="prerequisites"></a>Prasyarat

- Setidaknya satu [sumber data ditambahkan](data-sources.md).
- [Proses penyatuan](data-unification.md) selesai.
- Bidang ditambahkan ke [indeks pencarian &filter](search-filter-index.md).
- Customer Insights dan Teams berada dalam organisasi yang sama.
- Lingkungan Anda memiliki audiens target utama yang diatur untuk setiap pelanggan. Akun bisnis tidak didukung.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Mengkonfigurasi bot

1. Buka **Admin** > **Koneksi**.
1. Di ubin Microsoft Teams, pilih **konfigurasi**.
1. Anda akan diarahkan ke **area aplikasi** dalam Teams. Anda juga dapat membuka Teamsdan memilih **aplikasi** di sudut kiri bawah atau [mendapatkannya dari AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) langsung.
1. Cari **Customer Insights** dan pilih aplikasi.
1. Pilih **Tambahkan**.
1. Masuk ke Customer Insights di Teams. Pesan selamat datang ditampilkan.

## <a name="things-you-can-do-with-the-bot"></a>Berbagai hal yang dapat dilakukan dengan bot

Bot memberikan kemampuan pencarian untuk profil pelanggan terpadu.

- Masukkan **pencarian** diikuti dengan nama, alamat email, atau bidang lainnya di profil pelanggan terpadu yang ditambahkan ke indeks pencarian &filter.

  Anda akan mendapatkan kartu yang berisi hingga 15 bidang dari profil pelanggan yang dihasilkan. Beberapa kecocokan menghasilkan daftar hasil di mana Anda dapat memilih profil. Untuk mencari kecocokan yang tepat, tambahkan istilah pencarian dalam tanda kutip ganda.

- Jika organisasi Anda mempertahankan beberapa lingkungan Customer Insights di organisasi yang sama, masukkan **switchinstance** untuk memilih lingkungan tempat Anda ingin menghubungkan bot.

- Masukkan **bantuan** untuk melihat daftar perintah yang tersedia untuk bot.  

[!INCLUDE [footer-include](includes/footer-banner.md)]