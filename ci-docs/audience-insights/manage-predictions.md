---
title: Tugas bersama untuk skenario prediksi
description: Pelajari cara mengelola, memecahkan masalah, dan menyempurnakan prediksi.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315882"
---
# <a name="manage-predictions"></a><span data-ttu-id="d5895-103">Kelola prediksi</span><span class="sxs-lookup"><span data-stu-id="d5895-103">Manage predictions</span></span>

<span data-ttu-id="d5895-104">Artikel ini membahas beberapa tugas yang dibagikan sebagian besar skenario prediksi.</span><span class="sxs-lookup"><span data-stu-id="d5895-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="d5895-105">Memecahkan masalah prediksi gagal</span><span class="sxs-lookup"><span data-stu-id="d5895-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="d5895-106">Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.</span><span class="sxs-lookup"><span data-stu-id="d5895-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d5895-107">Pilih elipsis vertikal di sebelah prediksi yang ingin anda lihat log kesalahannya.</span><span class="sxs-lookup"><span data-stu-id="d5895-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="d5895-108">Pilih **Log**.</span><span class="sxs-lookup"><span data-stu-id="d5895-108">Select **Logs**.</span></span>

1. <span data-ttu-id="d5895-109">Memeriksa semua kesalahan.</span><span class="sxs-lookup"><span data-stu-id="d5895-109">Review all the errors.</span></span> <span data-ttu-id="d5895-110">Ada beberapa jenis kesalahan yang dapat terjadi, dan menjelaskan kondisi yang menyebabkan kesalahan.</span><span class="sxs-lookup"><span data-stu-id="d5895-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="d5895-111">Misalnya, kesalahan bahwa tidak ada cukup data yang dapat diprediksi secara akurat biasanya ditangani dengan memuat data tambahan ke dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d5895-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="d5895-112">Laporan penggunaan data input</span><span class="sxs-lookup"><span data-stu-id="d5895-112">Input data usability report</span></span>

<span data-ttu-id="d5895-113">Laporan kegunaan data input memberikan tampilan konsolidasi tentang kesalahan dan peringatan yang mungkin dihasilkan oleh prediksi standar Anda.</span><span class="sxs-lookup"><span data-stu-id="d5895-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="d5895-114">Ini juga memberikan rekomendasi bagaimana meningkatkan kinerja model.</span><span class="sxs-lookup"><span data-stu-id="d5895-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="d5895-115">Laporan tersedia setelah model menyelesaikan proses pelatihannya.</span><span class="sxs-lookup"><span data-stu-id="d5895-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="d5895-116">Ini dibuat untuk setiap model secara terpisah, terlepas dari apakah itu berhasil diselesaikan atau tidak.</span><span class="sxs-lookup"><span data-stu-id="d5895-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="d5895-117">Lihat Laporan penggunaan data input</span><span class="sxs-lookup"><span data-stu-id="d5895-117">View the input data usability report</span></span>

<span data-ttu-id="d5895-118">Setelah model standar menyelesaikan langkah pelatihannya, lihat laporan:</span><span class="sxs-lookup"><span data-stu-id="d5895-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="d5895-119">Pilih elipsis di samping nama model dan pilih **Laporan kegunaan data input**.</span><span class="sxs-lookup"><span data-stu-id="d5895-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="d5895-120">Pilih status model pilih Lihat **Lihat Laporan kegunaan data input** di panel samping.</span><span class="sxs-lookup"><span data-stu-id="d5895-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="d5895-121">Memilih salah satu model dalam daftar dan pilih **laporan kegunaan data input** di bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="d5895-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="d5895-122">Buka halaman hasil model dan pilih **laporan kegunaan data input** di bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="d5895-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="d5895-123">Informasi di laporan penggunaan data input</span><span class="sxs-lookup"><span data-stu-id="d5895-123">Information in the input data usability report</span></span>

<span data-ttu-id="d5895-124">Kolom berikut dalam laporan berisi informasi bermanfaat untuk meningkatkan data untuk model.</span><span class="sxs-lookup"><span data-stu-id="d5895-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Contoh laporan kegunaan data input yang memperlihatkan tabel dengan kesalahan, peringatan, dan rekomendasi.":::

- <span data-ttu-id="d5895-126">Nama: Nama deskriptif dari kesalahan, peringatan, atau rekomendasi.</span><span class="sxs-lookup"><span data-stu-id="d5895-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="d5895-127">Langkah: Fase model, latih atau skor, informasi mengacu pada.</span><span class="sxs-lookup"><span data-stu-id="d5895-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="d5895-128">Status: Tingkat keparahan informasi (kesalahan, peringatan, rekomendasi).</span><span class="sxs-lookup"><span data-stu-id="d5895-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="d5895-129">Nama kolom: Kolom dalam entitas yang perlu dimodifikasi untuk meningkatkan kinerja model.</span><span class="sxs-lookup"><span data-stu-id="d5895-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="d5895-130">Nama entitas: Nama entitas yang perlu dimodifikasi untuk meningkatkan kinerja model.</span><span class="sxs-lookup"><span data-stu-id="d5895-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="d5895-131">Detail: Detail tentang kesalahan, peringatan, atau rekomendasi.</span><span class="sxs-lookup"><span data-stu-id="d5895-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="d5895-132">Segarkan prediksi</span><span class="sxs-lookup"><span data-stu-id="d5895-132">Refresh a prediction</span></span>

<span data-ttu-id="d5895-133">Prediksi akan secara otomatis diperbarui pada jadwal yang sama [dengan penyegaran data Anda](system.md#schedule-tab) seperti dikonfigurasi dalam pengaturan.</span><span class="sxs-lookup"><span data-stu-id="d5895-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="d5895-134">Anda juga dapat me-refresh secara manual.</span><span class="sxs-lookup"><span data-stu-id="d5895-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="d5895-135">Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.</span><span class="sxs-lookup"><span data-stu-id="d5895-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d5895-136">Pilih elipsis vertikal di sebelah prediksi yang ingin Anda segarkan.</span><span class="sxs-lookup"><span data-stu-id="d5895-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="d5895-137">Pilih **Segarkan**.</span><span class="sxs-lookup"><span data-stu-id="d5895-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="d5895-138">Hapus prediksi</span><span class="sxs-lookup"><span data-stu-id="d5895-138">Delete a prediction</span></span>

<span data-ttu-id="d5895-139">Menghapus prediksi juga akan menghapus entitas keluarannya.</span><span class="sxs-lookup"><span data-stu-id="d5895-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="d5895-140">Buka **intelijen** > **prediksi** dan pilih tab **prediksi saya**.</span><span class="sxs-lookup"><span data-stu-id="d5895-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="d5895-141">Pilih elipsis vertikal di sebelah prediksi yang ingin Anda hapus.</span><span class="sxs-lookup"><span data-stu-id="d5895-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="d5895-142">Pilih **Hapus**.</span><span class="sxs-lookup"><span data-stu-id="d5895-142">Select **Delete**.</span></span>
