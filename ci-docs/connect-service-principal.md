---
title: Menyambung ke akun Azure Data Lake Storage menggunakan prinsipal layanan
description: Gunakan prinsipal layanan Azure untuk terhubung ke data lake Anda sendiri.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 1dd99edc327bd41b0442b390f2e4f8664269f553
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642659"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Menyambung ke akun Azure Data Lake Storage menggunakan prinsipal layanan Azure

Artikel ini membahas cara terhubung Dynamics 365 Customer Insights dengan akun dengan Azure Data Lake Storage menggunakan perwakilan layanan Azure alih-alih kunci akun penyimpanan. 

Alat otomatis yang menggunakan layanan Azure harus selalu memiliki izin terbatas. Selain masuk aplikasi sebagai pengguna yang memiliki hak istimewa, Azure menawarkan prinsipal layanan. Anda dapat menggunakan perwakilan layanan untuk menambahkan atau mengedit folder Model Data Umum dengan [aman sebagai sumber data](connect-common-data-model.md) atau [membuat atau memperbarui lingkungan](create-environment.md).

> [!IMPORTANT]
> - Akun Penyimpanan Data Lake yang akan menggunakan perwakilan layanan harus Gen2 dan memiliki [ruang nama hierarki diaktifkan](/azure/storage/blobs/data-lake-storage-namespace). Akun penyimpanan Azure Data Lake Gen1 tidak didukung.
> - Anda memerlukan izin admin untuk langganan Azure Anda untuk membuat perwakilan layanan.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Membuat prinsipal layanan Azure untuk Customer Insights

Sebelum membuat perwakilan layanan baru untuk Customer Insights, periksa apakah sudah ada di organisasi Anda.

### <a name="look-for-an-existing-service-principal"></a>Mencari prinsipal layanan yang ada

1. Buka [portal admin Azure](https://portal.azure.com), lalu masuk ke organisasi Anda.

2. Dari **Layanan Azure**, pilih **Azure Active Directory**.

3. Di dalam **Kelola**, pilih **aplikasi Enterprise**.

4. Cari ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` aplikasi Microsoft dengan nama `Dynamics 365 AI for Customer Insights`.

5. Jika Anda menemukan rekaman yang cocok, berarti principal layanan sudah ada. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Cuplikan layar yang menampilkan prinsipal layanan yang ada.":::
   
6. Jika tidak ada hasil, buat prinsipal layanan baru.

### <a name="create-a-new-service-principal"></a>Buat prinsipal layanan baru

1. Instal versi terbaru Azure Active Directory PowerShell untuk Graph. Untuk informasi lebih lanjut, buka [Menginstal Azure Active Directory PowerShell untuk Graph](/powershell/azure/active-directory/install-adv2).

   1. Di PC, pilih tombol Windows di keyboard dan cari **Windows PowerShell**, lalu pilih **Jalankan sebagai administrator**.
   
   1. Di jendela PowerShell yang terbuka, masukkan `Install-Module AzureAD`.

2. Buat prinsipal layanan untuk Customer Insights dengan modul Azure AD PowerShell.

   1. Di jendela PowerShell, masukkan `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Ganti *[ID Direktori Anda]* dengan ID Direktori sebenarnya dari langganan Azure Anda di mana Anda ingin membuat perwakilan layanan. Parameter nama lingkungan, `AzureEnvironmentName` adalah opsional.
  
   1. Masukkan `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Perintah ini membuat perwakilan layanan untuk Wawasan Pelanggan pada langganan Azure yang dipilih. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Berikan izin kepada prinsipal layanan untuk mengakses akun Penyimpanan

Buka portal Microsoft Azure untuk memberikan izin kepada perwakilan layanan untuk akun penyimpanan yang ingin Anda gunakan di Customer Insights.

1. Buka [portal admin Azure](https://portal.azure.com), lalu masuk ke organisasi Anda.

1. Buka akun penyimpanan yang Anda inginkan agar perwakilan layanan untuk akses Customer Insights.

1. Pada panel kiri, pilih **kontrol akses (IAM)**, lalu pilih **Tambah** > **Tambah penetapan peran**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Cuplikan layar yang menampilkan portal Azure saat menambahkan penetapan peran.":::

1. Di panel **Tambah penetapan peran**, atur properti berikut:
   - Peran: **kontributor data Blob penyimpanan**
   - Tetapkan akses ke: **pengguna, grup, atau prinsipal Layanan**
   - Pilih anggota: **Dynamics 365 AI for Customer Insights** ([perwakilan layanan yang](#create-a-new-service-principal) Anda buat sebelumnya dalam prosedur ini)

1.  Pilih **Tinjau + tetapkan**.

Dapat memakan waktu hingga 15 menit untuk menyebarkan perubahan.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Masukkan ID sumber daya Azure atau detail langganan Azure dalam lampiran akun penyimpanan ke Wawasan Pelanggan

Anda dapat melampirkan akun Penyimpanan Danau Data di Wawasan Pelanggan untuk [menyimpan data](manage-environments.md) output atau [menggunakannya sebagai sumber data](connect-dataverse-managed-lake.md). Pilihan ini memungkinkan Anda memilih antara pendekatan berbasis sumber daya atau berbasis langganan. Tergantung pada pendekatan yang Anda pilih, ikuti prosedur di salah satu bagian berikut.

### <a name="resource-based-storage-account-connection"></a>Koneksi akun penyimpanan berbasis sumber daya

1. Buka [portal admin Azure](https://portal.azure.com), masuk ke langganan Anda dan buka akun penyimpanan.

1. Pada panel kiri, buka **Pengaturan** > **Properti**.

1. Salin nilai ID sumber daya akun penyimpanan.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salin ID sumber daya akun penyimpanan.":::

1. Di Wawasan Pelanggan, masukkan ID sumber daya di bidang sumber daya yang ditampilkan di layar koneksi akun penyimpanan.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Masukkan informasi ID sumber daya akun penyimpanan.":::   

1. Lanjutkan dengan langkah-langkah yang tersisa di Customer Insights untuk melampirkan akun penyimpanan.

### <a name="subscription-based-storage-account-connection"></a>Koneksi akun penyimpanan berbasis langganan

1. Buka [portal admin Azure](https://portal.azure.com), masuk ke langganan Anda dan buka akun penyimpanan.

1. Pada panel kiri, buka **Pengaturan** > **Properti**.

1. **Tinjau grup** Langganan **,** Sumber Daya, dan **Nama** akun penyimpanan untuk memastikan Bahwa Anda memilih nilai yang tepat di Customer Insights.

1. Di Wawasan Pelanggan, pilih nilai untuk bidang yang sesuai saat melampirkan akun penyimpanan.

1. Lanjutkan dengan langkah-langkah yang tersisa di Customer Insights untuk melampirkan akun penyimpanan.


[!INCLUDE [footer-include](includes/footer-banner.md)]