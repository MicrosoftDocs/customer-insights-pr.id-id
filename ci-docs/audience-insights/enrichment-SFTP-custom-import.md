---
title: Pengayaan dengan impor kustom SFTP
description: Informasi umum tentang pengayaan impor kustom SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269610"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="bbf61-103">Memperkaya profil pelanggan dengan data kustom (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="bbf61-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="bbf61-104">Impor kustom protokol transfer file aman (SFTP) memungkinkan Anda mengimpor data yang tidak harus melalui proses penyatuan data.</span><span class="sxs-lookup"><span data-stu-id="bbf61-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="bbf61-105">Cara yang fleksibel, aman, dan mudah untuk membawa data Anda.</span><span class="sxs-lookup"><span data-stu-id="bbf61-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="bbf61-106">Impor kustom SFTP dapat digunakan bersama dengan [ekspor SFTP](export-sftp.md) yang memungkinkan Anda mengekspor data profil pelanggan yang diperlukan untuk pengayaan.</span><span class="sxs-lookup"><span data-stu-id="bbf61-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="bbf61-107">Data selanjutnya dapat diproses, diperkaya, dan impor kustom SFTP dapat digunakan untuk menghadirkan data yang diperkaya kembali ke kemampuan wawasan audiens Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bbf61-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bbf61-108">Prasyarat</span><span class="sxs-lookup"><span data-stu-id="bbf61-108">Prerequisites</span></span>

<span data-ttu-id="bbf61-109">Untuk mengkonfigurasikan impor kustom SFTP, persyaratan berikut harus dipenuhi:</span><span class="sxs-lookup"><span data-stu-id="bbf61-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="bbf61-110">Anda memiliki kredensial pengguna (nama pengguna dan sandi) untuk lokasi SFTP dengan data yang akan diimpor.</span><span class="sxs-lookup"><span data-stu-id="bbf61-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="bbf61-111">Anda memiliki URL dan nomor port (biasanya 22) untuk host SFTP.</span><span class="sxs-lookup"><span data-stu-id="bbf61-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="bbf61-112">Anda memiliki nama file dan lokasi file yang akan diimpor pada host SFTP.</span><span class="sxs-lookup"><span data-stu-id="bbf61-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="bbf61-113">Ada file *model.JSON* yang menentukan skema untuk data yang akan diimpor.</span><span class="sxs-lookup"><span data-stu-id="bbf61-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="bbf61-114">File ini harus berada di direktori yang sama dengan file yang akan diimpor.</span><span class="sxs-lookup"><span data-stu-id="bbf61-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="bbf61-115">Anda memiliki izin [administratif](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="bbf61-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="bbf61-116">Konfigurasi</span><span class="sxs-lookup"><span data-stu-id="bbf61-116">Configuration</span></span>

1. <span data-ttu-id="bbf61-117">Buka tab **Data** > **Pengayaan** dan pilih **Temukan**.</span><span class="sxs-lookup"><span data-stu-id="bbf61-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="bbf61-118">Di **petak impor kustom SFTP** pilih **Perkaya data**.</span><span class="sxs-lookup"><span data-stu-id="bbf61-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bbf61-119">![petak Impor Kustom SFTP](media/SFTP_Custom_Import_tile.png "petak Impor Kustom SFTP")</span><span class="sxs-lookup"><span data-stu-id="bbf61-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="bbf61-120">Pilih **Mulai** dan berikan kredensial dan alamat untuk server SFTP.</span><span class="sxs-lookup"><span data-stu-id="bbf61-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="bbf61-121">Misalnya, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="bbf61-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="bbf61-122">Masukkan nama file yang berisi data dan jalur ke file di server SFTP jika tidak di dalam folder root.</span><span class="sxs-lookup"><span data-stu-id="bbf61-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="bbf61-123">Konfirmasikan semua input dengan memilih **Sambungkan ke impor kustom**.</span><span class="sxs-lookup"><span data-stu-id="bbf61-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bbf61-124">![Flyout konfigurasi impor kustom SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Flyout konfigurasi impor kustom SFTP")</span><span class="sxs-lookup"><span data-stu-id="bbf61-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="bbf61-125">Menentukan pemetaan bidang</span><span class="sxs-lookup"><span data-stu-id="bbf61-125">Defining field mappings</span></span> 

<span data-ttu-id="bbf61-126">Direktori yang berisi file yang akan diimpor pada server SFTP juga harus berisi file *model.JSON*.</span><span class="sxs-lookup"><span data-stu-id="bbf61-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="bbf61-127">File ini mendefinisikan skema yang akan digunakan untuk mengimpor data.</span><span class="sxs-lookup"><span data-stu-id="bbf61-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="bbf61-128">Skema harus menggunakan [Common Data Model](https://docs.microsoft.com/common-data-model/) untuk menentukan pemetaan bidang.</span><span class="sxs-lookup"><span data-stu-id="bbf61-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="bbf61-129">Contoh sederhana dari file model.JSON terlihat seperti ini:</span><span class="sxs-lookup"><span data-stu-id="bbf61-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="bbf61-130">Hasil pengayaan</span><span class="sxs-lookup"><span data-stu-id="bbf61-130">Enrichment results</span></span>

<span data-ttu-id="bbf61-131">Untuk memulai proses pengayaan, pilih **Jalankan** dari bilah perintah.</span><span class="sxs-lookup"><span data-stu-id="bbf61-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="bbf61-132">Anda juga dapat membiarkan sistem menjalankan pengayaan secara otomatis sebagai bagian dari [penyegaran terjadwal](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bbf61-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bbf61-133">Waktu pemrosesan tergantung pada ukuran data yang akan diimpor dan sambungan ke server SFTP.</span><span class="sxs-lookup"><span data-stu-id="bbf61-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="bbf61-134">Setelah proses pengayaan selesai, Anda dapat meninjau data pengayaan kustom yang baru diimpor dalam **pengayaan saya**.</span><span class="sxs-lookup"><span data-stu-id="bbf61-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="bbf61-135">Selain itu, Anda akan menemukan waktu pembaruan terakhir dan jumlah profil yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="bbf61-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="bbf61-136">Anda dapat mengakses tampilan rinci setiap profil diperkaya dengan memilih **Lihat data yang diperkaya**.</span><span class="sxs-lookup"><span data-stu-id="bbf61-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bbf61-137">Langkah berikutnya</span><span class="sxs-lookup"><span data-stu-id="bbf61-137">Next steps</span></span>

<span data-ttu-id="bbf61-138">Bangun di atas data pelanggan yang diperkaya.</span><span class="sxs-lookup"><span data-stu-id="bbf61-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="bbf61-139">Buat [segmen](segments.md), [tindakan](measures.md), dan [ekspor data](export-destinations.md) untuk memberikan pengalaman yang disesuaikan dengan pelanggan Anda.</span><span class="sxs-lookup"><span data-stu-id="bbf61-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]