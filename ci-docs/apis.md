---
title: Bekerja dengan API Customer Insights
description: Gunakan API dan pahami batasan.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387344"
---
# <a name="work-with-customer-insights-apis"></a>Bekerja dengan API Customer Insights

Dynamics 365 Customer Insights menyediakan API untuk membangun aplikasi Anda sendiri berdasarkan data Anda dalam Customer Insights.

> [!IMPORTANT]
> Rincian API ini, tercantum pada [referensi API customer insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Mereka mencakup informasi tambahan tentang operasi, parameter, dan respons.

Coba API Customer Insights, buat Azure App Registration, dan mulai menggunakan pustaka klien.

## <a name="get-started-trying-the-customer-insights-apis"></a>Memulai mencoba API Customer Insights

Aktifkan API Customer Insights dan cobalah. Admin Customer Insights harus mengaktifkan akses API ke Customer Insights. Setelah akses diaktifkan, setiap pengguna dapat menggunakan API dengan kunci langganan.

1. [Masuk](https://home.ci.ai.dynamics.com) ke Customer Insights. Jika Anda belum memiliki langganan, [Daftar untuk versi uji coba dari Customer Insights](https://aka.ms/tryci).

1. Buka **Keamanan** > **Admin** dan pilih tab **API**.

1. Jika akses API ke lingkungan belum disiapkan, pilih **Aktifkan**.

   Mengaktifkan API akan membuat kunci langganan utama dan sekunder untuk instans yang digunakan dalam permintaan API. Untuk meregenerasi kunci, pilih **Regenerasi primer** atau **Regenerasi sekunder** pada tab **API**.

1. Pilih [**Jelajahi API**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) kami untuk mencoba API.

1. Cari dan pilih operasi API dan pilih **Coba**.

   :::image type="content" source="media/try-api.png" alt-text="Cara menguji API.":::

1. Pada panel sisi, atur nilai dalam menu dropdown **Otorisasi** ke **implisit**. Header `Authorization` ditambahkan dengan token penahan. Kunci langganan Anda diisi secara otomatis.
  
1. Atau, Tambahkan semua parameter kueri yang diperlukan.

1. Gulir ke bagian bawah panel samping, lalu pilih **kirim**.

   Respons HTTP ditampilkan di bagian bawah panel.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Buat pendaftaran Aplikasi baru di portal Azure

Buat pendaftaran [aplikasi baru](/graph/auth-register-app-v2) untuk menggunakan API Customer Insights di aplikasi Azure menggunakan izin yang didelegasikan.

1. Selesaikan bagian [Memulai](#get-started-trying-the-customer-insights-apis).

1. Masuk ke [portal Azure](https://portal.azure.com) dengan akun yang dapat mengakses data Customer Insights.

1. Cari lalu pilih **Pendaftaran aplikasi**.

1. Pilih **pendaftaran baru** berikan nama aplikasi dan pilih jenis akun.

   Atau, tambahkan URL pengalihan. http://localhost cukup untuk mengembangkan aplikasi di komputer lokal.

1. Pilih **Daftarkan**.

1. Di pendaftaran aplikasi baru, buka **izin API**.

1. Pilih **Tambahkan izin** dan pilih **Dynamics 365 AI for Customer Insights** di panel samping.

1. Untuk **jenis izin**, pilih **Izin yang didelegasikan**, lalu izin **user_impersonation**.

1. Pilih **Tambahkan izin**.

1. Pilih **Berikan izin admin untuk...** untuk menyelesaikan pendaftaran aplikasi.

1. Untuk mengakses API tanpa pengguna masuk, buka [Izin](#server-to-server-application-permissions) aplikasi server-ke-server.

Anda dapat menggunakan ID Aplikasi/Klien untuk pendaftaran aplikasi ini dengan [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) untuk mendapatkan token pembawa untuk dikirim dengan permintaan Anda ke API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Untuk informasi tentang menggunakan API di pustaka klien kami, lihat [pustaka klien Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Izin aplikasi server-ke-server

Buat pendaftaran aplikasi yang tidak memerlukan interaksi pengguna dan dapat dijalankan di server.

1. Di pendaftaran aplikasi di portal Azure, buka **izin api**.

1. Pilih **Tambahkan Izin**.

1. Pilih tab **API organisasi saya menggunakan**, lalu pilih **Dynamics 365 AI for Customer Insights** dari daftar.

1. Untuk **jenis izin**, pilih **Izin Aplikasi**, lalu izin **CustomerInsights.Api.All**.

1. Pilih **Tambahkan izin**.

1. Kembali ke **izin API** untuk pendaftaran aplikasi Anda.

1. Pilih **Berikan izin admin untuk...** untuk menyelesaikan pendaftaran aplikasi.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Tambahkan nama pendaftaran aplikasi sebagai pengguna di Customer Insights.

   1. Buka Customer Insights, buka **Keamanan** > **Admin** dan pilih **Tambahkan pengguna**.

   1. Cari nama pendaftaran aplikasi, pilih dari hasil pencarian, lalu pilih **Simpan**.

## <a name="sample-queries"></a>Contoh kueri

Untuk daftar singkat kueri sampel OData untuk bekerja dengan API, lihat [Contoh](odata-examples.md) kueri OData.

## <a name="customer-insights-client-libraries"></a>Pustaka klien Customer Insights

Mulai menggunakan pustaka klien yang tersedia untuk API Customer Insights. Semua kode sumber pustaka dan aplikasi sampel dapat ditemukan di [halaman GitHub Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Gunakan pustaka klien C# dari NuGet.org. Saat ini, paket menargetkan kerangka kerja netstandard2.0 dan netcoreapp2.0. Untuk informasi selengkapnya tentang NuGet paket, lihat [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Tambahkan pustaka klien C# ke proyek C#

1. Di Visual Studio, buka **manajer paket NuGet** untuk proyek Anda.

1. Cari **Microsoft.Dynamics.CustomerInsights.Api**.

1. Pilih **Instal** untuk menambahkan paket ke proyek.

   Atau, jalankan perintah ini di **konsol manajer paket NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Gunakan pustaka klien C#

1. Gunakan [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) untuk membuat `AccessToken` menggunakan [pendaftaran aplikasi Azure](#create-a-new-app-registration-in-the-azure-portal) yang ada.

1. Setelah berhasil mengautentikasi dan memperoleh token, buat yang baru atau gunakan yang sudah ada `HttpClient` dengan **"Otorisasi"** DefaultRequestHeaders yang diatur ke **Bearer "token akses"** dan **Ocp-Apim-Subscription-Key** yang diatur ke [**kunci** langganan dari lingkungan](#get-started-trying-the-customer-insights-apis) Customer Insights Anda.   

   Atur ulang header **otorisasi** bila sesuai. Misalnya, saat token kedaluwarsa.

1. Lewati `HttpClient` ini ke dalam konstruksi klien `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Lakukan panggilan dengan klien ke "metode ekstensi", misalnya `GetAllInstancesAsync`. Jika akses ke underlying `Microsoft.Rest.HttpOperationResponse` lebih disukai, gunakan "metode pesan http", misalnya,`GetAllInstancesWithHttpMessagesAsync`.

1. Respons kemungkinan `object` mengetik karena metode ini dapat mengembalikan beberapa jenis (misalnya, `IList<InstanceInfo>` dan `ApiErrorResult`). Untuk memeriksa jenis pengembalian, gunakan objek dalam jenis respons yang ditentukan pada halaman [detail API untuk operasi tersebut](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).

   Jika diperlukan informasi lebih lanjut tentang permintaan, gunakan **metode pesan http** untuk mengakses objek respons mentah.

### <a name="nodejs-package"></a>Paket NodeJS

Gunakan pustaka klien NodeJS yang tersedia melalui NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Paket Python

Gunakan pustaka klien Python yang tersedia melalui PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
