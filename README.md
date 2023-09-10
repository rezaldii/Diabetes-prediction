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
- Diabetes adalah penyakit kronis yang umum yang mempengaruhi jutaan orang di seluruh dunia.
- Diagnosis dan pengobatan dini diabetes sangat penting untuk mencegah komplikasi serius.
- Ada kebutuhan untuk alat yang dapat membantu dokter mendiagnosis diabetes dan memberikan perawatan yang tepat kepada pasien.

### Goals

Berdasarkan Problem Statements, tujuan untuk proyek ini adalah:
- Mengembangkan model pembelajaran mesin yang dapat memprediksi risiko seseorang terkena diabetes berdasarkan data kesehatan mereka.
- Memberikan wawasan tentang faktor-faktor yang mempengaruhi risiko seseorang terkena diabetes.
- Berkontribusi pada pengembangan strategi pencegahan dan pengobatan yang lebih efektif untuk diabetes.

## Data Understanding

Dataset yang digunakan dalam proyek ini adalah Dataset Prediksi Diabetes, yang dapat diunduh dari [Kaggle](https://www.kaggle.com/datasets/iammustafatz/diabetes-prediction-dataset). Dataset ini berisi data kesehatan untuk 100.000 individu dan digunakan untuk memprediksi risiko diabetes.

Variabel dalam Dataset Prediksi Diabetes adalah sebagai berikut:

- **gender**: Jenis kelamin individu. Ini adalah variabel kategorikal dengan tiga nilai unik: Female (Perempuan), Male (Laki-laki), dan Other (Lainnya).
- **age**: Usia individu. Ini adalah variabel numerik dengan nilai mulai dari 0,08 hingga 80 tahun.
- **hypertension**: Menunjukkan apakah individu memiliki hipertensi atau tidak. Ini adalah variabel biner dengan nilai 0 (tidak ada hipertensi) dan 1 (memiliki hipertensi).
- **heart_disease**: Menunjukkan apakah individu memiliki penyakit jantung atau tidak. Ini adalah variabel biner dengan nilai 0 (tidak ada penyakit jantung) dan 1 (memiliki penyakit jantung).
- **smoking_history**: Riwayat merokok individu. Ini adalah variabel kategorikal dengan enam nilai unik: No Info, never (tidak pernah), former (mantan), current (saat ini), not current (tidak saat ini), dan ever (pernah).
- **bmi**: Indeks Massa Tubuh individu. Ini adalah variabel numerik dengan nilai mulai dari 10,01 hingga 95,69.
- **HbA1c_level**: Tingkat HbA1c individu. Ini adalah variabel numerik dengan nilai mulai dari 3,5 hingga 9.
- **blood_glucose_level**: Tingkat glukosa darah individu. Ini adalah variabel numerik dengan nilai mulai dari 80 hingga 300.
- **diabetes**: Menunjukkan apakah individu memiliki diabetes atau tidak. Ini adalah variabel target untuk prediksi, dan merupakan variabel biner dengan nilai 0 (tidak ada diabetes) dan 1 (memiliki diabetes).

Dataset ini tidak mengandung nilai yang hilang dan setiap kolom memiliki tipe data yang sesuai untuk nilainya.

Frekuensi counts untuk variabel kategorikal menunjukkan bahwa ada lebih banyak perempuan daripada laki-laki dalam dataset, dan sebagian besar individu tidak pernah merokok atau tidak memiliki informasi tentang riwayat merokok mereka.

## Data Preparation
Pada tahap persiapan data, beberapa teknik pemrosesan data telah diterapkan untuk mempersiapkan dataset sebelum digunakan untuk melatih model prediksi diabetes. Teknik-teknik tersebut dijelaskan berikut ini dalam urutan yang dilakukan:

1. **Standardisasi Data Numerik** 
-  Memilih fitur-fitur numerik yang perlu distandarisasi, yaitu 'age', 'bmi', 'HbA1c_level', dan 'blood_glucose_level'.
- Menginisialisasi objek Standard Scaler untuk standarisasi.
- Melakukan standarisasi pada fitur-fitur tersebut menggunakan Standard Scaler.

2. **One-Hot Encoding untuk Variabel Kategorikal**
- Melakukan one-hot encoding pada kolom "gender" dan "smoking_history" untuk mengubahnya menjadi format yang dapat dipahami oleh model.
- One-hot encoding digunakan dengan pengaturan drop_first=True untuk menghindari multicollinearity.

3. **Seleksi Fitur Berdasarkan Korelasi**
- Menghitung korelasi antara setiap fitur dalam dataset yang telah dienkripsi dengan target "diabetes".
- Menentukan ambang batas korelasi yang relevan (dalam contoh ini, 0.1).
- Memilih fitur-fitur yang memiliki korelasi relevan dengan "diabetes" berdasarkan ambang batas tersebut.

4. **Pembagian Data Menjadi Set Pelatihan dan Set Tes**
- Memisahkan fitur-fitur yang relevan dan target "diabetes" dari dataset yang telah dienkripsi.
- Menggunakan train_test_split dari scikit-learn untuk membagi data menjadi set pelatihan (80% dari data) dan set tes (20% dari data).

## Modeling

Pada tahapan ini, digunakan tiga jenis model machine learning untuk memprediksi kasus diabetes, yaitu Regresi Logistik, Pohon Keputusan, dan Random Forest. Berikut adalah tahapan-tahapan dan parameter-parameter yang digunakan dalam proses pemodelan:

### 1. Regresi Logistik

**Tahapan:**

- Inisialisasi model Regresi Logistik
- Melatih model pada set pelatihan
- Memprediksi kelas target pada set tes
- Menghitung akurasi model
- Menampilkan laporan klasifikasi
- Menghitung dan menampilkan matriks konfusi

**Parameter:**

Model Regresi Logistik adalah model yang sederhana dan tidak memiliki banyak hyperparameter yang perlu disetel secara khusus. Pada contoh di atas, digunakan `random_state` yang disetel ke 42 untuk menjaga konsistensi hasil.

### 2. Pohon Keputusan

**Tahapan:**

- Inisialisasi model Pohon Keputusan
- Penyetelan hyperparameter dengan menggunakan Grid Search
- Memprediksi kelas target pada set tes
- Menghitung akurasi model Pohon Keputusan setelah penyetelan
- Menampilkan laporan klasifikasi setelah penyetelan
- Menghitung dan menampilkan matriks konfusi setelah penyetelan

**Parameter:**

Penyetelan hyperparameter pada model Pohon Keputusan menggunakan Grid Search dengan parameter-parameter berikut:
- `max_depth`: Kedalaman maksimum dari pohon keputusan.
- `min_samples_split`: Jumlah minimum sampel yang dibutuhkan untuk membagi simpul.
- `min_samples_leaf`: Jumlah minimum sampel yang dibutuhkan pada simpul daun.
- `criterion`: Kriteria pemilihan fitur terbaik, yang dapat berupa 'gini' atau 'entropy'.

### 3. Random Forest

**Tahapan:**

- Inisialisasi model Random Forest
- Penyetelan hyperparameter dengan menggunakan Grid Search
- Memprediksi kelas target pada set tes
- Menghitung akurasi model Random Forest yang ditingkatkan
- Menampilkan laporan klasifikasi
- Menghitung dan menampilkan matriks konfusi

**Parameter:**

Penyetelan hyperparameter pada model Random Forest menggunakan Grid Search dengan parameter-parameter berikut:
- `n_estimators`: Jumlah pohon dalam ensemble Random Forest.
- `max_depth`: Kedalaman maksimum dari setiap pohon dalam ensemble.
- `min_samples_split`: Jumlah minimum sampel yang dibutuhkan untuk membagi simpul dalam setiap pohon.
- `min_samples_leaf`: Jumlah minimum sampel yang dibutuhkan pada simpul daun dalam setiap pohon.

Pada akhirnya, parameter terbaik yang ditemukan untuk model Random Forest adalah:
- `n_estimators`: 100
- `max_depth`: 10
- `min_samples_split`: 2
- `min_samples_leaf`: 1

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