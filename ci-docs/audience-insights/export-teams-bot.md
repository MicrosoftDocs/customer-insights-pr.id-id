---
title: Bot untuk Microsoft Teams
description: Cari profil pelanggan terpadu di Microsoft Teams dengan bantuan bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267956"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="37888-103">Bot Teams untuk Dynamics 365 Customer Insights (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="37888-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="37888-104">Hubungkan dengan Microsoft Teams untuk memungkinkan bot mencari profil pelanggan terpadu dalam saluran Teams.</span><span class="sxs-lookup"><span data-stu-id="37888-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="37888-105">![Bot Teams menampilkan rekaman pelanggan](media/teams-bot.png "Bot Teams menampilkan rekaman pelanggan")</span><span class="sxs-lookup"><span data-stu-id="37888-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="37888-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="37888-106">Prerequisites</span></span>

<span data-ttu-id="37888-107">Untuk mengkonfigurasi dan mengkonfigurasi bot, prasyarat berikut harus dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="37888-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="37888-108">Setidaknya ada satu [sumber data ditambahkan](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="37888-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="37888-109">[Proses penyatuan](data-unification.md) selesai.</span><span class="sxs-lookup"><span data-stu-id="37888-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="37888-110">Bidang ditambahkan ke [indeks pencarian dan filter](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="37888-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="37888-111">Customer Insights dan Teams berada dalam organisasi yang sama.</span><span class="sxs-lookup"><span data-stu-id="37888-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="37888-112">Mengkonfigurasi bot</span><span class="sxs-lookup"><span data-stu-id="37888-112">Configure the bot</span></span>

1. <span data-ttu-id="37888-113">Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="37888-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="37888-114">Di ubin Microsoft Teams, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="37888-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="37888-115">Anda akan diarahkan ke **area aplikasi** dalam Teams.</span><span class="sxs-lookup"><span data-stu-id="37888-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="37888-116">Anda juga dapat membuka Teamsdan memilih **aplikasi** di sudut kiri bawah atau [mendapatkannya dari AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) langsung.</span><span class="sxs-lookup"><span data-stu-id="37888-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="37888-117">Cari **Customer Insights** dan pilih aplikasi.</span><span class="sxs-lookup"><span data-stu-id="37888-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="37888-118">Pilih **Tambahkan**.</span><span class="sxs-lookup"><span data-stu-id="37888-118">Select **Add**.</span></span>
1. <span data-ttu-id="37888-119">Setelah masuk ke Customer Insights dalam Teams, Anda akan melihat pesan pembuka, dan dapat memulai.</span><span class="sxs-lookup"><span data-stu-id="37888-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="37888-120">Berbagai hal yang dapat dilakukan dengan bot</span><span class="sxs-lookup"><span data-stu-id="37888-120">Things you can do with the bot</span></span>

<span data-ttu-id="37888-121">Bot memberikan kemampuan pencarian untuk profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="37888-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="37888-122">Masukkan **pencarian** diikuti nama, alamat email, atau bidang lain pada profil pelanggan terpadu yang ditambahkan ke indeks pencarian dan filter.</span><span class="sxs-lookup"><span data-stu-id="37888-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="37888-123">Anda akan mendapatkan kartu yang berisi hingga 15 bidang dari profil pelanggan yang dihasilkan.</span><span class="sxs-lookup"><span data-stu-id="37888-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="37888-124">Beberapa kecocokan menghasilkan daftar hasil di mana Anda dapat memilih profil.</span><span class="sxs-lookup"><span data-stu-id="37888-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="37888-125">Anda dapat menambahkan istilah pencarian dalam tanda kutip ganda untuk mencari pencocokan yang sama persis.</span><span class="sxs-lookup"><span data-stu-id="37888-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="37888-126">Jika organisasi Anda mengelola beberapa lingkungan Customer Insights di organisasi yang sama, Anda dapat memasukkan **switchinstance** untuk memilih lingkungan yang akan dihubungkan dengan bot.</span><span class="sxs-lookup"><span data-stu-id="37888-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="37888-127">Masukkan **bantuan** untuk melihat daftar perintah yang tersedia untuk bot.</span><span class="sxs-lookup"><span data-stu-id="37888-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]