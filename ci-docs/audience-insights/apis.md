---
title: Bekerja dengan API
description: Gunakan API dan pahami batasan.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689134"
---
# <a name="work-with-customer-insights-apis"></a>Bekerja dengan API Customer Insights

Dynamics 365 Customer Insights menyediakan API untuk membuat aplikasi Anda sendiri berdasarkan data Anda dalam Customer Insights.

> [!IMPORTANT]
> Rincian API ini, tercantum pada [referensi API customer insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Mereka mencakup informasi tambahan tentang operasi, parameter, dan respons.

Artikel ini memandu Anda mengakses API Customer Insights, membuat pendaftaran aplikasi Azure, dan membantu Anda memulai dengan pustaka klien yang tersedia.

## <a name="get-started-trying-the-customer-insights-apis"></a>Memulai mencoba API Customer Insights

1. [Masuk](https://home.ci.ai.dynamics.com) ke Customer Insights. Jika Anda belum memiliki langganan, [Daftar untuk versi uji coba dari Customer Insights](https://aka.ms/tryci).

1. Untuk mengaktifkan API di lingkungan Customer Insights Anda, buka **admin** > **izin**. Anda memerlukan izin admin untuk melakukannya.

1. Buka tab **API** dan pilih tombol **Aktifkan**.    
   Mengaktifkan API akan membuat kunci langganan utama dan sekunder untuk instans yang digunakan dalam permintaan API. Anda dapat membuat ulang kunci dengan memilih **Buat lagi utama** atau **Buat lagi sekunder** pada **admin** > **izin** > **api**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Aktifkan API Customer Insights":::

1. Pilih **Jelajahi API kami** untuk mencoba API.

1. Pilih operasi API dan pilih **coba**.

1. Di panel sisi, atur nilai dalam menu drop-down **otorisasi** ke **implisit**. Header `Authorization` ditambahi token pembawa. Kunci langganan akan diisi secara otomatis.
  
1. Atau, Tambahkan semua parameter kueri yang diperlukan.

1. Gulir ke bagian bawah panel samping, lalu pilih **kirim**.

Respons HTTP akan segera muncul di bawah.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Buat pendaftaran Aplikasi baru di portal Azure

Langkah-langkah ini membantu Anda memulai menggunakan API Customer Insights dalam aplikasi Azure menggunakan izin delegasi. Pastikan untuk menyelesaikan [Bagian Memulai](#get-started-trying-the-customer-insights-apis) terlebih dahulu.

1. Masuk ke [portal Azure](https://portal.azure.com) dengan akun yang dapat mengakses data Customer Insights.

1. Di sebelah kiri, pilih **pendaftaran aplikasi**.

1. Pilih **pendaftaran baru** berikan nama aplikasi dan pilih jenis akun.
   Atau, tambahkan URL pengalihan. http://localhost cukup untuk mengembangkan aplikasi di komputer lokal.

1. Di pendaftaran aplikasi baru, buka **izin API**.

1. Pilih **Tambah izin** dan pilih **Customer Insights** di panel sisi.

1. Untuk **jenis izin**, pilih **izin delegasi** dan pilih izin **user_impersonation**.

1. Pilih **Tambahkan izin**. Jika Anda perlu mengakses API tanpa login pengguna, Tinjau Bagian [izin aplikasi server-ke-server](#server-to-server-application-permissions).

1. Pilih **Berikan izin admin untuk...** untuk menyelesaikan pendaftaran aplikasi.

Anda dapat menggunakan ID aplikasi/klien untuk pendaftaran aplikasi ini dengan Microsoft Authentication Library (MSAL) untuk mendapatkan token pembawa untuk mengirim permintaan Anda ke API.

Untuk informasi lebih lanjut tentang MSAL, lihat [ikhtisar dari Microsoft Authentication Library (msal)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Untuk informasi lebih lanjut tentang pendaftaran aplikasi di Azure, lihat [pengalaman pendaftaran aplikasi portal Azure baru](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).

Untuk informasi tentang cara menggunakan pustaka klien API kami, lihat [pustaka klien Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Izin aplikasi server-ke-server

[Bagian pendaftaran aplikasi](#create-a-new-app-registration-in-the-azure-portal) menguraikan cara mendaftarkan aplikasi yang mengharuskan pengguna masuk untuk autentikasi. Pelajari cara membuat pendaftaran aplikasi yang tidak memerlukan interaksi pengguna dan dapat dijalankan di server.

1. Di pendaftaran aplikasi di portal Azure, buka **izin api**.

1. Pilih **Tambah izin** dan pilih **Customer Insights** di panel sisi.

1. Untuk **jenis izin**, pilih **izin aplikasi** dan pilih izin **CustomerInsights.Api.All**.

1. Pilih **Tambahkan izin**.

1. Untuk memberikan izin admin atas izin aplikasi ini, Anda harus menambahkan prinsipal layanan.

   1. Instal modul Azure Active Directory (AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Hubungkan ke akun AD Anda: `Connect-AzureAD -TenantId <your tenant id>`. Anda dapat menemukan ID penyewa pada **Ikhtisar** > **Azure Active Directory**.
   1. Jalankan perintah berikut untuk menambahkan prinsipal Layanan Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` parameter appId yang terkait dengan aplikasi API Customer Insights.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Sampel prinsipal layanan":::

1. Kembali ke **izin API** untuk pendaftaran aplikasi Anda.

1. Pilih **Berikan izin admin untuk...** untuk menyelesaikan pendaftaran aplikasi.

1. Sebagai akhir, kita harus menambahkan nama pendaftaran aplikasi sebagai pengguna di Customer Insights.    
   Buka Customer Insights, buka **admin** > **izin** dan pilih **Tambah Pengguna**.

1. Cari nama pendaftaran aplikasi, pilih dari hasil pencarian, lalu pilih **Simpan**.

## <a name="customer-insights-client-libraries"></a>Pustaka klien Customer Insights

Bagian ini akan membantu Anda memulai menggunakan pustaka klien yang tersedia untuk API Customer Insights.

### <a name="c-nuget"></a>C# NuGet

Pelajari cara memulai menggunakan pustaka klien C# dari NuGet.org. Untuk informasi lebih lanjut tentang paket NuGet, lihat [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Saat ini, paket ini menargetkan kerangka kerja netstandard2.0 dan netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Tambahkan pustaka klien C# ke proyek C#

1. Di Visual Studio, buka **manajer paket NuGet** untuk proyek Anda.

1. Cari **Microsoft.Dynamics.CustomerInsights.Api**.

1. Pilih **Instal** untuk menambahkan paket ke proyek.
   Atau, jalankan perintah ini di **konsol manajer paket NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Tambahkan paket NuGet ke proyek Visual Studio":::

#### <a name="use-the-c-client-library"></a>Gunakan pustaka klien C#

1. Gunakan [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) untuk membuat `AccessToken` menggunakan [pendaftaran aplikasi Azure](#create-a-new-app-registration-in-the-azure-portal) yang ada.

1. Setelah berhasil mengautentikasi dan memperoleh token, buat baru atau gunakan `HttpClient` yang ada dengan **"otorisasi" defaultrequestheaders** diatur ke **pembawa <access token>** dan **OCP-apim-Subscription-Key** diatur ke [**kunci langganan** dari lingkungan Customer Insights Anda ](#get-started-trying-the-customer-insights-apis).    
   Atur ulang header **otorisasi** bila sesuai. Misalnya, saat token kedaluwarsa.

1. Lewati `HttpClient` ini ke dalam konstruksi klien `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Sampel httpclient":::

1. Lakukan panggilan dengan klien ke "metode ekstensi", misalnya `GetAllInstancesAsync`. Jika akses ke `Microsoft.Rest.HttpOperationResponse` yang mendasari lebih disukai, gunakan "metode pesan http", misalnya `GetAllInstancesWithHttpMessagesAsync`.

1. Respons kemungkinan akan berupa jenis `object` karena metode dapat menghasilkan beberapa jenis (misalnya, `IList<InstanceInfo>` dan `ApiErrorResult`). Untuk memeriksa jenis hasil, Anda dapat dengan aman mentransmisikan objek ke jenis respons yang ditentukan pada [halaman rincian API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) untuk operasi tersebut.    
   Jika diperlukan informasi lebih lanjut tentang permintaan, gunakan **metode pesan http** untuk mengakses objek respons mentah.
