---
title: Koneksi ke layanan lain dari Customer Insights.
description: Bagikan data ke layanan lain.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896101"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="46a5f-103">Ikhtisar koneksi (pratinjau)</span><span class="sxs-lookup"><span data-stu-id="46a5f-103">Connections (preview) overview</span></span>

<span data-ttu-id="46a5f-104">Koneksi adalah kunci untuk memungkinkan berbagi data ke dan dari Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="46a5f-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="46a5f-105">Setiap koneksi menetapkan berbagi data dengan layanan tertentu.</span><span class="sxs-lookup"><span data-stu-id="46a5f-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="46a5f-106">Koneksi adalah fondasi untuk [mengkonfigurasi pengayaan pihak ketiga](enrichment-hub.md) dan [mengonfigurasi ekspor](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="46a5f-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="46a5f-107">Sambungan yang sama dapat digunakan beberapa kali.</span><span class="sxs-lookup"><span data-stu-id="46a5f-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="46a5f-108">Misalnya, satu koneksi ke Dynamics 365 Marketing berfungsi untuk beberapa ekspor dan satu koneksi Leadspace dapat digunakan untuk beberapa pengayaan.</span><span class="sxs-lookup"><span data-stu-id="46a5f-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="46a5f-109">Buka **Admin** > **Koneksi** untuk membuat dan melihat koneksi.</span><span class="sxs-lookup"><span data-stu-id="46a5f-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="46a5f-110">Tab **Koneksi** memperlihatkan semua koneksi aktif.</span><span class="sxs-lookup"><span data-stu-id="46a5f-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="46a5f-111">Daftar memperlihatkan baris untuk setiap koneksi.</span><span class="sxs-lookup"><span data-stu-id="46a5f-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="46a5f-112">Dapatkan gambaran umum, deskripsi, dan cari tahu apa yang bisa Anda lakukan dengan setiap opsi ekstensibilitas pada tab **Temukan**.</span><span class="sxs-lookup"><span data-stu-id="46a5f-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="46a5f-113">Ekspor</span><span class="sxs-lookup"><span data-stu-id="46a5f-113">Exports</span></span>

<span data-ttu-id="46a5f-114">Hanya administrator yang dapat mengonfigurasi koneksi baru, tetapi mereka dapat memberikan akses ke kontributor untuk menggunakan koneksi yang ada.</span><span class="sxs-lookup"><span data-stu-id="46a5f-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="46a5f-115">Administrator mengontrol ke mana data dapat pergi, kontributor menentukan muatan dan frekuensi yang sesuai dengan kebutuhan mereka.</span><span class="sxs-lookup"><span data-stu-id="46a5f-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="46a5f-116">Untuk informasi selengkapnya, lihat [Mengizinkan kontributor menggunakan koneksi untuk ekspor](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="46a5f-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="46a5f-117">Pengayaan</span><span class="sxs-lookup"><span data-stu-id="46a5f-117">Enrichments</span></span>

<span data-ttu-id="46a5f-118">Hanya administrator yang dapat mengonfigurasi koneksi baru tetapi koneksi yang dibuat selalu tersedia untuk administrator dan kontributor.</span><span class="sxs-lookup"><span data-stu-id="46a5f-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="46a5f-119">Administrator mengelola kredensial dan memberikan persetujuan untuk transfer data.</span><span class="sxs-lookup"><span data-stu-id="46a5f-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="46a5f-120">Koneksi kemudian dapat digunakan untuk pengayaan oleh administrator dan kontributor.</span><span class="sxs-lookup"><span data-stu-id="46a5f-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="46a5f-121">Tambah koneksi baru</span><span class="sxs-lookup"><span data-stu-id="46a5f-121">Add a new connection</span></span>

<span data-ttu-id="46a5f-122">Untuk menambahkan koneksi, Anda perlu memiliki [izin administrator](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="46a5f-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="46a5f-123">Jika Anda tersambung ke layanan Microsoft lainnya, kami menganggap kedua layanan berada dalam organisasi yang sama.</span><span class="sxs-lookup"><span data-stu-id="46a5f-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="46a5f-124">Buka **Admin** > **Koneksi (pratinjau)**.</span><span class="sxs-lookup"><span data-stu-id="46a5f-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="46a5f-125">Buka tab **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="46a5f-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="46a5f-126">Pilih **Tambahkan Koneksi** untuk membuat koneksi baru.</span><span class="sxs-lookup"><span data-stu-id="46a5f-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="46a5f-127">Pilih dari menu tarik-turun tipe koneksi apa yang ingin Anda buat.</span><span class="sxs-lookup"><span data-stu-id="46a5f-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="46a5f-128">Di panel **Siapkan koneksi**, berikan detail yang diperlukan.</span><span class="sxs-lookup"><span data-stu-id="46a5f-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="46a5f-129">**Nama tampilan** dan tipe koneksi menjelaskan koneksi.</span><span class="sxs-lookup"><span data-stu-id="46a5f-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="46a5f-130">Sebaiknya pilih nama yang menjelaskan tujuan dan target koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="46a5f-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="46a5f-131">Bidang yang tepat tergantung pada layanan apa yang Anda sambungkan.</span><span class="sxs-lookup"><span data-stu-id="46a5f-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="46a5f-132">Anda dapat mempelajari detail jenis koneksi tertentu di artikel tentang layanan target.</span><span class="sxs-lookup"><span data-stu-id="46a5f-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="46a5f-133">Pilih **Simpan** untuk membuat koneksi.</span><span class="sxs-lookup"><span data-stu-id="46a5f-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="46a5f-134">Anda juga dapat memilih **konfigurasi** di ubin pada tab **temukan**.</span><span class="sxs-lookup"><span data-stu-id="46a5f-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="46a5f-135">Izinkan kontributor menggunakan koneksi untuk ekspor</span><span class="sxs-lookup"><span data-stu-id="46a5f-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="46a5f-136">Saat menyiapkan atau mengedit koneksi ekspor, Anda memilih pengguna mana yang diizinkan menggunakan koneksi khusus ini untuk menentukan [ekspor](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="46a5f-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="46a5f-137">Secara default koneksi tersedia untuk pengguna dengan peran administrator.</span><span class="sxs-lookup"><span data-stu-id="46a5f-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="46a5f-138">Anda bisa mengubah pengaturan ini di **Pilih siapa yang bisa menggunakan koneksi ini** dan mengizinkan pengguna dengan peran kontributor untuk menggunakan koneksi ini.</span><span class="sxs-lookup"><span data-stu-id="46a5f-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="46a5f-139">Kontributor tidak akan dapat melihat atau mengedit koneksi.</span><span class="sxs-lookup"><span data-stu-id="46a5f-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="46a5f-140">Mereka hanya akan melihat nama tampilan dan jenisnya ketika membuat ekspor.</span><span class="sxs-lookup"><span data-stu-id="46a5f-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="46a5f-141">Dengan berbagi koneksi, Anda memperbolehkan kontributor menggunakan koneksi.</span><span class="sxs-lookup"><span data-stu-id="46a5f-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="46a5f-142">Kontributor akan melihat koneksi bersama saat mereka menyiapkan ekspor.</span><span class="sxs-lookup"><span data-stu-id="46a5f-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="46a5f-143">Mereka dapat mengelola setiap ekspor yang menggunakan koneksi khusus ini.</span><span class="sxs-lookup"><span data-stu-id="46a5f-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="46a5f-144">Anda dapat mengubah pengaturan ini sambil mempertahankan ekspor yang telah ditentukan oleh kontributor.</span><span class="sxs-lookup"><span data-stu-id="46a5f-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="46a5f-145">Edit koneksi</span><span class="sxs-lookup"><span data-stu-id="46a5f-145">Edit a connection</span></span>

1. <span data-ttu-id="46a5f-146">Buka **Admin** > **Koneksi (pratinjau)**.</span><span class="sxs-lookup"><span data-stu-id="46a5f-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="46a5f-147">Buka tab **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="46a5f-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="46a5f-148">Pilih elipsis vertikal untuk koneksi yang ingin diedit.</span><span class="sxs-lookup"><span data-stu-id="46a5f-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="46a5f-149">Pilih **Edit**.</span><span class="sxs-lookup"><span data-stu-id="46a5f-149">Select **Edit**.</span></span>

1. <span data-ttu-id="46a5f-150">Ubah nilai yang ingin Anda perbarui dan pilih **Simpan**.</span><span class="sxs-lookup"><span data-stu-id="46a5f-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="46a5f-151">Hapus koneksi</span><span class="sxs-lookup"><span data-stu-id="46a5f-151">Remove a connection</span></span>

<span data-ttu-id="46a5f-152">Jika koneksi yang Anda hapus digunakan oleh pengayaan atau ekspor, Pertama-tama Anda harus melepaskan atau menghapusnya.</span><span class="sxs-lookup"><span data-stu-id="46a5f-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="46a5f-153">Dialog hapus akan memandu Anda ke pengayaan atau ekspor yang relevan.</span><span class="sxs-lookup"><span data-stu-id="46a5f-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="46a5f-154">Pengayaan dan ekspor terpisah menjadi tidak aktif.</span><span class="sxs-lookup"><span data-stu-id="46a5f-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="46a5f-155">Anda mengaktifkannya kembali dengan menambahkan koneksi lain ke koneksi tersebut di halaman [Pengayaan](enrichment-hub.md) atau [Ekspor](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="46a5f-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="46a5f-156">Buka **Admin** > **Koneksi (pratinjau)**.</span><span class="sxs-lookup"><span data-stu-id="46a5f-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="46a5f-157">Buka tab **Koneksi**.</span><span class="sxs-lookup"><span data-stu-id="46a5f-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="46a5f-158">Pilih elipsis vertikal untuk koneksi yang ingin dihapus.</span><span class="sxs-lookup"><span data-stu-id="46a5f-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="46a5f-159">Dari menu dropdown, pilih **hilangkan**.</span><span class="sxs-lookup"><span data-stu-id="46a5f-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="46a5f-160">Dialog konfirmasi akan ditampilkan.</span><span class="sxs-lookup"><span data-stu-id="46a5f-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="46a5f-161">Jika ada pengayaan atau ekspor menggunakan koneksi ini, pilih tombol untuk melihat apa yang menggunakan koneksi.</span><span class="sxs-lookup"><span data-stu-id="46a5f-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="46a5f-162">**Ekspor:** Anda dapat memilih untuk menghapus atau memutuskan sambungan ekspor agar dapat menghapus koneksi.</span><span class="sxs-lookup"><span data-stu-id="46a5f-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="46a5f-163">Untuk memutuskan sambungan ekspor, administrator bisa menggunakan tindakan **Putuskan sambungan**.</span><span class="sxs-lookup"><span data-stu-id="46a5f-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="46a5f-164">Tindakan ini tersedia untuk ekspor individual dan beberapa ekspor yang dipilih.</span><span class="sxs-lookup"><span data-stu-id="46a5f-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="46a5f-165">Dengan memutuskan sambungan, Anda menyimpan konfigurasi ekspor, tetapi tidak akan dijalankan hingga koneksi lain ditambahkan ke konfigurasi tersebut.</span><span class="sxs-lookup"><span data-stu-id="46a5f-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="46a5f-166">**Pengayaan:** Anda dapat memilih untuk menghapus atau menonaktifkan pengayaan agar dapat menghapus koneksi.</span><span class="sxs-lookup"><span data-stu-id="46a5f-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="46a5f-167">Setelah koneksi tidak memiliki dependensi lagi, kembali ke **Admin** > **Koneksi** dan coba hapus koneksi lagi.</span><span class="sxs-lookup"><span data-stu-id="46a5f-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="46a5f-168">Pilih **Hapus**, untuk mengonfirmasi penghapusan tersebut.</span><span class="sxs-lookup"><span data-stu-id="46a5f-168">To confirm the deletion select **Remove**.</span></span>

