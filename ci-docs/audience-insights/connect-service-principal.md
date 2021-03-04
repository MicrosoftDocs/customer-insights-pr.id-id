---
title: Menyambung ke akun Azure Data Lake Storage Gen2 dengan prinsipal Layanan
description: Gunakan prinsipal layanan Azure untuk wawasan audiens untuk menyambung ke Data Lake Anda sendiri saat melampirkan ke wawasan audiens.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267726"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="d7d39-103">Menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure untuk wawasan audiens</span><span class="sxs-lookup"><span data-stu-id="d7d39-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="d7d39-104">Alat otomatis yang menggunakan layanan Azure harus selalu memiliki izin terbatas.</span><span class="sxs-lookup"><span data-stu-id="d7d39-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="d7d39-105">Selain masuk aplikasi sebagai pengguna yang memiliki hak istimewa, Azure menawarkan prinsipal layanan.</span><span class="sxs-lookup"><span data-stu-id="d7d39-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="d7d39-106">Baca terus untuk mempelajari cara menyambung wawasan audiens dengan akun Azure Data Lake Storage Gen2 menggunakan prinsip layanan Azure dan bukan kunci akun penyimpanan.</span><span class="sxs-lookup"><span data-stu-id="d7d39-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="d7d39-107">Anda dapat menggunakan prinsipal layanan untuk [menambahkan atau mengedit folder Common Data Model sebagai sumber data](connect-common-data-model.md) atau [membuat yang baru atau memperbarui lingkungan yang ada](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="d7d39-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="d7d39-108">Akun penyimpanan Azure Data Lake Gen2 yang ingin menggunakan layanan utama harus [mengaktifkan Spasi Nama hierarkis (HNS)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="d7d39-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="d7d39-109">Anda memerlukan izin admin untuk langganan Azure Anda untuk membuat prinsipal layanan.</span><span class="sxs-lookup"><span data-stu-id="d7d39-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="d7d39-110">Membuat prinsipal layanan Azure untuk wawasan audiens</span><span class="sxs-lookup"><span data-stu-id="d7d39-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="d7d39-111">Sebelum membuat prinsipal layanan baru untuk wawasan audiens, periksa apakah sudah ada di organisasi anda.</span><span class="sxs-lookup"><span data-stu-id="d7d39-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="d7d39-112">Mencari prinsipal layanan yang ada</span><span class="sxs-lookup"><span data-stu-id="d7d39-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="d7d39-113">Buka [portal admin Azure](https://portal.azure.com), lalu masuk ke organisasi Anda.</span><span class="sxs-lookup"><span data-stu-id="d7d39-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="d7d39-114">Pilih **Azure Active Directory** dari layanan Azure.</span><span class="sxs-lookup"><span data-stu-id="d7d39-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="d7d39-115">Di dalam **Kelola**, pilih **aplikasi Enterprise**.</span><span class="sxs-lookup"><span data-stu-id="d7d39-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="d7d39-116">Cari ID aplikasi pihak pertama wawasan audiens `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` atau nama `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="d7d39-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="d7d39-117">Jika Anda menemukan rekaman yang cocok, berarti prinsipal layanan untuk wawasan audiens ada.</span><span class="sxs-lookup"><span data-stu-id="d7d39-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="d7d39-118">Anda tidak perlu membuatnya lagi.</span><span class="sxs-lookup"><span data-stu-id="d7d39-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Screenshot yang menunjukkan prinsipal layanan yang ada.":::
   
6. <span data-ttu-id="d7d39-120">Jika tidak ada hasil, buat prinsipal layanan baru.</span><span class="sxs-lookup"><span data-stu-id="d7d39-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="d7d39-121">Buat prinsipal layanan baru</span><span class="sxs-lookup"><span data-stu-id="d7d39-121">Create a new service principal</span></span>

1. <span data-ttu-id="d7d39-122">Instal versi terbaru **Azure Active Directory PowerShell for Graph**.</span><span class="sxs-lookup"><span data-stu-id="d7d39-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="d7d39-123">Untuk informasi lebih lanjut, lihat [menginstal Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="d7d39-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="d7d39-124">Di PC, pilih tombol Windows di keyboard dan Cari **Windows PowerShell** dan **Jalankan sebagai administrator**.</span><span class="sxs-lookup"><span data-stu-id="d7d39-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="d7d39-125">Di jendela PowerShell yang terbuka, masukkan `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="d7d39-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="d7d39-126">Buat prinsipal layanan untuk audiens wawasan dengan modul Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7d39-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="d7d39-127">Di jendela PowerShell, masukkan `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="d7d39-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="d7d39-128">Ganti "ID penyewa Anda" dengan ID sebenarnya dari penyewa Anda yang akan membuat prinsipal layanan.</span><span class="sxs-lookup"><span data-stu-id="d7d39-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="d7d39-129">Parameter nama lingkungan `AzureEnvironmentName` adalah opsional.</span><span class="sxs-lookup"><span data-stu-id="d7d39-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="d7d39-130">Masukkan `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="d7d39-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="d7d39-131">Perintah ini akan membuat prinsipal layanan untuk wawasan audiens pada penyewa yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="d7d39-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="d7d39-132">Berikan izin kepada prinsipal layanan untuk mengakses akun Penyimpanan</span><span class="sxs-lookup"><span data-stu-id="d7d39-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="d7d39-133">Buka portal Azure untuk memberikan izin kepada prinsipal layanan untuk akun penyimpanan yang ingin anda gunakan di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="d7d39-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="d7d39-134">Buka [portal admin Azure](https://portal.azure.com), lalu masuk ke organisasi Anda.</span><span class="sxs-lookup"><span data-stu-id="d7d39-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="d7d39-135">Buka akun penyimpanan yang akan menjadi prinsipal layanan untuk wawasan audiens agar dapat diakses.</span><span class="sxs-lookup"><span data-stu-id="d7d39-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="d7d39-136">Pilih **kontrol akses (IAM)** dari panel navigasi dan pilih **Tambah** > **Tambah penetapan peran**.</span><span class="sxs-lookup"><span data-stu-id="d7d39-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screeshot menampilkan portal Azure saat menambahkan penetapan peran.":::
   
1. <span data-ttu-id="d7d39-138">Di panel **Tambah penetapan peran**, atur properti berikut:</span><span class="sxs-lookup"><span data-stu-id="d7d39-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="d7d39-139">Peran: *kontributor data Blob penyimpanan*</span><span class="sxs-lookup"><span data-stu-id="d7d39-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="d7d39-140">Tetapkan akses ke: *pengguna, grup, atau prinsipal Layanan*</span><span class="sxs-lookup"><span data-stu-id="d7d39-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="d7d39-141">Pilih: *Dynamics 365 AI for Customer Insights* ([prinsipal layanan yang Anda buat](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="d7d39-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="d7d39-142">Pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="d7d39-142">Select **Save**.</span></span>

<span data-ttu-id="d7d39-143">Dapat memakan waktu hingga 15 menit untuk menyebarkan perubahan.</span><span class="sxs-lookup"><span data-stu-id="d7d39-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="d7d39-144">Masukkan ID sumber daya azure atau rincian langganan azure di lampiran akun penyimpanan ke wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="d7d39-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="d7d39-145">Lampirkan akun penyimpanan Azure Data Lake di wawasan audiens untuk [menyimpan data output](manage-environments.md) atau [gunakan sebagai sumber data](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="d7d39-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="d7d39-146">Memilih pilihan Azure data Lake memungkinkan Anda memilih antara pendekatan berbasis sumber daya atau berbasis langganan.</span><span class="sxs-lookup"><span data-stu-id="d7d39-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="d7d39-147">Ikuti langkah-langkah berikut untuk menyediakan informasi yang diperlukan tentang pendekatan yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="d7d39-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="d7d39-148">Koneksi akun penyimpanan berbasis sumber daya</span><span class="sxs-lookup"><span data-stu-id="d7d39-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="d7d39-149">Buka [portal admin Azure](https://portal.azure.com), masuk ke langganan Anda dan buka akun penyimpanan.</span><span class="sxs-lookup"><span data-stu-id="d7d39-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="d7d39-150">Buka **pengaturan** > **properti** di panel navigasi.</span><span class="sxs-lookup"><span data-stu-id="d7d39-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="d7d39-151">Salin nilai ID sumber daya akun penyimpanan.</span><span class="sxs-lookup"><span data-stu-id="d7d39-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salin ID sumber daya akun penyimpanan.":::

1. <span data-ttu-id="d7d39-153">Di wawasan audiens, masukkan ID sumber daya di bidang sumber daya yang ditampilkan di layar koneksi akun penyimpanan.</span><span class="sxs-lookup"><span data-stu-id="d7d39-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Masukkan informasi ID sumber daya akun penyimpanan.":::   
   
1. <span data-ttu-id="d7d39-155">Lanjutkan dengan langkah yang tersisa di wawasan audiens untuk melampirkan akun penyimpanan.</span><span class="sxs-lookup"><span data-stu-id="d7d39-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="d7d39-156">Koneksi akun penyimpanan berbasis langganan</span><span class="sxs-lookup"><span data-stu-id="d7d39-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="d7d39-157">Buka [portal admin Azure](https://portal.azure.com), masuk ke langganan Anda dan buka akun penyimpanan.</span><span class="sxs-lookup"><span data-stu-id="d7d39-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="d7d39-158">Buka **pengaturan** > **properti** di panel navigasi.</span><span class="sxs-lookup"><span data-stu-id="d7d39-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="d7d39-159">Tinjau **langganan**, **grup sumber daya**, dan **nama** akun penyimpanan untuk memastikan bahwa anda memilih nilai yang tepat di wawasan audiens.</span><span class="sxs-lookup"><span data-stu-id="d7d39-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="d7d39-160">Di wawasan audiens, pilih nilai atau untuk bidang yang terkait saat melampirkan akun penyimpanan.</span><span class="sxs-lookup"><span data-stu-id="d7d39-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="d7d39-161">Lanjutkan dengan langkah yang tersisa di wawasan audiens untuk melampirkan akun penyimpanan.</span><span class="sxs-lookup"><span data-stu-id="d7d39-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]