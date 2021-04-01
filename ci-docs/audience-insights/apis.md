---
title: Bekerja dengan API
description: Gunakan API dan pahami batasan.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 011fa700563c53534554a6b73e87c2391bfdf714
ms.sourcegitcommit: a872f59e6febe4d4bd678ddd0b60a1660acca0f3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 03/24/2021
ms.locfileid: "5710464"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="75c30-103">Bekerja dengan API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="75c30-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="75c30-104">Dynamics 365 Customer Insights menyediakan API untuk membuat aplikasi Anda sendiri berdasarkan data Anda dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="75c30-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75c30-105">Rincian API ini, tercantum pada [referensi API customer insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="75c30-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="75c30-106">Mereka mencakup informasi tambahan tentang operasi, parameter, dan respons.</span><span class="sxs-lookup"><span data-stu-id="75c30-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="75c30-107">Artikel ini memandu Anda mengakses API Customer Insights, membuat pendaftaran aplikasi Azure, dan membantu Anda memulai dengan pustaka klien yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="75c30-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="75c30-108">Memulai mencoba API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="75c30-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="75c30-109">[Masuk](https://home.ci.ai.dynamics.com) ke Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="75c30-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="75c30-110">Jika Anda belum memiliki langganan, [Daftar untuk versi uji coba dari Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="75c30-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="75c30-111">Untuk mengaktifkan API di lingkungan Customer Insights Anda, buka **admin** > **izin**.</span><span class="sxs-lookup"><span data-stu-id="75c30-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="75c30-112">Anda memerlukan izin admin untuk melakukannya.</span><span class="sxs-lookup"><span data-stu-id="75c30-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="75c30-113">Buka tab **API** dan pilih tombol **Aktifkan**.</span><span class="sxs-lookup"><span data-stu-id="75c30-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="75c30-114">Mengaktifkan API akan membuat kunci langganan utama dan sekunder untuk instans yang digunakan dalam permintaan API.</span><span class="sxs-lookup"><span data-stu-id="75c30-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="75c30-115">Anda dapat membuat ulang kunci dengan memilih **Buat lagi utama** atau **Buat lagi sekunder** pada **admin** > **izin** > **api**.</span><span class="sxs-lookup"><span data-stu-id="75c30-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Aktifkan API Customer Insights":::

1. <span data-ttu-id="75c30-117">Pilih **Jelajahi API kami** untuk [mencoba API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="75c30-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="75c30-118">Pilih operasi API dan pilih **coba**.</span><span class="sxs-lookup"><span data-stu-id="75c30-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="75c30-119">Di panel sisi, atur nilai dalam menu drop-down **otorisasi** ke **implisit**.</span><span class="sxs-lookup"><span data-stu-id="75c30-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="75c30-120">Header `Authorization` ditambahi token pembawa.</span><span class="sxs-lookup"><span data-stu-id="75c30-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="75c30-121">Kunci langganan akan diisi secara otomatis.</span><span class="sxs-lookup"><span data-stu-id="75c30-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="75c30-122">Atau, Tambahkan semua parameter kueri yang diperlukan.</span><span class="sxs-lookup"><span data-stu-id="75c30-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="75c30-123">Gulir ke bagian bawah panel samping, lalu pilih **kirim**.</span><span class="sxs-lookup"><span data-stu-id="75c30-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="75c30-124">Respons HTTP akan segera muncul di bawah.</span><span class="sxs-lookup"><span data-stu-id="75c30-124">The HTTP response will soon appear below.</span></span>


   :::image type="content" source="media/try-apis.gif" alt-text="Gif animasi yang menunjukkan cara memilih uji API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="75c30-126">Buat pendaftaran Aplikasi baru di portal Azure</span><span class="sxs-lookup"><span data-stu-id="75c30-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="75c30-127">Langkah-langkah ini membantu Anda memulai menggunakan API Customer Insights dalam aplikasi Azure menggunakan izin delegasi.</span><span class="sxs-lookup"><span data-stu-id="75c30-127">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="75c30-128">Pastikan untuk menyelesaikan [Bagian Memulai](#get-started-trying-the-customer-insights-apis) terlebih dahulu.</span><span class="sxs-lookup"><span data-stu-id="75c30-128">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="75c30-129">Masuk ke [portal Azure](https://portal.azure.com) dengan akun yang dapat mengakses data Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="75c30-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="75c30-130">Di sebelah kiri, pilih **pendaftaran aplikasi**.</span><span class="sxs-lookup"><span data-stu-id="75c30-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="75c30-131">Pilih **pendaftaran baru** berikan nama aplikasi dan pilih jenis akun.</span><span class="sxs-lookup"><span data-stu-id="75c30-131">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="75c30-132">Atau, tambahkan URL pengalihan.</span><span class="sxs-lookup"><span data-stu-id="75c30-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="75c30-133">http://localhost cukup untuk mengembangkan aplikasi di komputer lokal.</span><span class="sxs-lookup"><span data-stu-id="75c30-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="75c30-134">Di pendaftaran aplikasi baru, buka **izin API**.</span><span class="sxs-lookup"><span data-stu-id="75c30-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Gif animasi untuk mengatur izin API dalam pendaftaran aplikasi.":::

1. <span data-ttu-id="75c30-136">Pilih **Tambah izin** dan pilih **Customer Insights** di panel sisi.</span><span class="sxs-lookup"><span data-stu-id="75c30-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="75c30-137">Untuk **jenis izin**, pilih **izin delegasi** dan pilih izin **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="75c30-137">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="75c30-138">Pilih **Tambahkan izin**.</span><span class="sxs-lookup"><span data-stu-id="75c30-138">Select **Add permissions**.</span></span> <span data-ttu-id="75c30-139">Jika Anda perlu mengakses API tanpa login pengguna, Tinjau Bagian [izin aplikasi server-ke-server](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="75c30-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="75c30-140">Pilih **Berikan izin admin untuk...** untuk menyelesaikan pendaftaran aplikasi.</span><span class="sxs-lookup"><span data-stu-id="75c30-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="75c30-141">Anda dapat menggunakan ID aplikasi/klien untuk pendaftaran aplikasi ini dengan Microsoft Authentication Library (MSAL) untuk mendapatkan token pembawa untuk mengirim permintaan Anda ke API.</span><span class="sxs-lookup"><span data-stu-id="75c30-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Gif animasi untuk memberikan persetujuan admin.":::

<span data-ttu-id="75c30-143">Untuk informasi lebih lanjut tentang MSAL, lihat [ikhtisar dari Microsoft Authentication Library (msal)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="75c30-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="75c30-144">Untuk informasi lebih lanjut tentang pendaftaran aplikasi di Azure, lihat [pengalaman pendaftaran aplikasi portal Azure baru](/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="75c30-144">For more information about app registration in Azure, see [The new Azure portal app registration experience](/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="75c30-145">Untuk informasi tentang cara menggunakan pustaka klien API kami, lihat [pustaka klien Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="75c30-145">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="75c30-146">Izin aplikasi server-ke-server</span><span class="sxs-lookup"><span data-stu-id="75c30-146">Server-to-server application permissions</span></span>

<span data-ttu-id="75c30-147">[Bagian pendaftaran aplikasi](#create-a-new-app-registration-in-the-azure-portal) menguraikan cara mendaftarkan aplikasi yang mengharuskan pengguna masuk untuk autentikasi.</span><span class="sxs-lookup"><span data-stu-id="75c30-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="75c30-148">Pelajari cara membuat pendaftaran aplikasi yang tidak memerlukan interaksi pengguna dan dapat dijalankan di server.</span><span class="sxs-lookup"><span data-stu-id="75c30-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="75c30-149">Di pendaftaran aplikasi di portal Azure, buka **izin api**.</span><span class="sxs-lookup"><span data-stu-id="75c30-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="75c30-150">Pilih **Tambah izin** dan pilih **Customer Insights** di panel sisi.</span><span class="sxs-lookup"><span data-stu-id="75c30-150">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="75c30-151">Untuk **jenis izin**, pilih **izin aplikasi** dan pilih izin **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="75c30-151">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="75c30-152">Pilih **Tambahkan izin**.</span><span class="sxs-lookup"><span data-stu-id="75c30-152">Select **Add permissions**.</span></span>

1. <span data-ttu-id="75c30-153">Untuk memberikan izin admin atas izin aplikasi ini, Anda harus menambahkan prinsipal layanan.</span><span class="sxs-lookup"><span data-stu-id="75c30-153">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="75c30-154">Instal modul Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="75c30-154">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="75c30-155">Hubungkan ke akun AD Anda: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="75c30-155">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="75c30-156">Anda dapat menemukan ID penyewa pada **Ikhtisar** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="75c30-156">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="75c30-157">Jalankan perintah berikut untuk menambahkan prinsipal Layanan Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` parameter appId yang terkait dengan aplikasi API Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="75c30-157">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Sampel prinsipal layanan":::

1. <span data-ttu-id="75c30-159">Kembali ke **izin API** untuk pendaftaran aplikasi Anda.</span><span class="sxs-lookup"><span data-stu-id="75c30-159">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="75c30-160">Pilih **Berikan izin admin untuk...** untuk menyelesaikan pendaftaran aplikasi.</span><span class="sxs-lookup"><span data-stu-id="75c30-160">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Gif animasi untuk memberikan persetujuan admin.":::

1. <span data-ttu-id="75c30-162">Sebagai akhir, kita harus menambahkan nama pendaftaran aplikasi sebagai pengguna di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="75c30-162">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="75c30-163">Buka Customer Insights, buka **admin** > **izin** dan pilih **Tambah Pengguna**.</span><span class="sxs-lookup"><span data-stu-id="75c30-163">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="75c30-164">Cari nama pendaftaran aplikasi, pilih dari hasil pencarian, lalu pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="75c30-164">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="75c30-165">Pustaka klien Customer Insights</span><span class="sxs-lookup"><span data-stu-id="75c30-165">Customer Insights client libraries</span></span>

<span data-ttu-id="75c30-166">Bagian ini akan membantu Anda memulai menggunakan pustaka klien yang tersedia untuk API Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="75c30-166">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="75c30-167">Semua kode sumber pustaka dan aplikasi sampel dapat ditemukan di [halaman GitHub Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="75c30-167">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="75c30-168">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="75c30-168">C# NuGet</span></span>

<span data-ttu-id="75c30-169">Pelajari cara memulai menggunakan pustaka klien C# dari NuGet.org. Untuk informasi lebih lanjut tentang paket NuGet, lihat [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="75c30-169">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="75c30-170">Saat ini, paket ini menargetkan kerangka kerja netstandard2.0 dan netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="75c30-170">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="75c30-171">Tambahkan pustaka klien C# ke proyek C#</span><span class="sxs-lookup"><span data-stu-id="75c30-171">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="75c30-172">Di Visual Studio, buka **manajer paket NuGet** untuk proyek Anda.</span><span class="sxs-lookup"><span data-stu-id="75c30-172">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="75c30-173">Cari **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="75c30-173">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="75c30-174">Pilih **Instal** untuk menambahkan paket ke proyek.</span><span class="sxs-lookup"><span data-stu-id="75c30-174">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="75c30-175">Atau, jalankan perintah ini di **konsol manajer paket NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="75c30-175">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Tambahkan paket NuGet ke proyek Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="75c30-177">Gunakan pustaka klien C#</span><span class="sxs-lookup"><span data-stu-id="75c30-177">Use the C# client library</span></span>

1. <span data-ttu-id="75c30-178">Gunakan [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) untuk membuat `AccessToken` menggunakan [pendaftaran aplikasi Azure](#create-a-new-app-registration-in-the-azure-portal) yang ada.</span><span class="sxs-lookup"><span data-stu-id="75c30-178">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="75c30-179">Setelah berhasil mengautentikasi dan memperoleh token, buat baru atau gunakan `HttpClient` yang ada dengan **"otorisasi" defaultrequestheaders** diatur ke **pembawa <access token>** dan **OCP-apim-Subscription-Key** diatur ke [**kunci langganan** dari lingkungan Customer Insights Anda ](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="75c30-179">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="75c30-180">Atur ulang header **otorisasi** bila sesuai.</span><span class="sxs-lookup"><span data-stu-id="75c30-180">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="75c30-181">Misalnya, saat token kedaluwarsa.</span><span class="sxs-lookup"><span data-stu-id="75c30-181">For example, when the token expired.</span></span>

1. <span data-ttu-id="75c30-182">Lewati `HttpClient` ini ke dalam konstruksi klien `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="75c30-182">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Sampel httpclient":::

1. <span data-ttu-id="75c30-184">Lakukan panggilan dengan klien ke "metode ekstensi", misalnya `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="75c30-184">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="75c30-185">Jika akses ke `Microsoft.Rest.HttpOperationResponse` yang mendasari lebih disukai, gunakan "metode pesan http", misalnya `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="75c30-185">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="75c30-186">Respons kemungkinan akan berupa jenis `object` karena metode dapat menghasilkan beberapa jenis (misalnya, `IList<InstanceInfo>` dan `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="75c30-186">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="75c30-187">Untuk memeriksa jenis hasil, Anda dapat dengan aman mentransmisikan objek ke jenis respons yang ditentukan pada [halaman rincian API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) untuk operasi tersebut.</span><span class="sxs-lookup"><span data-stu-id="75c30-187">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="75c30-188">Jika diperlukan informasi lebih lanjut tentang permintaan, gunakan **metode pesan http** untuk mengakses objek respons mentah.</span><span class="sxs-lookup"><span data-stu-id="75c30-188">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="75c30-189">Paket NodeJS</span><span class="sxs-lookup"><span data-stu-id="75c30-189">NodeJS package</span></span>

<span data-ttu-id="75c30-190">Gunakan pustaka klien NodeJS yang tersedia melalui NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="75c30-190">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="75c30-191">Paket Python</span><span class="sxs-lookup"><span data-stu-id="75c30-191">Python package</span></span>

<span data-ttu-id="75c30-192">Gunakan pustaka klien Python yang tersedia melalui PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="75c30-192">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
