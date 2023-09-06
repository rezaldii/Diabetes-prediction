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

### Variabel-variabel dalam Dataset Cuaca Seattle adalah sebagai berikut:
- date: Tanggal pengamatan cuaca (tipe data: object).
- precipitation: Curah hujan pada hari itu (tipe data: float64).
- temp_max: Suhu maksimum (tipe data: float64).
- temp_min: Suhu minimum (tipe data: float64).
- wind: Kecepatan angin (tipe data: float64).
- weather: Kondisi cuaca (tipe data: object).

Dataset ini memiliki total 1461 baris data dengan 6 kolom. Data ini akan digunakan untuk melakukan analisis cuaca historis dan mengembangkan model prediksi cuaca di masa depan. Variabel-variabel ini akan diolah dan dianalisis lebih lanjut dalam proyek ini untuk memahami pola cuaca dan melakukan prediksi cuaca yang lebih akurat.

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
Menggunakan LabelEncoder untuk mengubah kolom "weather" yang berisi kategori cuaca menjadi nilai numerik.
### Standarisasi Fitur Numerik
Melakukan standarisasi pada fitur-fitur numerik untuk memastikan skala yang seragam.

## Modeling
### K-Nearest Neighbor (KNN)
Pada tahap ini, menggunakan algoritma K-Nearest Neighbor (KNN) untuk membangun model prediksi cuaca. Algoritma KNN digunakan untuk mengklasifikasikan data berdasarkan kemiripan dengan tetangga terdekat.

Penggunaan KNN pada proyek ini melibatkan:

- Import KNeighborsClassifier dari sklearn.neighbors.
- Membuat sebuah objek KNeighborsClassifier dengan n_neighbors=10, yang berarti kita akan mempertimbangkan 10 tetangga terdekat dalam proses klasifikasi.
- Melatih model KNN menggunakan data pelatihan (X_train_scaled dan y_train).
- Membuat prediksi cuaca pada data pelatihan dan data uji.
- Mengukur akurasi model pada data pelatihan dan data uji menggunakan accuracy_score.
- Menampilkan laporan klasifikasi yang mencakup precision, recall, dan f1-score untuk setiap kategori cuaca.

### Random Forest
Random Forest adalah salah satu algoritma ensemble yang menggabungkan beberapa pohon keputusan (decision trees) untuk meningkatkan akurasi prediksi. Pada proyek ini, kita menggunakan Random Forest untuk membangun model prediksi cuaca.

Penggunaan Random Forest pada proyek ini melibatkan:

- Import RandomForestClassifier dari sklearn.ensemble.
- Membuat sebuah objek RandomForestClassifier dengan n_estimators=100, yang berarti kita akan menggunakan 100 pohon keputusan.
- Melatih model Random Forest menggunakan data pelatihan (X_train_scaled dan y_train).
- Membuat prediksi cuaca pada data pelatihan dan data uji.
- Mengukur akurasi model pada data pelatihan dan data uji menggunakan accuracy_score.
- Menampilkan laporan klasifikasi yang mencakup precision, recall, dan f1-score untuk setiap kategori cuaca.

### Boosting Algorithm (Gradient Boosting)
Boosting adalah teknik ensemble lainnya yang menggabungkan beberapa model lemah untuk membuat model yang lebih kuat. Pada proyek ini, kita menggunakan algoritma Gradient Boosting untuk membangun model prediksi cuaca.

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