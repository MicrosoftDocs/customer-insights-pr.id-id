---
title: Add-in Kartu Pelanggan untuk aplikasi Dynamics 365
description: Tampilkan data wawasan audiens di aplikasi Dynamics 365 dengan add-in ini.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059592"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="ec819-103">Add-in Kartu Pelanggan (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="ec819-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ec819-104">Dapatkan tampilan 360 derajat pelanggan Anda secara langsung di aplikasi Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ec819-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="ec819-105">Dengan Add-in Kartu Pelanggan yang terinstal di aplikasi Dynamics 365 yang didukung, Anda dapat memilih untuk menampilkan demografi, wawasan, dan timeline aktivitas.</span><span class="sxs-lookup"><span data-stu-id="ec819-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="ec819-106">Add-in akan mengambil data dari Customer Insights tanpa mempengaruhi data dalam aplikasi Dynamics 365 yang tersambung.</span><span class="sxs-lookup"><span data-stu-id="ec819-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ec819-107">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="ec819-107">Prerequisites</span></span>

- <span data-ttu-id="ec819-108">Add-in hanya berfungsi dengan aplikasi yang diarahkan model Dynamics 365, seperti Sales, atau Customer Service, versi 9.0 dan versi yang lebih baru.</span><span class="sxs-lookup"><span data-stu-id="ec819-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="ec819-109">Agar data Dynamics 365 Anda dapat memetakan ke profil pelanggan wawasan audiens, mereka perlu [diserap dari aplikasi Dynamics 365 menggunakan konektor Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ec819-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="ec819-110">Semua pengguna Add-in Kartu Pelanggan Dynamics 365 harus [ditambahkan sebagai pengguna](permissions.md) dalam wawasan audiens untuk melihat data.</span><span class="sxs-lookup"><span data-stu-id="ec819-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="ec819-111">[Kemampuan pencarian dan filter yang dikonfigurasi](search-filter-index.md) di audiens wawasan diperlukan agar pencarian data dapat bekerja.</span><span class="sxs-lookup"><span data-stu-id="ec819-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="ec819-112">Setiap kontrol add-in mengandalkan data tertentu dalam wawasan audiens:</span><span class="sxs-lookup"><span data-stu-id="ec819-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="ec819-113">Kontrol pengukuran: memerlukan [tindakan yang dikonfigurasi](measures.md).</span><span class="sxs-lookup"><span data-stu-id="ec819-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="ec819-114">Kontrol inteligensi: Memerlukan data yang dihasilkan menggunakan [prediksi](predictions.md) atau [model kustom](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="ec819-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="ec819-115">Kontrol demografis: bidang demografis, (seperti usia atau jenis kelamin) tersedia di profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="ec819-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="ec819-116">Kontrol pengayaan: memerlukan [pengayaan](enrichment-hub.md) aktif yang diterapkan ke profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="ec819-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="ec819-117">Kontrol Timeline: memerlukan [aktivitas yang dikonfigurasi](activities.md).</span><span class="sxs-lookup"><span data-stu-id="ec819-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="ec819-118">Instal Add-in Kartu Pelanggan</span><span class="sxs-lookup"><span data-stu-id="ec819-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="ec819-119">Add-in kartu pelanggan adalah solusi untuk aplikasi Customer Engagement di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ec819-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="ec819-120">Untuk menginstal solusi, buka AppSource dan Cari **kartu pelanggan Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="ec819-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="ec819-121">Pilih [Add-in kartu pelanggan di AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) dan pilih **Dapatkan sekarang**.</span><span class="sxs-lookup"><span data-stu-id="ec819-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="ec819-122">Anda mungkin harus masuk dengan kredensial admin Anda agar aplikasi Dynamics 365 menginstal solusi.</span><span class="sxs-lookup"><span data-stu-id="ec819-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="ec819-123">Bisa diperlukan beberapa waktu agar solusi dapat diinstal ke lingkungan Anda.</span><span class="sxs-lookup"><span data-stu-id="ec819-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="ec819-124">Mengkonfigurasi Add-in kartu pelanggan</span><span class="sxs-lookup"><span data-stu-id="ec819-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="ec819-125">Sebagai admin, buka bagian **pengaturan** dalam Dynamics 365, lalu pilih **solusi**.</span><span class="sxs-lookup"><span data-stu-id="ec819-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="ec819-126">Pilih tautan **nama tampilan** untuk solusi **Add-in Kartu Pelanggan Dynamics 365 Customer Insights (Pratinjau)**.</span><span class="sxs-lookup"><span data-stu-id="ec819-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ec819-127">![pilih Nama tampilan](media/select-display-name.png "pilih Nama tampilan")</span><span class="sxs-lookup"><span data-stu-id="ec819-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="ec819-128">Pilih **Masuk** dan masukkan kredensial untuk akun admin yang Anda gunakan untuk mengkonfigurasi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ec819-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ec819-129">Periksa apakah Pemblokir pop-up browser tidak memblokir jendela autentikasi saat Anda memilih tombol **Masuk**.</span><span class="sxs-lookup"><span data-stu-id="ec819-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="ec819-130">pilih lingkungan Customer Insights yang ingin Anda ambil datanya.</span><span class="sxs-lookup"><span data-stu-id="ec819-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="ec819-131">Tentukan pemetaan bidang untuk rekaman di aplikasi Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ec819-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="ec819-132">Tergantung pada data dalam Customer Insights, Anda dapat memilih untuk memetakan pilihan berikut:</span><span class="sxs-lookup"><span data-stu-id="ec819-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="ec819-133">Untuk memetakan dengan kontak, pilih bidang di entitas Pelanggan yang sesuai dengan ID entitas kontak Anda.</span><span class="sxs-lookup"><span data-stu-id="ec819-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="ec819-134">Untuk memetakan dengan akun, pilih bidang di entitas Pelanggan yang sesuai dengan ID entitas akun Anda.</span><span class="sxs-lookup"><span data-stu-id="ec819-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ec819-135">![Bidang id kontak](media/contact-id-field.png "Bidang id kontak")</span><span class="sxs-lookup"><span data-stu-id="ec819-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="ec819-136">Pilih **Simpan konfigurasi** untuk menyimpan pengaturan.</span><span class="sxs-lookup"><span data-stu-id="ec819-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="ec819-137">Selanjutnya, Anda harus menetapkan peran keamanan di Dynamics 365 agar pengguna dapat menyesuaikan dan melihat kartu pelanggan.</span><span class="sxs-lookup"><span data-stu-id="ec819-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="ec819-138">Di Dynamics 365, pergi ke **pengaturan** > **keamanan** > **pengguna**.</span><span class="sxs-lookup"><span data-stu-id="ec819-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="ec819-139">Pilih pengguna untuk mengedit peran pengguna dan pilih **Kelola peran**.</span><span class="sxs-lookup"><span data-stu-id="ec819-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="ec819-140">Tetapkan **peran Penyesuai kartu Customer Insights** kepada pengguna yang akan menyesuaikan konten untuk ditampilkan pada kartu untuk seluruh organisasi.</span><span class="sxs-lookup"><span data-stu-id="ec819-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="ec819-141">Tambahkan kontrol Kartu Pelanggan ke formulir</span><span class="sxs-lookup"><span data-stu-id="ec819-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="ec819-142">Untuk menambahkan kontrol kartu pelanggan ke formulir kontak, buka **pengaturan** > **penyesuaian** di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ec819-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="ec819-143">Pilih **Sesuaikan sistem**.</span><span class="sxs-lookup"><span data-stu-id="ec819-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="ec819-144">Telusuri entitas **kontak**, perluas lalu pilih **formulir**.</span><span class="sxs-lookup"><span data-stu-id="ec819-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="ec819-145">Pilih formulir kontak yang ingin ditambahkan kontrol kartu pelanggan.</span><span class="sxs-lookup"><span data-stu-id="ec819-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ec819-146">![Pilih formulir kontak](media/contact-active-forms.png "Pilih formulir kontak")</span><span class="sxs-lookup"><span data-stu-id="ec819-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="ec819-147">Untuk menambahkan kontrol, di editor formulir, tarik bidang apa pun dari **penjelajah bidang** ke tempat Anda ingin kontrol ditampilkan.</span><span class="sxs-lookup"><span data-stu-id="ec819-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="ec819-148">Pilih bidang di formulir yang baru saja ditambahkan, lalu pilih **Ubah properti**.</span><span class="sxs-lookup"><span data-stu-id="ec819-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="ec819-149">Buka tab **Kontrol** dan pilih **Tambahkan kontrol**.</span><span class="sxs-lookup"><span data-stu-id="ec819-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="ec819-150">Pilih salah satu kontrol kustom yang tersedia dan pilih **Tambah**.</span><span class="sxs-lookup"><span data-stu-id="ec819-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="ec819-151">Di dialog **properti bidang**, kosongkan kotak centang **label tampilan di formulir**.</span><span class="sxs-lookup"><span data-stu-id="ec819-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="ec819-152">Pilih opsi **web** untuk kontrol.</span><span class="sxs-lookup"><span data-stu-id="ec819-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="ec819-153">Untuk kontrol pengayaan, pilih jenis pengayaan yang akan ditampilkan dengan mengonfigurasi bidang **enrichmenttype**.</span><span class="sxs-lookup"><span data-stu-id="ec819-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="ec819-154">Tambahkan kontrol pengayaan terpisah untuk setiap jenis pengayaan.</span><span class="sxs-lookup"><span data-stu-id="ec819-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="ec819-155">Pilih **Simpan** dan **publikasikan** untuk mempublikasikan formulir kontak yang diperbarui.</span><span class="sxs-lookup"><span data-stu-id="ec819-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="ec819-156">Buka formulir kontak yang dipublikasikan.</span><span class="sxs-lookup"><span data-stu-id="ec819-156">Go to the published contact form.</span></span> <span data-ttu-id="ec819-157">Anda akan melihat kontrol yang baru ditambahkan.</span><span class="sxs-lookup"><span data-stu-id="ec819-157">You'll see the newly added control.</span></span> <span data-ttu-id="ec819-158">Anda mungkin harus masuk saat pertama kali menggunakannya.</span><span class="sxs-lookup"><span data-stu-id="ec819-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="ec819-159">Untuk menyesuaikan yang ingin Anda Tampilkan pada kontrol kustom, pilih tombol Edit di sudut kanan atas.</span><span class="sxs-lookup"><span data-stu-id="ec819-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="ec819-160">Tingkatkan Add-in Kartu Pelanggan</span><span class="sxs-lookup"><span data-stu-id="ec819-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="ec819-161">Add-in Kartu Pelanggan tidak ditingkatkan secara otomatis.</span><span class="sxs-lookup"><span data-stu-id="ec819-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="ec819-162">Untuk meningkatkan ke versi terbaru, ikuti prosedur ini dalam aplikasi Dynamics 365 yang telah terinstal Add-in.</span><span class="sxs-lookup"><span data-stu-id="ec819-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="ec819-163">Dalam aplikasi Dynamics 365, buka **Pengaturan** > **Penyesuaian** dan pilih **Solusi**.</span><span class="sxs-lookup"><span data-stu-id="ec819-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="ec819-164">Pada tabel add-in, cari **CustomerInsightsCustomerCard** dan pilih baris.</span><span class="sxs-lookup"><span data-stu-id="ec819-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="ec819-165">Pilih **Terapkan Peningkatan Solusi** pada bilah tindakan.</span><span class="sxs-lookup"><span data-stu-id="ec819-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Tingkatkan solusi di area Penyesuaian aplikasi Dynamics 365":::

1. <span data-ttu-id="ec819-167">Setelah memulai proses peningkatan, Anda akan melihat indikator pemuatan hingga peningkatan selesai.</span><span class="sxs-lookup"><span data-stu-id="ec819-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="ec819-168">Jika tidak ada versi yang lebih baru, peningkatan akan menampilkan pesan kesalahan.</span><span class="sxs-lookup"><span data-stu-id="ec819-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
