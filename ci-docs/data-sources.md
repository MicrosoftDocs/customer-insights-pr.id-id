---
title: Ikhtisar sumber data
description: Pelajari cara mengimpor atau menyerap data dari berbagai sumber.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 591353bf1ba2f9ca05ddd137e1cf29dc0b0fba97
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245653"
---
# <a name="data-sources-overview"></a>Ikhtisar sumber data

Dynamics 365 Customer Insights menyediakan koneksi untuk membawa data dari serangkaian sumber yang luas. Menghubungkan ke sumber data sering disebut sebagai proses *penyerapan data*. Setelah menyerap data, Anda dapat [menyatukan](data-unification.md), menghasilkan wawasan, dan mengaktifkan data untuk membangun pengalaman yang dipersonalisasi.

## <a name="add-or-edit-data-sources"></a>Menambahkan atau mengedit sumber data

Anda dapat melampirkan atau mengimpor sumber data ke Customer Insights. Tautan di bawah ini memberikan petunjuk tentang menambahkan dan mengedit sumber data.

**Melampirkan sumber data**

Jika Anda memiliki data yang disiapkan di salah satu layanan data Azure Microsoft, Customer Insights dapat dengan mudah terhubung ke sumber data tanpa harus menyerap kembali data tersebut. pilih salah satu dari opsi berikut ini:
- [Azure Data Lake Storage(file csv atau parket dalam folder Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics(Basis data danau)](connect-synapse.md)
- [Microsoft Dataverse danau data](connect-dataverse-managed-lake.md)

**Mengimpor dan mengubah**

Jika Anda menggunakan sumber data lokal, Microsoft, atau data pihak ketiga, impor dan ubah data menggunakan Power Query konektor.
- [Power Query Konektor](connect-power-query.md)

## <a name="review-data-sources"></a>Meninjau sumber data

Jika lingkungan Anda dikonfigurasi untuk menggunakan penyimpanan Customer Insights dan Anda menggunakan sumber data lokal, Anda menggunakan Power Platform aliran data. Dengan Power Platform aliran data, Anda dapat melihat sumber data bersama dan sumber data yang dikelola oleh orang lain. Halaman **Sumber** Data mencantumkan sumber data dalam tiga bagian:
- **Dibagikan**: Sumber data yang dapat dikelola oleh semua admin Customer Insights. Power Platform aliran data, akun penyimpanan Anda sendiri, dan melampirkan ke danau data yang Dataverse dikelola adalah contoh sumber data bersama.
- **Dikelola oleh saya**: Power Platform aliran data dibuat dan dikelola hanya oleh Anda. Admin Customer Insights lainnya hanya dapat melihat aliran data ini tetapi tidak mengedit, me-refresh, atau menghapusnya.
- **Dikelola oleh orang lain**: Power Platform aliran data yang dibuat oleh admin lain. Anda hanya dapat melihatnya. Ini mencantumkan pemilik aliran data untuk dihubungi untuk bantuan apa pun.
> [!NOTE]
> Semua entitas dapat dilihat dan digunakan oleh pengguna lain. Meskipun sumber data dimiliki oleh pengguna yang membuatnya, entitas yang dihasilkan dari penyerapan data dapat digunakan oleh setiap pengguna Customer Insights.

Jika lingkungan Anda tidak menggunakan Power Platform aliran data, **halaman Sumber** Data hanya berisi daftar semua sumber data. Tidak ada bagian yang ditampilkan.

## <a name="manage-existing-data-sources"></a>Mengelola sumber data yang sudah ada

Buka **Sumber** > **Data Data** untuk melihat nama setiap sumber data yang diserap, statusnya, dan terakhir kali data disegarkan untuk sumber tersebut. Anda bisa mengurutkan daftar sumber data menurut kolom mana pun atau menggunakan kotak pencarian untuk menemukan sumber data yang ingin Anda kelola.

Pilih sumber data untuk melihat tindakan yang tersedia.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Sumber Data ditambahkan.":::

- [**Edit**](#add-or-edit-data-sources) sumber data untuk mengubah propertinya.
- [**Refresh**](#refresh-data-sources) sumber data untuk menyertakan data terbaru.
- [**Perkaya**](data-sources-enrichment.md) sumber data sebelum penyatuan.
- **Hapus** sumber data. Sumber data hanya dapat dihapus jika data tidak digunakan dalam pemrosesan apa pun seperti penyatuan, wawasan, aktivasi, atau ekspor.

## <a name="refresh-data-sources"></a>Segarkan sumber data

Sumber data dapat disegarkan dengan jadwal otomatis atau diperbarui secara manual sesuai permintaan. [Sumber](connect-power-query.md#add-data-from-on-premises-data-sources) data lokal disegarkan pada jadwal mereka sendiri yang disiapkan selama penyerapan data. Untuk sumber data terlampir, penyerapan data menghabiskan data terbaru yang tersedia dari sumber data tersebut.

Buka **Jadwal** > **Sistem** > [**Admin**](schedule-refresh.md) untuk mengonfigurasi refresh terjadwal sistem dari sumber data yang Anda konsumsi.

Untuk menyegarkan sumber data sesuai permintaan:

1. Buka **Data** > **Sumber data**.

1. Pilih sumber data yang ingin Anda refresh dan pilih **Refresh**. Sumber data sekarang dipicu untuk penyegaran manual. Merefresh sumber data akan memperbarui skema entitas dan data untuk semua entitas yang ditentukan dalam sumber data.

1. Pilih status untuk membuka **panel Detail** kemajuan dan lihat kemajuan. Untuk membatalkan pekerjaan, pilih **Batalkan pekerjaan** di bagian bawah panel.

[!INCLUDE [footer-include](includes/footer-banner.md)]
