# Laporan Proyek Machine Learning - Rezaldi

## Domain Proyek

Dalam proyek ini, analisis cuaca Seattle memiliki dampak positif pada berbagai bidang kehidupan sehari-hari. Data cuaca yang dianalisis mencakup berbagai informasi, seperti tanggal, curah hujan, suhu maksimum dan minimum, kecepatan angin, dan kondisi cuaca. Tujuan utama proyek ini adalah untuk meramalkan kondisi cuaca di masa depan berdasarkan data historis.

Manfaat dari analisis cuaca ini mencakup:

Perencanaan Aktivitas Luar Ruangan: Dengan informasi cuaca yang lebih akurat, masyarakat dapat merencanakan aktivitas luar ruangan seperti piknik, hiking, atau olahraga dengan lebih baik. Hal ini memungkinkan mereka untuk menghindari hari-hari dengan potensi cuaca buruk, meningkatkan kesenangan dan keselamatan kegiatan mereka.

Manajemen Pertanian: Petani dapat menggunakan prediksi cuaca untuk mengatur jadwal penanaman dan panen secara lebih efisien. Mereka juga dapat mengambil tindakan preventif saat cuaca ekstrem seperti hujan deras atau suhu rendah yang dapat memengaruhi hasil panen.

Keselamatan Transportasi: Pihak berwenang dan pengemudi dapat mempersiapkan diri untuk cuaca buruk yang dapat mempengaruhi lalu lintas dan keselamatan jalan raya. Ini juga dapat membantu maskapai penerbangan dalam menjadwalkan penerbangan dengan lebih baik.

Manajemen Energi: Prediksi cuaca yang akurat dapat membantu manajemen energi, terutama dalam sektor yang terkait dengan pasokan listrik dan penggunaan energi. Ini dapat membantu menghindari pemadaman listrik atau masalah pasokan selama kondisi cuaca ekstrem.

Dalam mencapai tujuan ini, proyek ini akan menggunakan berbagai teknik dan algoritma, seperti regresi linier, K-Nearest Neighbor, Random Forest, dan Boosting Algorithm, serta teknik visualisasi data dengan menggunakan perpustakaan seperti matplotlib dan seaborn. Dengan memahami pola cuaca dan membuat prediksi yang akurat, proyek ini berpotensi memberikan informasi yang berharga kepada masyarakat, membantu mereka dalam mengambil keputusan yang lebih baik dalam kehidupan sehari-hari, dan mendukung berbagai sektor yang bergantung pada informasi cuaca yang handal.

## Business Understanding

### Problem Statements
Berdasarkan latar belakang sebelumnya, masalah yang dapat diatasi melalui proyek ini adalah seperti yang disebutkan di bawah ini:
- Meramalkan Kondisi Cuaca yang Lebih Akurat: Bagaimana meramalkan kondisi cuaca di Seattle secara akurat dengan menggunakan data cuaca historis?
- Pemberian Informasi Cuaca yang Lebih Bermanfaat: Bagaimana kita dapat memanfaatkan analisis data cuaca untuk memberikan informasi yang bermanfaat kepada masyarakat Seattle dalam menghadapi perubahan cuaca yang mungkin memengaruhi aktivitas mereka?
- Pengembangan Model Machine Learning yang Unggul: Bagaimana mengembangkan model machine learning yang dapat memberikan hasil prediksi cuaca yang lebih baik daripada model-model sebelumnya? Bagaimana keunggulan model ini akan diukur?

### Goals
Menjelaskan tujuan dari pernyataan masalah:
- Mengembangkan Model Prediksi Cuaca yang Akurat: Mengembangkan model prediksi cuaca dengan tingkat akurasi yang tinggi berdasarkan data cuaca historis, termasuk variabel seperti curah hujan, suhu maksimum dan minimum, serta kecepatan angin.
- Memberikan Pelayanan Informasi Cuaca yang Bermanfaat: Memberikan pelayanan informasi cuaca yang dapat membantu masyarakat Seattle dalam perencanaan aktivitas luar ruangan, manajemen pertanian, dan perjalanan sehari-hari mereka.
- Mengukur Keunggulan Model: Mengembangkan model machine learning yang unggul dalam meramalkan cuaca dengan memanfaatkan teknik-teknik terbaru dalam analisis data, dan mengukur keunggulan model tersebut melalui metrik yang relevan, seperti akurasi, precision, recall, dan f1-score.

    ### Solution statements
    - Melakukan  analisa, eksplorasi, pemrosesan pada data dengan memvisualisasikan data agar mendapat gambaran bagaimana data tersebut. Berikut adalah analisa yang dapat dilakukan :
        - Mengubah tipe data yang tidak sesuai 
        - Menangani outlier pada data dengan menggunakan IQR Method
        - Melakukan normalisasi pada data terutama pada fitur numerik
    - Membuat model untuk memprediksi cuaca dimasa depan. Berikut beberapa algoritma yang digunakan pada proyek ini :
        - K-Nearest Neighbor
        - Random Forest
        - Boosting Algorithm

## Data Understanding
Dalam proyek ini, data yang digunakan adalah dataset cuaca Seattle yang dapat diunduh dari [Kaggle](https://www.kaggle.com/datasets/ananthr1/weather-prediction).

Dalam dataset cuaca Seattle, terdapat 1461 sampel yang mencakup data cuaca dari 1 Januari 2012 hingga 31 Desember 2015.
- Kategori cuaca yang paling sering muncul dalam dataset adalah "rain"
- Kategori cuaca "sun" memiliki kemunculan yang hampir sama dengan "rain"
- Kategori cuaca "fog" memiliki kemunculan yang lebih sedikit dibandingkan dengan "rain" dan "sun"
- "drizzle" dan "snow" adalah kategori cuaca yang lebih jarang terjadi

### Variabel-variabel dalam Dataset Cuaca Seattle adalah sebagai berikut:
- date: Tanggal pengamatan cuaca (tipe data: object).
- precipitation: Curah hujan pada hari itu (tipe data: float64).
- temp_max: Suhu maksimum (tipe data: float64).
- temp_min: Suhu minimum (tipe data: float64).
- wind: Kecepatan angin (tipe data: float64).
- weather: Kondisi cuaca (tipe data: object).

#### Statistik Deskriptif
- precipitation: Jumlah rata-rata curah hujan adalah sekitar 3,03, menunjukkan fluktuasi yang patut dicatat (standar deviasi sekitar 6,68). Data yang berkaitan dengan curah hujan berkisar dari 0 hingga 55,9.
- temp_max: suhu maksimum rata-rata kira-kira 16,44, dengan jumlah variasi yang sederhana (standar deviasi sekitar 7,35). Suhu maksimum berfluktuasi antara -1,6 hingga 35,6.
- temp_min: suhu minimum rata-rata adalah sekitar 8,23, dengan variasi sedang (standar deviasi sekitar 5,02). Suhu minimum berosilasi antara -7,1 hingga 18,3.
- wind: kecepatan angin rata-rata sekitar 3,24, dengan jumlah variasi sedang (standar deviasi sekitar 1,44). Kecepatan angin berkisar dari 0,4 hingga 9,5.

## Exploratory Data Analysis
### Pengubahan Tipe Data
Mengubah tipe data kolom "date" menjadi tipe data datetime dan kolom "weather" menjadi tipe data kategori.
### Penanganan Missing Values
Tidak ada missing values dalam dataset ini, sehingga tidak diperlukan langkah-langkah khusus untuk menangani missing values.
### Penanganan Outliers
- Melakukan analisis outliers menggunakan boxplot untuk kolom "precipitation," "temp_max," "temp_min," dan "wind."
- Menggunakan metode IQR (Interquartile Range) untuk menghapus outliers pada kolom "precipitation" dan "wind."

## Data Preparation
### Label Encoding
Label Encoding adalah teknik yang digunakan untuk mengubah data kategori (kategori cuaca dalam hal ini) menjadi nilai numerik. Kita menggunakan Label Encoding untuk mengubah kolom "weather" yang berisi kategori cuaca menjadi nilai numerik. Alasan kita memilih teknik Label Encoding adalah karena algoritma machine learning umumnya membutuhkan input berupa nilai numerik, bukan kategori teks. Dengan kata lain, model-machine learning yang kita bangun memerlukan representasi numerik untuk data kategori cuaca.

Dampak dari Label Encoding pada kualitas model adalah:

- Kemampuan Model: Model-machine learning yang menggunakan data yang telah di-label encoding dapat memahami dan memproses data dengan lebih baik karena data telah diubah menjadi bentuk yang dapat dihitung (numerik).

- Peningkatan Akurasi: Label Encoding dapat meningkatkan akurasi model, terutama jika ada hubungan ordinal (urutan) dalam kategori yang di-label. Misalnya, jika cuaca "hujan" di-label sebagai 0, "cerah" sebagai 1, dan "berawan" sebagai 2, model dapat menggunakan informasi ini dalam prediksi.

- Sederhana dalam Implementasi: Label Encoding adalah teknik yang sederhana untuk mengubah kategori menjadi angka, sehingga mudah diimplementasikan.
### Standarisasi Fitur Numerik
Standarisasi adalah teknik yang digunakan untuk mengubah fitur numerik sehingga memiliki rata-rata 0 dan deviasi standar 1. Alasan kita memilih teknik standarisasi adalah untuk memastikan bahwa semua fitur numerik memiliki skala yang seragam. Beberapa algoritma machine learning, seperti K-Nearest Neighbors (KNN) dan algoritma berbasis jarak lainnya, sangat sensitif terhadap perbedaan skala dalam fitur-fitur numerik. Dengan standarisasi, kita memastikan bahwa setiap fitur numerik memiliki dampak yang setara pada model.

Dampak dari Standarisasi pada kualitas model adalah:

- Perbaikan Konvergensi: Standarisasi dapat membantu algoritma konvergen lebih cepat, terutama untuk algoritma berbasis jarak seperti KNN atau algoritma berbasis gradien seperti Gradient Boosting.

- Pengurangan Overfitting: Standarisasi dapat membantu mengurangi risiko overfitting, karena algoritma tidak akan terlalu "menghargai" fitur yang memiliki skala yang besar.

- Peningkatan Akurasi: Standarisasi dapat meningkatkan akurasi model, terutama jika fitur-fitur numerik memiliki skala yang berbeda-beda.

- Interpretabilitas Model: Standarisasi dapat membuat model lebih mudah diinterpretasikan, karena semua fitur numerik memiliki skala yang seragam.

## Modeling
### K-Nearest Neighbor (KNN)
Alasan Pemilihan: KNN adalah algoritma yang digunakan untuk tugas klasifikasi dan regresi. Alasan memilih KNN adalah karena sifatnya yang sederhana dan mudah dipahami. Ini adalah pilihan yang baik ketika Anda memiliki data yang tidak memiliki pola yang jelas atau ketika Anda ingin menghindari asumsi tertentu tentang data Anda.

Cara Kerja: KNN bekerja dengan mencari k-nearest neighbors (tetangga terdekat) dari suatu titik data yang ingin diprediksi. Prediksi dibuat berdasarkan mayoritas label dari tetangga-tetangga tersebut. Algoritma ini menggunakan metrik jarak (misalnya, Euclidean distance) untuk mengukur seberapa mirip titik data yang akan diprediksi dengan tetangga-tetangga yang ada.

Penggunaan KNN pada proyek ini melibatkan:

- Import KNeighborsClassifier dari sklearn.neighbors.
- Membuat sebuah objek KNeighborsClassifier dengan n_neighbors=10, yang berarti kita akan mempertimbangkan 10 tetangga terdekat dalam proses klasifikasi.
- Melatih model KNN menggunakan data pelatihan (X_train_scaled dan y_train).
- Membuat prediksi cuaca pada data pelatihan dan data uji.
- Mengukur akurasi model pada data pelatihan dan data uji menggunakan accuracy_score.
- Menampilkan laporan klasifikasi yang mencakup precision, recall, dan f1-score untuk setiap kategori cuaca.

### Random Forest
Alasan Pemilihan: Random Forest adalah pilihan yang baik ketika Anda ingin mengatasi masalah overfitting dan meningkatkan akurasi. Ini juga cocok untuk tugas klasifikasi dan regresi. Keunggulan Random Forest adalah kemampuannya untuk mengatasi sejumlah besar fitur dan data yang beragam.

Cara Kerja: Random Forest adalah ensemble learning algorithm yang menggunakan sejumlah besar pohon keputusan. Setiap pohon dihasilkan dari sampel acak dari data pelatihan dan fitur-fiturnya. Prediksi akhir diperoleh dengan menggabungkan hasil prediksi dari setiap pohon (melalui mayoritas atau rata-rata, tergantung pada masalahnya).

Penggunaan Random Forest pada proyek ini melibatkan:

- Import RandomForestClassifier dari sklearn.ensemble.
- Membuat sebuah objek RandomForestClassifier dengan n_estimators=100, yang berarti kita akan menggunakan 100 pohon keputusan.
- Melatih model Random Forest menggunakan data pelatihan (X_train_scaled dan y_train).
- Membuat prediksi cuaca pada data pelatihan dan data uji.
- Mengukur akurasi model pada data pelatihan dan data uji menggunakan accuracy_score.
- Menampilkan laporan klasifikasi yang mencakup precision, recall, dan f1-score untuk setiap kategori cuaca.

### Boosting Algorithm (Gradient Boosting)
Alasan Pemilihan: Gradient Boosting adalah algoritma ensemble yang kuat dan sering digunakan dalam kompetisi data science karena kemampuannya menghasilkan prediksi yang sangat akurat. Ini cocok untuk tugas klasifikasi dan regresi.

Cara Kerja: Gradient Boosting bekerja dengan menggabungkan sejumlah besar model lemah (biasanya pohon keputusan dangkal) secara berurutan. Setiap model yang dibangun mencoba memperbaiki kesalahan prediksi model sebelumnya. Proses ini berfokus pada sampel yang memiliki kesalahan prediksi tinggi sebelumnya, sehingga secara bertahap menghasilkan prediksi yang lebih baik.


Penggunaan Gradient Boosting pada proyek ini melibatkan:

- Import GradientBoostingClassifier dari sklearn.ensemble.
- Membuat sebuah objek GradientBoostingClassifier dengan n_estimators=100, yang berarti kita akan menggunakan 100 pohon keputusan dalam proses boosting.
- Melatih model Gradient Boosting menggunakan data pelatihan (X_train_scaled dan y_train).
- Membuat prediksi cuaca pada data pelatihan dan data uji.
- Mengukur akurasi model pada data pelatihan dan data uji menggunakan accuracy_score.
- Menampilkan laporan klasifikasi yang mencakup precision, recall, dan f1-score untuk setiap kategori cuaca.

## Evaluation
Tahap evaluasi dilakukan untuk membandingkan performa ketiga model yang telah dibangun, yaitu K-Nearest Neighbor (KNN), Random Forest, dan Gradient Boosting. Evaluasi dilakukan dengan mengukur akurasi, precision, recall, dan f1-score dari masing-masing model pada data pelatihan dan data uji.

Hasil evaluasi akan membantu kita dalam memilih model terbaik untuk digunakan dalam prediksi cuaca di masa depan. Model dengan akurasi yang tinggi dan nilai precision, recall, dan f1-score yang baik akan menjadi pilihan utama.

Dalam proyek ini, kita telah mengevaluasi ketiga model dan hasilnya adalah sebagai berikut:

### K-Nearest Neighbor (KNN)
- Training Accuracy: 0.786
- Test Accuracy: 0.786
- Classification Report (KNN):
    - Precision, recall, dan f1-score untuk setiap kategori cuaca.
### Random Forest
- Training Accuracy: 0.997
- Test Accuracy: 0.819
- Classification Report (Random Forest):
    - Precision, recall, dan f1-score untuk setiap kategori cuaca.
### Boosting Algorithm (Gradient Boosting)
- Training Accuracy: 0.897
- Test Accuracy: 0.802
- Classification Report (Gradient Boosting):
    - Precision, recall, dan f1-score untuk setiap kategori cuaca.

Berdasarkan hasil evaluasi, kita dapat melihat bahwa model Random Forest memiliki akurasi yang cukup tinggi pada data uji (0.819) dan hasil yang baik dalam precision, recall, dan f1-score untuk setiap kategori cuaca. Oleh karena itu, model Random Forest dapat dipilih sebagai model terbaik untuk digunakan dalam prediksi cuaca di masa depan.