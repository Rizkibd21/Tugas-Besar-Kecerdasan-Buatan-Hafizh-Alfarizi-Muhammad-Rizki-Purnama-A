# UAS Kecerdasan Buatan – Klasifikasi Media Cairan

## 📌 Deskripsi Proyek

Proyek ini bertujuan membangun sistem klasifikasi berbasis machine learning untuk membedakan dua jenis cairan (air dan minyak)
berdasarkan sinyal digital dari sensor kapasitif. Dataset yang digunakan diambil dari Kaggle dan memuat 10 nilai intensitas sinyal
secara berurutan sebagai fitur input serta satu label target. Model utama yang digunakan adalah **Random Forest Classifier**, yang
menunjukkan performa akurasi tinggi (>95%) serta memiliki visualisasi evaluasi yang lengkap seperti confusion matrix, ROC curve, dan precision-recall curve.

## 🧠 Tujuan Proyek

* Membangun sistem klasifikasi cairan berbasis AI
* Memprediksi jenis cairan berdasarkan pola sinyal digital dari sensor
* Menganalisis performa model menggunakan metrik evaluasi lengkap
* Memberikan solusi praktis untuk industri berbasis sensor cairan

## 💡 Business Case

Penggunaan AI dalam deteksi jenis cairan sangat bermanfaat pada berbagai industri seperti monitoring sistem pendingin,
deteksi kebocoran pipa, dan otomatisasi proses produksi. Dengan menggunakan sinyal dari sensor kapasitif, sistem dapat
secara otomatis menentukan jenis cairan tanpa perlu intervensi manual atau metode kimia.

## 📂 Struktur Repository

```
UAS-KecerdasanBuatan/
├── README.md                                                                   # Penjelasan umum proyek dan struktur
├── Laporan Tugas Besar KEcerdasan Buatan (Hafizh & Rizki.P).pdf                # Laporan lengkap UAS
├── Tugas Besar Kecerdasan Buatan.ipynb                                         # Notebook Jupyter dengan seluruh pipeline
└── data/
    ├── dataset_cleaned.csv                                                     # Dataset asli dari Kaggle
    └── sumber1 - sumber 6                                                      # Folder berisi PDF jurnal ilmiah pendukung
```

## 🧪 Model Machine Learning

* Algoritma: **Random Forest Classifier**
* Parameter utama: `n_estimators=100`, `random_state=42`
* Teknik validasi: Split 80:20 (train-test split dengan stratifikasi)
* Fitur: col1 – col10 (nilai intensitas sinyal digital sensor kapasitif)
* Target: `1` = air, `0` = minyak

## 🧹 Data Preparation

* Pembersihan delimiter dari satu kolom menjadi banyak kolom numerik
* Konversi nilai menjadi float
* Normalisasi menggunakan `StandardScaler`
* Mapping label dan split data

## 📈 Visualisasi Modeling & Evaluasi

* **Feature Importance**: Menunjukkan fitur mana yang paling berkontribusi
* **Confusion Matrix**: Menampilkan akurasi klasifikasi
* **ROC Curve**: Menunjukkan performa deteksi positif-negatif
* **Precision-Recall Curve**: Memvalidasi performa untuk dataset biner
* **Learning Curve**: Menilai overfitting dan stabilitas model
* **Distribusi Probabilitas**: Visualisasi keyakinan prediksi

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

## 👥 Anggota Kelompok

* Hafizh Alfarizi (2306049)
* Muhamamd Rizki Purnama Abdullah (2306053)

## 📤 Cara Menjalankan

1. Buka Google Colab
2. Upload file `dataset_cleaned.csv` secara manual
3. Jalankan `Tugas Besar Kecerdasan Buatan.ipynb`
4. Ikuti proses: EDA → Preprocessing → Training → Evaluation → Visualisasi

---

📎 **Catatan**: Laporan ini disusun dalam rangka memenuhi tugas UAS mata kuliah *Kecerdasan Buatan*, dengan fokus pada penerapan klasifikasi biner berbasis data sinyal sensor industri.
