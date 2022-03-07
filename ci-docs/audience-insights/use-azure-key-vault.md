---
title: Bawa Azure key vault Anda sendiri untuk mengelola rahasia
description: Pelajari lebih lanjut cara mengkonfigurasi Customer Insights agar dapat menggunakan Azure key vault Anda sendiri.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: 6f521dfce3e0922238d16beee3be8e1bbcfc63a5
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606087"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Bawa Azure key vault Anda sendiri (pratinjau)

Menautkan [Azure key vault](/azure/key-vault/general/basic-concepts) khusus ke lingkungan wawasan audiens membantu organisasi memenuhi persyaratan kesesuaian.
Key Vault khusus dapat digunakan untuk melakukan tahapan dan menggunakan rahasia di batas kepatuhan organisasi. Audiens dapat menggunakan rahasia di Azure Key Vault untuk [mengkonfigurasi sambungan](connections.md) ke sistem pihak ketiga.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Menautkan Key Vault ke lingkungan wawasan audiens

### <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi Key Vault dalam wawasan audiens, prasyarat berikut harus dipenuhi:

- Anda memiliki langganan Azure.

- Anda memiliki peran [Administrator](permissions.md#administrator) di wawasan audiens. Pelajari lebih lanjut tentang [izin pengguna di wawasan audiens](permissions.md#assign-roles-and-permissions).

- Anda memiliki peran [kontributor](/azure/role-based-access-control/built-in-roles#contributor) dan [Administrator Akses Pengguna](/azure/role-based-access-control/built-in-roles#user-access-administrator) di Key Vault atau grup sumber daya yang memiliki Key Vault. Untuk informasi lebih lanjut, lihat [Menambah atau menghilangkan penetapan peran Azure menggunakan portal Azure](/azure/role-based-access-control/role-assignments-portal). Jika Anda tidak memiliki peran Administrator Akses Pengguna di Key Vault, Anda harus mengkonfigurasi izin kontrol akses berbasis peran untuk prinsipal layanan Azure untuk Dynamics 365 Customer Insights secara terpisah. Ikuti langkah-langkah untuk [menggunakan prinsipal layanan Azure](connect-service-principal.md) untuk Key Vault yang harus ditautkan.

- Key Vault harus **menonaktifkan** firewall Key Vault.

- Key Vault berada di [lokasi Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) yang sama dengan lingkungan wawasan audiens. Kawasan lingkungan dalam wawasan audiens tercantum dalam **Admin** > **Sistem** > **tentang** > **Kawasan**.

### <a name="link-a-key-vault-to-the-environment"></a>Menautkan wawasan audiens Key Vault ke lingkungan

1. Pergi ke **Admin** > **Sistem**, dan pilih tab **Keamanan**.
1. Pada petak **Key Vault**, pilih **Konfigurasi**.
1. Pilih **langganan**.
1. Pilih Key Vault dari daftar dropdown **Key Vault**. Jika terlalu banyak Key Vault yang ditampilkan, pilih grup sumber daya untuk membatasi hasil pencarian.
1. Terima pernyataan **privasi dan kesesuaian Data**.
1. Pilih **Simpan**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Langkah-langkah untuk mengkonfigurasi Key Vault tertaut di wawasan audiens.":::

Ubin **Key Vault** sekarang menampilkan nama Key Vault tertaut, grup sumber daya, dan langganan. Ia telah siap digunakan dalam konfigurasi sambungan.
Untuk rincian tentang izin yang diberikan di Key Vault ke wawasan audiens, buka [Izin yang diberikan di Key Vault untuk wawasan audiens](#permissions-granted-on-the-key-vault-to-audience-insights), nanti di artikel ini.

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Izin yang diberikan di key vault ke wawasan audiens

Izin berikut diberikan ke wawasan audiens di key vault tertaut jika [kebijakan akses Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) atau [kontrol akses berbasis peran Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) diaktifkan.

### <a name="key-vault-access-policy"></a>Kebijakan akses Key Vault

| Jenis        | Izin          |
| ----------- | -------------------- |
| Tombol         | [Dapatkan Kunci](/rest/api/keyvault/get-keys), [Dapatkan Kunci](/rest/api/keyvault/get-key)                                 |
| Rahasia      | [Dapatkan Rahasia](/rest/api/keyvault/get-secrets), [Dapatkan Rahasia](/rest/api/keyvault/get-secret)                     |
| Sertifikat | [Dapatkan Sertifikat](/rest/api/keyvault/get-certificates), [Dapatkan Sertifikat](/rest/api/keyvault/get-certificate) |

Nilai yang mendahului adalah minimum untuk dicantumkan dan dibaca selama eksekusi.

### <a name="azure-role-based-access-control"></a>Kontrol akses berbasis peran Azure

Peran pengguna Pembaca Key Vault dan Rahasia Key Vault akan ditambahkan untuk wawasan audiens. Untuk rincian tentang peran ini, buka [peran built-in Azure untuk operasi bidang data Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Rekomendasi

- Gunakan Key Vault terpisah atau khusus yang hanya berisi rahasia yang diperlukan untuk audiens wawasan. Baca lebih lanjut tentang mengapa [key vault terpisah direkomendasikan](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Ikuti [praktik terbaik menggunakan Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) untuk mengakses pilihan kontrol, cadangan, audit, dan pemulihan.

## <a name="frequently-asked-questions"></a>Tanya jawab

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Dapatkah wawasan audiens menulis rahasia atau menimpa rahasia ke dalam Key Vault?

Tidak. Hanya izin baca dan cantumkan yang diuraikan dalam bagian [izin yang diberikan](#permissions-granted-on-the-key-vault-to-audience-insights) sebelumnya di artikel ini yang diberikan ke wawasan audiens. Sistem tidak dapat menambahkan, menghapus, atau menimpa rahasia di Key Vault. Hal ini juga menjadi alasan Anda tidak dapat memasukkan kredensial saat sambungan menggunakan Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Dapatkah saya mengubah sambungan dari menggunakan rahasia Key Vault menjadi autentikasi default?

Tidak. Anda tidak dapat mengubah kembali ke sambungan default setelah Anda mengonfigurasi dengan menggunakan rahasia dari Key Vault tertaut. Buat sambungan terpisah, dan hapus yang lama jika Anda tidak memerlukannya lagi.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Bagaimana cara mencabut akses ke key vault untuk wawasan audiens?

Tergantung pada apakah [kebijakan akses Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) atau [kontrol akses berbasis peran Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) diaktifkan, Anda harus menghilangkan izin untuk prinsipal layanan `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` dengan nama `Dynamics 365 AI for Customer Insights`. Semua sambungan yang menggunakan Key Vault akan berhenti berfungsi.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Rahasia yang digunakan saat koneksi dihilangkan dari Key Vault. Apa yang bisa saya lakukan?

Pemberitahuan muncul dalam wawasan audiens ketika rahasia yang dikonfigurasi dari key vault tidak dapat diakses lagi. Aktifkan [penghapusan lunak](/azure/key-vault/general/soft-delete-overview) di Key Vault untuk mengembalikan rahasia jika tidak sengaja dihilangkan.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>Sambungan tidak berfungsi, tapi rahasia saya ada di Key Vault. Apa yang mungkin menjadi penyebabnya?

Pemberitahuan akan muncul di wawasan audiens bila tidak dapat mengakses Key Vault. Penyebabnya mungkin:

- Izin untuk prinsipal layanan wawasan audiens dihilangkan. Mereka harus dikembalikan secara manual.

- Firewall di Key Vault diaktifkan. Firewall harus dinonaktifkan agar Key Vault dapat diakses untuk wawasan audiens lagi.
