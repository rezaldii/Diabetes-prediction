# Laporan Proyek Machine Learning - Rezaldi

## Domain Proyek

Diabetes adalah salah satu penyakit kronis yang paling umum di seluruh dunia. Menurut data dari International Diabetes Federation, pada tahun 2019 terdapat sekitar 463 juta orang dewasa yang menderita diabetes di seluruh dunia, dan diperkirakan akan meningkat menjadi 700 juta pada tahun 2045. Diabetes dapat menyebabkan berbagai komplikasi serius seperti penyakit jantung, stroke, kerusakan ginjal, dan kerusakan saraf. Oleh karena itu, penting untuk mendiagnosis dan mengobati diabetes sedini mungkin.

Proyek prediksi diabetes ini bertujuan untuk mengembangkan model yang dapat memprediksi apakah seseorang berisiko terkena diabetes atau tidak berdasarkan data kesehatan mereka. Dataset yang digunakan dalam proyek ini berasal dari Kaggle dan berisi data tentang faktor risiko diabetes seperti usia, jenis kelamin, tekanan darah, kadar gula darah, dan lain-lain. Dengan menggunakan teknik pembelajaran mesin, model ini dapat membantu dokter dalam mendiagnosis diabetes dan memberikan perawatan yang tepat kepada pasien. Ini juga dapat membantu individu untuk mengetahui risiko mereka terhadap diabetes dan mengambil langkah-langkah pencegahan yang diperlukan.

Selain itu, proyek ini juga dapat memberikan wawasan tentang faktor-faktor yang mempengaruhi risiko diabetes. Hal ini dapat membantu dalam pengembangan strategi pencegahan dan perawatan yang lebih efektif. Dengan demikian, proyek ini memiliki potensi untuk memberikan dampak positif bagi kesehatan masyarakat.

Penting juga untuk dicatat bahwa diabetes adalah penyakit yang kompleks dan dipengaruhi oleh banyak faktor. Oleh karena itu, model ini harus digunakan sebagai alat bantu dalam mendiagnosis diabetes dan bukan sebagai pengganti diagnosis medis yang tepat oleh dokter.

Dalam konteks teknis, proyek ini akan melibatkan beberapa tahapan penting dalam pembelajaran mesin, termasuk Data Understanding, Data Preparation, Modeling dan Evaluation. 

Secara keseluruhan, proyek ini menawarkan kesempatan untuk menerapkan dan meningkatkan keterampilan dalam analisis data dan pembelajaran mesin, serta memberikan kontribusi nyata terhadap peningkatan kesehatan masyarakat.

## Business Understanding

### Problem Statements

Berdasarkan informasi latar belakang, dapat diidentifikasi beberapa masalah yang perlu diatasi:
- Bagaimana kita dapat mengatasi masalah diabetes, sebuah penyakit kronis yang umum yang mempengaruhi jutaan orang di seluruh dunia?
- Bagaimana kita dapat meningkatkan diagnosis dan pengobatan dini diabetes untuk mencegah komplikasi serius?
- Apa alat yang dapat membantu dokter mendiagnosis diabetes dengan lebih akurat dan memberikan perawatan yang tepat kepada pasien?

### Goals

Berdasarkan Problem Statements, tujuan untuk proyek ini adalah:
- Mengembangkan model pembelajaran mesin yang dapat memprediksi risiko seseorang terkena diabetes berdasarkan data kesehatan mereka.
- Memberikan wawasan tentang faktor-faktor yang mempengaruhi risiko seseorang terkena diabetes.
- Berkontribusi pada pengembangan strategi pencegahan dan pengobatan yang lebih efektif untuk diabetes.

   ### Solution Statements

   - **Penerapan Model**: Untuk mengatasi masalah ini, akan diajukan beberapa solusi. Pertama, akan diimplementasikan tiga model berbeda, yaitu Random Forest, regresi logistik, dan model pohon keputusan, untuk mengidentifikasi model terbaik yang cocok untuk dataset ini. Selain itu, akan dilakukan feature engineering dengan menambahkan fitur-fitur interaksi dan mencoba berbagai teknik pemrosesan data untuk meningkatkan performa model.

   - **Evaluasi Kinerja Model**: penggunaan berbagai metrik evaluasi seperti akurasi, presisi, recall, dan F1-score.

   - **Penyetelan Hyperparameter**: menggunakan teknik Grid Search dan Random Search. Tujuannya adalah untuk menemukan kombinasi hyperparameter terbaik yang dapat meningkatkan performa model.

## Data Understanding

Data yang digunakan dalam proyek ini adalah [Diabetes Prediction Dataset](https://www.kaggle.com/datasets/iammustafatz/diabetes-prediction-dataset) yang diambil dari Kaggle. Dataset ini digunakan untuk memprediksi apakah seseorang memiliki diabetes berdasarkan berbagai fitur yang termasuk dalam dataset ini.

### Variabel-variabel dalam Diabetes Prediction Dataset adalah sebagai berikut:
1. **gender**: Jenis kelamin pasien (e.g., Female, Male, Other).
2. **age**: Usia pasien dalam tahun.
3. **hypertension**: Indikator hipertensi (1 jika ada, 0 jika tidak).
4. **heart_disease**: Indikator penyakit jantung (1 jika ada, 0 jika tidak).
5. **smoking_history**: Riwayat merokok pasien (e.g., never, former, current, not current, ever).
6. **bmi**: Indeks massa tubuh (BMI) pasien.
7. **HbA1c_level**: Tingkat HbA1c dalam darah pasien.
8. **blood_glucose_level**: Tingkat glukosa darah pasien.
9. **diabetes**: Indikator diabetes (1 jika ada, 0 jika tidak).

**Exploratory Data Analysis (EDA):** Pada tahap EDA, sejumlah visualisasi data telah dilakukan untuk lebih memahami karakteristik dataset. Visualisasi tersebut meliputi grafik batang untuk variabel jenis kelamin (gender) dan riwayat merokok (smoking_history), histogram untuk variabel usia (age), indeks massa tubuh (bmi), dan tingkat glukosa darah (blood_glucose_level). Selain itu, boxplot digunakan untuk melihat sebaran data usia, BMI, dan tingkat glukosa darah. Terdapat juga scatterplot untuk menggambarkan hubungan antara usia (age) dan indeks massa tubuh (bmi).

## Data Preparation
Dalam proyek ini, melakukan beberapa tahapan persiapan data untuk memastikan bahwa data siap digunakan dalam pembuatan model prediksi diabetes. Berikut adalah tahapan data preparation yang telah dilakukan:

1. **Standarisasi Fitur Numerik**: Pada tahap ini, fitur numerik seperti usia (age), indeks massa tubuh (bmi), tingkat HbA1c (HbA1c_level), dan tingkat glukosa darah (blood_glucose_level) telah distandarisasi menggunakan metode Standard Scaler. Alasan standarisasi ini penting adalah untuk memastikan bahwa semua fitur numerik memiliki skala yang seragam. Ini membantu mencegah fitur-fitur dengan skala yang besar mendominasi perhitungan model dan memungkinkan model untuk berkinerja lebih baik.

2. **One-Hot Encoding**: Kolom kategori seperti "gender" dan "smoking_history" telah diubah menjadi variabel biner menggunakan one-hot encoding. Alasan utama di balik ini adalah agar model pembelajaran mesin dapat memahami dan menggunakan informasi dari kolom kategori ini. Karena algoritma pembelajaran mesin umumnya memerlukan input dalam bentuk numerik, encoding ini memungkinkan kita untuk memasukkan informasi kategorikal ke dalam model tanpa bias.

3. **Seleksi Fitur Berdasarkan Korelasi**: Korelasi antara fitur-fitur numerik dengan variabel target "diabetes" telah dihitung. Fitur-fitur yang memiliki korelasi relevan dengan nilai ambang batas (0.1) telah dipilih untuk digunakan dalam pembuatan model. Alasan di balik ini adalah untuk mengurangi dimensi fitur dan fokus pada fitur-fitur yang memiliki pengaruh lebih besar terhadap variabel target. Ini dapat membantu meningkatkan kinerja model dan mengurangi overfitting.

4. **Pemisahan Data menjadi Set Pelatihan dan Set Tes**: Data telah dibagi menjadi dua set, yaitu set pelatihan (80% data) dan set tes (20% data) menggunakan fungsi `train_test_split` dari library scikit-learn. Alasan di balik ini adalah untuk memungkinkan evaluasi yang obyektif terhadap kinerja model. Set tes digunakan untuk menguji model pada data yang belum pernah dilihat sebelumnya, sehingga kita dapat memahami sejauh mana model yang dibangun dapat digeneralisasi ke data baru.

## Modeling

Dalam proyek ini, menggunakan tiga jenis model machine learning yang berbeda untuk memprediksi risiko diabetes: Regresi Logistik, Pohon Keputusan, dan Random Forest.

### 1. Regresi Logistik:
- **Tahapan Pemodelan**:
  - Proses pemodelan dimulai dengan inisialisasi model regresi logistik.
  - Model ini kemudian dilatih pada set pelatihan dan digunakan untuk memprediksi kelas target pada set tes.
  - Akurasi model dihitung, dan laporan klasifikasi serta matriks konfusi ditampilkan.

- **Kelebihan**:
  - Mudah dipahami dan diinterpretasi. Koefisien dapat memberikan wawasan tentang hubungan antara fitur dan target.
  - Kinerja baik untuk masalah klasifikasi biner sederhana.
  - Cenderung tidak overfitting karena model yang sederhana.

- **Kekurangan**:
  - Sering kali kurang mampu menangani masalah yang lebih kompleks dengan banyak fitur atau hubungan non-linear.
  - Performa mungkin tidak setinggi model lain seperti Pohon Keputusan atau Random Forest.

### 2. Pohon Keputusan:
- **Tahapan Pemodelan**:
  - Model pohon keputusan inisialisasi dengan sejumlah hyperparameter default.
  - Grid Search digunakan untuk melakukan penyetelan hyperparameter seperti `max_depth`, `min_samples_split`, `min_samples_leaf`, dan `criterion`.
  - Setelah penyetelan, model pohon keputusan terbaik dipilih.
  - Model ini dilatih pada set pelatihan dan digunakan untuk memprediksi kelas target pada set tes.

- **Kelebihan**:
  - Dapat menangani masalah klasifikasi dan regresi.
  - Mudah dipahami dan diinterpretasi.
  - Mampu menangani hubungan non-linear dan interaksi fitur.

- **Kekurangan**:
  - Cenderung overfitting terutama jika `max_depth` diatur sangat tinggi.
  - Model ini tidak stabil, yang berarti perubahan kecil dalam data pelatihan dapat menghasilkan pohon yang sangat berbeda.

### 3. Random Forest:
- **Tahapan Pemodelan**:
  - Model Random Forest inisialisasi dengan sejumlah hyperparameter default.
  - Grid Search digunakan untuk melakukan penyetelan hyperparameter seperti `n_estimators`, `max_depth`, `min_samples_split`, dan `min_samples_leaf`.
  - Setelah penyetelan, model Random Forest terbaik dipilih.
  - Model ini dilatih pada set pelatihan dan digunakan untuk memprediksi kelas target pada set tes.

- **Kelebihan**:
  - Dapat menangani masalah klasifikasi dan regresi.
  - Mengatasi masalah overfitting yang biasa terjadi pada Pohon Keputusan dengan menggunakan banyak pohon (ensemble).
  - Mampu menangani hubungan non-linear dan interaksi fitur.
  - Stabil dan konsisten dalam performa.

- **Kekurangan**:
  - Lebih kompleks daripada model Regresi Logistik, yang membuatnya lebih sulit diinterpretasi.
  - Dapat memerlukan lebih banyak waktu komputasi dibandingkan dengan model sederhana seperti Regresi Logistik.

**Pemilihan Model Terbaik**:
Setelah melakukan penyetelan hyperparameter, baik model Pohon Keputusan maupun Random Forest yang disesuaikan memiliki akurasi yang hampir sama pada set tes (sekitar 97.0% dan 97.1% masing-masing). Namun, Random Forest cenderung lebih stabil dan kurang cenderung overfitting dibandingkan dengan Pohon Keputusan. Oleh karena itu, sebagai solusi terbaik, akan memilih model Random Forest yang disesuaikan untuk memprediksi risiko diabetes. Model ini memiliki performa yang baik dan cenderung lebih dapat diandalkan dalam mengklasifikasikan pasien sebagai berisiko atau tidak berisiko diabetes.

## Evaluation

Dalam proyek ini, menggunakan beberapa metrik evaluasi yang umum digunakan dalam masalah klasifikasi, yaitu:

1. **Akurasi (Accuracy)**: Akurasi mengukur sejauh mana model berhasil mengklasifikasikan data dengan benar, baik kelas positif maupun kelas negatif. Rumusnya adalah:

   \[
   \text{Akurasi} = \frac{\text{Jumlah prediksi benar}}{\text{Total jumlah data}}
   \]

2. **Presisi (Precision)**: Presisi mengukur sejauh mana prediksi positif yang dibuat oleh model adalah benar. Presisi memberikan informasi tentang berapa banyak dari kasus yang diprediksi positif yang sebenarnya positif. Rumusnya adalah:

   \[
   \text{Presisi} = \frac{\text{Jumlah True Positives}}{\text{Jumlah True Positives + Jumlah False Positives}}
   \]

3. **Recall (Sensitivity atau True Positive Rate)**: Recall mengukur sejauh mana model berhasil menemukan semua kasus positif yang sebenarnya. Recall memberikan informasi tentang berapa banyak dari kasus positif yang sebenarnya yang berhasil diidentifikasi oleh model. Rumusnya adalah:

   \[
   \text{Recall} = \frac{\text{Jumlah True Positives}}{\text{Jumlah True Positives + Jumlah False Negatives}}
   \]

4. **F1-Score**: F1-Score adalah pengukuran yang menggabungkan presisi dan recall menjadi satu metrik yang seimbang. F1-Score adalah harmonic mean dari presisi dan recall. Rumusnya adalah:

   \[
   \text{F1-Score} = 2 \times \frac{\text{Presisi} \times \text{Recall}}{\text{Presisi} + \text{Recall}}
   \]

Hasil proyek berdasarkan metrik evaluasi yang digunakan adalah sebagai berikut:

- Model Regresi Logistik memiliki akurasi sebesar 95.7%, presisi sebesar 85.2%, recall sebesar 62.8%, dan F1-Score sebesar 72.3%. Model ini memiliki kinerja yang baik dalam mengklasifikasikan pasien, tetapi memiliki recall yang lebih rendah, yang berarti ia memiliki kecenderungan untuk tidak mendeteksi sejumlah besar kasus positif sebenarnya.

- Model Pohon Keputusan (setelah penyetelan) memiliki akurasi sebesar 97.0%, presisi sebesar 99.1%, recall sebesar 67.5%, dan F1-Score sebesar 80.3%. Model ini memiliki kinerja yang lebih baik daripada model Regresi Logistik, dengan recall yang lebih baik, yang berarti lebih baik dalam mendeteksi kasus positif.

- Model Random Forest (setelah penyetelan) memiliki akurasi sebesar 97.1%, presisi sebesar 99.7%, recall sebesar 67.3%, dan F1-Score sebesar 80.4%. Model ini memiliki kinerja yang hampir sama dengan model Pohon Keputusan, tetapi dengan presisi yang sedikit lebih tinggi.

Berdasarkan metrik evaluasi tersebut, baik model Pohon Keputusan maupun model Random Forest memiliki kinerja yang lebih baik daripada model Regresi Logistik. Model-model ini memiliki akurasi yang tinggi, presisi yang baik, dan recall yang layak, sehingga cocok digunakan untuk tujuan mengidentifikasi risiko diabetes. Model terbaik yang dipilih dalam proyek ini adalah model Random Forest karena memiliki performa yang sangat baik dalam hal presisi dan recall, serta mendukung keputusan klinis yang lebih baik.

## Referensi:
---

- Q. R. Cahyani et al., “Prediksi Risiko Penyakit Diabetes menggunakan Algoritma Regresi Logistik Diabetes Risk Prediction using Logistic Regression Algorithm Article Info ABSTRAK,” JOMLAI J. Mach. Learn. Artif. Intell., vol. 1, no. 2, pp. 2828–9099, 2022, doi: 10.55123/jomlai.v1i2.598.

- W. Apriliah, I. Kurniawan, M. Baydhowi, and T. Haryati, “SISTEMASI: Jurnal Sistem Informasi Prediksi Kemungkinan Diabetes pada Tahap Awal Menggunakan Algoritma Klasifikasi Random Forest,” J. Sist. Inf., vol. 10, pp. 163–171, 2021, [Online]. Available: http://sistemasi.ftik.unisi.ac.id

- A. Andriani, “Sistem Prediksi Penyakit Diabetes Berbasis Decision Tree,” J. Bianglala Inform., vol. I, no. 1, pp. 1–10, 2013, [Online]. Available: https://ejournal.bsi.ac.id/ejurnal/index.php/Bianglala/article/view/554/446

