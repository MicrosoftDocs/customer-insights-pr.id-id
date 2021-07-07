---
title: Bekerja dengan API
description: Gunakan API dan pahami batasan.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304746"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="c44bf-103">Bekerja dengan API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="c44bf-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="c44bf-104">Dynamics 365 Customer Insights menyediakan API untuk membangun aplikasi Anda sendiri berdasarkan data Anda dalam Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c44bf-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c44bf-105">Rincian API ini, tercantum pada [referensi API customer insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="c44bf-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="c44bf-106">Mereka mencakup informasi tambahan tentang operasi, parameter, dan respons.</span><span class="sxs-lookup"><span data-stu-id="c44bf-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="c44bf-107">Artikel ini menjelaskan cara mengakses API Customer Insights, membuat Pendaftaran Aplikasi Azure, dan memulai pustaka klien yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="c44bf-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="c44bf-108">Memulai mencoba API Customer Insights</span><span class="sxs-lookup"><span data-stu-id="c44bf-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="c44bf-109">[Masuk](https://home.ci.ai.dynamics.com) ke Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c44bf-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="c44bf-110">Jika Anda belum memiliki langganan, [Daftar untuk versi uji coba dari Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="c44bf-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="c44bf-111">Untuk mengaktifkan API di lingkungan Customer Insights Anda, buka **admin** > **izin**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="c44bf-112">Anda memerlukan izin admin untuk melakukannya.</span><span class="sxs-lookup"><span data-stu-id="c44bf-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="c44bf-113">Buka tab **API** dan pilih tombol **Aktifkan**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="c44bf-114">Mengaktifkan API akan membuat kunci langganan utama dan sekunder untuk instans yang digunakan dalam permintaan API.</span><span class="sxs-lookup"><span data-stu-id="c44bf-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="c44bf-115">Anda dapat membuat ulang kunci dengan memilih **Buat lagi utama** atau **Buat lagi sekunder** pada **admin** > **izin** > **api**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Aktifkan API Customer Insights":::

1. <span data-ttu-id="c44bf-117">Pilih **Jelajahi API kami** untuk [mencoba API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="c44bf-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="c44bf-118">Pilih operasi API dan pilih **coba**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="c44bf-119">Pada panel sisi, atur nilai dalam menu dropdown **Otorisasi** ke **implisit**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="c44bf-120">Header `Authorization` ditambahkan dengan token penahan.</span><span class="sxs-lookup"><span data-stu-id="c44bf-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="c44bf-121">Kunci langganan akan diisi secara otomatis.</span><span class="sxs-lookup"><span data-stu-id="c44bf-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="c44bf-122">Atau, Tambahkan semua parameter kueri yang diperlukan.</span><span class="sxs-lookup"><span data-stu-id="c44bf-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="c44bf-123">Gulir ke bagian bawah panel samping, lalu pilih **kirim**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="c44bf-124">Respons HTTP akan segera muncul di bawah.</span><span class="sxs-lookup"><span data-stu-id="c44bf-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Cara menguji API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="c44bf-126">Buat pendaftaran Aplikasi baru di portal Azure</span><span class="sxs-lookup"><span data-stu-id="c44bf-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="c44bf-127">Langkah-langkah ini membantu Anda memulai menggunakan API Customer Insights di aplikasi Azure menggunakan izin yang didelegasikan.</span><span class="sxs-lookup"><span data-stu-id="c44bf-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="c44bf-128">Pastikan untuk menyelesaikan [bagian memulai](#get-started-trying-the-customer-insights-apis) terlebih dulu.</span><span class="sxs-lookup"><span data-stu-id="c44bf-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="c44bf-129">Masuk ke [portal Azure](https://portal.azure.com) dengan akun yang dapat mengakses data Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c44bf-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="c44bf-130">Di sebelah kiri, pilih **pendaftaran aplikasi**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="c44bf-131">Pilih **pendaftaran baru** berikan nama aplikasi dan pilih jenis akun.</span><span class="sxs-lookup"><span data-stu-id="c44bf-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="c44bf-132">Atau, tambahkan URL pengalihan.</span><span class="sxs-lookup"><span data-stu-id="c44bf-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="c44bf-133">http://localhost cukup untuk mengembangkan aplikasi di komputer lokal.</span><span class="sxs-lookup"><span data-stu-id="c44bf-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="c44bf-134">Di pendaftaran aplikasi baru, buka **izin API**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Cara mengatur izin API dalam pendaftaran Aplikasi.":::

1. <span data-ttu-id="c44bf-136">Pilih **Tambah izin** dan pilih **Customer Insights** di panel sisi.</span><span class="sxs-lookup"><span data-stu-id="c44bf-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="c44bf-137">Untuk **jenis izin**, pilih **Izin yang didelegasikan**, lalu izin **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="c44bf-138">Pilih **Tambahkan izin**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-138">Select **Add permissions**.</span></span> <span data-ttu-id="c44bf-139">Jika Anda perlu mengakses API tanpa login pengguna, Tinjau Bagian [izin aplikasi server-ke-server](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="c44bf-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="c44bf-140">Pilih **Berikan izin admin untuk...** untuk menyelesaikan pendaftaran aplikasi.</span><span class="sxs-lookup"><span data-stu-id="c44bf-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="c44bf-141">Anda dapat menggunakan ID aplikasi/klien untuk pendaftaran aplikasi ini dengan Microsoft Authentication Library (MSAL) untuk mendapatkan token pembawa untuk mengirim permintaan Anda ke API.</span><span class="sxs-lookup"><span data-stu-id="c44bf-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Cara memberikan persetujuan admin.":::

<span data-ttu-id="c44bf-143">Untuk informasi lebih lanjut tentang MSAL, lihat [ikhtisar dari Microsoft Authentication Library (msal)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="c44bf-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="c44bf-144">Untuk informasi lebih lanjut tentang pendaftaran aplikasi di Azure, lihat [Mendaftarkan aplikasi](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="c44bf-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="c44bf-145">Untuk informasi tentang menggunakan API di pustaka klien kami, lihat [pustaka klien Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="c44bf-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="c44bf-146">Izin aplikasi server-ke-server</span><span class="sxs-lookup"><span data-stu-id="c44bf-146">Server-to-server application permissions</span></span>

<span data-ttu-id="c44bf-147">[Bagian pendaftaran aplikasi](#create-a-new-app-registration-in-the-azure-portal) menguraikan cara mendaftarkan aplikasi yang mengharuskan pengguna masuk untuk autentikasi.</span><span class="sxs-lookup"><span data-stu-id="c44bf-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="c44bf-148">Pelajari cara membuat pendaftaran aplikasi yang tidak memerlukan interaksi pengguna dan dapat dijalankan di server.</span><span class="sxs-lookup"><span data-stu-id="c44bf-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="c44bf-149">Di pendaftaran aplikasi di portal Azure, buka **izin api**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="c44bf-150">Pilih **Tambahkan Izin**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="c44bf-151">Pilih tab **API organisasi saya menggunakan**, lalu pilih **Dynamics 365 AI for Customer Insights** dari daftar.</span><span class="sxs-lookup"><span data-stu-id="c44bf-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="c44bf-152">Untuk **jenis izin**, pilih **Izin Aplikasi**, lalu izin **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="c44bf-153">Pilih **Tambahkan izin**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="c44bf-154">Kembali ke **izin API** untuk pendaftaran aplikasi Anda.</span><span class="sxs-lookup"><span data-stu-id="c44bf-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="c44bf-155">Pilih **Berikan izin admin untuk...** untuk menyelesaikan pendaftaran aplikasi.</span><span class="sxs-lookup"><span data-stu-id="c44bf-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Cara memberikan persetujuan admin.":::

1. <span data-ttu-id="c44bf-157">Sebagai akhir, kita harus menambahkan nama pendaftaran aplikasi sebagai pengguna di Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c44bf-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="c44bf-158">Buka Customer Insights, buka **admin** > **izin** dan pilih **Tambah Pengguna**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="c44bf-159">Cari nama pendaftaran aplikasi, pilih dari hasil pencarian, lalu pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="c44bf-160">Pustaka klien Customer Insights</span><span class="sxs-lookup"><span data-stu-id="c44bf-160">Customer Insights client libraries</span></span>

<span data-ttu-id="c44bf-161">Bagian ini akan membantu Anda memulai menggunakan pustaka klien yang tersedia untuk API Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c44bf-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="c44bf-162">Semua kode sumber pustaka dan aplikasi sampel dapat ditemukan di [halaman GitHub Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="c44bf-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="c44bf-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="c44bf-163">C# NuGet</span></span>

<span data-ttu-id="c44bf-164">Pelajari cara memulai menggunakan pustaka klien C# dari NuGet.org. Untuk informasi lebih lanjut tentang paket NuGet, lihat [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="c44bf-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="c44bf-165">Saat ini, paket ini menargetkan kerangka kerja netstandard2.0 dan netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="c44bf-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="c44bf-166">Tambahkan pustaka klien C# ke proyek C#</span><span class="sxs-lookup"><span data-stu-id="c44bf-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="c44bf-167">Di Visual Studio, buka **manajer paket NuGet** untuk proyek Anda.</span><span class="sxs-lookup"><span data-stu-id="c44bf-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="c44bf-168">Cari **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="c44bf-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="c44bf-169">Pilih **Instal** untuk menambahkan paket ke proyek.</span><span class="sxs-lookup"><span data-stu-id="c44bf-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="c44bf-170">Atau, jalankan perintah ini di **konsol manajer paket NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="c44bf-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Tambahkan paket NuGet ke proyek Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="c44bf-172">Gunakan pustaka klien C#</span><span class="sxs-lookup"><span data-stu-id="c44bf-172">Use the C# client library</span></span>

1. <span data-ttu-id="c44bf-173">Gunakan [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) untuk membuat `AccessToken` menggunakan [pendaftaran aplikasi Azure](#create-a-new-app-registration-in-the-azure-portal) yang ada.</span><span class="sxs-lookup"><span data-stu-id="c44bf-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="c44bf-174">Setelah berhasil mengautentikasi dan memperoleh token, buat baru atau gunakan `HttpClient` yang ada dengan **"otorisasi" defaultrequestheaders** diatur ke **pembawa <access token>** dan **OCP-apim-Subscription-Key** diatur ke [**kunci langganan** dari lingkungan Customer Insights Anda ](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="c44bf-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="c44bf-175">Atur ulang header **otorisasi** bila sesuai.</span><span class="sxs-lookup"><span data-stu-id="c44bf-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="c44bf-176">Misalnya, saat token kedaluwarsa.</span><span class="sxs-lookup"><span data-stu-id="c44bf-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="c44bf-177">Lewati `HttpClient` ini ke dalam konstruksi klien `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="c44bf-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Sampel httpclient":::

1. <span data-ttu-id="c44bf-179">Lakukan panggilan dengan klien ke "metode ekstensi"—misalnya `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="c44bf-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="c44bf-180">Jika akses ke `Microsoft.Rest.HttpOperationResponse` yang mendasari lebih disukai, gunakan "metode pesan http"—misalnya `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="c44bf-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="c44bf-181">Respons kemungkinan akan berupa jenis `object` karena metode dapat menghasilkan beberapa jenis (misalnya, `IList<InstanceInfo>` dan `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="c44bf-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="c44bf-182">Untuk memeriksa jenis hasil, Anda dapat dengan aman mentransmisikan objek ke jenis respons yang ditentukan pada [halaman rincian API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) untuk operasi tersebut.</span><span class="sxs-lookup"><span data-stu-id="c44bf-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="c44bf-183">Jika diperlukan informasi lebih lanjut tentang permintaan, gunakan **metode pesan http** untuk mengakses objek respons mentah.</span><span class="sxs-lookup"><span data-stu-id="c44bf-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="c44bf-184">Paket NodeJS</span><span class="sxs-lookup"><span data-stu-id="c44bf-184">NodeJS package</span></span>

<span data-ttu-id="c44bf-185">Gunakan pustaka klien NodeJS yang tersedia melalui NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="c44bf-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="c44bf-186">Paket Python</span><span class="sxs-lookup"><span data-stu-id="c44bf-186">Python package</span></span>

<span data-ttu-id="c44bf-187">Gunakan pustaka klien Python yang tersedia melalui PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="c44bf-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
