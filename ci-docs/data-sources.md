---
title: Ikhtisar sumber data
description: Pelajari cara mengimpor atau menyerap data dari berbagai sumber.
ms.date: 05/18/2022
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
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051457"
---
# <a name="data-sources-overview"></a>Ikhtisar sumber data

Dynamics 365 Customer Insights menyediakan koneksi untuk membawa data dari serangkaian sumber yang luas. Menghubungkan ke sumber data sering disebut sebagai proses *penyerapan data*. Setelah menyerap data, Anda dapat [menyatukan](data-unification.md), menghasilkan wawasan, dan mengaktifkan data untuk membangun pengalaman yang dipersonalisasi.

## <a name="add-data-sources"></a>Tambahkan sumber data

Anda dapat melampirkan atau mengimpor sumber data ke Customer Insights. Tautan di bawah ini memberikan petunjuk tentang menambahkan sumber data.

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

Buka **Sumber** > **Data Data** untuk melihat nama setiap sumber data yang diserap, statusnya, dan terakhir kali data disegarkan untuk sumber tersebut. Anda dapat mengurutkan daftar sumber data menurut setiap kolom.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Sumber Data ditambahkan.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuat data dapat memakan waktu. Setelah penyegaran berhasil, data yang terserap dapat ditinjau dari halaman **entitas**. Untuk informasi lebih lanjut, [Entitas](entities.md).

## <a name="refresh-data-sources"></a>Segarkan sumber data

Sumber data dapat disegarkan dengan jadwal otomatis atau diperbarui secara manual sesuai permintaan. [Sumber](connect-power-query.md#add-data-from-on-premises-data-sources) data lokal disegarkan pada jadwal mereka sendiri yang disiapkan selama penyerapan data. Untuk sumber data terlampir, penyerapan data menghabiskan data terbaru yang tersedia dari sumber data tersebut.

Buka **Jadwal** > **Sistem** > [**Admin**](system.md#schedule-tab) untuk mengonfigurasi refresh terjadwal sistem dari sumber data yang Anda konsumsi.

Untuk me-refresh sumber data sesuai permintaan, ikuti langkah berikut:

1. Buka **Data** > **Sumber data**.

1. Pilih elipsis vertikal (&vellip;) di samping sumber data yang ingin Anda refresh dan pilih **Refresh** dari daftar dropdown. Sumber data sekarang dipicu untuk penyegaran manual. Merefresh sumber data akan memperbarui skema entitas dan data untuk semua entitas yang ditentukan dalam sumber data.

1. Pilih **Hentikan penyegaran** jika Anda ingin membatalkan refresh yang ada dan sumber data akan kembali ke status refresh terakhirnya.

## <a name="delete-a-data-source"></a>Hapus sumber data

Sumber data hanya dapat dihapus jika data tidak digunakan dalam pemrosesan apa pun seperti penyatuan, wawasan, aktivasi, atau ekspor.

1. Buka **Data** > **Sumber data**.

2. Pilih elipsis vertikal (&vellip;) di samping sumber data ingin Anda hapus dan pilih **Hapus** dari menu tarik-turun.

3. Konfirmasikan penghapusan.


[!INCLUDE [footer-include](includes/footer-banner.md)]
