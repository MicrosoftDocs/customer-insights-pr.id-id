---
title: Ikhtisar sumber data
description: Pelajari cara mengimpor atau menyerap data dari berbagai sumber.
ms.date: 09/29/2022
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
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610056"
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

Sumber data dapat disegarkan dengan jadwal otomatis atau diperbarui secara manual sesuai permintaan. [Sumber](connect-power-query.md#add-data-from-on-premises-data-sources) data lokal disegarkan pada jadwal mereka sendiri yang disiapkan selama penyerapan data. Untuk tips pemecahan masalah, lihat [Memecahkan masalah refresh Power Query sumber data berbasis PPDF](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

Untuk sumber data terlampir, penyerapan data menghabiskan data terbaru yang tersedia dari sumber data tersebut.

Buka **Jadwal** > **Sistem** > [**Admin**](schedule-refresh.md) untuk mengonfigurasi refresh terjadwal sistem dari sumber data yang Anda konsumsi.

Untuk menyegarkan sumber data sesuai permintaan:

1. Buka **Data** > **Sumber data**.

1. Pilih sumber data yang ingin Anda refresh dan pilih **Refresh**. Sumber data sekarang dipicu untuk penyegaran manual. Merefresh sumber data akan memperbarui skema entitas dan data untuk semua entitas yang ditentukan dalam sumber data.

1. Pilih status untuk membuka **panel Detail** kemajuan dan lihat kemajuan. Untuk membatalkan pekerjaan, pilih **Batalkan pekerjaan** di bagian bawah panel.

## <a name="corrupt-data-sources"></a>Sumber data yang rusak

Data yang diserap mungkin memiliki catatan rusak yang dapat menyebabkan proses penyerapan data diselesaikan dengan kesalahan atau peringatan.

> [!NOTE]
> Jika penyerapan data selesai dengan kesalahan, pemrosesan selanjutnya (seperti penyatuan atau pembuatan aktivitas) yang memanfaatkan sumber data ini akan dilewati. Jika penyerapan dilengkapi dengan peringatan, pemrosesan selanjutnya berlanjut tetapi beberapa catatan mungkin tidak disertakan.

Kesalahan ini dapat dilihat di detail tugas.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Detail tugas memperlihatkan kesalahan data yang rusak.":::

Rekaman yang rusak ditampilkan dalam entitas yang dibuat sistem.

### <a name="fix-corrupt-data"></a>Memperbaiki data yang rusak

1. Untuk melihat data yang rusak, buka **Entitas** > **Data** dan cari entitas yang rusak di **bagian Sistem**. Skema penamaan entitas yang rusak: 'DataSourceName_EntityName_corrupt'.

1. Pilih entitas yang rusak lalu tab **Data**.

1. Identifikasi bidang yang rusak dalam catatan dan alasannya.

   :::image type="content" source="media/corruption-reason.png" alt-text="Alasan korupsi." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Entitas** > **Data** hanya menampilkan sebagian dari rekaman yang rusak. Untuk melihat semua rekaman yang rusak, ekspor file ke kontainer di akun penyimpanan menggunakan [proses](export-destinations.md) ekspor Customer Insights. Jika menggunakan akun penyimpanan sendiri, Anda juga dapat melihat folder Customer Insights di akun penyimpanan Anda.

1. Perbaiki data yang rusak. Misalnya, untuk sumber data Azure Data Lake, [perbaiki data di Data Lake Storage atau perbarui tipe data dalam file](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data) manifest/model.json. Untuk Power Query sumber data, perbaiki data dalam file sumber dan [perbaiki tipe data langkah](connect-power-query.md#data-type-does-not-match-data) transformasi pada **Power Query halaman - Edit kueri**.

Setelah penyegaran berikutnya dari sumber data, rekaman yang dikoreksi diserap ke Customer Insights dan diteruskan ke proses hilir.

Misalnya, kolom 'ulang tahun' memiliki himpunan tipe data sebagai 'tanggal'. Rekaman pelanggan memasukkan ulang tahun mereka sebagai '01/01/19777'. Sistem menandai catatan ini sebagai korup. Ubah ulang tahun dalam sistem sumber menjadi '1977'. Setelah refresh otomatis sumber data, bidang sekarang memiliki format yang valid dan rekaman dihapus dari entitas yang rusak.

[!INCLUDE [footer-include](includes/footer-banner.md)]
