# Laporan Proyek Machine Learning - Rizki Abd

# Domain Proyek

Sensor kapasitif banyak digunakan dalam dunia industri untuk mendeteksi jenis cairan secara otomatis. Deteksi yang akurat dan real-time terhadap cairan seperti air dan minyak sangat penting dalam otomasi industri, sistem kendali kualitas, dan monitoring lingkungan. Machine learning menjadi pendekatan yang efektif dalam membangun sistem klasifikasi berbasis data sinyal sensor ini. Dataset yang digunakan berupa 10 intensitas sinyal berturut-turut dari sensor kapasitif untuk membedakan cairan.

## Business Understanding

### Problem Statements

1. **Bagaimana membedakan jenis cairan berdasarkan sinyal digital dari sensor kapasitif?**
2. **Model machine learning apa yang paling efektif untuk klasifikasi cairan berbasis sinyal sensor?**
3. **Bagaimana mengevaluasi akurasi model dan meningkatkan performa klasifikasi?**

### Goals

1. Membangun model klasifikasi media cairan (air vs minyak) menggunakan data sinyal sensor kapasitif.
2. Mengevaluasi kinerja model Random Forest melalui metrik akurasi, precision, recall, dan F1-score.
3. Menyediakan visualisasi komprehensif untuk mendukung analisis performa model.

### Solution Statement

* Lakukan parsing dan pembersihan data dari satu kolom menjadi bentuk tabel numerik.
* Lakukan eksplorasi data dan preprocessing.
* Implementasikan Random Forest Classifier.
* Lakukan evaluasi dengan metrik dan visualisasi komprehensif seperti ROC curve, precision-recall curve, dan learning curve.

## Data Understanding

### Sumber Dataset

Dataset digunakan dari Kaggle berjudul *Binary Classification for Sensor Signals* oleh Mexwell. Setiap baris data berisi 10 nilai intensitas sinyal dan label akhir (1 untuk air, 0 untuk minyak).

### Struktur Dataset

* **Jumlah sampel**: 2.569 baris
* **Fitur**: 10 kolom numerik (col1–col10)
* **Label target**: 1 = air, 0 = minyak
* **Format**: CSV

### Deskripsi Kolom

| Kolom      | Tipe Data | Deskripsi                                |
| ---------- | --------- | ---------------------------------------- |
| col1–col10 | float64   | Nilai intensitas sinyal sensor kapasitif |
| target     | int       | Label biner: 1 (air), 0 (minyak)         |

## Exploratory Data Analysis (EDA)

EDA dilakukan untuk memahami karakteristik awal dataset sebelum proses modeling dilakukan. Tahap ini penting untuk mendeteksi ketidakseimbangan data, korelasi antar fitur, serta pola distribusi nilai-nilai input.

### 1. Distribusi Label

Visualisasi menggunakan countplot menunjukkan bahwa data relatif seimbang antara dua kelas target, yaitu air (1) dan minyak (0). Keseimbangan label ini penting karena membantu model tidak bias terhadap salah satu kelas. Jika jumlah sampel pada salah satu kelas jauh lebih sedikit, model berisiko melakukan prediksi yang tidak proporsional.

### 2. Korelasi Antar Fitur

Heatmap menunjukkan adanya korelasi lemah hingga sedang antara fitur-fitur tertentu, yang mengindikasikan bahwa tidak ada fitur yang terlalu redundan. Hal ini bermanfaat dalam pemodelan karena memberi sinyal bahwa setiap fitur dapat membawa informasi yang unik ke dalam proses klasifikasi. Korelasi rendah juga mengurangi risiko multikolinearitas.

### 3. Statistik Deskriptif

Tabel berikut memperlihatkan ringkasan statistik umum dari fitur. Nilai mean berada di kisaran \~5, dengan standar deviasi sekitar 2, yang berarti distribusi data tidak terlalu tersebar. Rentang nilai dari \~0.2 hingga \~10 menunjukkan bahwa skala antar fitur cukup bervariasi, sehingga normalisasi menjadi langkah penting sebelum pemodelan dilakukan.

| Fitur                  | Mean  | Std Dev | Min   | Max    |
| ---------------------- | ----- | ------- | ----- | ------ |
| col1–col10 (rata-rata) | \~5.0 | \~2.0   | \~0.2 | \~10.0 |

Tidak ditemukan missing values dalam dataset.

## Data Preparation

Sebelum membangun model klasifikasi, data perlu dibersihkan dan diproses agar dapat digunakan oleh algoritma pembelajaran mesin. Data preparation mencakup parsing, konversi tipe data, normalisasi, dan pembagian data.

1. Parsing file CSV yang awalnya hanya memiliki 1 kolom menjadi 11 kolom.
2. Konversi data string ke float.
3. Label `+1` dimapping ke `1` (air) dan `-1` ke `0` (minyak).
4. Normalisasi fitur menggunakan `StandardScaler`.
5. Split data 80% training dan 20% testing dengan `train_test_split()` dan `stratify`.

## Modeling

Setelah data dipersiapkan, langkah selanjutnya adalah memilih dan melatih model klasifikasi. Model yang dipilih harus sesuai dengan karakteristik data, mampu menangani fitur numerik, serta bekerja baik pada jumlah data yang tidak terlalu besar.
Model yang digunakan adalah **Random Forest Classifier** karena memiliki performa yang baik dalam data tabular dan tidak memerlukan banyak tuning parameter.

### Parameter Utama

* `n_estimators = 100`
* `random_state = 42`

### Alasan Pemilihan

Random Forest lebih tahan terhadap overfitting dan mendukung interpretasi fitur melalui feature importance. Algoritma ini lebih unggul dibanding KNN atau SVM dalam stabilitas dan efisiensi untuk dataset berukuran menengah.

## Evaluation

Evaluasi dilakukan untuk mengukur performa model dalam memprediksi jenis cairan. Evaluasi dilakukan dengan metrik kuantitatif serta visualisasi untuk memahami perilaku model terhadap data testing.

### Metrik Evaluasi

Model dievaluasi menggunakan:

* Confusion Matrix
* Accuracy
* Precision
* Recall
* F1-Score

### Visualisasi

1. **Feature Importance**: Visualisasi ini menggambarkan kontribusi masing-masing fitur terhadap proses pengambilan keputusan model. Fitur dengan skor penting tinggi menunjukkan bahwa perubahan nilainya sangat memengaruhi hasil klasifikasi. Ini membantu dalam interpretasi model dan identifikasi fitur yang paling relevan terhadap jenis cairan.

2. **Confusion Matrix**: Matriks ini menunjukkan jumlah prediksi benar dan salah untuk masing-masing kelas. Nilai diagonal menunjukkan prediksi yang benar, sementara nilai non-diagonal menunjukkan kesalahan klasifikasi. Confusion matrix sangat membantu untuk memahami distribusi kesalahan dan bias model terhadap satu kelas tertentu.

3. **ROC Curve dan AUC Score**: ROC curve memvisualisasikan trade-off antara true positive rate (sensitivity) dan false positive rate pada berbagai threshold. Semakin mendekati sudut kiri atas, semakin baik modelnya. AUC (Area Under the Curve) yang mendekati 1 menandakan performa klasifikasi yang sangat baik.

4. **Precision-Recall Curve**: Digunakan untuk mengevaluasi model pada data yang seimbang maupun tidak seimbang. Precision menunjukkan seberapa banyak prediksi positif yang benar, sementara recall menunjukkan seberapa banyak kasus positif yang berhasil dikenali. Kurva ini membantu memilih threshold yang optimal.

5. **Learning Curve**: Visualisasi ini menunjukkan perubahan performa model terhadap peningkatan ukuran data training. Jika kurva training dan testing bertemu pada nilai yang tinggi, ini menandakan bahwa model tidak mengalami overfitting dan memiliki generalisasi yang baik.

6. **Distribusi Probabilitas Prediksi**: Diagram ini menunjukkan seberapa yakin model terhadap setiap prediksi yang dibuat. Probabilitas yang terdistribusi jelas terhadap dua kutub kelas menandakan bahwa model memiliki kepercayaan tinggi dan prediksi yang konsisten.

7. **Confusion Matrix**: Menunjukkan distribusi prediksi benar dan salah.

8. **ROC Curve** dan **AUC Score**: Mengukur performa binary classifier.

9. **Precision-Recall Curve**: Menunjukkan trade-off antara precision dan recall.

10. **Learning Curve**: Menunjukkan dinamika performa training vs test saat jumlah data bertambah.

11. **Distribusi Probabilitas Prediksi**: Memperlihatkan kepercayaan model terhadap kelas.

Model mencapai akurasi >95%, yang menunjukkan performa prediktif yang sangat tinggi. F1-score yang seimbang antara precision dan recall mengindikasikan bahwa model tidak hanya akurat tetapi juga mampu menangani kedua jenis kelas dengan proporsional. Visualisasi seperti ROC curve menunjukkan area under the curve (AUC) mendekati 1, yang menegaskan bahwa model memiliki kemampuan klasifikasi yang sangat baik. Selain itu, distribusi probabilitas prediksi menunjukkan bahwa model memiliki keyakinan tinggi pada prediksi yang dibuat, memperkuat keandalan output-nya.

## Kesimpulan

Hasil evaluasi dan visualisasi menunjukkan bahwa model bekerja dengan sangat baik. Bagian ini merangkum performa akhir serta memberi rekomendasi untuk pengembangan lanjutan.
Model Random Forest berhasil digunakan untuk klasifikasi jenis cairan dengan sinyal kapasitif, memberikan akurasi tinggi dan interpretasi visual yang baik. Tujuan proyek tercapai. Untuk pengembangan selanjutnya, bisa diuji model ensemble lain seperti XGBoost dan penambahan jumlah data melalui akuisisi lanjutan.

## Referensi

* Mexwell. (2023). *Binary Classification for Sensor Signals*. Kaggle. [https://www.kaggle.com/datasets/mexwell/binary-classification-for-sensor-signals](https://www.kaggle.com/datasets/mexwell/binary-classification-for-sensor-signals)
* Ding, Y., et al. (2020). *Using Machine Learning for Material Detection with Capacitive Proximity Sensors*. [https://www.researchgate.net/publication/343335941](https://www.researchgate.net/publication/343335941)
* Ahmad, S., et al. (2022). *Wireless Capacitive Liquid-Level Detection Sensor Based on Zero‑Power RFID Sensing Architecture*. [https://www.researchgate.net/publication/366606414](https://www.researchgate.net/publication/366606414)
* Rana, N., et al. (2025). *Flow Pattern Classification Using AI and Capacitance Sensors*. [https://arxiv.org/abs/2502.16432](https://arxiv.org/abs/2502.16432)
* Alvenrigh, A., & Supriyanto, E. (2023). *Klasifikasi Jenis Cairan Berdasarkan Sensor Kapasitif*. [https://ejournal.stekom.ac.id/index.php/jteks/article/view/205](https://ejournal.stekom.ac.id/index.php/jteks/article/view/205)
* Mansouri, M., et al. (2023). *Binary classification of sensor signals using capacitive sensors*. [https://doi.org/10.1186/s40537-023-00766-5](https://doi.org/10.1186/s40537-023-00766-5)
* Ren, Y., et al. (2024). *Capacitive and Non‑Contact Liquid Level Detection Sensor*. [https://doi.org/10.3390/electronics13112228](https://doi.org/10.3390/electronics13112228)
