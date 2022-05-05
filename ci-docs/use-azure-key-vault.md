---
title: Bawa Azure key vault Anda sendiri untuk mengelola rahasia
description: Pelajari lebih lanjut cara mengkonfigurasi Customer Insights agar dapat menggunakan Azure key vault Anda sendiri.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 9eb06a1190fe4e8012ecd3d6742b8b3f5f4d6349
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653481"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Bawa Azure key vault Anda sendiri (pratinjau)

Menautkan brankas [kunci Azure khusus](/azure/key-vault/general/basic-concepts) ke lingkungan Wawasan Pelanggan membantu organisasi memenuhi persyaratan kepatuhan.
Key Vault khusus dapat digunakan untuk melakukan tahapan dan menggunakan rahasia di batas kepatuhan organisasi. Customer Insights dapat menggunakan rahasia di Azure Key Vault untuk [menyiapkan koneksi](connections.md) ke sistem pihak ketiga.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Menautkan brankas kunci ke lingkungan Wawasan Pelanggan

### <a name="prerequisites"></a>Prasyarat

Untuk mengonfigurasi brankas kunci di Customer Insights, prasyarat berikut harus dipenuhi:

- Anda memiliki langganan Azure.

- Anda memiliki [peran Administrator](permissions.md#admin) dalam Wawasan Pelanggan. Pelajari izin pengguna lebih [lanjut di Customer Insights](permissions.md#assign-roles-and-permissions).

- Anda memiliki peran [kontributor](/azure/role-based-access-control/built-in-roles#contributor) dan [Administrator Akses Pengguna](/azure/role-based-access-control/built-in-roles#user-access-administrator) di Key Vault atau grup sumber daya yang memiliki Key Vault. Untuk informasi lebih lanjut, lihat [Menambah atau menghilangkan penetapan peran Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal). Jika Anda tidak memiliki peran Administrator Akses Pengguna di Key Vault, Anda harus mengkonfigurasi izin kontrol akses berbasis peran untuk prinsipal layanan Azure untuk Dynamics 365 Customer Insights secara terpisah. Ikuti langkah-langkah untuk [menggunakan prinsipal layanan Azure](connect-service-principal.md) untuk Key Vault yang harus ditautkan.

- Key Vault harus **menonaktifkan** firewall Key Vault.

- Brankas kunci berada di lokasi [Azure yang sama](https://azure.microsoft.com/global-infrastructure/geographies/#overview) dengan lingkungan Wawasan Pelanggan. Wilayah lingkungan di Customer Insights tercantum di bawah **AdminSystemAboutRegion** > **·** > **·** > **·**.

### <a name="link-a-key-vault-to-the-environment"></a>Menautkan wawasan audiens Key Vault ke lingkungan

1. Buka **AdminSecurity** > **·**, lalu pilih **tab Key Vault**.
1. Pada petak **Key Vault**, pilih **Konfigurasi**.
1. Pilih **langganan**.
1. Pilih Key Vault dari daftar dropdown **Key Vault**. Jika terlalu banyak Key Vault yang ditampilkan, pilih grup sumber daya untuk membatasi hasil pencarian.
1. Terima pernyataan **privasi dan kesesuaian Data**.
1. Pilih **Simpan**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Langkah-langkah untuk menyiapkan brankas kunci tertaut di Wawasan Pelanggan.":::

Ubin **Key Vault** sekarang menampilkan nama Key Vault tertaut, grup sumber daya, dan langganan. Ia telah siap digunakan dalam konfigurasi sambungan.
Untuk detail tentang izin mana pada brankas kunci yang diberikan kepada Wawasan Pelanggan, buka [Izin yang diberikan pada brankas](#permissions-granted-on-the-key-vault) kunci, nanti di artikel ini.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Gunakan Key Vault dalam konfigurasi sambungan

Saat [mengkonfigurasi sambungan](connections.md) ke sistem pihak ketiga, rahasia dari Key Vault yang ditautkan dapat digunakan untuk mengkonfigurasi sambungan.

1. Buka **Admin** > **Koneksi**.
1. Pilih **Tambahkan koneksi**.
1. Untuk jenis sambungan yang didukung, tombol **Gunakan Key Vault** tersedia jika Anda menautkan Key Vault.
1. Alih-alih memasukkan rahasia secara manual, Anda dapat memilih nama rahasia yang menuju nilai rahasia di Key Vault.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Panel sambungan dengan sambungan SFTP yang menggunakan rahasia Key Vault.":::

## <a name="supported-connection-types"></a>Jenis koneksi yang didukung

Koneksi [ekspor](export-destinations.md) berikut didukung:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Izin yang diberikan pada brankas kunci

Izin berikut diberikan kepada Customer Insights pada brankas kunci tertaut jika [kebijakan](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) akses Key Vault atau [kontrol](/azure/key-vault/general/rbac-guide?tabs=azure-cli) akses berbasis peran Azure diaktifkan.

### <a name="key-vault-access-policy"></a>Kebijakan akses Key Vault

| Jenis        | Izin          |
| ----------- | -------------------- |
| Tombol         | [Dapatkan Kunci](/rest/api/keyvault/get-keys), [Dapatkan Kunci](/rest/api/keyvault/get-key)                                 |
| Rahasia      | [Dapatkan Rahasia](/rest/api/keyvault/get-secrets), [Dapatkan Rahasia](/rest/api/keyvault/get-secret)                     |
| Sertifikat | [Dapatkan Sertifikat](/rest/api/keyvault/get-certificates), [Dapatkan Sertifikat](/rest/api/keyvault/get-certificate) |

Nilai yang mendahului adalah minimum untuk dicantumkan dan dibaca selama eksekusi.

### <a name="azure-role-based-access-control"></a>Kontrol akses berbasis peran Azure

Peran Pengguna Key Vault Pembaca dan Key Vault Secrets akan ditambahkan untuk Customer Insights. Untuk rincian tentang peran ini, buka [peran built-in Azure untuk operasi bidang data Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Rekomendasi

- Gunakan brankas kunci terpisah atau khusus yang hanya berisi rahasia yang diperlukan untuk Wawasan Pelanggan. Baca lebih lanjut tentang mengapa [key vault terpisah direkomendasikan](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Ikuti [praktik terbaik menggunakan Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) untuk mengakses pilihan kontrol, cadangan, audit, dan pemulihan.

## <a name="frequently-asked-questions"></a>Tanya jawab

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Dapatkah Customer Insights menulis rahasia atau menimpa rahasia ke dalam brankas kunci?

Tidak. Hanya izin baca dan daftar yang diuraikan di [bagian izin](#permissions-granted-on-the-key-vault) yang diberikan sebelumnya di artikel ini yang diberikan kepada Customer Insights. Sistem tidak dapat menambahkan, menghapus, atau menimpa rahasia di Key Vault. Hal ini juga menjadi alasan Anda tidak dapat memasukkan kredensial saat sambungan menggunakan Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Dapatkah saya mengubah sambungan dari menggunakan rahasia Key Vault menjadi autentikasi default?

Tidak. Anda tidak dapat mengubah kembali ke sambungan default setelah Anda mengonfigurasi dengan menggunakan rahasia dari Key Vault tertaut. Buat sambungan terpisah, dan hapus yang lama jika Anda tidak memerlukannya lagi.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Bagaimana cara mencabut akses ke brankas kunci untuk Wawasan Pelanggan?

Tergantung pada apakah [kebijakan akses Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) atau [kontrol akses berbasis peran Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) diaktifkan, Anda harus menghilangkan izin untuk prinsipal layanan `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` dengan nama `Dynamics 365 AI for Customer Insights`. Semua sambungan yang menggunakan Key Vault akan berhenti berfungsi.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Rahasia yang digunakan saat koneksi dihilangkan dari Key Vault. Apa yang bisa saya lakukan?

Pemberitahuan muncul di Customer Insights saat rahasia yang dikonfigurasi dari brankas kunci tidak dapat diakses lagi. Aktifkan [penghapusan lunak](/azure/key-vault/general/soft-delete-overview) di Key Vault untuk mengembalikan rahasia jika tidak sengaja dihilangkan.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Sambungan tidak berfungsi, tapi rahasia saya ada di Key Vault. Apa yang mungkin menjadi penyebabnya?

Pemberitahuan muncul di Customer Insights saat tidak dapat mengakses brankas kunci. Penyebabnya mungkin:

- Izin untuk perwakilan layanan Customer Insights telah dihapus. Mereka harus dikembalikan secara manual.

- Firewall di Key Vault diaktifkan. Firewall harus dinonaktifkan untuk membuat brankas kunci dapat diakses kembali untuk Customer Insights.
