---
title: Instal dan konfigurasikan Add -in kartu pelanggan
description: Instal dan konfigurasikan Add -in kartu pelanggan untuk Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644047"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="d6f66-103">Add-in Kartu Pelanggan (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="d6f66-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d6f66-104">Dapatkan tampilan 360 derajat pelanggan Anda secara langsung di aplikasi Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d6f66-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="d6f66-105">Melihat batas waktu demografi, wawasan, dan aktivitas dengan Add-in kartu pelanggan.</span><span class="sxs-lookup"><span data-stu-id="d6f66-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d6f66-106">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="d6f66-106">Prerequisites</span></span>

- <span data-ttu-id="d6f66-107">Aplikasi Dynamics 365 (misalnya pusat penjualan atau pusat Customer Service), versi 9.0 dan yang lebih baru dengan Antarmuka Terpadu diaktifkan.</span><span class="sxs-lookup"><span data-stu-id="d6f66-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="d6f66-108">Profil pelanggan [yang terserap dari aplikasi Dynamics 365 menggunakan Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="d6f66-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="d6f66-109">Pengguna Add-in kartu pelanggan harus [ditambahkan sebagai pengguna](permissions.md) di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="d6f66-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="d6f66-110">[Kemampuan pencarian dan filter yang dikonfigurasi](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="d6f66-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="d6f66-111">Kontrol demografis: bidang demografis, seperti usia atau jenis kelamin tersedia di profil pelanggan terpadu.</span><span class="sxs-lookup"><span data-stu-id="d6f66-111">Demographic control: Demographic fields, such as age or gender are available in the unified customer profile.</span></span>
- <span data-ttu-id="d6f66-112">Kontrol pengayaan: memerlukan [pengayaan](enrichment-hub.md) aktif yang diterapkan ke profil pelanggan.</span><span class="sxs-lookup"><span data-stu-id="d6f66-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="d6f66-113">Kontrol kecerdasan: Memerlukan data yang dibuat menggunakan Pembelajaran Mesin Azure ([Prediksi](predictions.md) atau [Model Kustom](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="d6f66-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="d6f66-114">Kontrol pengukuran: memerlukan [tindakan yang dikonfigurasi](measures.md).</span><span class="sxs-lookup"><span data-stu-id="d6f66-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="d6f66-115">Kontrol Timeline: memerlukan [aktivitas yang dikonfigurasi](activities.md).</span><span class="sxs-lookup"><span data-stu-id="d6f66-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="d6f66-116">Instal Add-in Kartu Pelanggan</span><span class="sxs-lookup"><span data-stu-id="d6f66-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="d6f66-117">Add-in kartu pelanggan adalah solusi untuk aplikasi Customer Engagement di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d6f66-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="d6f66-118">Untuk menginstal solusi, buka AppSource dan Cari **kartu pelanggan Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="d6f66-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="d6f66-119">Pilih [Add-in kartu pelanggan di AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) dan pilih **Dapatkan sekarang**.</span><span class="sxs-lookup"><span data-stu-id="d6f66-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="d6f66-120">Anda mungkin harus masuk dengan kredensial admin Anda agar aplikasi Dynamics 365 menginstal solusi.</span><span class="sxs-lookup"><span data-stu-id="d6f66-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="d6f66-121">Bisa diperlukan beberapa waktu agar solusi dapat diinstal ke lingkungan Anda.</span><span class="sxs-lookup"><span data-stu-id="d6f66-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="d6f66-122">Mengkonfigurasi Add-in kartu pelanggan</span><span class="sxs-lookup"><span data-stu-id="d6f66-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="d6f66-123">Sebagai admin, buka bagian **pengaturan** dalam Dynamics 365, lalu pilih **solusi**.</span><span class="sxs-lookup"><span data-stu-id="d6f66-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="d6f66-124">Pilih tautan **nama tampilan** untuk solusi **Add-in Kartu Pelanggan Dynamics 365 Customer Insights (Pratinjau)**.</span><span class="sxs-lookup"><span data-stu-id="d6f66-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d6f66-125">![pilih Nama tampilan](media/select-display-name.png "pilih Nama tampilan")</span><span class="sxs-lookup"><span data-stu-id="d6f66-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="d6f66-126">Pilih **Masuk** dan masukkan kredensial untuk akun admin yang Anda gunakan untuk mengkonfigurasi Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d6f66-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d6f66-127">Periksa apakah Pemblokir pop-up browser tidak memblokir jendela autentikasi saat Anda memilih tombol **Masuk**.</span><span class="sxs-lookup"><span data-stu-id="d6f66-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="d6f66-128">pilih lingkungan yang ingin Anda ambil datanya.</span><span class="sxs-lookup"><span data-stu-id="d6f66-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="d6f66-129">Tentukan pemetaan bidang ke rekaman di aplikasi Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d6f66-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="d6f66-130">Untuk memetakan dengan kontak, pilih bidang di entitas Pelanggan yang sesuai dengan ID entitas kontak Anda.</span><span class="sxs-lookup"><span data-stu-id="d6f66-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="d6f66-131">Untuk memetakan dengan akun, pilih bidang di entitas Pelanggan yang sesuai dengan ID entitas akun Anda.</span><span class="sxs-lookup"><span data-stu-id="d6f66-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d6f66-132">![Bidang id kontak](media/contact-id-field.png "Bidang id kontak")</span><span class="sxs-lookup"><span data-stu-id="d6f66-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="d6f66-133">Pilih **Simpan konfigurasi** untuk menyimpan pengaturan.</span><span class="sxs-lookup"><span data-stu-id="d6f66-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="d6f66-134">Selanjutnya, Anda harus menetapkan peran keamanan di Dynamics 365 agar pengguna dapat menyesuaikan dan melihat kartu pelanggan.</span><span class="sxs-lookup"><span data-stu-id="d6f66-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="d6f66-135">Di Dynamics 365, pergi ke **pengaturan** > **keamanan** > **pengguna**.</span><span class="sxs-lookup"><span data-stu-id="d6f66-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="d6f66-136">Pilih pengguna untuk mengedit peran pengguna dan pilih **Kelola peran**.</span><span class="sxs-lookup"><span data-stu-id="d6f66-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="d6f66-137">Tetapkan **peran Penyesuai kartu Customer Insights** kepada pengguna yang akan menyesuaikan konten untuk ditampilkan pada kartu untuk seluruh organisasi.</span><span class="sxs-lookup"><span data-stu-id="d6f66-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="d6f66-138">Tambahkan kontrol Kartu Pelanggan ke formulir</span><span class="sxs-lookup"><span data-stu-id="d6f66-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="d6f66-139">Untuk menambahkan kontrol kartu pelanggan ke formulir kontak, buka **pengaturan** > **penyesuaian** di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d6f66-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="d6f66-140">Pilih **Sesuaikan sistem**.</span><span class="sxs-lookup"><span data-stu-id="d6f66-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="d6f66-141">Telusuri entitas **kontak**, perluas lalu pilih **formulir**.</span><span class="sxs-lookup"><span data-stu-id="d6f66-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="d6f66-142">Pilih formulir kontak yang ingin ditambahkan kontrol kartu pelanggan.</span><span class="sxs-lookup"><span data-stu-id="d6f66-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d6f66-143">![Pilih formulir kontak](media/contact-active-forms.png "Pilih formulir kontak")</span><span class="sxs-lookup"><span data-stu-id="d6f66-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="d6f66-144">Untuk menambahkan kontrol, di editor formulir, tarik bidang apa pun dari **penjelajah bidang** ke tempat Anda ingin kontrol ditampilkan.</span><span class="sxs-lookup"><span data-stu-id="d6f66-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="d6f66-145">Pilih bidang di formulir yang baru saja ditambahkan, lalu pilih **Ubah properti**.</span><span class="sxs-lookup"><span data-stu-id="d6f66-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="d6f66-146">Buka tab **Kontrol** dan pilih **Tambahkan kontrol**.</span><span class="sxs-lookup"><span data-stu-id="d6f66-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="d6f66-147">Pilih salah satu kontrol kustom yang tersedia dan pilih **Tambah**.</span><span class="sxs-lookup"><span data-stu-id="d6f66-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="d6f66-148">Di dialog **properti bidang**, kosongkan kotak centang **label tampilan di formulir**.</span><span class="sxs-lookup"><span data-stu-id="d6f66-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="d6f66-149">Pilih opsi **web** untuk kontrol.</span><span class="sxs-lookup"><span data-stu-id="d6f66-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="d6f66-150">Untuk kontrol pengayaan, pilih jenis pengayaan yang akan ditampilkan dengan mengonfigurasi bidang **enrichmenttype**.</span><span class="sxs-lookup"><span data-stu-id="d6f66-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="d6f66-151">Anda harus menambahkan kontrol pengayaan terpisah untuk setiap jenis pengayaan.</span><span class="sxs-lookup"><span data-stu-id="d6f66-151">You need to add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="d6f66-152">Pilih **Simpan** dan **publikasikan** untuk mempublikasikan formulir kontak yang diperbarui.</span><span class="sxs-lookup"><span data-stu-id="d6f66-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="d6f66-153">Buka formulir kontak yang dipublikasikan.</span><span class="sxs-lookup"><span data-stu-id="d6f66-153">Go to the published contact form.</span></span> <span data-ttu-id="d6f66-154">Anda akan melihat kontrol yang baru ditambahkan.</span><span class="sxs-lookup"><span data-stu-id="d6f66-154">You'll see the newly added control.</span></span> <span data-ttu-id="d6f66-155">Anda mungkin harus masuk saat pertama kali menggunakannya.</span><span class="sxs-lookup"><span data-stu-id="d6f66-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="d6f66-156">Untuk menyesuaikan yang ingin Anda Tampilkan pada kontrol kustom, pilih tombol Edit di sudut kanan atas.</span><span class="sxs-lookup"><span data-stu-id="d6f66-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>
