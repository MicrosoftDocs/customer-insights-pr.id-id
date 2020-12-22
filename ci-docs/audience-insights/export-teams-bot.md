---
title: Bot untuk Microsoft Teams
description: Cari profil pelanggan terpadu di Microsoft Teams dengan bantuan bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 45ea23fbefe5f1d44c3961183b76d2cc5c45355e
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406068"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="e010f-103">Bot Teams untuk Dynamics 365 Customer Insights (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="e010f-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="e010f-104">Hubungkan dengan Microsoft Teams untuk memungkinkan bot mencari profil pelanggan terpadu dalam saluran Teams.</span><span class="sxs-lookup"><span data-stu-id="e010f-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e010f-105">![Bot Teams menampilkan rekaman pelanggan](media/teams-bot.png "Bot Teams menampilkan rekaman pelanggan")</span><span class="sxs-lookup"><span data-stu-id="e010f-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e010f-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="e010f-106">Prerequisites</span></span>

<span data-ttu-id="e010f-107">Untuk mengkonfigurasi dan mengkonfigurasi bot, prasyarat berikut harus dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="e010f-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e010f-108">Setidaknya ada satu [sumber data ditambahkan](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="e010f-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="e010f-109">[Proses penyatuan](data-unification.md) selesai.</span><span class="sxs-lookup"><span data-stu-id="e010f-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="e010f-110">Bidang ditambahkan ke [indeks pencarian dan filter](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="e010f-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="e010f-111">Customer Insights dan Teams berada dalam organisasi yang sama.</span><span class="sxs-lookup"><span data-stu-id="e010f-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="e010f-112">Mengkonfigurasi bot</span><span class="sxs-lookup"><span data-stu-id="e010f-112">Configure the bot</span></span>

1. <span data-ttu-id="e010f-113">Di wawasan audiens, buka **Admin** > **Tujuan ekspor**.</span><span class="sxs-lookup"><span data-stu-id="e010f-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="e010f-114">Di ubin Microsoft Teams, pilih **konfigurasi**.</span><span class="sxs-lookup"><span data-stu-id="e010f-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="e010f-115">Anda akan diarahkan ke **area aplikasi** dalam Teams.</span><span class="sxs-lookup"><span data-stu-id="e010f-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="e010f-116">Anda juga dapat membuka Teamsdan memilih **aplikasi** di sudut kiri bawah atau [mendapatkannya dari AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) langsung.</span><span class="sxs-lookup"><span data-stu-id="e010f-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="e010f-117">Cari **Customer Insights** dan pilih aplikasi.</span><span class="sxs-lookup"><span data-stu-id="e010f-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="e010f-118">Pilih **Tambahkan**.</span><span class="sxs-lookup"><span data-stu-id="e010f-118">Select **Add**.</span></span>
1. <span data-ttu-id="e010f-119">Setelah masuk ke Customer Insights dalam Teams, Anda akan melihat pesan pembuka, dan dapat memulai.</span><span class="sxs-lookup"><span data-stu-id="e010f-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="e010f-120">Berbagai hal yang dapat dilakukan dengan bot</span><span class="sxs-lookup"><span data-stu-id="e010f-120">Things you can do with the bot</span></span>

<span data-ttu-id="e010f-121">Bot memberikan kemampuan pencarian untuk profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="e010f-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="e010f-122">Masukkan **pencarian** diikuti nama, alamat email, atau bidang lain pada profil pelanggan terpadu yang ditambahkan ke indeks pencarian dan filter.</span><span class="sxs-lookup"><span data-stu-id="e010f-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="e010f-123">Anda akan mendapatkan kartu yang berisi hingga 15 bidang dari profil pelanggan yang dihasilkan.</span><span class="sxs-lookup"><span data-stu-id="e010f-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="e010f-124">Beberapa kecocokan menghasilkan daftar hasil di mana Anda dapat memilih profil.</span><span class="sxs-lookup"><span data-stu-id="e010f-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="e010f-125">Anda dapat menambahkan istilah pencarian dalam tanda kutip ganda untuk mencari pencocokan yang sama persis.</span><span class="sxs-lookup"><span data-stu-id="e010f-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="e010f-126">Jika organisasi Anda mengelola beberapa lingkungan Customer Insights di organisasi yang sama, Anda dapat memasukkan **switchinstance** untuk memilih lingkungan yang akan dihubungkan dengan bot.</span><span class="sxs-lookup"><span data-stu-id="e010f-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="e010f-127">Masukkan **bantuan** untuk melihat daftar perintah yang tersedia untuk bot.</span><span class="sxs-lookup"><span data-stu-id="e010f-127">Enter **help** to see a list of available commands for the bot.</span></span>  
