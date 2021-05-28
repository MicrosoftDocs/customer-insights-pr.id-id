---
title: Segmen yang disarankan berdasarkan aktivitas.
description: Biarkan Pembelajaran Mesin anda menemukan segmen baru dan menarik berdasarkan aktivitas pelanggan.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034083"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="48eeb-103">Segmen yang disarankan berdasarkan data aktivitas (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="48eeb-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="48eeb-104">Temukan segmen menarik dari pelanggan Anda berdasarkan data aktivitas pelanggan yang diserap ke Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="48eeb-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="48eeb-105">Contoh data aktivitas adalah transaksi, durasi panggilan dukungan, pembelian, atau retur.</span><span class="sxs-lookup"><span data-stu-id="48eeb-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="48eeb-106">Untuk menyarankan segmen, data aktivitas akan analisis untuk potensi, frekuensi, dan nilai moneter (atau durasi).</span><span class="sxs-lookup"><span data-stu-id="48eeb-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="48eeb-107">Atau, Anda dapat membuat [segmen yang disarankan untuk meningkatkan ukuran atau lebih memahami pengaruh atribut](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="48eeb-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Tab segmen yang disarankan yang menampilkan saran segmen untuk segmen berbasis aktivitas dan berbasis atribut.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="48eeb-109">Mengkategorikan pelanggan berdasarkan aktivitas</span><span class="sxs-lookup"><span data-stu-id="48eeb-109">Categorize customers by activity</span></span>

<span data-ttu-id="48eeb-110">Dengan [data aktivitas](activities.md) yang tersedia dalam Customer Insights, kami dapat menghasilkan saran yang mewakili grup pelanggan:</span><span class="sxs-lookup"><span data-stu-id="48eeb-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="48eeb-111">sebagian besar pelanggan aktif</span><span class="sxs-lookup"><span data-stu-id="48eeb-111">most active customers</span></span> 
- <span data-ttu-id="48eeb-112">Pelanggan yang melakukan pembelian terbanyak</span><span class="sxs-lookup"><span data-stu-id="48eeb-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="48eeb-113">Pelanggan yang menghasilkan pendapatan terbanyak</span><span class="sxs-lookup"><span data-stu-id="48eeb-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="48eeb-114">Pelanggan yang belum aktif akhir-akhir ini</span><span class="sxs-lookup"><span data-stu-id="48eeb-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="48eeb-115">Pelanggan yang sering berinteraksi dengan bisnis Anda</span><span class="sxs-lookup"><span data-stu-id="48eeb-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="48eeb-116">Jika Anda memiliki bisnis ritel, Anda dapat mengetahui pelanggan yang menghasilkan pendapatan terbanyak dan memberi mereka hadiah dengan kupon.</span><span class="sxs-lookup"><span data-stu-id="48eeb-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="48eeb-117">Atau Anda dapat mengidentifikasi pelanggan sesekali dan menawarkan kepada mereka untuk bergabung dalam program penghargaan sehingga mereka lebih sering mengunjungi bisnis Anda.</span><span class="sxs-lookup"><span data-stu-id="48eeb-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="48eeb-118">Jika Anda berada dalam bisnis perawatan kesehatan yang menyediakan layanan kesehatan publik dan tujuan Anda adalah mengurangi biaya untuk masing-masing pasien.</span><span class="sxs-lookup"><span data-stu-id="48eeb-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="48eeb-119">Cara untuk melakukannya dapat berupa mengurangi kunjungan berulang dengan memberikan perawatan terbaik dalam kunjungan sesedikit mungkin.</span><span class="sxs-lookup"><span data-stu-id="48eeb-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="48eeb-120">Dalam kasus ini, sasaran Anda adalah menjaga frekuensi kunjungan tetap rendah dan meminimalkan biaya berulang untuk pasien.</span><span class="sxs-lookup"><span data-stu-id="48eeb-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="48eeb-121">Atau Anda dapat mengidentifikasi segmen pasien yang sering melakukan janji temu dan biaya berulang tinggi serta menganalisis kasus ini untuk meningkatkan perawatan individu.</span><span class="sxs-lookup"><span data-stu-id="48eeb-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="48eeb-122">Data yang diperlukan</span><span class="sxs-lookup"><span data-stu-id="48eeb-122">Required data</span></span>

<span data-ttu-id="48eeb-123">Saran dibuat berdasarkan data input yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="48eeb-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="48eeb-124">Profil pelanggan: Semua pelanggan atau anggota dari segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="48eeb-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="48eeb-125">Periode waktu: Bulan lalu, tahun lalu, atau jangka waktu kustom.</span><span class="sxs-lookup"><span data-stu-id="48eeb-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="48eeb-126">Jenis aktivitas: pembelian, transaksi ritel, transaksi online, kasus dukungan pelanggan, langganan, dan sebagainya.</span><span class="sxs-lookup"><span data-stu-id="48eeb-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="48eeb-127">Entitas dalam Customer Insights yang berisi data aktivitas: Entitas UnifiedActivity atau entitas untuk aktivitas tertentu.</span><span class="sxs-lookup"><span data-stu-id="48eeb-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="48eeb-128">Dimensi untuk dimasukkan: Kekinian, frekuensi, atau dimensi moneter, tergantung pada kebutuhan bisnis Anda.</span><span class="sxs-lookup"><span data-stu-id="48eeb-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="48eeb-129">Membuat segmen yang disarankan</span><span class="sxs-lookup"><span data-stu-id="48eeb-129">Generate suggested segments</span></span>

1. <span data-ttu-id="48eeb-130">Buka **Segmen**.</span><span class="sxs-lookup"><span data-stu-id="48eeb-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="48eeb-131">Pilih tab **Saran (pratinjau)**.</span><span class="sxs-lookup"><span data-stu-id="48eeb-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="48eeb-132">Pilih **Cari saran baru**, lalu pilih **Lihat atau antisipasi perilaku pelanggan**.</span><span class="sxs-lookup"><span data-stu-id="48eeb-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="48eeb-133">Pilih **Mulai** untuk menjalankan pengalaman terpandu.</span><span class="sxs-lookup"><span data-stu-id="48eeb-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Langkah pertama wizard konfigurasi untuk segmen yang disarankan berdasarkan aktivitas.":::

1. <span data-ttu-id="48eeb-135">Berikan data input yang diperlukan, lalu pilih **selanjutnya**.</span><span class="sxs-lookup"><span data-stu-id="48eeb-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="48eeb-136">Pilih pelanggan: Sertakan semua pelanggan atau segmen tertentu.</span><span class="sxs-lookup"><span data-stu-id="48eeb-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="48eeb-137">Pilih aktivitas: Pilih jenis aktivitas dan entitas yang mendeskripsikan aktivitas.</span><span class="sxs-lookup"><span data-stu-id="48eeb-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="48eeb-138">Preferensi: Atur periode waktu untuk dipertimbangkan, faktor untuk saran, dan petakan atribut.</span><span class="sxs-lookup"><span data-stu-id="48eeb-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="48eeb-139">Tinjau input Anda, lalu pilih **Jalankan** untuk menjalankan model dan buat saran.</span><span class="sxs-lookup"><span data-stu-id="48eeb-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="48eeb-140">Tergantung pada jumlah profil pelanggan dan aktivitas yang dipilih, proses ini dapat berlangsung selama beberapa menit.</span><span class="sxs-lookup"><span data-stu-id="48eeb-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="48eeb-141">Setelah membuat saran, Anda dapat memfilternya berdasarkan dimensi atau nilai yang paling Anda minati.</span><span class="sxs-lookup"><span data-stu-id="48eeb-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="48eeb-142">Lihat detail segmen yang disarankan</span><span class="sxs-lookup"><span data-stu-id="48eeb-142">View details of a suggested segment</span></span>

<span data-ttu-id="48eeb-143">Setelah saran dibuat, Anda akan menemukannya terdaftar di **Saran** > **Segmen (pratinjau)** di bagian **saran berbasis Aktivitas**.</span><span class="sxs-lookup"><span data-stu-id="48eeb-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Panel sisi yang diperluas yang menampilkan data terperinci dari segmen yang disarankan.":::

<span data-ttu-id="48eeb-145">Pilih **Lihat saran** pada segmen yang disarankan untuk melihat rincian segmen tersebut.</span><span class="sxs-lookup"><span data-stu-id="48eeb-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="48eeb-146">Panel sisi memberikan rincian seperti derajat setiap dimensi dibandingkan dengan grup target.</span><span class="sxs-lookup"><span data-stu-id="48eeb-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="48eeb-147">Video ini juga menyorot jumlah calon anggota dalam segmen dan persentase terkait dari total pelanggan.</span><span class="sxs-lookup"><span data-stu-id="48eeb-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="48eeb-148">Jika Anda ingin menyimpan saran sebagai segmen, pilih **Buat segmen**.</span><span class="sxs-lookup"><span data-stu-id="48eeb-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="48eeb-149">Simpan saran sebagai segmen</span><span class="sxs-lookup"><span data-stu-id="48eeb-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="48eeb-150">Buka **Segmen** > **Saran (pratinjau)**.</span><span class="sxs-lookup"><span data-stu-id="48eeb-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="48eeb-151">Pilih segmen yang ingin disimpan.</span><span class="sxs-lookup"><span data-stu-id="48eeb-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="48eeb-152">Di panel sisi, pilih **Buat segmen**.</span><span class="sxs-lookup"><span data-stu-id="48eeb-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="48eeb-153">Setelah menyimpan segmen, segmen tersebut akan ditampilkan dalam daftar segmen pada tab **Semua segmen**. Segmen tersebut sekarang dapat [di-refresh atau dihapus seperti segmen lain](segments.md).</span><span class="sxs-lookup"><span data-stu-id="48eeb-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="48eeb-154">Anda tidak dapat mengedit rincian segmen.</span><span class="sxs-lookup"><span data-stu-id="48eeb-154">You can't edit the segment details.</span></span> <span data-ttu-id="48eeb-155">Namun, Anda dapat mengubah kriteria input untuk saran dan membuat saran yang berbeda.</span><span class="sxs-lookup"><span data-stu-id="48eeb-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="48eeb-156">Refresh atau edit rangkaian saran</span><span class="sxs-lookup"><span data-stu-id="48eeb-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="48eeb-157">Buka **Segmen** > **Saran (pratinjau)** lalu cari segmen di bagian **saran berbasis Aktivitas**.</span><span class="sxs-lookup"><span data-stu-id="48eeb-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="48eeb-158">Pilih **Refresh saran** untuk me-refresh saran sekaligus menyimpan atribut yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="48eeb-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="48eeb-159">Atau pilih **Edit saran** untuk memodifikasi atribut yang dikonfigurasi.</span><span class="sxs-lookup"><span data-stu-id="48eeb-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="48eeb-160">Sistem akan menjalankan ulang proses, membuat saran segmen berdasarkan data terbaru, dan mengganti saran saat ini.</span><span class="sxs-lookup"><span data-stu-id="48eeb-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
