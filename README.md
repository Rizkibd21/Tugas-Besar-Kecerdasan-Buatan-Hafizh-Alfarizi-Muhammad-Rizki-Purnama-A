# Referensi Struktur Laporan Yang Dipilih Adalah Dari Lembar Jawaban Soal UAS (pdf), Tidak Menggunakan Struktur .md
## README - UAS Kecerdasan Buatan

## Judul Proyek

**Klasifikasi Media Cairan Menggunakan Algoritma Random Forest**

## 👥 Anggota Kelompok

* Hafizh Alfarizi (2306049)
* Muhamamd Rizki Purnama Abdullah (2306053)

## Langkah-Langkah Pengerjaan

### 1. Menentukan Topik dan Dataset

Topik proyek yang diambil adalah klasifikasi jenis cairan (air dan minyak) berdasarkan sinyal digital dari sensor kapasitif. Dataset diambil dari Kaggle dengan nama "Binary Classification for Sensor Signals" oleh Mexwell. Dataset terdiri dari 10 kolom nilai intensitas sinyal dan 1 kolom label target.

### 2. Memahami Struktur dan Isi Dataset

Dataset awal hanya memiliki satu kolom berisi string terpisah dengan delimiter `;`. Total data sebanyak 2.569 baris. Fitur terdiri dari 10 kolom numerik (col1–col10), dan label target berupa 1 (air) dan 0 (minyak).

### 3. Pembersihan dan Persiapan Data

* Dataset dipisahkan menjadi 11 kolom.
* Nilai diubah menjadi tipe data float.
* Label `+1` dan `-1` dikonversi menjadi 1 dan 0.
* Dilakukan normalisasi data menggunakan StandardScaler.
* Data dibagi menjadi 80% untuk training dan 20% untuk testing menggunakan `train_test_split` dengan `stratify`.

### 4. Exploratory Data Analysis (EDA)

* Visualisasi distribusi kelas menggunakan countplot.
* Korelasi antar fitur ditampilkan dalam heatmap.
* Statistik deskriptif untuk setiap fitur ditampilkan.
* Tidak ditemukan missing values atau outlier ekstrim.

### 5. Pemilihan dan Implementasi Model

* Model yang digunakan: Random Forest Classifier.
* Parameter utama: `n_estimators=100`, `random_state=42`.
* Alasan pemilihan: Random Forest tahan terhadap overfitting, cocok untuk data tabular, dan memberikan interpretasi pentingnya fitur.

### 6. Evaluasi Model

Evaluasi dilakukan menggunakan:

* Confusion Matrix
* Accuracy, Precision, Recall, F1-Score
* ROC Curve dan AUC
* Precision-Recall Curve
* Learning Curve
* Distribusi probabilitas prediksi

### 7. Visualisasi dan Interpretasi

* Feature Importance: menunjukkan fitur yang paling berkontribusi.
* Confusion Matrix: menunjukkan proporsi prediksi benar/salah.
* ROC Curve: area AUC mendekati 1 menandakan performa sangat baik.
* Precision-Recall Curve: membantu menentukan trade-off optimal.
* Learning Curve: menunjukkan tidak terjadi overfitting.
* Probabilitas prediksi: menunjukkan keyakinan model terhadap prediksi.

### 8. Penyusunan Laporan

Seluruh proses dokumentasi ditulis dalam file `notebook_model.ipynb` dan laporan akhir disusun dalam file `uas_ai.pdf`. Referensi ilmiah minimal 5 jurnal ditambahkan dalam laporan sesuai gaya APA.

Beberapa isi yang disampaikan dalam laporan antara lain:

* Penjelasan domain dan kasus bisnis industri berbasis sensor cairan
* Deskripsi dan interpretasi hasil EDA yang menunjukkan distribusi kelas seimbang dan korelasi lemah antar fitur
* Justifikasi pemilihan algoritma Random Forest dibanding KNN/SVM
* Hasil evaluasi lengkap disertai grafik dan interpretasi performa model berdasarkan AUC, F1-score, dan learning curve
* Rekomendasi pengembangan model untuk penggunaan lebih lanjut

Laporan ini berfungsi sebagai dokumen utama untuk menjelaskan keseluruhan proyek dari tahap business understanding hingga kesimpulan dan referensi ilmiah.
Seluruh proses dokumentasi ditulis dalam file `notebook_model.ipynb` dan laporan akhir disusun dalam file `uas_ai.pdf`. Referensi ilmiah minimal 5 jurnal ditambahkan dalam laporan sesuai gaya APA.

## Struktur Folder Repository

```
data/
├── README.md                                                           # Ringkasan langkah pengerjaan
├── Laporan Tugas Besar KEcerdasan Buatan (Hafizh & Rizki.P).pdf        # Laporan akhir
├── Tugas_Besar_Kecerdasan_Buatan.ipynb                                 # Notebook pemrosesan dan modeling
└── data/
    ├── dataset_cleaned.csv           # Dataset dari Kaggle
    ├── sumber 1                      # PDF jurnal ilmiah
    ├── sumber 2           
    ├── sumber 3            
    ├── sumber 4                      
    ├── sumber 5           
    └── sumber 6            
```
📎 README ini disusun untuk memenuhi instruksi tugas UAS Kecerdasan Buatan agar menjelaskan langkah-langkah pengerjaan secara ringkas dan sistematis.

## 📊 Metrik Evaluasi

* Accuracy
* Precision
* Recall
* F1-Score

## 🔧 Tools & Library

* Python 3.11+
* Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn
* Google Colab

## 📚 Referensi Ilmiah

* Kaggle Dataset oleh Mexwell (2023)
* Ding et al. (2020) – ML for Material Detection with Capacitive Sensors
* Ahmad et al. (2022) – Wireless RFID Liquid-Level Detection Sensor
* Rana et al. (2025) – Capacitance Flow Pattern Classification
* Alvenrigh & Supriyanto (2023) – Sensor Kapasitif & Pembelajaran Mesin
* Ren et al. (2024) – Non-Contact Capacitive Liquid Level Detection


## 📤 Cara Menjalankan

1. Buka Google Colab
2. Upload file `dataset_cleaned.csv` secara manual
3. Jalankan `Tugas Besar Kecerdasan Buatan.ipynb`
4. Ikuti proses: EDA → Preprocessing → Training → Evaluation → Visualisasi

---
## Catatan Tambahan

* Semua kode dijalankan dan diuji di Google Colab.
* File dataset diunggah secara manual.
* Laporan dan notebook siap diunggah ke GitHub.


📎 **Catatan**: Laporan ini disusun dalam rangka memenuhi tugas UAS mata kuliah *Kecerdasan Buatan*, dengan fokus pada penerapan klasifikasi biner berbasis data sinyal sensor industri.
