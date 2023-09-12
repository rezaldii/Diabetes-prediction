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

Dalam proyek ini, data yang digunakan berasal dari [Kaggle - Diabetes Prediction Dataset](https://www.kaggle.com/datasets/iammustafatz/diabetes-prediction-dataset). Dataset ini digunakan untuk memprediksi kemungkinan seseorang mengidap diabetes berdasarkan berbagai fitur seperti usia, jenis kelamin, riwayat penyakit jantung, riwayat merokok, indeks massa tubuh (BMI), tingkat HbA1c, dan tingkat glukosa darah.

### Variabel-variabel pada Diabetes Prediction Dataset adalah sebagai berikut:
- **gender**: Jenis kelamin pasien (e.g., Female, Male, Other).
- **age**: Usia pasien dalam tahun.
- **hypertension**: Indikator hipertensi (0: Tidak, 1: Ya).
- **heart_disease**: Indikator penyakit jantung (0: Tidak, 1: Ya).
- **smoking_history**: Riwayat merokok pasien (e.g., never, current, former, not current, ever).
- **bmi**: Indeks massa tubuh (BMI) pasien.
- **HbA1c_level**: Tingkat HbA1c dalam darah pasien.
- **blood_glucose_level**: Tingkat glukosa dalam darah pasien.
- **diabetes**: Status diabetes (0: Non-diabetes, 1: Diabetes).

### Data Understanding Steps:
1. Data telah dimuat ke dalam DataFrame dan ditampilkan 5 baris pertama sebagai contoh.
2. Informasi tentang jumlah baris dan kolom dalam dataset telah disajikan.
3. Jenis data (data types) dari setiap kolom telah ditampilkan.
4. Statistik deskriptif seperti mean, std, min, dan max untuk kolom numerik telah disajikan.
5. Jumlah nilai yang hilang (missing values) dalam setiap kolom telah dicantumkan. Dalam kasus ini, tidak ada nilai yang hilang dalam dataset.
6. Jumlah nilai unik dalam setiap kolom telah disajikan.
7. Frekuensi jumlah masing-masing kategori dalam kolom kategorikal seperti jenis kelamin dan riwayat merokok telah ditampilkan dalam bentuk tabel dan grafik batang.
8. Visualisasi data seperti histogram, box plot, dan scatter plot digunakan untuk memahami distribusi dan hubungan antara variabel numerik seperti usia, BMI, dan tingkat glukosa darah.
9. Dilakukan pengujian hipotesis statistik untuk menguji perbedaan rata-rata BMI antara pasien diabetes dan non-diabetes, serta perbedaan rata-rata BMI antara kelompok berbeda berdasarkan riwayat merokok.
10. Dibuat tabel kontingensi dan dilakukan uji chi-square untuk menguji hubungan antara jenis kelamin dan diabetes.
11. Korelasi antara usia (age) dan indeks massa tubuh (BMI) dihitung menggunakan metode Pearson dan divisualisasikan sebagai scatter plot.
12. Deteksi anomali dilakukan dengan menggunakan Isolation Forest untuk variabel numerik tertentu seperti usia, BMI, tingkat HbA1c, dan tingkat glukosa darah.
13. Verifikasi kualitas data meliputi pemeriksaan data duplikat dan penanganan nilai outlier untuk variabel numerik tertentu.
14. Dalam proses verifikasi kualitas data, nilai "Other" dalam kolom "gender" diganti dengan NaN untuk meningkatkan konsistensi data.

## Data Preparation
Pada proyek ini, beberapa tahapan data preparation telah dilakukan untuk memastikan kualitas dan kesiapan data sebelum digunakan dalam pembuatan model prediksi diabetes. Berikut adalah tahapan-tahapan tersebut:

### 1. Standarisasi Fitur Numerik
Tahapan ini melibatkan standarisasi fitur-fitur numerik seperti "age," "bmi," "HbA1c_level," dan "blood_glucose_level" menggunakan Standard Scaler. Alasan utama untuk standarisasi adalah agar skala fitur-fitur tersebut seragam. Beberapa algoritma pembelajaran mesin, seperti regresi logistik dan SVM, sangat rentan terhadap perbedaan skala antar fitur. Dengan melakukan standarisasi, kita memastikan bahwa setiap fitur memiliki mean nol dan deviasi standar satu.

**Output**:
```
   gender       age  hypertension  heart_disease smoking_history       bmi  \
0  Female  1.700840             0              1           never -0.310970   
1  Female  0.543372             0              0         No Info  0.048828   
2    Male -0.614096             0              0           never  0.048828   
3  Female -0.257952             0              0         current -0.604890   
4    Male  1.522768             1              1         current -1.164014   

   HbA1c_level  blood_glucose_level  diabetes  anomaly  
0     1.024846             0.043554         0        1  
1     1.024846            -1.423096         0        1  
2     0.167291             0.483549         0        1  
3    -0.499697             0.410216         0        1  
4    -0.690265             0.410216         0        1  
```

### 2. One-Hot Encoding
Fitur kategori seperti "gender" dan "smoking_history" telah diubah menjadi variabel biner menggunakan one-hot encoding. Ini dilakukan karena beberapa algoritma pembelajaran mesin memerlukan input dalam bentuk numerik. One-hot encoding memungkinkan kita untuk memasukkan informasi ini ke dalam model tanpa bias.

**Output**:
```
    age  hypertension  heart_disease    bmi  HbA1c_level  blood_glucose_level  \
0  80.0             0              1  25.19          6.6                  140   
1  54.0             0              0  27.32          6.6                   80   
2  28.0             0              0  27.32          5.7                  158   
3  36.0             0              0  23.45          5.0                  155   
4  76.0             1              1  20.14          4.8                  155   

   diabetes  anomaly  gender_Male  smoking_history_current  \
0         0        1        False                    False   
1         0        1        False                    False   
2         0        1         True                    False   
3         0        1        False                     True   
4         0        1         True                     True   

   smoking_history_ever  smoking_history_former  smoking_history_never  \
0                 False                   False                   True   
1                 False                   False                  False   
2                 False                   False                   True   
3                 False                   False                  False   
4                 False                   False                  False   

   smoking_history_not current  
0                        False  
1                        False  
2                        False  
3                        False  
4                        False  
```

### 3. Seleksi Fitur
Korelasi antara fitur-fitur numerik dengan variabel target "diabetes" telah dihitung. Fitur-fitur yang memiliki korelasi relevan dengan ambang batas 0.1 telah dipilih untuk digunakan dalam model prediksi. Ini bertujuan untuk mengurangi dimensi fitur dan hanya mempertahankan fitur yang memiliki pengaruh signifikan terhadap prediksi diabetes.

### 4. Pemisahan Data
Data telah dibagi menjadi dua set, yaitu set pelatihan (80% data) dan set tes (20% data) menggunakan `train_test_split` dari scikit-learn. Hal ini dilakukan untuk menguji kinerja model pada data yang belum pernah dilihat sebelumnya. Jumlah sampel dalam set pelatihan adalah 76,916, sedangkan jumlah sampel dalam set tes adalah 19,230.

## Modeling

Dalam tahap pemodelan, menggunakan tiga algoritma machine learning, yaitu:

1. **Regresi Logistik**:
   - Algoritma ini digunakan sebagai model baseline untuk memahami sejauh mana model sederhana ini dapat mengklasifikasikan pasien berisiko diabetes.
   - Parameter yang digunakan pada model regresi logistik adalah parameter defaultnya karena model ini tidak memiliki banyak hyperparameter yang dapat diatur.

2. **Pohon Keputusan**:
   - Algoritma ini digunakan setelah melakukan penyetelan hyperparameter menggunakan Grid Search untuk meningkatkan kinerja.
   - Parameter yang diatur melalui Grid Search adalah:
     - `max_depth`: Kedalaman maksimum setiap pohon keputusan.
     - `min_samples_split`: Jumlah sampel minimum yang diperlukan untuk membagi node internal.
     - `min_samples_leaf`: Jumlah sampel minimum yang diperlukan untuk berada di node daun.
     - `criterion`: Kriteria pengukuran kualitas split, yang bisa berupa 'gini' atau 'entropy'.

3. **Random Forest**:
   - Algoritma ini juga digunakan setelah melakukan penyetelan hyperparameter menggunakan Grid Search untuk meningkatkan kinerja.
   - Parameter yang diatur melalui Grid Search adalah:
     - `n_estimators`: Jumlah pohon dalam ensemble Random Forest.
     - `max_depth`: Kedalaman maksimum setiap pohon dalam ensemble.
     - `min_samples_split`: Jumlah sampel minimum yang diperlukan untuk membagi node internal.
     - `min_samples_leaf`: Jumlah sampel minimum yang diperlukan untuk berada di node daun.

**Kelebihan dan Kekurangan Algoritma**:

- **Regresi Logistik**:
  - Kelebihan: Model yang sederhana dan mudah diinterpretasi. Cepat dilatih dan cocok sebagai model baseline.
  - Kekurangan: Kurang mampu menangani hubungan non-linear dalam data.

- **Pohon Keputusan**:
  - Kelebihan: Dapat menangani hubungan non-linear, mudah diinterpretasi, dan mampu menangani berbagai jenis data.
  - Kekurangan: Cenderung overfitting jika tidak ada pembatasan kedalaman (max_depth).

- **Random Forest**:
  - Kelebihan: Mengatasi overfitting dengan menggabungkan banyak pohon, mampu menangani data dengan banyak fitur, dan memiliki kinerja yang baik secara umum.
  - Kekurangan: Lebih kompleks dan memerlukan penyetelan hyperparameter.

**Proses Improvement**:
- Untuk model Pohon Keputusan dan Random Forest, saya melakukan penyetelan hyperparameter menggunakan Grid Search untuk meningkatkan kinerja model. Proses ini melibatkan eksplorasi berbagai kombinasi hyperparameter untuk mencari yang terbaik.

**Pemilihan Model Terbaik**:
- Model terbaik di antara ketiga model yang telah diuji adalah **Random Forest yang ditingkatkan**. Model ini memiliki akurasi setara dengan model Pohon Keputusan yang ditingkatkan dan sedikit lebih baik dalam mengklasifikasikan kelas 1 (risiko diabetes).
- Kelebihan model Random Forest yang ditingkatkan adalah kemampuannya untuk mengatasi overfitting dan memiliki kinerja yang baik secara keseluruhan.

Berikut adalah parameter terbaik yang ditemukan untuk masing-masing model:
- **Regresi Logistik**: Menggunakan parameter default.
- **Pohon Keputusan**: {'max_depth': 10, 'min_samples_leaf': 1, 'min_samples_split': 2, 'criterion': 'gini'}
- **Random Forest**: {'max_depth': 10, 'min_samples_leaf': 1, 'min_samples_split': 2, 'n_estimators': 100}

Saya memilih model **Random Forest yang ditingkatkan** sebagai model terbaik karena memiliki kinerja yang setara dengan Pohon Keputusan yang ditingkatkan, tetapi mungkin lebih stabil dan kurang cenderung overfitting. Model ini juga memiliki akurasi yang baik dalam mengklasifikasikan risiko diabetes.

## Evaluation

Dalam proyek ini, menggunakan beberapa metrik evaluasi yang umum digunakan dalam masalah klasifikasi, yaitu:

- **Akurasi (Accuracy)**: Akurasi mengukur sejauh mana model berhasil mengklasifikasikan data dengan benar, baik kelas positif maupun kelas negatif. Rumusnya adalah:

   ![Akurasi](https://latex.codecogs.com/gif.latex?%5Ctext%7BAkurasi%7D%20%3D%20%5Cfrac%7B%5Ctext%7BJumlah%20prediksi%20benar%7D%7D%7B%5Ctext%7BTotal%20jumlah%20data%7D%7D)

- **Presisi (Precision)**: Presisi mengukur sejauh mana prediksi positif yang dibuat oleh model adalah benar. Presisi memberikan informasi tentang berapa banyak dari kasus yang diprediksi positif yang sebenarnya positif. Rumusnya adalah:

   ![Presisi](https://latex.codecogs.com/gif.latex?%5Ctext%7BPresisi%7D%20%3D%20%5Cfrac%7B%5Ctext%7BJumlah%20True%20Positives%7D%7D%7B%5Ctext%7BJumlah%20True%20Positives%20&plus;%20Jumlah%20False%20Positives%7D%7D)

- **Recall (Sensitivity atau True Positive Rate)**: Recall mengukur sejauh mana model berhasil menemukan semua kasus positif yang sebenarnya. Recall memberikan informasi tentang berapa banyak dari kasus positif yang sebenarnya yang berhasil diidentifikasi oleh model. Rumusnya adalah:

   ![Recall](https://latex.codecogs.com/gif.latex?%5Ctext%7BRecall%7D%20%3D%20%5Cfrac%7B%5Ctext%7BJumlah%20True%20Positives%7D%7D%7B%5Ctext%7BJumlah%20True%20Positives%20&plus;%20Jumlah%20False%20Negatives%7D%7D)

- **F1-Score**: F1-Score adalah pengukuran yang menggabungkan presisi dan recall menjadi satu metrik yang seimbang. F1-Score adalah harmonic mean dari presisi dan recall. Rumusnya adalah:

   ![F1-Score](https://latex.codecogs.com/gif.latex?%5Ctext%7BF1-Score%7D%20%3D%202%20%5Ctimes%20%5Cfrac%7B%5Ctext%7BPresisi%7D%20%5Ctimes%20%5Ctext%7BRecall%7D%7D%7B%5Ctext%7BPresisi%7D%20&plus;%20%5Ctext%7BRecall%7D%7D)

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

