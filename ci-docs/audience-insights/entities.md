---
title: Entitas dan himpunan data
description: Lihat data pada halaman entitas.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269380"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="6b014-103">Entitas dalam wawasan audiens</span><span class="sxs-lookup"><span data-stu-id="6b014-103">Entities in audience insights</span></span>

<span data-ttu-id="6b014-104">Setelah [mengkonfigurasi sumber data](data-sources.md), buka halaman **entitas** untuk mengevaluasi kualitas data yang terserap.</span><span class="sxs-lookup"><span data-stu-id="6b014-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="6b014-105">Entitas dianggap sebagai himpunan data.</span><span class="sxs-lookup"><span data-stu-id="6b014-105">Entities are considered datasets.</span></span> <span data-ttu-id="6b014-106">Beberapa kemampuan Dynamics 365 Customer Insights dibangun di sekitar entitas ini.</span><span class="sxs-lookup"><span data-stu-id="6b014-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="6b014-107">Meninjau mereka secara dekat dapat membantu Anda memvalidasi output dari kemampuan tersebut.</span><span class="sxs-lookup"><span data-stu-id="6b014-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="6b014-108">Halaman **entitas** mencantumkan entitas dan mencakup beberapa kolom:</span><span class="sxs-lookup"><span data-stu-id="6b014-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="6b014-109">**Nama**: nama entitas data Anda.</span><span class="sxs-lookup"><span data-stu-id="6b014-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="6b014-110">Jika Anda melihat simbol peringatan di samping nama entitas, berarti bahwa data untuk entitas tersebut tidak berhasil dimuat.</span><span class="sxs-lookup"><span data-stu-id="6b014-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="6b014-111">**Sumber**: jenis sumber data yang menyerap entitas</span><span class="sxs-lookup"><span data-stu-id="6b014-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="6b014-112">**Dibuat oleh**: Nama orang yang membuat entitas</span><span class="sxs-lookup"><span data-stu-id="6b014-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="6b014-113">**Dibuat**: tanggal dan waktu pembuatan entitas</span><span class="sxs-lookup"><span data-stu-id="6b014-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="6b014-114">**Diperbarui oleh**: Nama orang yang memperbarui entitas</span><span class="sxs-lookup"><span data-stu-id="6b014-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="6b014-115">**Terakhir Diperbarui**: tanggal dan waktu pembaruan terakhir entitas</span><span class="sxs-lookup"><span data-stu-id="6b014-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="6b014-116">**Refresh terakhir**: tanggal dan waktu penyegaran data terakhir</span><span class="sxs-lookup"><span data-stu-id="6b014-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="6b014-117">Menjelajahi data entitas tertentu</span><span class="sxs-lookup"><span data-stu-id="6b014-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="6b014-118">Pilih entitas untuk menjelajahi bidang dan rekaman yang berbeda yang tercakup dalam entitas tersebut.</span><span class="sxs-lookup"><span data-stu-id="6b014-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6b014-119">![Pilih entitas](media/data-manager-entities-data.png "Pilih entitas")</span><span class="sxs-lookup"><span data-stu-id="6b014-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="6b014-120">Tab **data** dipilih secara default dan menampilkan rincian daftar tabel tentang rekaman individual entitas.</span><span class="sxs-lookup"><span data-stu-id="6b014-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6b014-121">![Tabel bidang](media/data-manager-entities-fields.PNG "Tabel bidang")</span><span class="sxs-lookup"><span data-stu-id="6b014-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="6b014-122">Tab **Bidang** menampilkan tabel untuk meninjau rincian untuk entitas yang dipilih, seperti nama bidang, jenis data, dan jenis.</span><span class="sxs-lookup"><span data-stu-id="6b014-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="6b014-123">Kolom **jenis** menunjukkan jenis terkait Common Data Model, yang baik yang diidentifikasi secara otomatis oleh sistem, atau yang [dipetakan secara manual](map-entities.md) oleh pengguna.</span><span class="sxs-lookup"><span data-stu-id="6b014-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="6b014-124">Jenis semantik ini dapat berbeda dari jenis data atribut misalnya, bidang *email* di bawah ini memiliki jenis data *teks* namun jenis Common Data Model (semantik)-nya mungkin *email* atau *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="6b014-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="6b014-125">Kedua tabel hanya menampilkan sampel data entitas.</span><span class="sxs-lookup"><span data-stu-id="6b014-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="6b014-126">Untuk melihat himpunan data lengkap, buka halaman **sumber data**, pilih entitas, pilih **Edit**, lalu lihat data entitas ini dengan editor Power Query seperti dijelaskan dalam [sumber data](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="6b014-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="6b014-127">Untuk mempelajari lebih lanjut tentang data yang terserap di entitas, kolom **ringkasan** memberi Anda beberapa karakteristik penting data, seperti null, nilai yang tidak ada, nilai unik, jumlah, dan distribusi, sebagaimana berlaku untuk data Anda.</span><span class="sxs-lookup"><span data-stu-id="6b014-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="6b014-128">Pilih ikon diagram untuk melihat ringkasan data.</span><span class="sxs-lookup"><span data-stu-id="6b014-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6b014-129">![Simbol ringkasan](media/data-manager-entities-summary.png "Tabel Ringkasan Data")</span><span class="sxs-lookup"><span data-stu-id="6b014-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="6b014-130">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="6b014-130">Next step</span></span>

<span data-ttu-id="6b014-131">Lihat topik [Satukan](data-unification.md) untuk mempelajari cara *memetakan*, *mencocokkan*, dan *menggabungkan* data yang terserap.</span><span class="sxs-lookup"><span data-stu-id="6b014-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]