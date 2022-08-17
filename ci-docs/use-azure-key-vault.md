---
title: Bawa Azure key vault Anda sendiri (pratinjau)
description: Pelajari cara mengonfigurasi Customer Insights untuk menggunakan brankas kunci Azure Anda sendiri untuk mengelola rahasia.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246159"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Bawa Azure key vault Anda sendiri (pratinjau)

Menautkan brankas [kunci Azure khusus](/azure/key-vault/general/basic-concepts) ke lingkungan Customer Insights membantu organisasi memenuhi persyaratan kepatuhan.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Menautkan brankas kunci ke lingkungan Customer Insights

Siapkan brankas kunci khusus untuk membuat panggung dan menggunakan rahasia dalam batas kepatuhan organisasi.

### <a name="prerequisites"></a>Prasyarat

- Langganan Azure aktif.

- Peran [Administrator](permissions.md#admin) [yang](permissions.md#add-users) ditetapkan dalam Customer Insights.

- [kontributor](/azure/role-based-access-control/built-in-roles#contributor) dan [Administrator](/azure/role-based-access-control/built-in-roles#user-access-administrator) Akses Pengguna pada brankas kunci atau grup sumber daya tempat brankas kunci berada. Untuk informasi lebih lanjut, lihat [Menambah atau menghilangkan penetapan peran Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal). Jika Anda tidak memiliki peran Administrator Akses Pengguna di brankas kunci, siapkan izin kontrol akses berbasis peran untuk perwakilan Dynamics 365 Customer Insights layanan Azure secara terpisah. Ikuti langkah-langkah untuk [menggunakan prinsipal layanan Azure](connect-service-principal.md) untuk Key Vault yang harus ditautkan.

- Brankas kunci harus menonaktifkan **firewall** Key Vault.

- Brankas kunci berada di lokasi [Azure yang sama](https://azure.microsoft.com/global-infrastructure/geographies/#overview) dengan lingkungan Customer Insights. Di Customer Insights, buka **Sistem** > **Admin** dan **tab Tentang** untuk melihat wilayah lingkungan.

### <a name="recommendations"></a>Rekomendasi

- [Gunakan brankas](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) kunci terpisah atau khusus yang hanya berisi rahasia yang diperlukan untuk Customer Insights.

- Ikuti [praktik terbaik menggunakan Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) untuk mengakses pilihan kontrol, cadangan, audit, dan pemulihan.

### <a name="link-a-key-vault-to-the-environment"></a>Menautkan wawasan audiens Key Vault ke lingkungan

1. Buka **Keamanan** > **Admin**, lalu pilih tab **Key Vault**.
1. Pada petak **Key Vault**, pilih **Konfigurasi**.
1. Pilih **langganan**.
1. Pilih Key Vault dari daftar dropdown **Key Vault**. Jika terlalu banyak brankas kunci tersedia, pilih grup sumber daya untuk membatasi hasil pencarian.
1. Tinjau [privasi dan kepatuhan Data](connections.md#data-privacy-and-compliance) dan pilih **Saya setuju**.
1. Pilih **Simpan**.

Petak **peta Key Vault** memperlihatkan nama brankas kunci, langganan, dan grup sumber daya yang ditautkan. Ia telah siap digunakan dalam konfigurasi sambungan.
Untuk mengetahui detail tentang izin mana pada brankas kunci yang diberikan kepada Customer Insights, buka [Izin yang diberikan pada brankas](#permissions-granted-on-the-key-vault) kunci.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Gunakan Key Vault dalam konfigurasi sambungan

Saat [menyiapkan koneksi](connections.md) ke [sistem pihak](#supported-connection-types) ketiga yang didukung, gunakan rahasia dari Key Vault yang ditautkan untuk mengonfigurasi koneksi.

1. Buka **Admin** > **Koneksi**.
1. Pilih **Tambahkan koneksi**.
1. Untuk jenis sambungan yang didukung, tombol **Gunakan Key Vault** tersedia jika Anda menautkan Key Vault.
1. Alih-alih memasukkan rahasia secara manual, pilih nama rahasia yang menunjuk ke nilai rahasia di brankas kunci.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Panel sambungan dengan sambungan SFTP yang menggunakan rahasia Key Vault.":::

1. Pilih **Simpan** untuk membuat koneksi.

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
| Tombol         | [Dapatkan Kunci](/rest/api/keyvault/keys/get-keys/get-keys), [Dapatkan Kunci](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Rahasia      | [Dapatkan Rahasia](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Dapatkan Rahasia](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Sertifikat | [Dapatkan Sertifikat](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Dapatkan Sertifikat](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Nilai yang mendahului adalah minimum untuk dicantumkan dan dibaca selama eksekusi.

### <a name="azure-role-based-access-control"></a>Kontrol akses berbasis peran Azure

Peran [Pengguna](/azure/key-vault/general/rbac-guide?tabs=azure-cli) Pembaca key vault dan Rahasia Key Vault akan ditambahkan untuk Customer Insights.

## <a name="frequently-asked-questions"></a>Tanya jawab

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Dapatkah Customer Insights menulis rahasia atau menimpa rahasia ke dalam brankas kunci?

Tidak. Hanya izin baca dan daftar yang diuraikan dalam [izin](#permissions-granted-on-the-key-vault) yang diberikan yang diberikan yang diberikan kepada Customer Insights. Sistem tidak dapat menambahkan, menghapus, atau menimpa rahasia di Key Vault. Hal ini juga menjadi alasan Anda tidak dapat memasukkan kredensial saat sambungan menggunakan Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Dapatkah saya mengubah sambungan dari menggunakan rahasia Key Vault menjadi autentikasi default?

Tidak. Anda tidak dapat mengubah kembali ke sambungan default setelah Anda mengonfigurasi dengan menggunakan rahasia dari Key Vault tertaut. Buat sambungan terpisah, dan hapus yang lama jika Anda tidak memerlukannya lagi.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Bagaimana cara mencabut akses ke brankas kunci untuk Customer Insights?

[Jika kebijakan](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) akses Key Vault atau [kontrol](/azure/key-vault/general/rbac-guide?tabs=azure-cli) akses berbasis peran Azure diaktifkan, hapus izin untuk perwakilan `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` layanan dengan nama `Dynamics 365 AI for Customer Insights`. Semua sambungan yang menggunakan Key Vault akan berhenti berfungsi.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Rahasia yang digunakan saat koneksi dihilangkan dari Key Vault. Apa yang bisa saya lakukan?

Pemberitahuan muncul di Customer Insights saat rahasia yang dikonfigurasi dari brankas kunci tidak dapat diakses lagi. Aktifkan [penghapusan lunak](/azure/key-vault/general/soft-delete-overview) di Key Vault untuk mengembalikan rahasia jika tidak sengaja dihilangkan.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Sambungan tidak berfungsi, tapi rahasia saya ada di Key Vault. Apa yang mungkin menjadi penyebabnya?

Pemberitahuan muncul di Customer Insights saat tidak dapat mengakses brankas kunci. Penyebabnya mungkin:

- Izin untuk perwakilan layanan Customer Insights dihapus. Mereka harus dikembalikan secara manual.

- Firewall di Key Vault diaktifkan. Firewall harus dinonaktifkan untuk membuat brankas kunci dapat diakses kembali oleh Customer Insights.
