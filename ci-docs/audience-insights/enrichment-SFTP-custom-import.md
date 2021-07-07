---
title: Pengayaan dengan impor kustom SFTP
description: Informasi umum tentang pengayaan impor kustom SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304654"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="4d6ec-103">Memperkaya profil pelanggan dengan data kustom (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="4d6ec-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="4d6ec-104">Impor kustom protokol transfer file aman (SFTP) memungkinkan Anda mengimpor data yang tidak harus melalui proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="4d6ec-105">Cara yang fleksibel, aman, dan mudah untuk membawa data Anda.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="4d6ec-106">Impor kustom SFTP dapat digunakan bersama dengan [ekspor SFTP](export-sftp.md) yang memungkinkan Anda mengekspor data profil pelanggan yang diperlukan untuk pengayaan.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="4d6ec-107">Selanjutnya data dapat diproses dan diperkaya, dan impor kustom SFTP dapat digunakan untuk mengembalikan data yang diperkaya menjadi kemampuan wawasan audiens Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4d6ec-108">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="4d6ec-108">Prerequisites</span></span>

<span data-ttu-id="4d6ec-109">Untuk mengkonfigurasikan impor kustom SFTP, persyaratan berikut harus dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="4d6ec-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4d6ec-110">Anda memiliki nama file dan lokasi (jalur) file yang akan diimpor di host SFTP.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="4d6ec-111">Ada file *model.json* yang menentukan [skema Common Data Model](/common-data-model/) untuk data yang akan diimpor.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="4d6ec-112">File ini harus berada di direktori yang sama dengan file yang akan diimpor.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="4d6ec-113">Koneksi SFTP telah dikonfigurasi oleh administrator *atau* Anda memiliki izin [administrator](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="4d6ec-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="4d6ec-114">Anda akan memerlukan kredensial pengguna, URL, dan nomor port untuk lokasi SFTP tempat Anda ingin mengimpor data.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="4d6ec-115">Mengonfigurasi impor</span><span class="sxs-lookup"><span data-stu-id="4d6ec-115">Configure the import</span></span>

1. <span data-ttu-id="4d6ec-116">Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="4d6ec-117">Pilih **Perkaya data saya** di **petak impor kustom SFTP** lalu pilih **Mulai**.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Petak Impor Kustom SFTP.":::

1. <span data-ttu-id="4d6ec-119">Pilih [koneksi](connections.md) dari daftar drop-down.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="4d6ec-120">Hubungi administrator jika tidak ada koneksi yang tersedia.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="4d6ec-121">Jika Anda administrator, Anda dapat membuat sambungan dengan memilih **Tambah sambungan** dan memilih **Impor Kustom SFTP** dari daftar dropdown.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="4d6ec-122">Pilih **Sambungkan ke Impor Kustom** untuk mengonfirmasi koneksi yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="4d6ec-123">Pilih **Berikutnya**, lalu masukkan **Jalur** dan **Nama File** dari file data yang akan diimpor.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Cuplikan layar saat memasukkan lokasi data.":::

1. <span data-ttu-id="4d6ec-125">Pilih **Selanjutnya** dan berikan nama untuk pengayaan dan nama untuk entitas output.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="4d6ec-126">Pilih **Simpan pengayaan** setelah meninjau pilihan Anda.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="4d6ec-127">Mengonfigurasi koneksi untuk Impor Kustom SFTP</span><span class="sxs-lookup"><span data-stu-id="4d6ec-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="4d6ec-128">Anda perlu menjadi administrator untuk mengonfigurasi koneksi.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="4d6ec-129">Pilih **Tambahkan koneksi** saat mengonfigurasi pengayaan *atau* masuk ke **Admin** > **Koneksi** dan pilih **Konfigurasi** pada petak Impor Kustom.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="4d6ec-130">Masukkan nama untuk koneksi dalam kotak **nama tampilan**.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="4d6ec-131">Masukkan nama pengguna, sandi, dan URL host yang valid untuk server tempat SFTP yang datanya akan diimpor berada.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="4d6ec-132">Tinjau dan berikan izin untuk **privasi dan kepatuhan data** dengan memilih kotak centang **Saya setuju**.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="4d6ec-133">Pilih **Verifikasi** untuk memvalidasi konfigurasi.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="4d6ec-134">Setelah verifikasi selesai, sambungan dapat disimpan dengan memilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="4d6ec-135">![halaman Panel Konfigurasi koneksi Experian](media/enrichment-SFTP-connection.png "halaman Panel Konfigurasi koneksi Experian")</span><span class="sxs-lookup"><span data-stu-id="4d6ec-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="4d6ec-136">Menentukan pemetaan bidang</span><span class="sxs-lookup"><span data-stu-id="4d6ec-136">Defining field mappings</span></span> 

<span data-ttu-id="4d6ec-137">Direktori yang berisi file yang akan diimpor pada server SFTP juga harus berisi file *model.JSON*.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="4d6ec-138">File ini mendefinisikan skema yang akan digunakan untuk mengimpor data.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="4d6ec-139">Skema harus menggunakan [Common Data Model](/common-data-model/) untuk menentukan pemetaan bidang.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="4d6ec-140">Contoh sederhana dari file model.JSON terlihat seperti ini:</span><span class="sxs-lookup"><span data-stu-id="4d6ec-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="4d6ec-141">Hasil pengayaan</span><span class="sxs-lookup"><span data-stu-id="4d6ec-141">Enrichment results</span></span>

<span data-ttu-id="4d6ec-142">Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="4d6ec-143">Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4d6ec-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4d6ec-144">Waktu pemrosesan tergantung pada ukuran data yang akan diimpor dan sambungan ke server SFTP.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="4d6ec-145">Setelah proses pengayaan selesai, Anda dapat meninjau data pengayaan kustom yang baru diimpor dalam **pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="4d6ec-146">Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4d6ec-147">Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4d6ec-148">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="4d6ec-148">Next steps</span></span>

<span data-ttu-id="4d6ec-149">Bangun di atas data pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4d6ec-150">Buat [segmen](segments.md) dan [ukuran](measures.md), dan [ekspor data](export-destinations.md) untuk memberikan pengalaman pribadi kepada pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="4d6ec-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
