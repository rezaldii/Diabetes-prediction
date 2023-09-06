# Laporan Proyek Machine Learning - Rezaldi

## Domain Proyek

Dalam proyek ini, analisis akan dilakukan pada data cuaca di Seattle. Data cuaca mencakup berbagai informasi, termasuk tanggal, curah hujan, suhu maksimum dan minimum, kecepatan angin, dan kondisi cuaca. Tujuan akhir dari proyek ini adalah untuk meramalkan kondisi cuaca di masa depan berdasarkan data historis yang sudah ada sebelumnya.

Data cuaca sangat penting dalam berbagai bidang kehidupan sehari-hari, seperti perencanaan aktivitas luar ruangan, manajemen pertanian, dan keselamatan transportasi. Dengan memahami pola cuaca masa lalu dan memanfaatkan algoritma pembelajaran mesin, prediksi cuaca yang lebih tepat dapat dibuat, sehingga memungkinkan individu untuk membuat keputusan yang terinformasi dengan baik.

Untuk menganalisis data cuaca dan membuat prediksi cuaca di masa depan, berbagai teknik dan algoritma, seperti regresi linier, K-Nearest Neighbor, Random Forest, dan Boosting Algorithm, akan digunakan dalam proyek ini. Selain itu, teknik visualisasi data, menggunakan perpustakaan seperti matplotlib dan seaborn, juga akan digunakan untuk memfasilitasi pemahaman yang lebih baik tentang pola cuaca yang ada.

Dengan memahami pola cuaca dan membuat prediksi yang akurat, saya dapat memberikan informasi yang berharga kepada masyarakat dan membantu mereka dalam mengambil keputusan yang lebih baik dalam kehidupan sehari-hari. 

## Business Understanding

### Problem Statements

Berdasarkan latar belakang sebelumnya, masalah yang dapat diatasi melalui proyek ini adalah seperti yang disebutkan di bawah ini:
- Bagaimana meramalkan kondisi cuaca di Seattle secara akurat dengan menggunakan data cuaca historis?
- Bagaimana kita dapat memanfaatkan analisis data cuaca untuk memberikan informasi yang bermanfaat kepada masyarakat Seattle dalam menghadapi perubahan cuaca yang mungkin memengaruhi aktivitas mereka?
- Bagaimana mengembangkan model machine learning yang dapat memberikan prediksi cuaca yang lebih baik daripada model-model sebelumnya?

### Goals

Menjelaskan tujuan dari pernyataan masalah:
- Mengembangkan model prediksi cuaca dengan tingkat akurasi yang tinggi berdasarkan data cuaca historis, termasuk variabel seperti curah hujan, suhu maksimum dan minimum, serta kecepatan angin.
- Memberikan pelayanan informasi cuaca yang dapat membantu masyarakat Seattle dalam perencanaan aktivitas luar ruangan, manajemen pertanian, dan perjalanan sehari-hari mereka.
- Mengembangkan model machine learning yang unggul dalam meramalkan cuaca dengan memanfaatkan teknik-teknik terbaru dalam analisis data.

    ### Solution statements
    - Mengajukan 2 atau lebih solution statement. Misalnya, menggunakan dua atau lebih algoritma untuk mencapai solusi yang diinginkan atau melakukan improvement pada baseline model dengan hyperparameter tuning.
    - Solusi yang diberikan harus dapat terukur dengan metrik evaluasi.

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.