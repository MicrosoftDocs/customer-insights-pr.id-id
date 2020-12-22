---
title: Menyambung ke akun Azure Data Lake Storage Gen2 dengan prinsipal Layanan
description: Gunakan prinsipal layanan Azure untuk wawasan audiens untuk menyambung ke Data Lake Anda sendiri saat melampirkan ke wawasan audiens.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644092"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Menyambungkan wawasan audiens ke akun Azure Data Lake Storage Gen2 dengan prinsipal layanan Azure untuk wawasan audiens

Alat otomatis yang menggunakan layanan Azure harus selalu memiliki izin terbatas. Selain masuk aplikasi sebagai pengguna yang memiliki hak istimewa, Azure menawarkan prinsipal layanan. Baca terus untuk mempelajari cara menyambung wawasan audiens dengan akun Azure Data Lake Storage Gen2 menggunakan prinsip layanan Azure dan bukan kunci akun penyimpanan. 

Anda dapat menggunakan prinsipal layanan untuk [menambahkan atau mengedit folder Common Data Model sebagai sumber data](connect-common-data-model.md) atau [membuat yang baru atau memperbarui lingkungan yang ada](manage-environments.md#create-an-environment-in-an-existing-organization).

Anda memerlukan izin admin untuk langganan Azure Anda untuk membuat prinsipal layanan.

## <a name="create-azure-service-principal-for-audience-insights"></a>Membuat prinsipal layanan Azure untuk wawasan audiens

Sebelum membuat prinsipal layanan baru untuk wawasan audiens, periksa apakah sudah ada di organisasi anda.

### <a name="look-for-an-existing-service-principal"></a>Mencari prinsipal layanan yang ada

1. Buka [portal admin Azure](https://portal.azure.com), lalu masuk ke organisasi Anda.

2. Pilih **Azure Active Directory** dari layanan Azure.

3. Di dalam **Kelola**, pilih **aplikasi Enterprise**.

4. Cari ID aplikasi pihak pertama wawasan audiens `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` atau nama `Dynamics 365 AI for Customer Insights`.

5. Jika Anda menemukan rekaman yang cocok, berarti prinsipal layanan untuk wawasan audiens ada. Anda tidak perlu membuatnya lagi.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Screenshot yang menunjukkan prinsipal layanan yang ada.":::
   
6. Jika tidak ada hasil, buat prinsipal layanan baru.

### <a name="create-a-new-service-principal"></a>Buat prinsipal layanan baru

1. Instal versi terbaru **Azure Active Directory PowerShell for Graph**. Untuk informasi lebih lanjut, lihat [menginstal Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - Di PC, pilih tombol Windows di keyboard dan Cari **Windows PowerShell** dan **Jalankan sebagai administrator**.
   
   - Di jendela PowerShell yang terbuka, masukkan `Install-Module AzureAD`.

2. Buat prinsipal layanan untuk audiens wawasan dengan modul Azure AD PowerShell.
   - Di jendela PowerShell, masukkan `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Ganti "ID penyewa Anda" dengan ID sebenarnya dari penyewa Anda yang akan membuat prinsipal layanan. Parameter nama lingkungan `AzureEnvironmentName` adalah opsional.
  
   - Masukkan `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Perintah ini akan membuat prinsipal layanan untuk wawasan audiens pada penyewa yang dipilih.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Berikan izin kepada prinsipal layanan untuk mengakses akun Penyimpanan

Buka portal Azure untuk memberikan izin kepada prinsipal layanan untuk akun penyimpanan yang ingin anda gunakan di wawasan audiens.

1. Buka [portal admin Azure](https://portal.azure.com), lalu masuk ke organisasi Anda.

1. Buka akun penyimpanan yang akan menjadi prinsipal layanan untuk wawasan audiens agar dapat diakses.

1. Pilih **kontrol akses (IAM)** dari panel navigasi dan pilih **Tambah** > **Tambah penetapan peran**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Screeshot menampilkan portal Azure saat menambahkan penetapan peran.":::
   
1. Di panel **Tambah penetapan peran**, atur properti berikut:
   - Peran: *kontributor data Blob penyimpanan*
   - Tetapkan akses ke: *pengguna, grup, atau prinsipal Layanan*
   - Pilih: *Dynamics 365 AI for Customer Insights* ([prinsipal layanan yang Anda buat](#create-a-new-service-principal))

1.  Pilih **Simpan**.

Dapat memakan waktu hingga 15 menit untuk menyebarkan perubahan.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Masukkan ID sumber daya azure atau rincian langganan azure di lampiran akun penyimpanan ke wawasan audiens.

Lampirkan akun penyimpanan Azure Data Lake di wawasan audiens untuk [menyimpan data output](manage-environments.md) atau [gunakan sebagai sumber data](connect-common-data-service-lake.md). Memilih pilihan Azure data Lake memungkinkan Anda memilih antara pendekatan berbasis sumber daya atau berbasis langganan.

Ikuti langkah-langkah berikut untuk menyediakan informasi yang diperlukan tentang pendekatan yang dipilih.

### <a name="resounce-based-storage-account-connection"></a>Koneksi akun penyimpanan berbasis sumber daya

1. Buka [portal admin Azure](https://portal.azure.com), masuk ke langganan Anda dan buka akun penyimpanan.

1. Buka **pengaturan** > **properti** di panel navigasi.

1. Salin nilai ID sumber daya akun penyimpanan.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salin ID sumber daya akun penyimpanan.":::

1. Di wawasan audiens, masukkan ID sumber daya di bidang sumber daya yang ditampilkan di layar koneksi akun penyimpanan.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Masukkan informasi ID sumber daya akun penyimpanan.":::   
   
1. Lanjutkan dengan langkah yang tersisa di wawasan audiens untuk melampirkan akun penyimpanan.

### <a name="subscription-based-storage-account-connection"></a>Koneksi akun penyimpanan berbasis langganan

1. Buka [portal admin Azure](https://portal.azure.com), masuk ke langganan Anda dan buka akun penyimpanan.

1. Buka **pengaturan** > **properti** di panel navigasi.

1. Tinjau **langganan**, **grup sumber daya**, dan **nama** akun penyimpanan untuk memastikan bahwa anda memilih nilai yang tepat di wawasan audiens.

1. Di wawasan audiens, pilih nilai atau untuk bidang yang terkait saat melampirkan akun penyimpanan.

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Masukkan informasi ID sumber daya akun penyimpanan.":::
   
1. Lanjutkan dengan langkah yang tersisa di wawasan audiens untuk melampirkan akun penyimpanan.
