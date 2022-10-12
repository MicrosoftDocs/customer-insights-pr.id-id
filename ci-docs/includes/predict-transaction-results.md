---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611128"
---
- **Performa model pelatihan**: Nilai A, B, atau C menunjukkan kinerja prediksi dan dapat membantu Anda membuat keputusan untuk menggunakan hasil yang disimpan dalam entitas output.

  Peringkat ditentukan berdasarkan aturan berikut:
  - **A** bila model ini secara akurat memprediksi minimal 50% dari total prediksi, dan bila persentase prediksi yang akurat untuk pelanggan yang pergi lebih besar dari tingkat dasar setidaknya 10%.
  - **B** bila model ini secara akurat memprediksi minimal 50% dari total prediksi, dan bila persentase prediksi yang akurat untuk pelanggan yang pergi adalah hingga 10% lebih besar dari tingkat dasar.
  - **C** ketika model secara akurat memprediksi kurang dari 50% dari total prediksi, atau ketika persentase prediksi akurat untuk pelanggan yang bergejolak kurang dari baseline.
  - **Baseline** mengambil input jendela waktu prediksi untuk model (misalnya, satu tahun), dan membuat fraksi waktu yang berbeda dengan membaginya dengan 2 hingga mencapai satu bulan atau kurang. Ia menggunakan pecahan ini untuk membuat aturan bisnis untuk pelanggan yang belum membeli dalam jangka waktu ini. Pelanggan ini dianggap sebagai pergi. Aturan bisnis berbasis waktu dengan kemampuan tertinggi untuk memprediksi siapa yang kemungkinan akan churn dipilih sebagai model dasar.

- **Kecenderungan untuk kehilangan (jumlah pelanggan)**: grup pelanggan berdasarkan prediksi risiko kehilangan. Secara opsional, [buat segmen pelanggan](../prediction-based-segment.md) dengan risiko churn tinggi. Segmen tersebut membantu memahami tempat batas Anda untuk keanggotaan segmen.

- **Faktor yang paling berpengaruh**: ada banyak faktor yang diperhitungkan saat membuat prediksi. Masing-masing faktor memiliki kepentingan yang dihitung untuk membuat prediksi model agregat. Gunakan faktor-faktor ini untuk membantu memvalidasi hasil prediksi Anda. Atau gunakan informasi ini nanti untuk [membuat segmen](../prediction-based-segment.md) yang dapat membantu memengaruhi risiko churn bagi pelanggan.