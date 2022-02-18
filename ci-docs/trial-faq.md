---
title: Tanya-Jawab Uji coba - Dynamics 365 Customer Insights
description: Solusi untuk pertanyaan umum terkait penyiapan dan manajemen uji coba Customer Insights. Pelajari cara menangani masalah platform dan khusus aplikasi.
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.service: customer-insights
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: f63ed39ba8c710d0c0149e0944efaafe27e7b9bb
ms.sourcegitcommit: 5dd32dc2b18027cf2aa954356dded4bc6aab9801
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/12/2022
ms.locfileid: "8115972"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Tanya Jawab uji coba Dynamics 365 Customer Insights

## <a name="sign-up"></a>Mendaftar

### <a name="what-are-the-system-requirements-for-the-trial"></a>Apa saja persyaratan sistem untuk uji coba?

Aplikasi ini adalah layanan berbasis cloud yang tidak memerlukan perangkat lunak khusus selain web browser terbaru, meskipun beberapa batasan berlaku. Untuk pengalaman uji coba terbaik, hindari mengakses situs uji coba dalam mode penyamaran dan pilih lokasi uji coba yang paling dekat dengan Anda. [Pelajari lebih lanjut persyaratan aplikasi web.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Bagaimana cara mendaftar untuk uji coba tanpa Microsoft 365 penyewa?

Anda dapat memasukkan alamat email non-kerja dan kami akan membuat akun dan penyewa untuk Anda.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Dapatkah saya mendaftar untuk beberapa aplikasi Dynamics 365 seperti Sales, Marketing, dan Customer Service?

Ya, Anda dapat. Untuk melihat semua uji coba yang tersedia, [kunjungi halaman hub uji coba](https://dynamics.microsoft.com/dynamics-365-free-trial). Anda dapat menggunakan akun email yang sama untuk mendaftar uji coba yang berbeda. Namun, beberapa aplikasi tidak dapat digunakan di situs uji coba yang sama. Setiap uji coba akan dilakukan di organisasi dan URL yang berbeda. Data uji coba tidak akan dibagikan di seluruh aplikasi.

## <a name="trial-app"></a>Aplikasi uji coba

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Saya tidak menerima email rincian uji coba setelah mendaftar, apa yang harus saya lakukan?

Saat mendaftar uji coba, Anda akan menerima email berisi detail uji coba. Jika Anda tidak melihat email di kotak masuk, periksa folder spam. Atau, gunakan langkah-langkah berikut untuk mengakses aplikasi:

1. Buka situs uji coba, lalu pilih **Coba secara gratis**.
1. Masukkan ID email yang Anda gunakan untuk mendaftar uji coba. Anda akan diarahkan ulang ke aplikasi uji coba.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Bagaimana cara menambahkan lebih banyak pengguna ke uji coba?

Untuk menambahkan pengguna, buka [Microsoft 365 pusat](https://admin.microsoft.com) admin menggunakan akun admin uji coba. Ikuti [panduan pusat admin](/microsoft-365/admin/add-users/add-users) untuk menambahkan pengguna hingga batas lisensi uji coba. Jika pengguna yang Anda tambahkan sudah memiliki Microsoft 365 akun, tetapkan peran keamanan yang sesuai di organisasi uji coba. Untuk informasi selengkapnya, lihat [Menetapkan peran keamanan ke pengguna](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Berapa pengguna yang dapat saya tambahkan ke lingkungan uji coba saya?

Anda dapat menambahkan jumlah pengguna yang tidak terbatas ke lingkungan uji coba.

### <a name="how-do-i-reset-the-trial-environment"></a>Bagaimana cara mengatur ulang lingkungan uji coba?

Anda tidak dapat mengatur ulang lingkungan uji coba. Namun, Anda dapat menunggu periode uji coba berakhir, lalu mendaftar lagi untuk uji coba baru.

## <a name="trial-expiration-and-extension"></a>Kedaluwarsa dan perpanjangan uji coba

### <a name="how-do-i-extend-the-trial"></a>Bagaimana cara memperpanjang masa uji coba?

Anda dapat memperpanjang uji coba dalam aplikasi secara langsung. Anda dapat memperpanjang uji coba satu kali.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Dapatkah saya mengonversi uji coba menjadi lisensi berbayar?

Umumnya, kami sarankan untuk memulai dari awal dengan data Anda sendiri saat memutakhirkan ke versi berbayar Customer Insights. 

Atau, jika Anda hanya menggunakan audiens wawasan, Anda dapat menyalin data dari lingkungan uji coba jika Anda membeli Customer Insights. Anda harus menjadi administrator uji coba Wawasan Pelanggan dan admin global penyewa Anda Microsoft 365, atau administrator Dynamics 365 di organisasi Anda untuk memigrasikan pengaturan dari lingkungan uji coba ke lingkungan berbayar. 

Setelah masuk ke instans Customer Insights berbayar Anda untuk pertama kalinya, Anda diminta untuk membuat lingkungan baru. Dalam proses ini, Anda dapat memilih untuk menyalin konfigurasi dari lingkungan yang ada dan memigrasikan sebagian besar pengaturan. Jika Anda memiliki izin yang disebutkan di atas, lingkungan uji coba akan ditampilkan dalam daftar ini. Untuk informasi selengkapnya, lihat [Menyalin konfigurasi lingkungan](audience-insights/manage-environments.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Apa saja batas uji coba dan kuota?

- Anda tidak dapat menggunakan akun Azure Data Lake Storage untuk menyimpan data output selama uji coba wawasan audiens. Namun, Anda dapat menyerap data dari akun Data Lake Storage.
- Anda dapat menyimpan data hingga 3 GB di lingkungan Dataverse yang disediakan secara otomatis saat memulai uji coba Customer Insights.

## <a name="customer-insights-specific-questions"></a>Pertanyaan khusus Customer Insights

### <a name="how-do-i-start-using-the-trial"></a>Bagaimana cara mulai menggunakan uji coba?

Setelah mendaftar uji coba, Anda akan dialihkan ke layar utama aplikasi. Layar utama memberikan tautan ke panduan dan tutorial pengguna. Untuk mempelajari lebih lanjut, kunjungi tautan di [Sumber daya tambahan](trial-signup.md#additional-resources) pada halaman pendaftaran uji coba.

### <a name="what-features-are-available-in-the-trial"></a>Fitur apa saja yang tersedia dalam uji coba?

Sebagian besar fitur kemampuan Customer Insights tersedia dalam uji coba.

Fitur-fitur **berikut tidak tersedia**: 
- Anda tidak dapat membuat lingkungan baru yang menggunakan akun penyimpanan Azure Data Lake Storage.
- Anda tidak dapat menghapus lingkungan uji coba. 

### <a name="how-long-does-the-trial-last"></a>Berapa lama uji coba berlangsung?

Uji coba Customer Insights berlangsung selama 30 hari. Anda dapat memperpanjang uji coba sekali setelah 23 hari saat masuk ke lingkungan uji coba Anda.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Bagaimana cara menghapus data sampel dari uji coba?

Anda tidak dapat menghapus data sampel dari uji coba.
