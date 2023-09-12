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

# Data Understanding

Dalam proyek ini, data yang digunakan adalah "Diabetes Prediction Dataset." Dapat mengunduh dataset ini dari Kaggle melalui tautan berikut: [Diabetes Prediction Dataset](https://www.kaggle.com/datasets/iammustafatz/diabetes-prediction-dataset).

- Dataset memiliki format CSV (Comma-Seperated Values).
- Dataset memiliki 100,000 baris (rows) dan 9 kolom (columns).
- Dataset memiliki 2 kolom bertipe object, 3 kolom bertipe float64 dan 4 kolom bertipe int64.
- Tidak ada missing value dalam dataset.

### Variabel-variabel pada Diabetes Prediction Dataset adalah sebagai berikut:

1. **gender**: Variabel ini menyimpan informasi tentang jenis kelamin pasien (e.g., Female, Male, Other).

2. **age**: Variabel ini adalah usia pasien dalam tahun.

3. **hypertension**: Variabel ini menunjukkan apakah pasien menderita hipertensi (0 untuk Tidak, 1 untuk Ya).

4. **heart_disease**: Variabel ini menunjukkan apakah pasien memiliki penyakit jantung (0 untuk Tidak, 1 untuk Ya).

5. **smoking_history**: Variabel ini berisi riwayat merokok pasien (e.g., never, former, current, not current, ever).

6. **bmi**: Variabel ini adalah indeks massa tubuh (BMI) pasien.

7. **HbA1c_level**: Variabel ini merupakan tingkat HbA1c dalam darah pasien.

8. **blood_glucose_level**: Variabel ini adalah tingkat glukosa darah pasien.

9. **diabetes**: Variabel ini adalah target yang akan diprediksi (0 untuk Tidak memiliki diabetes, 1 untuk Memiliki diabetes).

### Exploratory Data Analysis (EDA)

1. **Data Visualization (Visualisasi Data):**
   - Kode pertama menampilkan grafik batang untuk variabel jenis kelamin (gender).
   - Kode kedua menampilkan grafik batang untuk variabel riwayat merokok (smoking_history).
   - Kode ketiga menampilkan histogram untuk variabel usia (age).
   - Kode keempat menampilkan histogram untuk variabel indeks massa tubuh (bmi).
   - Kode kelima menampilkan histogram untuk variabel tingkat glukosa darah (blood_glucose_level).
   - Kode keenam, ketujuh, dan kedelapan menampilkan boxplot untuk variabel usia (age), indeks massa tubuh (bmi), dan tingkat glukosa darah (blood_glucose_level).
   - Kode kesembilan menampilkan scatterplot untuk memvisualisasikan hubungan antara usia (age) dan indeks massa tubuh (bmi).

   Output: Grafik-grafik dan plot data yang digunakan untuk memvisualisasikan distribusi dan hubungan antara variabel dalam dataset.

2. **Pengujian Hipotesis Statistik:**
   - Kode berikutnya adalah contoh pengujian hipotesis statistik. Dilakukan dua jenis pengujian:
     - Pertama, menggunakan uji t (t-test) untuk membandingkan rata-rata BMI antara pasien diabetes dan non-diabetes.
     - Kedua, menggunakan uji ANOVA untuk membandingkan rata-rata BMI antara kelompok berbeda berdasarkan riwayat merokok.

   Output: Hasil statistik seperti nilai t-statistic, p-value, dan kesimpulan berdasarkan alpha level (0.05) untuk setiap pengujian.

3. **Analisis Tabel Kontingensi:**
   - Dibuat tabel kontingensi untuk menganalisis hubungan antara jenis kelamin (gender) dan diabetes.
   - Selanjutnya, digunakan uji Chi-square untuk menguji apakah ada hubungan yang signifikan antara jenis kelamin dan diabetes.

   Output: Tabel kontingensi, nilai Chi-square, nilai p, derajat kebebasan, dan tabel frekuensi harapan.

4. **Korelasi dan Scatterplot:**
   - Diukur korelasi antara usia (age) dan indeks massa tubuh (bmi) menggunakan metode Pearson.
   - Dalam bentuk scatterplot, memvisualisasikan hubungan tersebut.

   Output: Nilai korelasi (positif lemah) dan scatterplot antara usia dan BMI.

5. **Deteksi Anomali (Outlier Detection):**
   - Dilakukan deteksi anomali pada beberapa variabel numerik (age, bmi, HbA1c level, blood glucose level) menggunakan metode IQR (Interquartile Range).
   - Juga dilakukan deteksi anomali dengan menggunakan metode Isolation Forest pada dua fitur (age dan bmi).

   Output: Data yang dianggap sebagai anomali berdasarkan batasan yang telah ditentukan.

### Verifikasi Kualitas Data

1. **Menghitung Jumlah Data Duplikat**:
   - Kode pertama menghitung jumlah data yang duplikat dalam dataset dengan menggunakan `.duplicated().sum()`. Hasilnya adalah 3,854 data duplikat.

2. **Menghapus Data Duplikat**:
   - Selanjutnya, kode menghapus data yang duplikat menggunakan `.drop_duplicates()`, sehingga dataset menjadi lebih bersih. Setelah penghapusan, ukuran dataset menjadi (96,146 baris, 10 kolom).

3. **Penanganan Outlier**:
   - Kode kemudian melakukan penanganan outlier untuk tiga variabel numerik: 'age', 'bmi', dan 'HbA1c_level'. Proses ini dilakukan dengan menghitung kuartil pertama (Q1) dan kuartil ketiga (Q3) untuk setiap variabel, menghitung IQR (Interquartile Range), dan menentukan batas bawah dan batas atas untuk mendeteksi outlier. Outlier diidentifikasi dan digantikan dengan nilai batas atas atau batas bawah.

4. **Pemeriksaan Ketidaksesuaian Data**:
   - Setelah penanganan outlier, dilakukan pemeriksaan data yang mungkin tidak sesuai. 
     - Pertama, kode memeriksa apakah ada nilai usia (age) yang kurang dari 0, tetapi tidak menemukan ketidaksesuaian tersebut.
     - Kemudian, kode memeriksa kolom 'gender' untuk memeriksa apakah ada nilai yang tidak sesuai. Terdapat beberapa entri dengan nilai "Other" yang dianggap tidak sesuai dengan pilihan jenis kelamin yang seharusnya hanya "Male" atau "Female". Kode mencetak data yang tidak sesuai ini.

5. **Penggantian Nilai "Other" dengan NaN**:
   - Kode mengganti nilai "Other" dalam kolom 'gender' dengan nilai NaN untuk mengatasi ketidaksesuaian ini.

6. **Menyimpan Dataset yang Diperbarui**:
   - Terakhir, dataset yang telah diperbarui disimpan dalam file CSV dengan nama "diabetes_prediction_dataset_updated.csv" menggunakan perintah `.to_csv()`.

**Output**:
- Output kode mencakup informasi tentang jumlah data duplikat sebelum penghapusan dan ukuran dataset setelah penghapusan. Selanjutnya, output mencetak data yang tidak sesuai dalam kolom 'gender', yang kemudian diperbaiki dengan mengganti nilai "Other" menjadi NaN.

## Data Preparation

1. **Standarisasi Fitur Numerik**:
   - Memilih fitur-fitur numerik yang akan distandarisasi, yaitu 'age', 'bmi', 'HbA1c_level', dan 'blood_glucose_level'.
   - Menggunakan StandardScaler dari scikit-learn untuk melakukan standarisasi pada fitur-fitur tersebut. Standarisasi mengubah distribusi data sehingga memiliki rerata (mean) sekitar 0 dan deviasi standar (standard deviation) sekitar 1.
   - Alasan: Standarisasi diperlukan agar berbagai fitur numerik memiliki skala yang serupa, sehingga algoritma machine learning yang sensitif terhadap skala, dapat bekerja dengan baik.

2. **One-Hot Encoding**:
   - Melakukan one-hot encoding pada kolom 'gender' dan 'smoking_history'.
   - Menggunakan pd.get_dummies() untuk mengganti kolom kategorikal ini menjadi representasi biner, di mana setiap kategori diubah menjadi kolom baru dengan nilai biner (0 atau 1).
   - Alasan: Algoritma machine learning umumnya memerlukan input dalam bentuk numerik, sehingga kolom kategorikal perlu diubah menjadi bentuk yang dapat digunakan oleh model. One-hot encoding memungkinkan pemasukkan informasi kategori ke dalam model tanpa menimbulkan ambiguitas atau urutan.

3. **Korelasi Fitur dengan Target**:
   - Menghitung korelasi antara fitur-fitur dengan target (diabetes) menggunakan metode .corr(). Mengurutkan korelasi ini dalam urutan menurun.
   - Menentukan ambang batas korelasi yang relevan (0.1) untuk mengekstrak fitur-fitur yang memiliki korelasi signifikan dengan target.
   - Alasan: Ini membantu identifikasi fitur-fitur yang paling berpotensi berpengaruh pada prediksi diabetes. Fitur-fitur dengan korelasi yang kuat terhadap target adalah kandidat yang baik untuk dimasukkan dalam model.

4. **Visualisasi Matriks Korelasi**:
   - Memvisualisasikan matriks korelasi dari fitur-fitur yang relevan dengan diabetes menggunakan heatmap.
   - Alasan: Visualisasi ini membantu memahami hubungan antara fitur-fitur yang relevan dan dapat membantu mengidentifikasi pola korelasi yang mungkin tidak terlihat dalam angka.

5. **Pemisahan Data**:
   - Memisahkan data menjadi set pelatihan (80%) dan set tes (20%) menggunakan train_test_split dari scikit-learn.
   - Juga mencetak jumlah sampel dalam set pelatihan dan set tes.
   - Alasan: Pemisahan data menjadi set pelatihan dan set tes penting untuk menguji kinerja model. Dengan memiliki set tes yang independen, dapat mengukur sejauh mana model yang telah dilatih di atas data pelatihan akan berkinerja pada data yang belum pernah dilihat sebelumnya.

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

