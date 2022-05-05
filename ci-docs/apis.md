---
title: Bekerja dengan API
description: Gunakan API dan pahami batasan.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: ecc8bb3dbec1d4583c4bf2a58058145343945299
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642610"
---
# <a name="work-with-customer-insights-apis"></a>Bekerja dengan API Customer Insights

Dynamics 365 Customer Insights menyediakan API untuk membangun aplikasi Anda sendiri berdasarkan data Anda dalam Customer Insights.

> [!IMPORTANT]
> Rincian API ini, tercantum pada [referensi API customer insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Mereka mencakup informasi tambahan tentang operasi, parameter, dan respons.

Artikel ini menjelaskan cara mengakses API Customer Insights, membuat Pendaftaran Aplikasi Azure, dan memulai pustaka klien yang tersedia.

## <a name="get-started-trying-the-customer-insights-apis"></a>Memulai mencoba API Customer Insights

1. [Masuk](https://home.ci.ai.dynamics.com) ke Customer Insights. Jika Anda belum memiliki langganan, [Daftar untuk versi uji coba dari Customer Insights](https://aka.ms/tryci).

1. Untuk mengaktifkan API di lingkungan Customer Insights Anda, buka **admin** > **izin**. Anda memerlukan izin admin untuk melakukannya.

1. Buka tab **API** dan pilih tombol **Aktifkan**.    
 
   Mengaktifkan API akan membuat kunci langganan utama dan sekunder untuk instans yang digunakan dalam permintaan API. Anda dapat membuat ulang kunci dengan memilih **Buat lagi utama** atau **Buat lagi sekunder** pada **admin** > **izin** > **api**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Pilih **Jelajahi API kami** untuk [mencoba API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Pilih operasi API dan pilih **coba**.

1. Pada panel sisi, atur nilai dalam menu dropdown **Otorisasi** ke **implisit**. Header `Authorization` ditambahkan dengan token penahan. Kunci langganan akan diisi secara otomatis.
  
1. Atau, Tambahkan semua parameter kueri yang diperlukan.

1. Gulir ke bagian bawah panel samping, lalu pilih **kirim**.

Respons HTTP akan segera muncul di bawah.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Buat pendaftaran Aplikasi baru di portal Azure

Langkah-langkah ini membantu Anda memulai menggunakan API Customer Insights di aplikasi Azure menggunakan izin yang didelegasikan. Pastikan untuk menyelesaikan [bagian memulai](#get-started-trying-the-customer-insights-apis) terlebih dulu.

1. Masuk ke [portal Azure](https://portal.azure.com) dengan akun yang dapat mengakses data Customer Insights.

1. Di sebelah kiri, pilih **pendaftaran aplikasi**.

1. Pilih **pendaftaran baru** berikan nama aplikasi dan pilih jenis akun.
 
   Atau, tambahkan URL pengalihan. http://localhost cukup untuk mengembangkan aplikasi di komputer lokal.

1. Di pendaftaran aplikasi baru, buka **izin API**.

<!--   :::image type="content" source="media/app-registration-1.gif" alt-text="How to set API permissions in App registration."::: -->

1. Pilih **Tambah izin** dan pilih **Customer Insights** di panel sisi.

1. Untuk **jenis izin**, pilih **Izin yang didelegasikan**, lalu izin **user_impersonation**.

1. Pilih **Tambahkan izin**. Jika Anda perlu mengakses API tanpa login pengguna, Tinjau Bagian [izin aplikasi server-ke-server](#server-to-server-application-permissions).

1. Pilih **Berikan izin admin untuk...** untuk menyelesaikan pendaftaran aplikasi.

Anda dapat menggunakan ID aplikasi/klien untuk pendaftaran aplikasi ini dengan Microsoft Authentication Library (MSAL) untuk mendapatkan token pembawa untuk mengirim permintaan Anda ke API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Untuk informasi lebih lanjut tentang MSAL, lihat [ikhtisar dari Microsoft Authentication Library (msal)](/azure/active-directory/develop/msal-overview).

Untuk informasi lebih lanjut tentang pendaftaran aplikasi di Azure, lihat [Mendaftarkan aplikasi](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Untuk informasi tentang menggunakan API di pustaka klien kami, lihat [pustaka klien Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Izin aplikasi server-ke-server

[Bagian pendaftaran aplikasi](#create-a-new-app-registration-in-the-azure-portal) menguraikan cara mendaftarkan aplikasi yang mengharuskan pengguna masuk untuk autentikasi. Pelajari cara membuat pendaftaran aplikasi yang tidak memerlukan interaksi pengguna dan dapat dijalankan di server.

1. Di pendaftaran aplikasi di portal Azure, buka **izin api**.

1. Pilih **Tambahkan Izin**. 

1. Pilih tab **API organisasi saya menggunakan**, lalu pilih **Dynamics 365 AI for Customer Insights** dari daftar. 

1. Untuk **jenis izin**, pilih **Izin Aplikasi**, lalu izin **CustomerInsights.Api.All**.

1. Pilih **Tambahkan izin**.

1. Kembali ke **izin API** untuk pendaftaran aplikasi Anda.

1. Pilih **Berikan izin admin untuk...** untuk menyelesaikan pendaftaran aplikasi.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Sebagai akhir, kita harus menambahkan nama pendaftaran aplikasi sebagai pengguna di Customer Insights.  
   
   Buka Customer Insights, buka **admin** > **izin** dan pilih **Tambah Pengguna**.

1. Cari nama pendaftaran aplikasi, pilih dari hasil pencarian, lalu pilih **Simpan**.

## <a name="customer-insights-client-libraries"></a>Pustaka klien Customer Insights

Bagian ini akan membantu Anda memulai menggunakan pustaka klien yang tersedia untuk API Customer Insights. Semua kode sumber pustaka dan aplikasi sampel dapat ditemukan di [halaman GitHub Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Pelajari cara memulai menggunakan pustaka klien C# dari NuGet.org. Untuk informasi lebih lanjut tentang paket NuGet, lihat [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Saat ini, paket ini menargetkan kerangka kerja netstandard2.0 dan netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Tambahkan pustaka klien C# ke proyek C#

1. Di Visual Studio, buka **manajer paket NuGet** untuk proyek Anda.

1. Cari **Microsoft.Dynamics.CustomerInsights.Api**.

1. Pilih **Instal** untuk menambahkan paket ke proyek.
 
   Atau, jalankan perintah ini di **konsol manajer paket NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Gunakan pustaka klien C#

1. Gunakan [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) untuk membuat `AccessToken` menggunakan [pendaftaran aplikasi Azure](#create-a-new-app-registration-in-the-azure-portal) yang ada.

1. Setelah berhasil mengautentikasi dan memperoleh token, buat token baru atau gunakan yang sudah `HttpClient` ada dengan "Otorisasi"**DefaultRequestHeaders tambahan** yang diatur ke **Bearer "token akses"** dan **Ocp-Apim-Subscription-Key** yang diatur ke [**kunci** langganan dari lingkungan](#get-started-trying-the-customer-insights-apis) Wawasan Pelanggan Anda.   
 
   Atur ulang header **otorisasi** bila sesuai. Misalnya, saat token kedaluwarsa.

1. Lewati `HttpClient` ini ke dalam konstruksi klien `CustomerInsights`.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Lakukan panggilan dengan klien ke "metode ekstensi"—misalnya `GetAllInstancesAsync`. Jika akses ke `Microsoft.Rest.HttpOperationResponse` yang mendasari lebih disukai, gunakan "metode pesan http"—misalnya `GetAllInstancesWithHttpMessagesAsync`.

1. Respons kemungkinan akan berupa jenis `object` karena metode dapat menghasilkan beberapa jenis (misalnya, `IList<InstanceInfo>` dan `ApiErrorResult`). Untuk memeriksa jenis hasil, Anda dapat dengan aman mentransmisikan objek ke jenis respons yang ditentukan pada [halaman rincian API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) untuk operasi tersebut.    
   
   Jika diperlukan informasi lebih lanjut tentang permintaan, gunakan **metode pesan http** untuk mengakses objek respons mentah.

### <a name="nodejs-package"></a>Paket NodeJS

Gunakan pustaka klien NodeJS yang tersedia melalui NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Paket Python

Gunakan pustaka klien Python yang tersedia melalui PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
