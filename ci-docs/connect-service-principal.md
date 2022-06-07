---
title: Menyambung ke akun Azure Data Lake Storage menggunakan prinsipal layanan
description: Gunakan prinsipal layanan Azure untuk terhubung ke data lake Anda sendiri.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: b18d1f42b9510ebf23f0666322819865d132173b
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833389"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Menyambung ke akun Azure Data Lake Storage menggunakan prinsipal layanan Azure

Artikel ini membahas cara menyambungkan Dynamics 365 Customer Insights dengan akun dengan Azure Data Lake Storage menggunakan perwakilan layanan Azure alih-alih kunci akun penyimpanan.

Alat otomatis yang menggunakan layanan Azure harus selalu memiliki izin terbatas. Selain masuk aplikasi sebagai pengguna yang memiliki hak istimewa, Azure menawarkan prinsipal layanan. Anda dapat menggunakan perwakilan layanan untuk menambahkan atau mengedit folder Common Data Model dengan [aman sebagai sumber data](connect-common-data-model.md) atau [membuat atau memperbarui lingkungan](create-environment.md).

> [!IMPORTANT]
>
> - Akun Data Lake Storage yang akan menggunakan perwakilan layanan harus Gen2 dan mengaktifkan [namespace hierarki](/azure/storage/blobs/data-lake-storage-namespace). Akun penyimpanan Azure Data Lake Gen1 tidak didukung.
> - Anda memerlukan izin admin untuk Penyewa Azure Anda untuk membuat perwakilan layanan.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Membuat prinsipal layanan Azure untuk Customer Insights

Sebelum membuat perwakilan layanan baru untuk Customer Insights, periksa apakah layanan tersebut sudah ada di organisasi Anda.

### <a name="look-for-an-existing-service-principal"></a>Mencari prinsipal layanan yang ada

1. Buka [portal admin Azure](https://portal.azure.com), lalu masuk ke organisasi Anda.

2. Dari **Layanan Azure**, pilih **Azure Active Directory**.

3. Di bawah **Kelola**, pilih **Aplikasi** Microsoft.

4. Tambahkan filter untuk **ID Aplikasi mulai dengan**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` atau cari nama `Dynamics 365 AI for Customer Insights`.

5. Jika Anda menemukan rekaman yang cocok, berarti principal layanan sudah ada.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Cuplikan layar yang menampilkan prinsipal layanan yang ada.":::

6. Jika tidak ada hasil yang dikembalikan, Anda dapat [membuat perwakilan](#create-a-new-service-principal) layanan baru. Dalam kebanyakan kasus, itu sudah ada dan Anda hanya perlu memberikan izin bagi perwakilan layanan untuk mengakses akun penyimpanan.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Berikan izin kepada prinsipal layanan untuk mengakses akun Penyimpanan

Buka portal Microsoft Azure untuk memberikan izin kepada perwakilan layanan untuk akun penyimpanan yang ingin Anda gunakan di Customer Insights.

1. Buka [portal admin Azure](https://portal.azure.com), lalu masuk ke organisasi Anda.

1. Buka akun penyimpanan yang Anda inginkan agar dapat diakses oleh perwakilan layanan customer insights.

1. Pada panel kiri, pilih **kontrol akses (IAM)**, lalu pilih **Tambah** > **Tambah penetapan peran**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Cuplikan layar yang menampilkan portal Azure saat menambahkan penetapan peran.":::

1. Di panel **Tambah penetapan peran**, atur properti berikut:
   - Peran: **kontributor data Blob penyimpanan**
   - Tetapkan akses ke: **pengguna, grup, atau prinsipal Layanan**
   - Pilih anggota: **Dynamics 365 AI for Customer Insights** ([perwakilan](#create-a-new-service-principal) layanan yang Anda cari sebelumnya dalam prosedur ini)

1. Pilih **Tinjau + tetapkan**.

Dapat memakan waktu hingga 15 menit untuk menyebarkan perubahan.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Masukkan ID sumber daya Azure atau detail langganan Azure di lampiran akun penyimpanan ke Customer Insights

Anda dapat melampirkan akun Data Lake Storage di Customer Insights untuk [menyimpan data](manage-environments.md) output atau [menggunakannya sebagai sumber data](connect-dataverse-managed-lake.md). Pilihan ini memungkinkan Anda memilih antara pendekatan berbasis sumber daya atau berbasis langganan. Tergantung pada pendekatan yang Anda pilih, ikuti prosedur di salah satu bagian berikut.

### <a name="resource-based-storage-account-connection"></a>Koneksi akun penyimpanan berbasis sumber daya

1. Buka [portal admin Azure](https://portal.azure.com), masuk ke langganan Anda dan buka akun penyimpanan.

1. Di panel kiri, buka **Titik Akhir** > **Pengaturan**.

1. Salin nilai ID sumber daya akun penyimpanan.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salin ID sumber daya akun penyimpanan.":::

1. Di Customer Insights, masukkan ID sumber daya di bidang sumber daya yang ditampilkan di layar koneksi akun penyimpanan.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Masukkan informasi ID sumber daya akun penyimpanan.":::   

1. Lanjutkan dengan langkah-langkah yang tersisa di Customer Insights untuk melampirkan akun penyimpanan.

### <a name="subscription-based-storage-account-connection"></a>Koneksi akun penyimpanan berbasis langganan

1. Buka [portal admin Azure](https://portal.azure.com), masuk ke langganan Anda dan buka akun penyimpanan.

1. Pada panel kiri, buka **Pengaturan** > **Properti**.

1. **Tinjau Langganan**, **Grup** sumber daya, dan **Nama** akun penyimpanan untuk memastikan bahwa Anda memilih nilai yang tepat di Customer Insights.

1. Di Customer Insights, pilih nilai untuk bidang terkait saat melampirkan akun penyimpanan.

1. Lanjutkan dengan langkah-langkah yang tersisa di Customer Insights untuk melampirkan akun penyimpanan.

### <a name="create-a-new-service-principal"></a>Buat prinsipal layanan baru

1. Instal versi terbaru Azure Active Directory PowerShell untuk Graph. Untuk informasi lebih lanjut, buka [Menginstal Azure Active Directory PowerShell untuk Graph](/powershell/azure/active-directory/install-adv2).

   1. Di PC Anda, tekan tombol Windows pada keyboard Anda dan cari **Windows PowerShell** dan pilih **Jalankan sebagai administrator**.

   1. Di jendela PowerShell yang terbuka, masukkan `Install-Module AzureAD`.

2. Buat prinsipal layanan untuk Customer Insights dengan modul Azure AD PowerShell.

   1. Di jendela PowerShell, masukkan `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Ganti *[ID Direktori Anda]* dengan ID Direktori aktual langganan Azure Anda di mana Anda ingin membuat perwakilan layanan. Parameter nama lingkungan, `AzureEnvironmentName` adalah opsional.
  
   1. Masukkan `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Perintah ini membuat perwakilan layanan untuk Customer Insights pada langganan Azure yang dipilih.

[!INCLUDE [footer-include](includes/footer-banner.md)]