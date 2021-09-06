---
title: Menyambung ke akun Azure Data Lake Storage menggunakan prinsipal layanan
description: Gunakan prinsipal layanan Azure untuk terhubung ke data lake Anda sendiri.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461152"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Menyambung ke akun Azure Data Lake Storage menggunakan prinsipal layanan Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
Alat otomatis yang menggunakan layanan Azure harus selalu memiliki izin terbatas. Selain masuk aplikasi sebagai pengguna yang memiliki hak istimewa, Azure menawarkan prinsipal layanan. Baca terus untuk mempelajari cara menghubungkan Dynamics 365 Customer Insights dengan akun Azure Data Lake Storage menggunakan prinsipal layanan Azure, bukan kunci akun penyimpanan. 

Anda dapat menggunakan prinsipal utama untuk [menambahkan atau mengedit folder Common Data Model sebagai sumber data](connect-common-data-model.md), atau [membuat atau memperbarui lingkungan](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - Akun Data Lake Storage yang akan menggunakan<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> prinsipal layanan harus memiliki [namespace hierarkis diaktifkan](/azure/storage/blobs/data-lake-storage-namespace).
> - Anda memerlukan izin admin untuk langganan Azure Anda untuk membuat prinsipal layanan.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Membuat prinsipal layanan Azure untuk Customer Insights

Sebelum membuat layanan baru untuk wawasan audiens atau wawasan keterlibatan, pastikan sudah ada di organisasi Anda.

### <a name="look-for-an-existing-service-principal"></a>Mencari prinsipal layanan yang ada

1. Buka [portal admin Azure](https://portal.azure.com), lalu masuk ke organisasi Anda.

2. Dari **Layanan Azure**, pilih **Azure Active Directory**.

3. Di dalam **Kelola**, pilih **aplikasi Enterprise**.

4. Cari Microsoft<!--note from editor: Via Microsoft Writing Style Guide.--> ID aplikasi:
   - Wawasan Audiens: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` dengan nama `Dynamics 365 AI for Customer Insights`
   - Wawasan keterlibatan: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` dengan nama `Dynamics 365 AI for Customer Insights engagement insights`

5. Jika Anda menemukan rekaman yang cocok, berarti principal layanan sudah ada. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Cuplikan layar yang menampilkan prinsipal layanan yang ada.":::
   
6. Jika tidak ada hasil, buat prinsipal layanan baru.

>[!NOTE]
>Agar dapat menggunakan kemampuan penuh Dynamics 365 Customer Insights, sebaiknya tambahkan kedua aplikasi ke prinsipal layanan.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Buat prinsipal layanan baru
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Instal versi terbaru Azure Active Directory PowerShell untuk Graph. Untuk informasi lebih lanjut, buka [Menginstal Azure Active Directory PowerShell untuk Graph](/powershell/azure/active-directory/install-adv2).

   1. Di PC, pilih tombol Windows di keyboard dan cari **Windows PowerShell**, lalu pilih **Jalankan sebagai administrator**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. Di jendela PowerShell yang terbuka, masukkan `Install-Module AzureAD`.

2. Buat prinsipal layanan untuk Customer Insights dengan modul Azure AD PowerShell.

   1. Di jendela PowerShell, masukkan `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Ganti *"[ID penyewa Anda]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> dengan ID aktual penyewa tempat Anda ingin membuat prinsipal layanan. Parameter nama lingkungan, `AzureEnvironmentName` adalah opsional.
  
   1. Masukkan `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Perintah ini akan membuat prinsipal layanan untuk wawasan audiens pada penyewa yang dipilih. 

   1. Masukkan `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Perintah ini membuat prinsipal layanan untuk wawasan keterlibatan<!--note from editor: Edit okay?--> pada penyewa yang dipilih.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Berikan izin kepada prinsipal layanan untuk mengakses akun Penyimpanan

Buka portal Azure untuk memberikan izin kepada prinsipal layanan untuk akun penyimpanan yang ingin anda gunakan di wawasan audiens.

1. Buka [portal admin Azure](https://portal.azure.com), lalu masuk ke organisasi Anda.

1. Buka akun penyimpanan yang akan menjadi prinsipal layanan untuk wawasan audiens agar dapat diakses.

1. Pada panel kiri, pilih **kontrol akses (IAM)**, lalu pilih **Tambah** > **Tambah penetapan peran**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Cuplikan layar yang menampilkan portal Azure saat menambahkan penetapan peran.":::

1. Di panel **Tambah penetapan peran**, atur properti berikut:
   - Peran: **kontributor data Blob penyimpanan**
   - Tetapkan akses ke: **pengguna, grup, atau prinsipal Layanan**
   - Pilih: **Dynamics 365 AI for Customer Insights** dan **wawasan keterlibatan Dynamics 365 AI for Customer Insights** (kedua [prinsipal layanan](#create-a-new-service-principal) yang Anda buat sebelumnya dalam prosedur ini)

1.  Pilih **Simpan**.

Dapat memakan waktu hingga 15 menit untuk menyebarkan perubahan.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Masukkan ID sumber daya azure atau rincian langganan azure di lampiran akun penyimpanan ke wawasan audiens

Anda dapat<!--note from editor: Edit suggested only if this section is optional.--> melampirkan akun Data Lake Storage dalam wawasan audiens untuk [menyimpan data output](manage-environments.md) atau [menggunakannya sebagai sumber data](connect-common-data-service-lake.md). Pilihan ini memungkinkan Anda memilih antara pendekatan berbasis sumber daya atau berbasis langganan. Tergantung pada pendekatan yang Anda pilih, ikuti prosedur di salah satu bagian berikut.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>Koneksi akun penyimpanan berbasis sumber daya

1. Buka [portal admin Azure](https://portal.azure.com), masuk ke langganan Anda dan buka akun penyimpanan.

1. Pada panel kiri, buka **Pengaturan** > **Properti**.

1. Salin nilai ID sumber daya akun penyimpanan.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salin ID sumber daya akun penyimpanan.":::

1. Dalam audiens, masukkan ID sumber daya pada bidang sumber daya yang ditampilkan di layar sambungan akun penyimpanan.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Masukkan informasi ID sumber daya akun penyimpanan.":::   

1. Lanjutkan dengan langkah yang tersisa di wawasan audiens untuk melampirkan akun penyimpanan.

### <a name="subscription-based-storage-account-connection"></a>Koneksi akun penyimpanan berbasis langganan

1. Buka [portal admin Azure](https://portal.azure.com), masuk ke langganan Anda dan buka akun penyimpanan.

1. Pada panel kiri, buka **Pengaturan** > **Properti**.

1. Tinjau **langganan**, **grup sumber daya**, dan **nama** akun penyimpanan untuk memastikan bahwa anda memilih nilai yang tepat di wawasan audiens.

1. Di wawasan audiens, pilih nilai untuk bidang terkait saat melampirkan akun penyimpanan.

1. Lanjutkan dengan langkah yang tersisa di wawasan audiens untuk melampirkan akun penyimpanan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]